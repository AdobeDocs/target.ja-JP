---
keywords: Visual Experience Composer;Visual Experience Composer のベストプラクティス;Visual Experience Composer の制限事項;Visual Experience Composer の注意事項;VEC のベストプラクティス;VEC
description: Adobe Targetで Visual Experience Composer(VEC) を使用する際に、エクスペリエンスを期待どおりに動作させるためのベストプラクティスを説明します。
title: Visual Experience Composer のベストプラクティスと制限事項
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '2395'
ht-degree: 93%

---

# Visual Experience Composer のベストプラクティスと制限事項

以下のベストプラクティスは、エクスペリエンスを期待どおりに動作させるために役立ちます。また、 [!DNL Adobe Target].

これらのベストプラクティスに従うことで、設計したエクスペリエンスで予期しない問題が発生する可能性を低減できます。

## ベストプラクティス {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

**at.js 参照を `<head>` 」セクションに追加します。**

訪問者 API サービスも使用する場合、at.js の上に訪問者 API スクリプトを配置します。

**拡張 Experience Composer は、アカウントレベル（アカウントで作成されるすべてのアクティビティで有効化）または個々のアクティビティレベルにて有効化が可能。**

アカウントレベルで拡張 Experience Composer を有効にするには、 [!UICONTROL 管理/Visual Experience Composer]をクリックし、スイッチをオンの位置に切り替えます。

Visual Experience Composer でアクティビティを作成する際に拡張 Experience Composer をアクティビティレベルで有効にするには、[!UICONTROL 設定／URL] をクリックし、スイッチをオンの位置に切り替えます。

**サイトのセ許可リストキュリティで保護されているページに拡張 Visual Experience Composer が読み込めない場合、特定の IP アドレスをできます。**

拡張 Visual Experience Composer の読み込みの問題は、次の IP アドレスを許可リストに加えるすることで解決できます。 これらの IP アドレスは、拡張 Experience Composer プロキシで使用されるアドビのサーバーのものです。これらは、アクティビティの編集にのみ必要です。サイトの訪問者は、これらの IP アドレスを許可リストに加えるする必要はありません。

米国：52.55.99.45、54.80.158.92 および 54.204.197.253

ヨーロッパ、中東、アフリカ（EMEA）：52.51.238.221、52.210.199.44 および 54.72.56.50

アジア太平洋（APAC）：52.193.67.35、54.199.198.109 および 54.199.241.57

**トップレベルの要素と、適切なテスト／ターゲット候補になりそうなその他の要素に一意の ID を使用する。**

body 要素内に直接配置されるあらゆる要素に一意の ID が必要です。body 内に新しい要素を挿入してコードを移動させる場合は、少なくとも親要素は認識しやすくします。

Adobe Target では ID は必須ではありませんが、ID を使用することによって、Experience Composer で作成するエクスペリエンスの信頼性が向上します。Target は、エクスペリエンスを配信する際に CSS セレクターを利用してコンテンツを変更します。エクスペリエンスを編集する場合、Visual Experience Composer は、変更対象となる HTML 要素に最も近く、ヌル以外の ID 属性を持つ親要素にこのセレクターを関連付けます。そのため、HTML の ID 属性の設定や変更をおこなうメカニズム（JavaScript ライブラリを含む）を使用することはお勧めできません。このようなメカニズムで設定または変更される ID を Target の Experience Composer でアクティビティ作成に使用することもできますが、JavaScript によって ID が変更された場合は、エクスペリエンス作成時に使用されていた ID が、エクスペリエンス実行時に利用できなくなっている可能性があります。ID が利用できない場合、その ID に関連付けられたセレクターは実行に失敗します。

**CSS クラスにわかりやすい名前を付ける。**

Visual Experience Composer で CSS クラスを編集する場合は、わかりやすいクラス名を付けて、簡単にクラスを識別できるようにすると便利です。これにより、確実に正しい CSS クラスを編集して、ページを期待どおりに表示させることができます。

要素を隠すまたは削除する際に、`!important` CSS プロパティを使用しない。

