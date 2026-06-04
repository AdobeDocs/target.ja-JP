---
keywords: Visual Experience Composer;Visual Experience Composer のベストプラクティス;Visual Experience Composer の制限事項;Visual Experience Composer の注意事項;VEC のベストプラクティス;VEC
description: '[!UICONTROL Visual Experience Composer] （VEC）を使用する際に、エクスペリエンスを期待どおりに動作させるためのベストプラクティスを説明します。'
title: '[!UICONTROL Visual Experience Composer]のベストプラクティスと制限事項は何ですか？'
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
TQID: https://experienceleague.adobe.com/upZDSyuS9VqUmYskNXrlYazhwRHmZGBpSR-cR-qliRs
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2552
ht-degree: 49%

---

# [!UICONTROL Visual Experience Composer]のベストプラクティスと制限事項

エクスペリエンスが意図したとおりに機能することを確認するには、[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）を使用する際のベストプラクティスに従ってください。 パフォーマンスを最大化し、一般的な問題を回避するための重要なヒントと制限事項を理解します。

## ベストプラクティス {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

VECを使用する際のベストプラクティスは次のとおりです。

### at.js参照をページの`<head>` セクションの上部に配置します。

+++詳細を見る
[!UICONTROL 訪問者API サービス ]も使用する場合は、上記のat.jsに訪問者API スクリプトを配置します。

+++

### [!UICONTROL 拡張 Experience Composer] は、アカウントレベル（アカウントで作成されるすべてのアクティビティで有効化）または個々のアクティビティレベルにて有効化が可能。

+++詳細を見る
[!UICONTROL Enhanced Experience Composer]をアカウントレベルで有効にするには、[!UICONTROL [!UICONTROL 管理] > [!UICONTROL Visual Experience Composer]]をクリックし、[!UICONTROL Enhanced Experience Composerを有効にする] スイッチをオンの位置に切り替えます。

[!UICONTROL Visual Experience Composer]でアクティビティを作成する際に、アクティビティレベルで[!UICONTROL 拡張Experience Composer]を有効にするには、[!UICONTROL 設定/[!UICONTROL  ページ配信]]をクリックし、[!UICONTROL 拡張Experience Composerを有効にする] スイッチをオンの位置に切り替えます。

+++

### サイトの安全なページで[!UICONTROL Enhanced Experience Composer]が読み込まれない場合、特定のIP アドレスを許可リストできます。

+++詳細を見る
[!UICONTROL Enhanced Experience Composer]の読み込み中に問題が発生した場合は、次のIP アドレスを許可リストに加えるして解決できます。 これらのIP アドレスは、[!UICONTROL Enhanced Experience Composer] プロキシに使用される[!DNL Adobe] サーバー用です。 これらは、アクティビティの編集にのみ必要です。 サイトへの訪問者は、これらのIP アドレスを許可リストに加えるする必要はありません。

詳しくは、[拡張Experience Composer *に関する問題のトラブルシューティングに関する記事の* パブリック IP](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md)でアクセスできない内部QA URLをEECが読み込むことはありません。

+++

### トップレベルの要素と、適切なテスト／ターゲット候補になりそうなその他の要素に一意の ID を使用する。

+++詳細
body 要素内に直接配置されるあらゆる要素に一意の ID が必要です。 body 内に新しい要素を挿入してコードを移動させる場合は、少なくとも親要素は認識しやすくします。

[!DNL Target]はIDを必要としませんが、IDを使用すると、エクスペリエンスコンポーザーで作成されたエクスペリエンスの信頼性が向上します。 [!DNL Target]は、エクスペリエンスの配信時に、CSS セレクターを使用してコンテンツを変更します。 エクスペリエンスを編集する場合、[!UICONTROL Visual Experience Composer]は、変更されるHTML要素に対してnull以外のID属性を持つ最も近い祖先にセレクターを固定します。 そのため、HTML の ID 属性の設定や変更をおこなうメカニズム（JavaScript ライブラリを含む）を使用することはお勧めできません。 これらのIDは、[!DNL Target] experience composerでアクティビティの作成に使用できる場合がありますが、JavaScriptでIDが変更された場合、エクスペリエンスの実行時にエクスペリエンスの作成時に使用されていたIDは使用できない場合があります。 ID が利用できない場合、その ID に関連付けられたセレクターは実行に失敗します。

+++

### CSS クラスにわかりやすい名前を付ける。

+++詳細
[!DNL Visual Experience Composer]でCSS クラスを編集する場合は、記述的なクラス名を使用して、クラスを識別しやすくすることが役立ちます。 これにより、確実に正しい CSS クラスを編集して、ページを期待どおりに表示させることができます。

要素を隠すまたは削除する際に、`!important` CSS プロパティを使用しない。

`!important` CSS プロパティが存在する場合、配信中に`target.js`が行った変更は、サイトのCSS ルールによって上書きされます。

+++

### ページのレイアウトで HTML のテーブルを使用しない。

+++詳細
[!DNL Target]はJavaScriptを使用してページの書式設定を行います。 テーブルベースのレイアウトを JavaScript で修正するのは困難です。 また、テーブルベースのレイアウトは、すべてのブラウザーで同じように表示されない可能性があります。 最適な結果を得るには、CSS を使用してページのレイアウトを作成してください。

+++

### iFrameの使用を最小限に抑えます。

+++詳細
ページやテストの管理を簡単にするには、iFrame を極力使用しないことをお勧めします。 Visual Experience Composerでは、iFrame内の一部のアクションを適用できますが、サイズ変更などの一部のアクションは正しく機能しません。 複数の iFrame が使用されているページでは、ページの管理やサイズ変更が難しくなります。 そのため、多くの iFrame が使用されているページでは、問題が発生することがあります。

+++

### できるだけ DOM Ready の直後に動的な DOM の変更をすべて整列させる。

+++詳細
`target.js`までにエクスペリエンスアプリケーションの前に変更が適用されない場合、コンテンツ配信が壊れる可能性があります。 この問題は、ターゲット要素の階層内に DOM の変更がある場合にのみ発生します。

+++

### アンカー要素内では、プレーンテキストまたは画像タグのみを使用します。

+++詳細
`<a>Anchor Text</a>`

OR

`<a href=""> <img src=""> </img> </a>`

+++

### インライン要素内では、ブロックレベルの要素を避ける。

+++詳細
ブロックレベルの要素は、アンカーやスパンなどのインライン要素の内部では使用しないでください。 これにより、インライン要素の高さと幅が失われるため、[!UICONTROL Visual Experience Composer]のオーバーレイツールが期待どおりに機能しない可能性があります。

+++

### Web サイト内で base タグを使用して URL とリンクを解決してはならない。

+++詳細
VECは、リンクを更新するプロキシサーバーを使用して、バックグラウンドでweb サイトを操作します。 base タグを追加すると、このプロキシサーバーが使用する URL が、ブラウザーによって再度解決され、壊れているように表示されます。

+++

### 「HTML を編集」を使用して DOM 構造を操作すると、セレクターが壊れることがある。

+++詳細
例えば、次の 2 つの操作をおこなったとします。

* クラスに要素 1 を追加
* 要素 1 の HTML を編集

変更するたびに、VECに新しい要素が作成されます。 2 つ目の操作では、要素 1 を変更しているので、要素 1 を削除すると、2 つ目の操作で変更する対象となる要素がなくなるので、変更が動作しなくなります。

つまり、テキストを持つ要素を追加し、別の操作でその要素を異なるテキストに編集した場合、コードエディターには、両方の操作が別々の要素として表示されます。 要素を編集した場合は、作成した元の要素を変更した新しい要素が作成され、その新しい要素に編集したテキストが設定されます。 その後、元の要素を削除すると、編集されたテキストは、編集された要素を見付けることができないので、表示されません。 2 つ目の要素は要素のリストには引き続き含まれていますが、変更元の要素が存在しなくなっているので、ページ上での効果がなくなります。

[!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)で使用されている[要素セレクターを参照してください。

+++

### リッチテキストエディターでテキスト要素のスタイルを設定する場合は、`<b>`および`<i>` タグを使用します。

+++詳細
* 太字テキストの場合、`<strong>` ではなく、`<b>` を使用します。
* 斜体の場合、`<em>` ではなく、`<i>` を使用します。

`<strong>` および `<em>` タグは、予期しない結果になる可能性があります。

+++

### フォームフィールドの削除は慎重におこなう。

+++詳細
フォームフィールドによっては送信のために必須のものがあります。 そうしたフォームフィールドを削除すると、送信に影響する可能性があります。

+++

### スクリプト内に`mboxCreate`を含めないでください。

+++詳細
`mboxCreate` は `document.write` を使用しているので、スクリプトには `mboxCreate` を含めないことをお勧めします。 代わりに、`mboxDefine` および `mboxUpdate` を使用して、同じ処理をおこないます。

+++

### 初期化にJavaScript コードが必要な場合は、[!DNL Target]を使用してHTML スニペットを更新しないでください。


+++詳細
ページコンポーネント（スライダー、カルーセルなど）に対してアクション（HTMLの編集）を実行すると、配信が壊れているように見える場合があります。 VECは、ページコンポーネントがJavaScriptによってインスタンス化された後にアクションを実行します。

しかし、ページのコンテンツが訪問者に配信される時には、コンポーネントのインスタンス化の前にアクションが適用されます。 このため、このコンポーネントの機能が配信の際に壊れたり壊れなかったりします。 機能は、コンポーネントを定義するためにページで使用されたスクリプトの性質に依存します。

配信をテストして一度は動作しても、その後も続けて動作するとは限りません。 競合条件があることもないこともあります。

* レース条件がある場合、配信は断続的に機能します。
* レースの条件がない場合、配信は常に機能します。

ページのテストは何度かおこない、期待どおりに配信が動作することを確認してください。

+++

### Web サイト内で base タグを使用して URL やリンクを解決してはならない。

+++詳細
[!UICONTROL Enhanced Experience Composer]を使用すると、すべてのリンク URLを更新してプロキシで動作させるプロキシサーバーによって、Web サイトが舞台裏で操作されます。 基本タグを追加すると、これらのURLはすべてブラウザーで解決されるため、破損しているように見えます。

+++

### ターゲットに使用される可能性のあるサイト上の重要なテキストは、HTML コードの要素内に入れる。

+++詳細
例えば、次のようなコードでは、VEC 内の「Shopping Cart」というテキストをターゲットにできません。

```html
<a href="https://www.botanicchoice.com/shop.axd/Cart"> 
   <img alt="Shopping Cart"src="/images/ico-cart.gif"></img> 
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

### JavaScript コードで`top`または`self`個の変数を使用しないでください。

+++詳細
[!UICONTROL Enhanced Experience Composer]が有効になっている場合、上位および自己変数の値が更新され、iframe バスティングが無効になります。 カスタム JavaScript コードの代わりに、X-frame オプションヘッダーを使用して iframe バスティングを追加してください。

+++

### ページを読み込む際にパラメーターが追加される場合は、必ず Web サイトのテストをおこなう。

+++詳細
例えば、`www.abc.com`を開くには、次のURL パラメーターが使用されます。

`www.abc.com?mboxEdit=1&mboxDisable=1`

これらのパラメーターは iframe 内の編集を可能にします。

こういったパラメーターを追加した後は、Web サイトが期待どおりに読み込まれるかどうか確認してください。

+++

### iframe で期待どおりにページが開くかどうかを確認。

+++詳細
Web サイトでiframe バスティング機能をオフにし、ダミーページのiframe内でweb サイトが期待どおりに開かれるかどうかを確認します。 次に例を示します。

```html
<!DOCTYPE 
<html> 
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

## 注意事項 {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

[!UICONTROL Visual Experience Composer]を使用してアクティビティをデザインする場合は、次の点に注意してください。

### [!UICONTROL Move]機能はz インデックスをサポートしていません。

+++詳細
z- インデックス機能がないので、移動後の要素を別の要素の上に移動することはできません。 詳しくは、[制限事項](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)を参照してください。

+++

### 要素を整列すると、クリック追跡に影響する。

+++詳細
クリック追跡用にマークされた要素を整列すると、それらの要素のパスが変更されます。 その結果、整列前の要素が配置されていた位置に存在する別の要素が、クリック追跡の対象になります。

これは、アクティビティのコンテンツを配信するコードと、クリックを追跡するコードの両方が、ページに配信される同じコードに含まれているためです。 別のページを表示して、クリック追跡を設定すると、アクティビティのコンテンツコードとクリック追跡コードがそのページに配信されます。 クリック追跡ページが、テストを実行しているページと同様のページ構造を持っている場合、クリック追跡ページでもテストコンテンツが表示される場合があります。

+++

### 要素を挿入すると、mboxである`<div>`で機能しない可能性があります。

+++詳細
mboxにオファーが含まれている場合、mboxが正しく実装されていない場合、要素を挿入すると`insertBefore`として表示され、`insertAfter`として表示されない場合があります。

+++

### 親要素と子要素の両方を編集する場合、親を先に編集する。

+++詳細
要素で画像アクションを交換してから、その親要素でテキストまたは HTML を編集すると、配信で問題が発生する可能性があります。 最善のワークフローは、子要素で画像を交換する前に親要素を編集することです。

+++

### mbox を子要素として含むページ要素は選択できない。

+++詳細
例えば、ページに以下の要素が含まれている場合：

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

ページ内でハードコードされたmboxが[!DNL Target]への呼び出しを行い、応答を受信するため、エクスペリエンスで外部divを選択しないでください。 この応答は、より大きなページ要素を対象とした応答の妨げになります。

+++

### 顧客の環境でプロキシ IPがブロックされる場合があります。

+++詳細
ステージング環境などの非ライブサイトで[!UICONTROL Enhanced Experienced Composer]を使用している場合、サイトがRIPをブロックすると、タイムアウトとアクセス拒否エラーが表示される場合があります。

+++

## 制限事項 {#section_F33C2EA27F2E417AA036BC199DD6C721}

VECを使用する場合は、次の制限事項を考慮してください。

### VEC互換性を[!DNL Chrome]拡張ポリシーの変更と処理しています。 {#ext}

+++詳細
Google Chrome](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}で[V3 マニフェストポリシーが更新されたため、拡張機能はブラウザーによって解析される前に元のDOMを変更できなくなります。 その結果、iframe-busting実装などの特定のセキュリティスクリプトによって、VECでのページの読み込みがブロックされる場合があります。

互換性を確保するために、ページが[!DNL Target] iframe内に読み込まれる場合、これらのスクリプトは条件付きで無効にする必要があります。 このプロセスは、VECの読み込み中に[!DNL Target]によって挿入される`window.adobeVecExtension` オブジェクトの存在を確認することで安全に実行できます。

次のコードスニペットは、VECでweb ページが読み込まれない原因となるiframe バストリングコードの例です。

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

簡単なチェックを使用すると、web ページが[!DNL Target]内に埋め込まれている場合を検証できます。 コードスニペットは次のようになります。

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

### コンテナの外に要素を移動し、その後にCSS プロパティを移動することはできません。

+++詳細
CSS プロパティが後に続くコンテナの外側に要素を移動することはできません。

+++

### [!UICONTROL Button]要素を再配置に選択することはできません。

+++詳細
[!UICONTROL  ボタン ]要素は、再配置のために直接選択できません。 並べ替えを有効にするには、大きなコンテナ内にボタンを配置します。

+++

### mbox ではオファーの置き換えのみを使用できる。

+++詳細
[!UICONTROL  クラスを編集]や[!UICONTROL 並べ替え]などのアクションは、mbox内では許可されていません。

+++

### 同じ要素を整列して移動してはならない。

+++詳細
要素を別の位置に移動した後、親コンテナを選択して子コンテナの整列を試みた場合、その移動した要素は整列しないで、現在の位置に残ります。 整列は希望どおりに表示されないことがあります。

+++

### [!UICONTROL 画像を変更] アクションは、カルーセル内の画像に対して機能しません。

+++詳細
例えば、ページに6枚の画像を含むカルーセルがあり、画像をカルーセルの2番目の画像と入れ替えたい場合、「[!UICONTROL 画像を変更]」アクションは機能しません。

回避策として、親コンテナを選択し、[!UICONTROL HTMLを編集] アクションを使用してカルーセルのHTMLを編集し、目的の画像の画像ソースを更新します。

+++

### mbox 内では画像のサイズを変更できない。

+++詳細
mbox 要素内で画像をスワップした後、mbox 要素のサイズに従ってその画像のサイズを変更しようとしても、サイズ変更は許可されません。

+++

### 画像を入れ替えた後、[!UICONTROL 編集] アクションを選択することはできません。

+++詳細
画像をスワップした後は、Scene7 の URL を編集できません。

+++

### 外部ソースを持つHTML要素は編集できません。

+++詳細
例：ビデオ、オーディオタグ、埋め込み、iFrame、フレーム。

+++

### プレーンテキストまたは画像タグ以外の要素を含むアンカー要素に対してクリック追跡が機能しない。

+++詳細
例えば、要素に JavaScript が含まれている場合、クリック追跡は機能しません。

+++

### ページは、VECが機能するためにURL パラメーターを受け入れる必要があります。

+++詳細
一部のサイトは、ページの URL パラメーターを除去します。 ただし、VECにはこれらのパラメーターが必要です。

+++

### HTMLの一部としてスクリプトを使用する場合、外部からアクセスされる変数と関数は、ウィンドウ名前空間の下で宣言する必要があります。

+++詳細
スクリプトは、ページの読み込み後、`target.js`の範囲内で実行されます。 このため、ローカルに定義された変数や関数は、外部のスクリプトブロックからアクセスできません。

*誤った構文:*

```html
<script> 
  var myVar = 123; 
  function myFunc() { 
    // 
  } 
</script>`
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

### [!UICONTROL Content] ライブラリ （Scene7）から画像を挿入し、HTMLを編集すると、画像のURLが壊れます。

+++詳細
「customHeaderMessage」 div 内に、任意のダミーテキストの入ったアンカー要素を追加します。

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

「[!UICONTROL  エレメントを挿入]」アクションを使用して、このdivを選択し、このダミーテキスト divの兄弟として画像を挿入します。

画像挿入後は、次のようになります。

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

ダミーテキストの span を削除します。

+++

### VECの`customCode` アクションは、[!DNL Internet Explorer] 8では機能しません。

+++詳細
スクリプト コンテンツを処理する際のIE8の制限により、`target.js`はIE8でこれをサポートしていません。 回避策として、ページにjQueryが含まれており、ウィンドウ オブジェクト上にグローバルに公開されている場合、`target.js`は`customCode` アクションの配信を使用できます。 `window.jQuery`と`window.jQuery.fn.prepend`が定義されていることを確認してください。

+++

### クリック追跡は、エクスペリエンスが作成されたページまたはリダイレクトされるページでのみサポートされる。

+++詳細
VECでは[!UICONTROL 参照] モードをクリック追跡に使用できますが、[!UICONTROL 参照] モードを使用してページにクリック追跡を追加することはできません。

+++
