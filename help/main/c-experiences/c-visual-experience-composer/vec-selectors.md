---
keywords: エクスペリエンスのターゲット設定;ランディングページテスト
description: 要素セレクターは、1 つ以上の要素を指定できる CSS 式です。 Adobe [!DNL Target] Visual Experience Composer(VEC)。
title: Visual Experience Composer(VEC) で要素セレクターを使用できますか？
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 79%

---

# Visual Experience Composer で使用される要素セレクター

要素セレクターとは、1 つ以上の要素を指定できる CSS 式です。

CSS セレクターの基本的な情報については、Mozilla Developer Network（MDN）にある[セレクター](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors)についてのドキュメントを参照してください。

アカウント設定で、要素クラスを使用するか、または要素 ID を使用するかを設定できます。クリック **[!UICONTROL 管理/Visual Experience Composer]**&#x200B;を選択してから、目的の CSS セレクターを選択します。

![css_selectors 画像](assets/css_selectors.png)

>[!NOTE]
>
>要素クラスは、A/B テスト、Automated Personalizationおよび多変量分析テストアクティビティでセレクターとして使用することができます。

CSS セレクターを使用するタイミングと一意の ID を使用するタイミングについて詳しくは、[Visual Experience Composer のベストプラクティスと制限事項](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#concept_E284B3F704C04406B174D9050A2528A6)を参照してください。

## Adobe [!DNL Target] 要素のセレクターを生成します {#section_D89D954BCBFB486CA081BE183776A475}

Target では、シンプルなアルゴリズムを使用してセレクターが作成されます。以下では、生成のロジックについて簡単に説明します。

1. `id="container"`のように要素に ID がある場合、要素のセレクターは`#container`になります。

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

1. 要素にクラス属性が含まれている場合、Target は要素に存在するすべてのクラスのうち、最初のクラスを利用します。

   Target は、`<HTML>`要素または ID を持つ要素が見つかるまで親要素を分析します。要素に ID が含まれており、セレクターが子孫に対して計算されている場合、この要素の ID がセレクターに使用されます。

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

1. 要素にクラスが含まれていない場合、Target は要素の`tagName`を使用し、`<HTML>`要素または ID を持つ要素が見つかるまで親要素を上にたどります。

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

   詳しくは、[CSS-Tricks Web ページの：nth-of-type についての解説](https://css-tricks.com/almanac/selectors/n/nth-of-type/)を参照してください。

上記のプロセスでは、次の点に注意してください。

* DOM で要素を一意に指定できてさえいれば、任意の CSS セレクターを使用することができます。
* 上記の方法は、いくつかある方法のうち、Target が使用しているものです。必ずこの方法を使用しなければならないわけではありません。1 つ目のポイントが守られていれば、任意のセレクターを追加できます。
* セレクターでは、任意の属性を使用できます。このドキュメントでは、例としてクラス名のみを使用しています。
