---
keywords: レコメンデーション
description: Visual Experience Composer （VEC）でページに加えられた変更が、Adobe Targetのエクスペリエンス表示機能にどのような影響を与えるかを示す一般的なシナリオを確認します。
title: 一般的なページ変更のシナリオ？
feature: Visual Experience Composer (VEC)
exl-id: 7a05fbf9-3427-436e-a54f-4f1dd16d885a
TQID: 'https://experienceleague.adobe.com/BI2SnUU5ilCf0auld15q1rpCrnLoPEwbe1fZO6G1quc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 4%
---
# ページ修正のシナリオ {#vec-scenarios}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、[!DNL Target]以外のページに対して行われた変更が、7つのシナリオと例を通じて[!DNL Target]のエクスペリエンス表示機能にどのように影響するかを説明します。

>[!ENDSHADEBOX]

[!DNL Target] セレクターは、エクスペリエンスの表示場所を決定します。 ページが[!DNL Target]以外で変更された場合、変更内容は[!DNL Target]がその場所を検索してエクスペリエンスを表示する機能に影響を与える可能性があります。

セレクターは常に、IDと同等ではない一意のクラスで動作します。 要素にクラスが割り当てられていない場合、セレクターは同じタグ名を持つ前の兄弟をカウントします。

>[!NOTE]
>
>シナリオでは、リスト項目を例として使用しますが、概念はあらゆる要素に適用されます。

シナリオの概要を次の表に示します。 どのシナリオでも、セレクターは`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`です。

| シナリオ | アクションが適用されました | 理由 |
|---|---|---|
| 選択した要素の前に、別のクラス名を持つ要素を挿入します | はい | `li.women-section:eq(0)`には影響がありません |
| 選択したエレメントと同じクラス名を持つエレメントの挿入 | いいえ | 新しい要素が最初の位置を取り、セレクターが壊れます |
| 選択したエレメントの後にエレメントを挿入 | はい | 新しいエレメントは、親エレメントと同じ位置に追加されます |
| 選択した要素の直前の要素を削除します | はい | 選択した項目のクラスは変更されません |
| 選択したエレメントのすぐ後のエレメントを削除します | はい | 選択した項目のクラスは変更されません |
| 選択した要素を削除 | はい | 要素が正常に削除されました |
| 選択した要素のクラスの名前を変更 | いいえ | `class`が見つかりません |

## 選択した要素の前に、別のクラス名を持つ要素を挿入します

新しい要素が[!DNL Target] セレクターの要素の兄弟として挿入されます。 エレメントクラスの最初のクラスがJavaScriptによって追加された場合、配信は失敗し、アクションは適用されません。

**挿入する要素：**

```html
<li class="kids-section">Kids</li>
```

**選択した要素：**

`<li class="women-section">Women</li>`

**セレクター：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：** `li.women-section:eq(0)`は影響を受けないため、セレクターは期待どおりに機能します。

**前：**

```html
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul>
</div>
```

**後：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul>
</div>
```

## 選択したエレメントと同じクラス名を持つエレメントの挿入

リストのアイテムが選択されている間に、リストが挿入されます。

**挿入する要素：**

```html
<ul class="nav">
   <li class="item"> Sale </li>
   <li class="item"> Offers </li>
</ul>
```

**選択した要素：**

`<li class="women-section">Women</li>`

**セレクター：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：** セレクターが機能しません。 `ul.nav:eq(0)`は、使用できない動的に追加された要素を指すため、アクションは適用されません。 アクティビティの作成後、同じクラスを持つ類似のリスト項目を動的または手動で追加すると、最初の位置に新しい要素が追加され、セレクターが壊れます。

**前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul>
</div>
```

**後（試行）:**

```html
<div id="wrap">
     <ul class="nav">
        <li class="item"> Sale</li>
        <li> class="item"> Offers</li>
     </ul>
     <ul class="nav">
       <li class="men-section"> Men</li>
       <li class="women-section">Women</li>
    </ul>
</div>
```

## 選択したエレメントの後にエレメントを挿入

選択したリスト項目の後にリストが挿入されます。

**挿入する要素：**

```html
<ul class="nav">
   <li class="men-section"> Men Clothes</li>
   <li class="women-section"> Women Clothes</li>
</ul>
```

**選択した要素：**

`<li class="women-section">Women Shoes</li>`

**セレクター：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**&#x200B;選択した項目で終わるリストの後にリストを挿入すると、期待どおりに動作します。 新しいエレメントは、選択したエレメントと同じ位置で、親エレメントに対して相対的に追加されます。

**前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men Shoes </li>       <li class="women-section">Women Shoes</li>
    </ul>
</div>
```

**後：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men Shoes </li>
        <li class="women-section">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## 選択した要素の直前の要素を削除します

選択した要素の前のリスト項目が削除されます。

**削除する要素：**

```html
<li class="men-section"> Men </li>
```

**選択した要素：**

`<li class="women-section">Women</li>`

**セレクター：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**&#x200B;選択した項目のクラスが変更されていないため、要素は正常に削除されました。

**前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**後：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## 選択したエレメントのすぐ後のエレメントを削除します

選択した要素の後のリスト項目が削除されます。

**削除する要素：**

```html
<li class="kids-section">Kids</li>
```

**選択した要素：**

`<li class="women-section">Women</li>`

**セレクター：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**&#x200B;選択した項目のクラスが変更されておらず、削除された要素の親サブツリー内に一意のクラスが含まれているため、要素は正常に削除されます。

**前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Kids</li>
    </ul>
</div>
```

**後：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## 選択した要素を削除

選択したリスト項目が削除されます。

**削除する要素：**

```html
<li class="women-section">Women</li>
```

**選択した要素：**

`<li class="women-section">Women</li>`

**セレクター：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**&#x200B;要素は正常に削除されました。

**前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**後：**

```html
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## 選択した要素のクラスの名前を変更

選択したリスト項目のクラスが変更されます。

**変更する要素：**

```html
<li class="women-section">Women</li>
```

**選択した要素：**

`<li class="women-section">Women</li>`

**セレクター：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：** `class`が見つからないため、クラスの名前を変更できません。

**前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**後（試行）:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div> 
```
