---
keywords: エクスペリエンスのターゲット設定;ランディングページテスト
description: 要素セレクターは、1 つ以上の要素を識別できる CSS 式です。 Adobe [!DNL Target] Visual Experience Composer （VEC）で要素セレクターを使用する方法を説明します。
title: Visual Experience Composer （VEC）で要素セレクターを使用できますか？
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
source-git-commit: 51e484d54f4d318ea59fdfdb16d1ed7014abdfdb
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 31%

---

# Visual Experience Composer で使用される要素セレクター

要素セレクターは、1 つ以上の要素を識別できる CSS 式です。

CSS セレクターに関する基本的な情報については、[&#x200B; （MDN）の &#x200B;](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) セレクター *[!DNL Mozilla Developer Network]* ドキュメントを参照してください。

アカウント設定で、要素クラスを使用するか、または要素 ID を使用するかを設定できます。「**[!UICONTROL Administration > Visual Experience Composer]**」をクリックして、優先 CSS セレクターを選択します。

* **要素 ID を使用**：同じ ID が複数の要素に使用されている場合、またはページ読み込み時に要素 ID が変更される可能性がある場合は、無効にします。
* **要素クラスを使用**：ページ上の要素クラスが変更される可能性がある場合は無効にします。
* **優先セレクターを使用**:VEC で一意のセレクターを使用して、web サイトの主要な領域を識別する場合に有効にします。

>[!NOTE]
>
>要素クラスは、[!UICONTROL A/B Test]、[!UICONTROL Automated Personalization]、[!UICONTROL &#x200B; Multivariate Test] の各アクティビティでセレクターとして使用することができます。

CSS セレクターを使用するタイミングと一意の ID を使用するタイミングについて詳しくは、[Visual Experience Composer のベストプラクティスと制限事項](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#concept_E284B3F704C04406B174D9050A2528A6)を参照してください。

## 要素 [!DNL Target] セレクターを生成する方法 {#section_D89D954BCBFB486CA081BE183776A475}

[!DNL Target] では、単純なアルゴリズムを使用してセレクターを作成します。 次に、生成ロジックについて簡単に説明します。

1. 要素に ID がある場合（例：`id="container"`）、その要素のセレクターは `#container` になります。

   例：

   ```html
   <div class="wrapper">
     <div id="container"> <!-- Selector is computed for this element -->
       <ul class="navigation">
         <li class="item active"> Home </li>
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

1. 要素に class 属性が含まれている場合、[!DNL Target] は要素に存在する任意のクラスの最初のクラスの活用を試みます。

   [!DNL Target] は、`<HTML>` 要素または ID を持つ要素が見つかるまで、親要素の解析を試みます。 要素に ID が含まれ、その下位子でセレクターが計算されると、この要素の ID がセレクターに提供されます。

   次に例を示します。

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li class="item active"> Home </li> <!-- Selector is computed for this element -->
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

   この例では、次のようになります。

   セレクター：`#container` > `ul.navigation:eq(0)` > `li.item:eq(0)`（「>」は直接の子を示します。）

   `eq` は、UL タグで、最初のクラスが `navigation` の要素のインデックスを示しています。したがって、`index`は 0 になります。詳しくは、MDN の[セレクター](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors)についての記事を参照してください。

1. 要素にクラスが含まれていない場合、[!DNL Target] は要素に `tagName` を使用し、`<HTML>` 要素または ID を持つ要素が見つかるまで、親要素を走査します。

   次に例を示します。

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li> Home </li>
         <li> Men </li>
         <li class="active"> Women </li>
         <li> Kids </li><!-- Selector is computed for this element -->
       </ul>
     </div>
   </div>
   ```

   セレクター：`#container` > `ul.navigation(0)` > `li:nth-of-type(4)`

上記のプロセスでは、次の点に注意してください。

* DOM で要素を一意に指定できてさえいれば、任意の CSS セレクターを使用することができます。
* 上記のアプローチは、[!DNL Target] で使用されるアプローチです。 [!DNL Target] では、この方法を使用する必要はありません。 1 つ目のポイントが守られていれば、任意のセレクターを追加できます。
* セレクターでは、任意の属性を使用できます。このドキュメントでは、例としてクラス名のみを使用しています。