1!important1 CSS プロパティが存在する場合、配信中に target.js によっておこなわれる変更は、サイトの CSS ルールによって無効にされます。

**ページのレイアウトで HTML のテーブルを使用しない。**

Target Standard/Premium は、ページのフォーマットに JavaScript を使用します。テーブルベースのレイアウトを JavaScript で修正するのは困難です。また、テーブルベースのレイアウトは、すべてのブラウザーで同じように表示されない可能性があります。最適な結果を得るには、CSS を使用してページのレイアウトを作成してください。

**iFrame を極力使用しない.**

ページやテストの管理を簡単にするには、iFrame を極力使用しないことをお勧めします。Visual Experience Composer は iFrame 内でいくつかのアクションを適用できますが、サイズ変更などアクションによっては適切に機能しないものもあります。複数の iFrame が使用されているページでは、ページの管理やサイズ変更が難しくなります。そのため、多くの iFrame が使用されているページでは、問題が発生することがあります。

**できるだけ DOM Ready の直後に動的な DOM の変更をすべて整列させる。**

target.js によるエクスペリエンスの適用前に、修正の適用が失敗すると、コンテンツの配信が破損する可能性があります。この問題は、ターゲット要素の階層内に DOM の変更がある場合にのみ発生します。

**アンカー要素内では、プレーンテキストまたは画像タグのみを使用します。**

`<a>Anchor Text</a>`

OR

`<a href=""> <img src=""> </img> </a>`

**インライン要素内では、ブロックレベルの要素を避ける。**

アンカーやスパンなどのインライン要素内でブロックレベルの要素を使用しないでください。インライン要素内でブロックレベルの要素を使用すると、高さと幅が失われ、その結果、Visual Experience Composer のオーバーレイツールが期待どおりに機能しないことがあります。

**Web サイト内で base タグを使用して URL とリンクを解決してはならない。**

Visual Experience Composer は、リンクを更新したプロキシサーバーを使用して Web サイトを背後で操作します。base タグを追加すると、このプロキシサーバーが使用する URL が、ブラウザーによって再度解決され、壊れているように表示されます。

**「HTML を編集」を使用して DOM 構造を操作すると、セレクターが壊れることがある。**

例えば、次の 2 つの操作をおこなったとします。

* クラスに要素 1 を追加
* 要素 1 の HTML を編集

変更をおこなうごとに、Visual Experience Composer で新しい要素が作成されます。2 つ目の操作では、要素 1 を変更しているので、要素 1 を削除すると、2 つ目の操作で変更する対象となる要素がなくなるので、変更が動作しなくなります。

つまり、テキストを持つ要素を追加し、別の操作でその要素を異なるテキストに編集した場合、コードエディターには、両方の操作が別々の要素として表示されます。要素を編集した場合は、作成した元の要素を変更した新しい要素が作成され、その新しい要素に編集したテキストが設定されます。その後、元の要素を削除すると、編集されたテキストは、編集された要素を見付けることができないので、表示されません。2 つ目の要素は要素のリストには引き続き含まれていますが、変更元の要素が存在しなくなっているので、ページ上での効果がなくなります。

[Visual Experience Composer で使用される要素セレクター](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)を参照してください。

**リッチテキストエディターでテキスト要素をスタイル指定する場合、`<b>` および `<i>` タグを使用する。**

* 太字テキストの場合、`<strong>` ではなく、`<b>` を使用します。
* 斜体の場合、`<em>` ではなく、`<i>` を使用します。

`<strong>` および `<em>` タグは、予期しない結果になる可能性があります。

**フォームフィールドの削除は慎重におこなう。**

フォームフィールドによっては送信のために必須のものがあります。そうしたフォームフィールドを削除すると、送信に影響する可能性があります。

**スクリプト内に `mboxCreate` を含めない。**

`mboxCreate` は `document.write` を使用しているので、スクリプトには `mboxCreate` を含めないことをお勧めします。代わりに、`mboxDefine` および `mboxUpdate` を使用して、同じ処理をおこないます。

**Target Standard を使用して html スニペットを更新しない。**

