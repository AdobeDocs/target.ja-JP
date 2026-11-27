---
keywords: Visual Experience Composer;Visual Experience Composer のベストプラクティス;Visual Experience Composer の制限事項;Visual Experience Composer の注意事項;VEC のベストプラクティス;VEC
description: '[!UICONTROL Visual Experience Composer] （VEC）を使用する際に、エクスペリエンスを期待どおりに動作させるためのベストプラクティスを説明します。'
title: '[!UICONTROL Visual Experience Composer]のベストプラクティスと制限事項は何ですか？'
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
TQID: 'https://experienceleague.adobe.com/upZDSyuS9VqUmYskNXrlYazhwRHmZGBpSR-cR-qliRs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '2420'
ht-degree: 7%
---
# [!UICONTROL Visual Experience Composer]のベストプラクティスと制限事項 {#vec-best-practices}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、**[!UICONTROL Visual Experience Composer]** （VEC）でエクスペリエンスを作成する際に注意すべきベストプラクティス、注意事項、制限事項について説明します。

>[!ENDSHADEBOX]

これらのプラクティスに従うと、[!DNL Adobe Target] **[!UICONTROL Visual Experience Composer]** （VEC）関数で作成されたエクスペリエンスが意図したとおりに役立ちます。 注意事項と制限事項は、一般的な問題を引き起こす可能性のある行動を記述するため、それらを把握することは、問題を回避し、パフォーマンスを維持するのに役立ちます。

## ベストプラクティス {#best-practices}

VECを使用する場合は、次の方法が適用されます。

### [!UICONTROL Enhanced Experience Composer]を有効にする {#enable-eec}

**[!UICONTROL 拡張Experience Composer]**&#x200B;は、アカウントレベルで有効にできます。これにより、アカウント内で作成されたすべてのアクティビティ、または個々のアクティビティレベルで有効にできます。

* **アカウントレベル：** **[!UICONTROL 管理]** > **[!UICONTROL Visual Experience Composer]**&#x200B;をクリックし、**[!UICONTROL 拡張Experience Composerを有効にする]** スイッチをオンの位置に切り替えます。
* **アクティビティレベル：** **[!UICONTROL Visual Experience Composer]**&#x200B;でアクティビティを作成する際、**[!UICONTROL 設定]** > **[!UICONTROL ページ配信]**&#x200B;をクリックし、**[!UICONTROL 拡張Experience Composerを有効にする]** スイッチをオンの位置に切り替えます。

### ページの設定と読み込み

+++ at.js参照をページの`<head>` セクションの上部に配置します。

**[!UICONTROL 訪問者API サービス]**&#x200B;も使用する場合は、上記のat.jsに訪問者API スクリプトを配置します。

+++

+++ [!UICONTROL Enhanced Experience Composer]がサイトの安全なページで読み込まれない場合は、IP アドレスを許可リストに加えるします。

