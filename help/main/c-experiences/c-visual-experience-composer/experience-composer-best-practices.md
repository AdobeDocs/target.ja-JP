---
keywords: Visual Experience Composer;Visual Experience Composer のベストプラクティス;Visual Experience Composer の制限事項;Visual Experience Composer の注意事項;VEC のベストプラクティス;VEC
description: '[!UICONTROL Visual Experience Composer] （VEC）の使用時にエクスペリエンスが期待どおりに動作するように、ベストプラクティスを説明します。'
title: ベストプラクティス [!UICONTROL Visual Experience Composer] 制限事項
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
source-git-commit: d7ca0867314808f4d38c0de0b8c1e1f0cbf70cc0
workflow-type: tm+mt
source-wordcount: '2434'
ht-degree: 37%

---

# ベストプラクティスと制限事項に [!UICONTROL Visual Experience Composer] いて

エクスペリエンスが意図したとおりに機能するように、[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）を使用する際は、ベストプラクティスに従ってください。 パフォーマンスを最大化し、一般的な問題を回避するための重要なヒントと制限事項に注意します。

## ベストプラクティス {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

VEC を使用する際のベストプラクティスは、次のとおりです。

### at.js 参照をページの `<head>` セクションの先頭に配置します。

+++詳細を表示
[!UICONTROL Visitor API Service] も使用する場合は、訪問者 API スクリプトを at.js の上に配置します。

+++

### この [!UICONTROL Enhanced Experience Composer] は、アカウントレベル（アカウントで作成されたすべてのアクティビティで有効）または個々のアクティビティレベルで有効にできます。

+++詳細を表示
アカウントレベルで [!UICONTROL Enhanced Experience Composer] を有効にするには、「[!UICONTROL [!UICONTROL Administration] > [!UICONTROL Visual Experience Composer]]」をクリックし、[!UICONTROL Enable Enhanced Experience Composer] のスイッチを「オン」の位置に切り替えます。

[!UICONTROL Visual Experience Composer] でアクティビティを作成しながらアクティビティレベルで [!UICONTROL Enhanced Experience Composer] を有効にするには、「[!UICONTROL Configure > [!UICONTROL Page Delivery]]」をクリックし、[!UICONTROL Enable Enhanced Experience Composer] の切り替えを「オン」の位置に切り替えます。

+++

### サイト上のセキュリティで保護されたページに [!UICONTROL Enhanced Experience Composer] が読み込まれない場合は、特定の IP アドレスを許可リストに加えるできます。

+++詳細を表示
[!UICONTROL Enhanced Experience Composer] の読み込みに関する問題は、次の IP アドレスを許可リストに加えるすることで解決できます。 これらの IP アドレスは、[!UICONTROL Enhanced Experience Composer] プロキシに使用される [!DNL Adobe] サーバー用です。 これらは、アクティビティの編集にのみ必要です。サイトへの訪問者は、これらの IP アドレスの許可リストに加えるは必要ありません。

詳しくは、[ 拡張 Experience Composer に関連する問題のトラブルシューティング *の「EEC は、公開 IP でアクセスできない内部 QA URL を読み込みません ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md) を参照してください*。

+++

### トップレベルの要素と、適切なテスト／ターゲット候補になりそうなその他の要素に一意の ID を使用する。

+++詳細
body 要素のすぐ内側にあるものはすべて、一意の ID を持つ必要があります。 body 内に新しい要素を挿入してコードを移動させる場合は、少なくとも親要素は認識しやすくします。

[!DNL Target] では ID は必要ありませんが、ID を使用すると Experience Composer で作成されたエクスペリエンスの信頼性が向上します。 [!DNL Target] は、CSS セレクターを使用して、エクスペリエンスの配信時にコンテンツを変更します。 エクスペリエンスを編集すると、変更するHTML要素の null 以外の ID 属性を持つ最も近い上位にセレクターがア [!UICONTROL Visual Experience Composer] カーされます。 そのため、HTML の ID 属性の設定や変更をおこなうメカニズム（JavaScript ライブラリを含む）を使用することはお勧めできません。これらの ID は [!DNL Target] Experience Composer でアクティビティの作成に使用できますが、JavaScriptで ID を変更した場合、エクスペリエンスの作成時に使用された ID は、エクスペリエンスの実行時には使用できない可能性があります。 ID が利用できない場合、その ID に関連付けられたセレクターは実行に失敗します。

+++

### CSS クラスにわかりやすい名前を付ける。

+++詳細
[!DNL Visual Experience Composer] で CSS クラスを編集する場合、わかりやすいクラス名を使用して、クラスを識別しやすくすると便利です。 これにより、確実に正しい CSS クラスを編集して、ページを期待どおりに表示させることができます。

要素を隠すまたは削除する際に、`!important` CSS プロパティを使用しない。

`!important` CSS プロパティが存在する場合は、配信中に `target.js` が行った変更は、サイトの CSS ルールによって上書きされます。

+++

### ページのレイアウトで HTML のテーブルを使用しない。

+++詳細
[!DNL Target] は、JavaScriptを使用してページを書式設定します。 テーブルベースのレイアウトを JavaScript で修正するのは困難です。また、テーブルベースのレイアウトは、すべてのブラウザーで同じように表示されない可能性があります。最適な結果を得るには、CSS を使用してページのレイアウトを作成してください。

+++

### iFrame の使用を最小限に抑えます。

+++詳細
iFrame の使用を最小限に抑え、ページとテストの管理を簡素化することをお勧めします。 Visual Experience Composer では、iFrame 内で一部の操作を適用できますが、サイズ変更など、一部の操作が正しく動作しません。 複数の iFrame が使用されているページでは、ページの管理やサイズ変更が難しくなります。そのため、多くの iFrame が使用されているページでは、問題が発生することがあります。

+++

### できるだけ DOM Ready の直後に動的な DOM の変更をすべて整列させる。

+++詳細
`target.js` によるエクスペリエンスアプリケーションの前に変更を適用できない場合は、コンテンツ配信が壊れる可能性があります。 この問題は、ターゲット要素の階層内に DOM の変更がある場合にのみ発生します。

+++

### アンカー要素内では、プレーンテキストまたは画像タグのみを使用します。

+++詳細
`<a>Anchor Text</a>`

OR

`<a href=""> <img src=""> </img> </a>`

+++

### インライン要素内では、ブロックレベルの要素を避ける。

+++詳細
ブロックレベル要素は、アンカーやスパンなどのインライン要素内で使用しないでください。 これにより、インライン要素の高さと幅が失われるので、[!UICONTROL Visual Experience Composer] のオーバーレイツールが期待どおりに動作しない場合があります。

+++

### Web サイト内で base タグを使用して URL とリンクを解決してはならない。

+++詳細
VEC では、リンクを更新するプロキシサーバーを使用して、バックグラウンドで web サイトを操作します。 base タグを追加すると、このプロキシサーバーが使用する URL が、ブラウザーによって再度解決され、壊れているように表示されます。

+++

### 「HTML を編集」を使用して DOM 構造を操作すると、セレクターが壊れることがある。

+++詳細
例えば、次の 2 つのアクションを実行したとします。

* クラスに要素 1 を追加
* 要素 1 の HTML を編集

変更するたびに、VEC に新しい要素が作成されます。 2 つ目の操作では、要素 1 を変更しているので、要素 1 を削除すると、2 つ目の操作で変更する対象となる要素がなくなるので、変更が動作しなくなります。

つまり、テキストを持つ要素を追加し、別の操作でその要素を異なるテキストに編集した場合、コードエディターには、両方の操作が別々の要素として表示されます。要素を編集した場合は、作成した元の要素を変更した新しい要素が作成され、その新しい要素に編集したテキストが設定されます。その後、元の要素を削除すると、編集されたテキストは、編集された要素を見付けることができないので、表示されません。2 つ目の要素は要素のリストには引き続き含まれていますが、変更元の要素が存在しなくなっているので、ページ上での効果がなくなります。

[!UICONTROL Visual Experience Composer][&#128279;](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337) で使用される  要素セレクターを参照してください。

+++

### リッチテキストエディターでテキスト要素のスタイルを設定する際は、`<b>` タグと `<i>` タグを使用します。

+++詳細
* 太字テキストの場合、`<strong>` ではなく、`<b>` を使用します。
* 斜体の場合、`<em>` ではなく、`<i>` を使用します。

`<strong>` および `<em>` タグは、予期しない結果になる可能性があります。

+++

### フォームフィールドの削除は慎重におこなう。

+++詳細
特定のフォームフィールドは、送信に必須である場合があります。 そうしたフォームフィールドを削除すると、送信に影響する可能性があります。

+++

### スクリプト内に `mboxCreate` を含めないでください。

+++詳細
`mboxCreate` は `document.write` を使用するので、スクリプトに `mboxCreate` を含めることはお勧めしません。 代わりに、`mboxDefine` および `mboxUpdate` を使用して、同じ処理をおこないます。

+++

### 初期化にHTML コードが必要な場合は、[!DNL Target] を使用してJavaScript スニペットを更新しないでください。


+++詳細
ページコンポーネント（スライダー、カルーセルなど）でアクション（「HTMLを編集」）を実行すると、配信が壊れているように見える場合があります。 VEC は、ページコンポーネントがJavaScriptによってインスタンス化された後に、アクションを実行します。

しかし、ページのコンテンツが訪問者に配信される時には、コンポーネントのインスタンス化の前にアクションが適用されます。このため、このコンポーネントの機能が配信の際に壊れたり壊れなかったりします。機能は、コンポーネントを定義するためにページで使用されたスクリプトの性質に依存します。

配信をテストして一度は動作しても、その後も続けて動作するとは限りません。競合条件があることもないこともあります。

* 競合状態が発生している場合、配信は断続的に動作します。
* 競合状態がない場合、配信は常に機能します。

ページのテストは何度かおこない、期待どおりに配信が動作することを確認してください。

+++

### Web サイト内で base タグを使用して URL やリンクを解決してはならない。

+++詳細
[!UICONTROL Enhanced Experience Composer] を使用すると、すべてのリンク URL を更新してプロキシで機能させるプロキシサーバーによって、web サイトがバックグラウンドで操作されます。 ベースタグを追加すると、これらの URL はすべてブラウザーで解決されるので、壊れているように見えます。

+++

### ターゲットに使用される可能性のあるサイト上の重要なテキストは、HTML コードの要素内に入れる。

+++詳細
例えば、コードが次のような場合、VEC で「買い物かご」テキストをターゲットにすることはできません。

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

この例では、VEC でアンカー要素全体が選択されているので、ターゲティングを実行すると他の要素に悪影響を与えます。

+++

### JavaScript コードでは `top` 変数や `self` 変数を使用しないでください。

+++詳細
[!UICONTROL Enhanced Experience Composer] が有効な場合、top 変数と self 変数の値が更新され、iframe バスティングが無効になります。 カスタム JavaScript コードの代わりに、X-frame オプションヘッダーを使用して iframe バスティングを追加してください。

+++

### ページを読み込む際にパラメーターが追加される場合は、必ず Web サイトのテストをおこなう。

+++詳細
例えば、`www.abc.com` を開くには、次の URL パラメーターが使用されます。

`www.abc.com?mboxEdit=1&mboxDisable=1`

これらのパラメーターは iframe 内の編集を可能にします。

こういったパラメーターを追加した後は、Web サイトが期待どおりに読み込まれるかどうか確認してください。

+++

### iframe で期待どおりにページが開くかどうかを確認。

+++詳細
Web サイトの iframe バスティングテクニックをオフにし、ダミーページの iframe 内で web サイトが期待どおりに開くかどうかを確認します。 次に例を示します。

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

[!UICONTROL Visual Experience Composer] を使用してアクティビティをデザインする際は、次の点に注意してください。

### [!UICONTROL Move] 機能は z-index をサポートしていません。

+++詳細
z インデックス機能がないため、移動された要素を別の要素の上に移動することはできません。 詳しくは、[制限事項](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)を参照してください。

+++

### 要素を整列すると、クリック追跡に影響する。

+++詳細
クリック追跡用にマークされた要素を並べ替えると、並べ替えられた要素のパスが変更される。 その結果、整列前の要素が配置されていた位置に存在する別の要素が、クリック追跡の対象になります。

これは、アクティビティのコンテンツを配信するコードと、クリックを追跡するコードの両方が、ページに配信される同じコードに含まれているためです。別のページを表示して、クリック追跡を設定すると、アクティビティのコンテンツコードとクリック追跡コードがそのページに配信されます。クリック追跡ページが、テストを実行しているページと同様のページ構造を持っている場合、クリック追跡ページでもテストコンテンツが表示される場合があります。

+++

### 要素の挿入は、mbox である `<div>` では機能しない場合があります。

+++詳細
mbox にオファーが含まれている場合、mbox が正しく実装されていなければ、要素の挿入は `insertBefore` として表示され、`insertAfter` として表示されない場合があります。

+++

### 親要素と子要素の両方を編集する場合、親を先に編集する。

+++詳細
要素の画像アクションを入れ替えて、その親要素のテキストまたはHTMLを編集すると、配信の問題が発生する場合があります。 最善のワークフローは、子要素で画像を交換する前に親要素を編集することです。

+++

### mbox を子要素として含むページ要素は選択できない。

+++詳細
例えば、ページに次のものが含まれている場合：

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

ページにハードコードされた mbox は引き続き [!DNL Target] を呼び出し、応答を受信するので、外側の div はエクスペリエンスで選択しないでください。 この応答は、より大きなページ要素を対象とした応答の妨げになります。

+++

### プロキシ IP は、お客様の環境でブロックされる可能性があります。

+++詳細
ステージング環境など、ライブ以外のサイトで [!UICONTROL Enhanced Experienced Composer] を使用している場合は、サイトが RIP をブロックすると、タイムアウトやアクセス拒否のエラーが表示される場合があります。

+++

## 制限事項 {#section_F33C2EA27F2E417AA036BC199DD6C721}

VEC を使用する際は、次の制限事項を考慮してください。

### 拡張機能ポリシーの変更に伴う VEC[!DNL Chrome] 互換性の処理。 {#ext}

Google Chrome[&#128279;](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank} の V3 マニフェストポリシーが更新されたため、ブラウザーによって解析される前に、拡張機能で元の DOM を変更できなくなりました。 その結果、特定のセキュリティスクリプト（iframe バスティング実装など）によって、VEC へのページの読み込みがブロックされる場合があります。

互換性を確保するために、ページが [!DNL Target] iframe 内に読み込まれる際には、これらのスクリプトを条件付きで無効にする必要があります。 このプロセスは、VEC 読み込み時に [!DNL Target] によって挿入される `window.adobeVecExtension` オブジェクトの存在を確認することで、安全に実行できます。

次のコードスニペットは、VEC で web ページが読み込まれない原因となる可能性がある iframe バスティングコードの例です。

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

簡単なチェックを使用して、web ページが [!DNL Target] 内に埋め込まれたタイミングを検証できます。 コードスニペットは次のようになります。

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

### CSS プロパティが続くコンテナの外部に要素を移動することはできません。

+++詳細
CSS プロパティが後に続くコンテナの外に要素を移動することはできません。

+++

### 並べ替える [!UICONTROL Button] 要素は選択できません。

+++詳細
並べ替え用に [!UICONTROL Button] 要素を直接選択することはできません。 並べ替えを有効にするには、大きいコンテナ内にボタンを配置します。

+++

### mbox ではオファーの置き換えのみを使用できる。

+++詳細
[!UICONTROL Edit Class] や [!UICONTROL Rearrange] などのアクションは、mbox 内では使用できません。

+++

### 同じ要素を整列して移動してはならない。

+++詳細
要素を別の場所に移動した場合、親コンテナを選択して子要素を再配置しようとしても、移動した要素は影響を受けず、その場所に残ります。 整列は希望どおりに表示されないことがあります。

+++

### [!UICONTROL Change Image] アクションは、カルーセル内の画像には機能しません。

+++詳細
例えば、ページに 6 つの画像があるカルーセルが含まれており、画像をカルーセルの 2 番目の画像にスワップしたい場合、[!UICONTROL Change Image] のアクションは機能しません。

これを回避するには、親コンテナを選択し、[!UICONTROL Edit HTML] アクションを使用してカルーセルのHTMLを編集し、目的の画像の画像ソースを更新します。

+++

### mbox 内では画像のサイズを変更できない。

+++詳細
mbox 要素内の画像を入れ替え、mbox 要素のサイズに合わせてその画像のサイズを変更しようとすると、サイズ変更は許可されません。

+++

### 画像を入れ替えた後で、[!UICONTROL Edit] のアクションを選択することはできません。

+++詳細
画像を入れ替えた後で、Scene7 の URL を編集することはできません。

+++

### 外部ソースを持つHTML要素は編集できません。

+++詳細
例：ビデオ、オーディオタグ、埋め込み、iFrames、フレーム。

+++

### プレーンテキストまたは画像タグ以外の要素を含むアンカー要素に対してクリック追跡が機能しない。

+++詳細
例えば、要素にJavaScriptが含まれている場合、クリックの追跡は機能しません。

+++

### VEC が機能するには、ページが URL パラメーターを受け入れる必要があります。

+++詳細
一部のサイトは、ページの URL パラメーターを取り除きます。 ただし、VEC にはこれらのパラメーターが必要です。

+++

### スクリプトをHTMLの一部として使用している場合は、外部からアクセスする変数および関数は、window 名前空間で宣言する必要があります。

+++詳細
スクリプトは、ページの読み込み後、`target.js` の範囲内で実行されます。 このため、ローカルに定義された変数や関数は、外部のスクリプトブロックからアクセスできません。

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

### [!UICONTROL Content] ライブラリ（Scene7）から画像を挿入してHTMLを編集すると、画像の URL が壊れます。

+++詳細
ダミーのテキストを使用して、「customHeaderMessage」 div 内にアンカー要素を追加します。

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

[!UICONTROL Insert Element] アクションを使用してこの div を選択し、このダミーテキスト div の兄弟として画像を挿入します。

画像挿入後は、次のようになります。

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

ダミーテキストの span を削除します。

+++

### VEC の `customCode` アクションは [!DNL Internet Explorer] 8 では機能しません。

+++詳細
スクリプトコンテンツを処理する際の IE8 の制限により、`target.js` では IE8 でこれをサポートしていません。 回避策として、ページに jQuery が含まれ、ウィンドウオブジェクトでグローバルに公開されてい `target.js` 場合は、`customCode` アクションの配信を使用できます。 `window.jQuery` と `window.jQuery.fn.prepend` が定義されていることを確認します。

+++

### クリック追跡は、エクスペリエンスが作成されたページまたはリダイレクトされるページでのみサポートされる。

+++詳細
VEC[!UICONTROL Browse] クリックの追跡にはモードが使用できますが、ページにクリックの追跡を追加する [!UICONTROL Browse] はモードを使用できません。

+++