ページのコンポーネント（スライダー、カルーセルなど）でアクション（HTML の編集）がおこなわれると、配信が壊れたように見えることがあります。Visual Experience Composer は、JavaScript がページのコンポーネントをインスタンス化した後にアクションを実行します。

しかし、ページのコンテンツが訪問者に配信される時には、コンポーネントのインスタンス化の前にアクションが適用されます。このため、このコンポーネントの機能が配信の際に壊れたり壊れなかったりします。機能は、コンポーネントを定義するためにページで使用されたスクリプトの性質に依存します。

配信をテストして一度は動作しても、その後も続けて動作するとは限りません。競合条件があることもないこともあります。

* 競合条件がある場合、配信は断続的に動作します。
* 競合条件がない場合、配信は常に動作します。

ページのテストは何度かおこない、期待どおりに配信が動作することを確認してください。

**Web サイト内で base タグを使用して URL やリンクを解決してはならない。**

拡張 Experience Composer を使用すると、プロキシサーバーが Web サイトを舞台裏で操作し、プロキシで動作するようすべての URL を更新します。base タグを追加すると、これらすべての URL がブラウザーによって解決され、壊れているように表示されます。

**ターゲットに使用される可能性のあるサイト上の重要なテキストは、HTML コードの要素内に入れる。**

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

この例では、アンカー要素全体が VEC によって選択され、ターゲットが実行された際に他の要素に悪影響を与えます。

**JavaScript コードでは、`top` または `self` 変数を使用しない。**

拡張 Experience Composer が有効になっていると、top 変数と self 変数の値が更新され、iframe バスティングが無効になります。カスタム JavaScript コードの代わりに、X-frame オプションヘッダーを使用して iframe バスティングを追加してください。

**ページを読み込む際にパラメーターが追加される場合は、必ず Web サイトのテストをおこなう。**

例えば、www.abc.com を開くために、次の URL パラメーターが利用されます。

`www.abc.com?mboxEdit=1&mboxDisable=1`

これらのパラメーターは iframe 内の編集を可能にします。

こういったパラメーターを追加した後は、Web サイトが期待どおりに読み込まれるかどうか確認してください。

**iframe で期待どおりにページが開くかどうかを確認。**

Web サイトの iframe バスティング技法を無効化し、ダミーページの iframe 内で期待どおりに開くかどうかを確認してください。次に例を示します。

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

## 注意事項 {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

Visual Experience Composer を使用してアクティビティを設計するときは、以下の注意事項を検討します。

**移動機能は z- インデックスをサポートしない。**

z- インデックス機能がないので、移動後の要素を別の要素の上に移動することはできません。詳しくは、[制限事項](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)を参照してください。

**要素を整列すると、クリック追跡に影響する。**

クリック追跡用にマークされた要素を整列すると、それらの要素のパスが変更されます。その結果、整列前の要素が配置されていた位置に存在する別の要素が、クリック追跡の対象になります。

これは、アクティビティのコンテンツを配信するコードと、クリックを追跡するコードの両方が、ページに配信される同じコードに含まれているためです。別のページを表示して、クリック追跡を設定すると、アクティビティのコンテンツコードとクリック追跡コードがそのページに配信されます。クリック追跡ページが、テストを実行しているページと同様のページ構造を持っている場合、クリック追跡ページでもテストコンテンツが表示される場合があります。

**mbox の `<div>` 内では要素の挿入ができないことがある。**

mbox がオファーを含む場合、mbox が正しく実装されていないと、要素の挿入が insertAfter ではなく insertBefore として表示される可能性があります。

**親要素と子要素の両方を編集する場合、親を先に編集する。**

要素で画像アクションを交換してから、その親要素でテキストまたは HTML を編集すると、配信で問題が発生する可能性があります。最善のワークフローは、子要素で画像を交換する前に親要素を編集することです。

**mbox を子要素として含むページ要素は選択できない。**

例えば、ページに以下の要素が含まれている場合：

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

このページにハードコードされている mbox は Target への呼び出しをおこなって応答を受け取るので、外側の div をエクスペリエンスで選択してはなりません。この応答は、より大きなページ要素を対象とした応答の妨げになります。

