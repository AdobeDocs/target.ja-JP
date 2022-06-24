---
keywords: ちらつき；at.js；実装；非同期；非同期；同期；同期
description: at.js とAdobe [!DNL Target] ページまたはアプリの読み込み中にちらつきを防ぎます（デフォルトのコンテンツは、アクティビティのコンテンツに置き換えられる前に一時的に表示されます）。
title: at.js はどのようにしてちらつきを制御しますか。
feature: at.js
role: Developer
exl-id: f6c26973-e046-42ed-91db-95c8a4210a9d
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 58%

---

# at.js によるちらつきの制御方法

Target at.js JavaScript ライブラリでページやアプリの読み込み中にちらつきを回避する方法について説明します。

ちらつきは、デフォルトコンテンツがアクティビティコンテンツに置き換わる前に訪問者に一時的に表示される際に発生します。ちらつきは、訪問者を混乱させる可能性があるので、望ましくありません。

## 自動作成されたグローバル mbox の使用 {#section_C502170D551C4F52AAFD8E82C41BB63A}

以下を有効にした場合、 [グローバル mbox 自動作成](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/global-mbox-overview/){target=_blank} 設定を at.js を設定すると、at.js はページの読み込み時に不透明度の設定を変更し、ちらつきを制御します。 at.js が読み込まれると、 `<body>` 要素を「0」に設定し、最初は訪問者に対してページを表示しなくなります。 Target からの応答を受信した、または Target のリクエストにエラーが検出された場合、at.js は不透明度を「1」にリセットします。これにより、訪問者は、アクティビティのコンテンツが適用された後にのみページを表示できます。

グローバル mbox を自動作成設定を at.js の設定時に有効にすると、at.js は HTML BODY スタイルの不透明度を 0 に設定します。Target からの応答を受け取ったら、at.js は HTML BODY の不透明度を 1 にリセットします。

不透明度を 0 に設定すると、ちらつきを回避するためにページコンテンツは非表示になりますが、ブラウザーは引き続きページをレンダリングし、CSS、画像などの必要なアセットをすべて読み込みます。

不透明度 0 が実装で機能しない場合は、`bodyHiddenStyle` をカスタマイズし、`body {visibility:hidden !important}` に設定することで、ちらつきを制御することもできます。どちらの値の本文も使用できます `{opacity:0 !important}` または `body {visibility:hidden !important}`特定の環境に適した

次の図は、本文非表示と本文表示の呼び出しを at.js 1.*x* と at.js 2.x の両方について示しています。

**at.js 2.x**

![Target フロー： at.js ページ読み込みリクエスト](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-flow-page-load-request.png)

**at.js 1.*x***

![](assets/target-flow2.png)

詳しくは、 `bodyHiddenStyle` 上書き： [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}。

## at.js を非同期に読み込むときのちらつき制御

at.js を非同期で読み込む方法は、ブラウザーによるレンダリングのブロックを防ぐのに最適ですが、Web ページにちらつきが生じることがあります。

事前に非表示になっていて、対象の HTML 要素が [!DNL Target] によってパーソナライズされてから表示されるスニペットを使用することで、ちらつきを防げます。

at.js は、ページに直接埋め込むか、タグマネージャー ( [!DNL Adobe Experience Platform Launch]) をクリックします。

at.js がページに埋め込まれている場合は、at.js を読み込む前にスニペットを追加する必要があります。 タグマネージャーを使用して at.js を読み込むと（同時に非同期で読み込まれる）、タグマネージャーを読み込む前にスニペットを追加する必要があります。 タグマネージャーが同期的に読み込まれる場合、スクリプトは at.js の前にタグマネージャー内に含まれることがあります。

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

## at.js 2.x の triggerView() でのちらつき制御

DOM の事前非表示は、最初のページ読み込みにのみ適用されます。 SPAの場合、DOM は `triggerView()` が呼び出されます。 SPAがコンテンツを DOM にレンダリングする時間と at.js の更新の間に、短いちらつきが生じる場合があります [!DNL Target] オファー。  ちらつきを最小限に抑えるには、 `triggerView` ページ読み込みコンテンツを変更するには、ページがレンダリングされたらすぐに「triggerView」を呼び出す必要があります。

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

## at.js 1.x での mboxCreate() によるリージョナル mbox の使用（at.js 2.x では未サポート）

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
