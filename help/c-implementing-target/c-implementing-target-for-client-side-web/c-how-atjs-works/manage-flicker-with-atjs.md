---
description: Target at.js JavaScript ライブラリでページやアプリの読み込み中にちらつきを回避する方法について説明します。
keywords: ちらつき;Target Standard;at.js;実装
seo-description: Adobe Target の at.js JavaScript ライブラリで、ページやアプリの読み込み中にちらつきを回避する方法について説明します。
seo-title: Adobe Target の at.js によるちらつきの制御方法
solution: 'Target '
title: at.js によるちらつきの制御方法
topic: Standard
uuid: 65f67c4a-a931-4e0d-80d9-29ab67b62573
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# at.js によるちらつきの制御方法{#how-at-js-manages-flicker}

Target at.js JavaScript ライブラリでページやアプリの読み込み中にちらつきを回避する方法について説明します。

ちらつきは、デフォルトコンテンツがアクティビティコンテンツに置き換わる前に訪問者に一時的に表示される際に発生します。ちらつきは、訪問者を混乱させる可能性があるので、望ましくありません。

## 自動作成されたグローバル mbox の使用 {#section_C502170D551C4F52AAFD8E82C41BB63A}

「[グローバル mbox を自動作成](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/understanding-global-mbox.md#concept_76AC0EC995A048238F3220F53773DB13)」設定を at.js 設定時に有効にすると、at.js はページの読み込み時に不透明度の設定を変更し、ちらつきを制御します。at.js が読み込まれると、その要素の不透明度の設定が <body> 「0」に変更され、そのページが最初は訪問者に対して表示されなくなります。Target からの応答を受信した、または Target のリクエストにエラーが検出された場合、at.js は不透明度を「1」にリセットします。これにより、訪問者は、アクティビティのコンテンツが適用された後にのみページを表示できます。

グローバル mbox を自動作成設定を at.js の設定時に有効にすると、at.js は HTML BODY スタイルの不透明度を 0 に設定します。Target からの応答を受け取ったら、at.js は HTML BODY の不透明度を 1 にリセットします。

不透明度を 0 に設定すると、ちらつきを回避するためにページコンテンツは非表示になりますが、ブラウザーは引き続きページをレンダリングし、CSS、画像などの必要なアセットをすべて読み込みます。

不透明度 0 が実装で機能しない場合は、`bodyHiddenStyle` をカスタマイズし、`body {visibility:hidden !important}` に設定することで、ちらつきを制御することもできます。値として body `{opacity:0 !important`} または `body {visibility:hidden !important}` のどちらでも、特定の環境に適したものを使用できます。

次の図は、本文非表示と本文表示の呼び出しを at.js 1.*x* およびat. js2. x.

**at. js2. x**

![Target フロー： at.js ページ読み込みリクエスト](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-flow-page-load-request.png)

**at.js 1.*x***

![](assets/target-flow2.png)

`bodyHiddenStyle` オーバーライドについて詳しくは、「[targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)」を参照してください。

## at.js を非同期に読み込むときのちらつき制御

at.js を非同期で読み込む方法は、ブラウザーによるレンダリングのブロックを防ぐのに最適ですが、Web ページにちらつきが生じることがあります。

事前に非表示になっていて、対象の HTML 要素が [!DNL Target] によってパーソナライズされてから表示されるスニペットを使用することで、ちらつきを防げます。Adobe DTM や新しい Adobe Launch などのタグマネージャーを使用して、事前に非表示になっているスニペットを追加することをお勧めします。このスニペットは、at.js の読み込みの前に追加する必要があります。

事前に非表示になるコードスニペットの例を次に示します。

```
;(function(win, doc, style, timeout) {
  var STYLE_ID = 'at-body-style';

  function getParent() {
    return doc.getElementsByTagName('head')[0];
  }

  function addStyle(parent, id, def) {
    if (!parent) {
      return;
    }

    var style = doc.createElement('style');
    style.id = id;
    style.innerHTML = def;
    parent.appendChild(style);
  }

  function removeStyle(parent, id) {
    if (!parent) {
      return;
    }

    var style = doc.getElementById(id);

    if (!style) {
      return;
    }

    parent.removeChild(style);
  }

  addStyle(getParent(), STYLE_ID, style);
  setTimeout(function() {
    removeStyle(getParent(), STYLE_ID);
  }, timeout);
}(window, document, "body {opacity: 0 !important}", 3000));
```

デフォルトでは、このスニペットによって HTML BODY 全体が事前に非表示になります。ページ全体ではなく、一部の HTML 要素のみを事前に非表示にしたい場合もあるでしょう。その場合はスタイルのパラメーターをカスタマイズします。ページ内の特定のセクションのみを事前に非表示にするスタイルに置き換えることができます。

例えば、container-1 と container-2 という ID で識別される 2 つのセクションがある場合は、次のスタイルに置き換えることができます。

```
#container-1, #container-2 {opacity: 0 !important}
```

デフォルト設定の代わりに次を使用します。

```
body {opacity: 0 !important}
```

## triggerView（）用のat. js2. xのちらつきの管理

SPA でターゲットとなるコンテンツを表示するために `triggerView()` を使用する場合、ちらつき制御が初期設定で提供されます。つまり、事前に非表示にするロジックを手動で追加する必要はありません。代わりに、at. js2. xは、ターゲットコンテンツを適用する前にビューを表示する必要がある位置を事前に非表示にします。

## getOffer() および applyOffer() によるちらつき制御

`getOffer()` と `applyOffer()` はどちらも、抽象度の低い API であるため、ちらつき制御の機能は組み込まれていません。セレクターまたは HTML 要素をオプションとして `applyOffer()` に渡せます。この場合、`applyOffer()` はアクティビティコンテンツをこの特定の要素に追加します。ただし、`getOffer()` および `applyOffer()` が呼び出される前に、この要素が適切に事前に非表示になっていることを確認する必要があります。

```
document.documentElement.style.opacity = "0";
 
adobe.target.getOffer({
    mbox: 'target-global-mbox',
    success: function(offer) {
        adobe.target.applyOffer({
            mbox: 'target-global-mbox',
            offer: offer
        });
 
        document.documentElement.style.opacity = "1";
    },
    error: function() {
        document.documentElement.style.opacity = "1";        
    }
});
```

## at. js1. xでのmboxCreate（）との地域のmboxの使用（at. js2. xではサポートされていません）

リージョナル mbox 実装を使用する場合、`mboxCreate()` を以下のサンプルコードと同様にプロビジョニングされたページと共に使用できます。

```
<div class="mboxDefault">
Some default content
</div>
<script>
mboxCreate('some-mbox');
</script>
```

ページが適切にプロビジョニングされている場合、at.js は、mboxDefault クラスを使用して要素の CSS「visibility」プロパティを適切に切り替えることで、ちらつきを制御します。