**プロキシ IP が顧客環境でブロックされることがある。**

実稼動環境以外（ステージング環境など）のサイトで拡張 Experience Composer を使用している場合、サイトで RIP をブロックしていると、タイムアウトが発生したり、アクセス拒否エラーが発生したりする場合があります。

**複数のページを追加するときに、エクスペリエンスパネルとページパネルの両方が同時に開くので、最適化のためにサイトを表示する Visual Experience Composer の幅が狭まる。その結果、リフロー可能なサイトが狭いスペース内で予想とは異なるレイアウトで表示される場合がある。**

対応策として、上部の左の山形アイコンをクリックし、エクスペリエンスパネルとページパネルを閉じてください。

## 制限事項 {#section_F33C2EA27F2E417AA036BC199DD6C721}

**移動機能**

CSS プロパティが後に続くコンテナの外側に要素を移動することはできません。

**mbox ではオファーの置き換えのみを使用できる。**

「分類の編集」や「整列」などのアクションは mbox 内では使用できません。

**同じ要素を整列して移動してはならない。**

要素を別の位置に移動した後、親コンテナを選択して子コンテナの整列を試みた場合、その移動した要素は整列しないで、現在の位置に残ります。整列は希望どおりに表示されないことがあります。

**「スワップ画像」アクションはカルーセル内の画像に使用できない。**

例えば、ページに 6 つの画像を持つカルーセルがあり、任意の画像をそのカルーセルの 2 つ目の画像で置き換えたい場合、「スワップ画像」アクションは機能しません。

対応策は、親コンテナを選択し、カルーセルの HTML を編集する「HTML を編集」アクションを使用して、目的の画像の画像ソースを更新することです。

**mbox 内では画像のサイズを変更できない。**

mbox 要素内で画像をスワップした後、mbox 要素のサイズに従ってその画像のサイズを変更しようとしても、サイズ変更は許可されません。

**画像をスワップした後は、「編集」アクションを選択できない。**

画像をスワップした後は、Scene7 の URL を編集できません。

**外部ソースを持つ HTML 要素は編集できない。**

例：ビデオ、オーディオタグ、埋め込み、iFrame、フレーム。

**プレーンテキストまたは画像タグ以外の要素を含むアンカー要素に対してクリック追跡が機能しない。**

例えば、要素に JavaScript が含まれている場合、クリック追跡は機能しません。

**Visual Experience Composer を動作させるには、ページで URL パラメーターを受け入れる必要がある。**

一部のサイトは、ページの URL パラメーターを除去します。ただし、Visual Experience Composer にはこれらのパラメーターが必要です。

**html の一部にスクリプトを使用する場合、外部からアクセスされる変数や関数は window 名前空間の下に定義する。**

スクリプトは、ページが読み込まれた後 target.js のスコープ内で実行されます。このため、ローカルに定義された変数や関数は、外部のスクリプトブロックからアクセスできません。

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

**コンテンツライブラリ（Scene7）から画像を挿入し HTML を編集すると画像 URL が壊れる。**

「customHeaderMessage」 div 内に、任意のダミーテキストの入ったアンカー要素を追加します。

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

「要素を挿入」アクションを使ってこの div を選択し、このダミーテキスト div の兄弟として画像を挿入します。 

画像挿入後は、次のようになります。

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

ダミーテキストの span を削除します。

**Visual Experience Composer 内の customCode アクションが Internet Explorer 8 で動作しない。**

IE 8 のスクリプト内容の処理における制限のため、target.js は IE 8 でこれをサポートしません。対応策としては、ページが jQuery を含み、window オブジェクトでグローバルに提示されている場合、target.js は customCode アクションを使用、配信できます。window.jQuery と window.jQuery.fn.prepend が定義されていることを確認します。

**クリック追跡は、エクスペリエンスが作成されたページまたはリダイレクトされるページでのみサポートされる。**

クリック追跡 VEC では参照モードが使えますが、ページにクリック追跡を追加するために使用することはできません。