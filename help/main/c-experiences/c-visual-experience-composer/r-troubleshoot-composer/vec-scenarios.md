---
keywords: レコメンデーション
description: Visual Experience Composer （VEC）でページに加えられた変更が、エクスペリエンスを表示するAdobe Targetの機能に与える影響を示す一般的なシナリオについて説明します。
title: 一般的なページ修正シナリオを教えてください。
feature: Visual Experience Composer (VEC)
exl-id: 7a05fbf9-3427-436e-a54f-4f1dd16d885a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 90%

---

# ページ修正のシナリオ

このトピックのシナリオでは、ページに加えられた変更が、Adobe Targetのエクスペリエンス表示機能にどのような影響を与えるかを示します。

Target セレクターは、エクスペリエンスを表示する位置を決定します。ページが Target 外で修正されると、Target のエクスペリエンス表示機能に影響することがあります。

セレクターを使用する場合、一意のクラスと ID は同じ意味になりません。セレクターは常に一意のクラスを使用します。要素にクラスが割り当てられていない場合、セレクターは、同じタグ名を持つ以前の兄弟の数を計算します。

>[!NOTE]
>
>ここで説明するシナリオでは、例としてリスト項目を使用していますが、同じ概念があらゆる要素に適用されます。

## シナリオ：選択された要素の前に、別のクラス名を持つ要素を挿入する {#section_298F661F72384F6AB957D5885A99D822}

この例では、Target セレクターの要素の兄弟として、新しい要素を挿入します。

この要素の最初のクラスは JavaScript で追加できる場合があります。その場合、配信は失敗し、アクションは適用されません。

**挿入する要素：**

```html
<li class="kids-section">Kids</li>
```

**選択される要素：**

`<li class="women-section">Women</li>`

セレクター：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**

`li.women-section:eq(0)`は影響を受けないので、セレクターは意図したとおりに機能します。

変更前：

```html
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul> 
</div>
```

変更後：

```html
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

## シナリオ：選択された要素と同じクラス名の要素を挿入する {#section_0969B88C2F154E648D9969C8C85EF55A}

このシナリオでは、リスト項目が選択されたときに、リストの挿入を試みます。

**挿入する要素：**

```html
<ul class="nav"> 
   <li class="item"> Sale </li> 
   <li> class="item"> Offers </li> 
</ul>
```

**選択**

`<li class="women-section">Women</li>`

セレクター：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**

`ul.nav:eq(0)`は動的に追加される要素を提供するので、セレクターは機能しません。要素は使用できず、アクションは適用されません。アクティビティの作成後に、同じクラスの同様のリスト項目が動的または手動で追加されると、最初の位置の新しい要素が作成されます。これによりセレクターが破損します。

変更前：

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

変更後（試行済み）：

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

## シナリオ：選択された要素の後に要素を挿入する {#section_15B07B84BEE94ED39D85BBBE0733E170}

このシナリオでは、選択された要素の後にリスト項目を挿入します。

**挿入する要素：**

```html
<ul class="nav"> 
   <li class="men-section"> Men Clothes</li> 
   <li class="women-section"> Women Clothes</li> 
</ul>
```

**選択される要素：**

`<li class="women-section">Women Shoes</li>`

セレクター：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**

このケースでは、リスト項目が選択されたリストの末尾にリストが正しく挿入されます。新しい要素は、親要素から見て、選択された要素と同じ位置に追加されます。

変更前：

```html
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>       <li class="women">Women Shoes</li>
    </ul>
</div>
```

変更後：

```html
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>
        <li class="women">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## シナリオ：ある要素の直前の要素を削除する {#section_F193674F04F84AA593EAA1137C880EBA}

このシナリオでは、選択された要素の前にあるリスト項目を削除します。

**削除する要素：**

```html
<li class="men-section"> Men </li>
```

**選択される要素：**

`<li class="women-section">Women</li>`

セレクター：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**

選択された項目のクラスは変更されないので、要素は正常に削除されます。

変更前：

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

変更後：

```html
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## シナリオ：ある要素の直後の要素を削除する {#section_F83B51BE54924FB58679D512DAF1EBB2}

このシナリオでは、選択された要素の後にあるリスト項目を削除します。

**削除する要素：**

```html
<li class="kids-section">Kids</li>
```

**選択される要素：**

`<li class="women-section">Women</li>`

セレクター：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**

選択された項目のクラスは変更されないので、要素は正常に削除されます。削除される要素の親サブツリー内には一意のクラスが含まれます。

変更前：

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Women</li>
    </ul>
</div>
```

変更後：

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## シナリオ：選択された要素を削除する {#section_1989CF1E2C344CC5963084ED83C18F9C}

このシナリオでは、選択されたリスト項目を削除します。

**削除する要素：**

```html
<li class="women-shoes">Women</li>
```

**選択される要素：**

`<li class="women-shoes">Women</li>`

セレクター：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**

要素は正常に削除されます。

変更前：

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```

変更後 

```html
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## シナリオ：選択された要素のクラスの名前を変更する {#section_79D244C588BA452DB8E433D82B7F63EA}

このシナリオでは、選択されたリスト項目のクラスを変更します。

**変更する要素：**

```html
<li class="women-section">Women</li>
```

**選択される要素：**

`<li class="women-section">Women</li>`

セレクター：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**

`class` が見つからないので、要素クラスの名前を変更できません。

変更前：

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

変更後（試行済み）：

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```
