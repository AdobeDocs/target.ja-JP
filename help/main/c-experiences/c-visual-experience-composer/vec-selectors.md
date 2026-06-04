---
keywords: エクスペリエンスのターゲット設定;ランディングページテスト
description: 要素セレクターは、1つ以上の要素を識別できるCSS式です。 Adobe [!DNL Target] Visual Experience Composer （VEC）でエレメントセレクターを使用する方法を説明します。
title: Visual Experience Composer （VEC）でエレメントセレクターを使用できますか？
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
TQID: https://experienceleague.adobe.com/sqvUyLFddt7HPHH62jwpOZmwTIMSg-hyLIUr8w-x7vg
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 29%

---

# Visual Experience Composer で使用される要素セレクター

要素セレクターは、1つ以上の要素を識別できるCSS式です。

CSS セレクターに関する基本的な情報は、*[!DNL Mozilla Developer Network]* （MDN）の[ セレクター](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) ドキュメントにあります。

アカウント設定で、要素クラスを使用するか、または要素 ID を使用するかを設定できます。 **[!UICONTROL 管理 / Visual Experience Composer]**&#x200B;をクリックし、任意のCSS セレクターを選択します。

* **要素IDを使用**：同じIDが複数の要素に使用されている場合や、ページ読み込み時に要素IDが変更される場合は、無効にします。
* **要素クラスを使用**: ページ上の要素クラスが変更される可能性がある場合は無効にします。
* **優先セレクターを使用**: VECで一意のセレクターを使用して、web サイトの主要な領域を識別する場合に有効にします。

>[!NOTE]
>
>エレメントクラスは、[!UICONTROL A/B テスト ]、[!UICONTROL Automated Personalization]、[!UICONTROL 多変量テスト ]のアクティビティでセレクターとして使用できます。

CSS セレクターを使用するタイミングと一意の ID を使用するタイミングについて詳しくは、[Visual Experience Composer のベストプラクティスと制限事項](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#concept_E284B3F704C04406B174D9050A2528A6)を参照してください。

## [!DNL Target]が要素のセレクターを生成する方法 {#section_D89D954BCBFB486CA081BE183776A475}

[!DNL Target]は、簡単なアルゴリズムを使用してセレクターを作成します。 生成ロジックの簡単な説明を次に示します。

1. 要素にID （例：`id="container"`）がある場合、要素のセレクターは`#container`です。

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

1. 要素にクラス属性が含まれている場合、[!DNL Target]は、要素に存在するクラスの最初のクラスを活用しようとします。

   [!DNL Target]は、`<HTML>`要素またはIDを持つ要素が見つかるまで、親要素を解析しようとします。 要素にIDが含まれ、その子の子孫でセレクターが計算されるたびに、この要素のIDがセレクターに寄与します。

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

   `eq` は、UL タグで、最初のクラスが `navigation` の要素のインデックスを示しています。 したがって、`index`は 0 になります。 詳しくは、MDN の[セレクター](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors)についての記事を参照してください。

1. 要素にクラスが含まれていない場合、[!DNL Target]は要素に`tagName`を使用し、`<HTML>`要素またはIDを持つ要素のいずれかが見つかるまで親要素を上に移動します。

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
* 上記の方法は、[!DNL Target]が使用する方法です。 [!DNL Target]では、このアプローチを使用する必要はありません。 1 つ目のポイントが守られていれば、任意のセレクターを追加できます。
* セレクターでは、任意の属性を使用できます。 このドキュメントでは、クラス名のみを例として使用します。