**[!UICONTROL Enhanced Experience Composer]** プロキシに使用されている[!DNL Adobe] サーバーのIP アドレスを許可リストに加えるすると、読み込み中の問題が解決されます。 これらのIP アドレスは、アクティビティ編集にのみ必要です。 サイトへの訪問者は、許可リストに加えるする必要はありません。 IP アドレスは[に記載されています。EECは、*Enhanced Experience Composer*&#x200B;に関する問題のトラブルシューティングで、パブリック IP](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#eec-ip-addresses)でアクセスできない内部QA URLを読み込みません。

+++

+++ Web サイトの基本タグを使用してURLとリンクを解決しないでください。

VECでは、**[!UICONTROL Enhanced Experience Composer]**&#x200B;を含め、すべてのリンク URLを更新してプロキシで動作させるプロキシ サーバーを通じて、バックグラウンドでWeb サイトを操作します。 基本タグが追加されると、ブラウザーはこれらのURLを再度解決するため、破損しているように見えます。

+++

+++ JavaScript コードで`top`または`self`変数を使用しないでください。

**[!UICONTROL Enhanced Experience Composer]**&#x200B;が有効になっている場合、`top`変数と`self`変数の値が更新され、iframe バスティングが無効になります。 カスタム JavaScript コードの代わりに、X-Frame-Options ヘッダーを使用してiframe バスティングを追加します。

+++

+++ ページの読み込み時にパラメーターが追加された場合は、必ずweb サイトをテストします。

例えば、次のURL パラメーターを使用して、iframeで編集するために`www.abc.com`を開きます。

`www.abc.com?mboxEdit=1&mboxDisable=1`

このようなパラメーターを追加した後、web サイトが期待どおりに読み込まれることを確認してください。

+++

+++ ページがiframeで期待どおりに開くことを確認します。

Web サイトでiframe バスティング機能をオフにし、ダミーページでiframeでweb サイトが期待どおりに開かれるかどうかを確認します。 次に例を示します。

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>JS Bin</title>
</head>
<body>
  <iframe src="https://www.homedepot.com"</iframe>
</body>
</html>
```

+++

### ページマークアップ

+++ トップレベルの要素や、テストやターゲティングに適した候補であるその他の要素に対して、一意のIDを使用します。

body要素の中にあるすべてのものは一意のIDを持つべきであり、そうすれば少なくとも親要素は新しい要素がbodyに注入され、コードが動き回ったときに認識しやすくなります。

[!DNL Target]はIDを必要としませんが、IDはExperience Composerで作成されたエクスペリエンスの信頼性を高めます。 [!DNL Target]は、エクスペリエンスの配信時にCSS セレクターを使用してコンテンツを変更します。 エクスペリエンスが編集されると、**[!UICONTROL Visual Experience Composer]**&#x200B;は、null ID以外の属性を持つ変更されたHTML要素の最も近い祖先にセレクターをアンカーします。 したがって、HTML ID属性を設定または変更するJavaScript ライブラリを含むメカニズムを使用することはお勧めできません。 これらのIDは、アクティビティの作成時にExperience Composerで使用できる場合がありますが、JavaScriptで変更した場合、エクスペリエンスの実行時に作成時に使用されるIDは使用できない場合があります。 IDが利用できない場合、そのIDにアンカーされているセレクターは失敗します。

+++

+++ 記述的なCSS クラス名を使用します。

記述的なクラス名を使用すると、**[!UICONTROL Visual Experience Composer]**&#x200B;でCSS クラスを編集する際に、クラスを識別しやすくなります。 これにより、適切なCSS クラスが編集され、ページが期待どおりに表示されます。

+++

+++ 要素を非表示または削除する場合は、`!important` CSS プロパティを使用しないでください。

`!important` CSS プロパティが存在する場合、サイトのCSS ルールは、配信中に`target.js`が行った変更を上書きします。

+++

+++ ページレイアウトにはHTMLの表を使用しないでください。

[!DNL Target]はJavaScriptを使用してページの書式を設定します。また、JavaScriptではテーブルベースのレイアウトを変更するのが困難です。 また、テーブルベースのレイアウトは、すべてのブラウザーで同じように表示されない場合があります。 最適な結果を得るには、CSS を使用してページのレイアウトを作成してください。

+++

+++ iFrameの使用を最小限に抑えます。

iFrameを最小化すると、ページとテストの管理が簡単になります。 **[!UICONTROL Visual Experience Composer]**&#x200B;は、iFrame内の一部のアクションを適用できますが、サイズ変更などの一部のアクションは正しく機能しません。 複数のiFrameを使用するページは管理やサイズ変更が難しいため、iFrameを多用したページをテストすると問題が発生する可能性があります。

+++

+++ アンカー要素では、プレーンテキストまたは画像タグのみを使用します。

アンカー要素には、次のいずれかのプレーンテキストが含まれます。

`<a>Anchor Text</a>`

画像タグを使用します。

`<a href=""> <img src=""> </img> </a>`

+++

+++ インライン要素内では、ブロックレベルの要素を避ける。

アンカーやスパンなどのインライン要素では、ブロックレベルの要素を使用しないでください。 これにより、インライン要素の高さと幅が失われるため、**[!UICONTROL Visual Experience Composer]**&#x200B;のオーバーレイツールが期待どおりに機能しない可能性があります。

+++

+++ フォームフィールドの削除は慎重におこなう。

特定のフォームフィールドは送信に必須である場合があるため、削除すると送信に影響する可能性があります。

+++

+++ 要素内のHTML コードでターゲティングに使用される可能性のある重要なテキストを保持します。

例えば、次のようなコードの場合、VECでショッピングカートのテキストをターゲットにすることはできません。

```html
<a href="https://www.botanicchoice.com/shop.axd/Cart">
   <img alt="Shopping Cart" src="/images/ico-cart.gif"></img>
   Shopping Cart:
   <span id="HeaderCartQtyTotal">
      0
  </span>
  Items
  <span id="HeaderCartPriceTotal"></span>
</a>
```

この例では、VECでアンカー要素全体が選択されており、ターゲティングが実行された場合に他の要素に悪影響を及ぼします。

+++

### 編集と配信

+++ DOMの準備が整った後、できるだけ早くすべての動的DOMの変更を配置します。

`target.js`がエクスペリエンスを適用する前に変更が適用されない場合、コンテンツ配信が壊れる可能性があります。 この問題は、ターゲット要素の階層内に DOM の変更がある場合にのみ発生します。

+++

+++ Edit HTMLを使用してDOM構造を操作すると、セレクターが壊れる可能性があります。

例えば、次の2つのアクションが実行されます。

* クラスが要素1に追加されます。
* Element 1のHTMLが編集されます。

変更するたびに、VECに新しい要素が作成されます。 2番目のアクションは要素1を変更するので、要素1が削除された場合、2番目のアクションには変更するものがなくなり、変更は機能しなくなります。

同様に、要素にテキストと別のアクションを追加し、その要素を異なるテキストで編集する場合、コードエディターは両方のアクションを別々の要素として表示します。 編集を行うと、元の要素を修正し、編集したテキストを含む新しい要素が作成されます。 元の要素が削除された場合、編集したテキストは変更する要素を見つけることができず、表示されません。 2番目の要素は要素のリストに残りますが、変更された要素が存在しなくなったため、ページには影響しません。

**[!UICONTROL Visual Experience Composer]**&#x200B;[&#128279;](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#vec-selectors)で使用されている要素セレクターを参照してください。

+++

+++ リッチテキストエディターでテキスト要素のスタイルを設定する場合は、`<b>`および`<i>` タグを使用します。

* 太字テキストの場合、`<strong>` ではなく、`<b>` を使用します。
* 斜体の場合、`<em>` ではなく、`<i>` を使用します。

`<strong>`および`<em>` タグが予期しない結果を引き起こす可能性があります。

+++

+++ スクリプト内に`mboxCreate`を含めないでください。

`mboxCreate`は`document.write`を使用しているため、スクリプトに含めることはお勧めできません。 `mboxDefine`と`mboxUpdate`を同じ目的で使用します。

+++

+++ スニペットの初期化にJavaScript コードが必要な場合は、HTML スニペットを[!DNL Target]で更新しないでください。

スライダーやカルーセルなどのページコンポーネントに対してアクション（HTMLの編集）を実行すると、配信が壊れているように見える場合があります。 VECは、JavaScriptがページコンポーネントをインスタンス化した後にアクションを実行します。 ただし、ページコンテンツが訪問者に配信されると、コンポーネントがインスタンス化される前にアクションが適用されます。 その結果、ページ上のコンポーネントを定義するスクリプトによっては、コンポーネントの機能が配信時に壊れたり、壊れなかったりする可能性があります。

最初に機能する配信テストは、競合条件が存在する可能性があるため、配信が引き続き機能することを保証するものではありません。

* レース条件がある場合、配信は断続的に機能します。
* レースの条件がない場合、配信は常に機能します。

ページを複数回テストし、配信が期待通りに機能することを確認します。

+++

## 注意事項 {#caveats}

アクティビティをデザインするために&#x200B;**[!UICONTROL Visual Experience Composer]**&#x200B;を使用する場合は、次の注意事項が適用されます。

+++ [!UICONTROL Move]機能はz インデックスをサポートしていません。

Z インデックス機能を使用しない場合、移動された要素を別の要素の上に配置することはできません。 詳しくは、[制限事項](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)を参照してください。

+++

+++ 要素を整列すると、クリック追跡に影響する。

クリックトラッキング用にマークされたエレメントを再配置すると、再配置されたエレメントのパスが変更されます。 その結果、元の要素が再配置される前の場所の要素でクリックが追跡されます。

これは、アクティビティコンテンツを配信するコードとクリックを追跡するコードが、ページに配信される1つのコードに含まれているために発生します。 別のページを参照し、クリックトラッキングが設定されている場合、両方のコードがそのページに配信されます。 クリックトラッキングページが、テストが実行されるページと類似したページ構造を持つ場合、テストコンテンツがクリックトラッキングページにも表示される場合があります。

+++

+++ 要素を挿入すると、mboxである`<div>`で機能しない可能性があります。

mboxにオファーが含まれており、mboxが正しく実装されていない場合、挿入された要素は`insertAfter`ではなく`insertBefore`として表示される可能性があります。

+++

+++ 親エレメントと子エレメントの両方を編集する場合は、まず親エレメントを編集します。

画像アクションがエレメント上でスワップされ、その親エレメントのテキストまたはHTMLが編集されると、配信の問題が発生する可能性があります。 最善のワークフローは、子要素で画像を交換する前に親要素を編集することです。

+++

+++ mboxを子要素として含むページ要素は選択しないでください。

例えば、ページに次のコードが含まれている場合：

```html
<div>
  <div class="mboxDefault" >
  </div>
  <script>mboxCreate('myMbox');
</script>
</div>
```

ページ内でハードコードされたmboxが[!DNL Target]への呼び出しを行い、応答を受信するため、エクスペリエンスで外部divを選択しないでください。 この応答は、より大きなページ要素を対象とした応答の妨げになります。

+++

+++ プロキシ IP アドレスは、お客様の環境でブロックされる可能性があります。

**[!UICONTROL 拡張Experience Composer]**&#x200B;がステージング環境などの非ライブサイトで使用されている場合、サイトがプロキシ IP アドレスをブロックすると、タイムアウトとアクセス拒否エラーが発生する可能性があります。

+++

## 制限事項 {#section_F33C2EA27F2E417AA036BC199DD6C721}

VECを使用する場合は、次の制限が適用されます。

### ページの要件

+++ VECの互換性と[!DNL Chrome]拡張機能ポリシーの変更を処理します。

Google Chrome[&#128279;](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}で更新されたV3 マニフェストポリシーでは、ブラウザーが解析する前に拡張機能が元のDOMを変更できなくなります。 その結果、iframe-busting実装などの特定のセキュリティスクリプトによって、VECでのページの読み込みがブロックされる場合があります。

互換性を確保するために、ページが[!DNL Target] iframe内に読み込まれたときに、これらのスクリプトを条件付きで無効にします。 これは、[!DNL Target]がVECの読み込み中に挿入する`window.adobeVecExtension` オブジェクトの存在を確認することで、安全に実行できます。

次のコードスニペットは、Web ページがVECに読み込まれるのを防ぐことができるiframe バストリングコードの例です。

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

簡単なチェックでは、web ページが[!DNL Target]内に埋め込まれている場合を確認できます。 コードスニペットは次のようになります。

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

+++ ページは、VECが機能するためにURL パラメーターを受け入れる必要があります。

一部のサイトでは、ページからURL パラメーターが削除されますが、VECではこれらのパラメーターが必要です。

+++

+++ スクリプトをHTMLの一部として使用する場合は、ウィンドウ名前空間の下の外部からアクセスされる変数と関数を宣言します。

スクリプトは、ページの読み込み後に`target.js`の範囲内で実行されるので、ローカルに宣言された変数または関数は、スクリプトブロックの外部からアクセスできません。

*誤った構文:*

```html
<script>
  var myVar = 123;
  function myFunc() {
    //
  }
</script>
```

*正しい構文:*

```html
<script>
  window.myVar = 123;
  window.myFunc = function() {
    //
  };
</script>
```

+++

+++ VECの`customCode` アクションは、[!DNL Internet Explorer] 8では機能しません。

`target.js`は、スクリプト コンテンツを処理する際のIE8の制限により、IE8でこのアクションをサポートしていません。 回避策として、ページにjQueryが含まれており、jQueryがウィンドウ オブジェクト上でグローバルに公開されている場合、`target.js`は`customCode` アクションを配信できます。 `window.jQuery`と`window.jQuery.fn.prepend`が定義されていることを確認してください。

+++

### 並べ替えとmbox

**CSS プロパティが続くコンテナの外側に要素を移動することはできません。**

+++ [!UICONTROL Button]要素を再配置に選択できません。

**[!UICONTROL ボタン]**&#x200B;要素は、再配置のために直接選択できません。 並べ替えを有効にするには、大きなコンテナ内にボタンを配置します。

+++

+++ 同じエレメントを並べ替えたり、移動したりしないでください。

エレメントが別の場所に移動され、親コンテナが子エレメントの並べ替えに選択された場合、移動されたエレメントは影響を受けず、そのエレメントが存在する場所に残ります。 整列は希望どおりに表示されないことがあります。

+++

+++ mbox ではオファーの置き換えのみを使用できる。

**[!UICONTROL クラスを編集]**&#x200B;や&#x200B;**[!UICONTROL 並べ替え]**&#x200B;などのアクションは、mbox内では許可されていません。

+++

### 画像

+++ [!UICONTROL 画像を変更] アクションは、カルーセル内の画像に対して機能しません。

例えば、ページに6枚の画像を含むカルーセルがあり、1枚の画像がカルーセルの2番目の画像と入れ替えられる場合、**[!UICONTROL 画像を変更]** アクションは機能しません。

回避策として、親コンテナを選択し、**[!UICONTROL HTMLを編集]** アクションを使用してカルーセルのHTMLを編集し、目的の画像の画像ソースを更新します。

+++

+++ mbox 内では画像のサイズを変更できない。

画像がmbox要素でスワップされ、mbox要素のサイズに応じてサイズ変更された場合、サイズ変更は許可されません。

+++

+++ 画像をスワップした後、[!UICONTROL 編集] アクションを選択できません。

画像がスワップされた後、Scene7 URLは編集できません。

+++

+++ [!UICONTROL Content] ライブラリ （Scene7）から画像を挿入し、HTMLを編集すると、画像のURLが壊れます。

ダミーテキストを含む`customHeaderMessage` div内にアンカー要素を追加します。

```html
<a href="#">
<span> Dummy text </span>
</a>
```

「**[!UICONTROL エレメントを挿入]**」アクションを使用してこのdivを選択し、画像をダミーテキストの兄弟として挿入します。

画像を挿入すると、コードは次のようになります。

```html
<a href="#">
<span> Dummy text </span>
<img src=""> This is inserted Image. </img>
</a>
```

ダミーテキストの span を削除します。

+++

### クリックの追跡と外部コンテンツ

+++ プレーンテキストまたは画像タグ以外の要素を含むアンカー要素に対してクリック追跡が機能しない。

例えば、要素に JavaScript が含まれている場合、クリック追跡は機能しません。

+++

+++ クリック追跡は、エクスペリエンスが作成されたページまたはリダイレクトされるページでのみサポートされる。

VECでは&#x200B;**[!UICONTROL 参照]** モードをクリック追跡に使用できますが、**[!UICONTROL 参照]** モードを使用してページにクリック追跡を追加することはできません。

+++

+++ 外部ソースを持つHTML要素は編集できません。

例：ビデオ、オーディオタグ、埋め込み、iFrame、フレーム。

+++
