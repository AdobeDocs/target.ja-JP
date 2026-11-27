---
keywords: エクスペリエンスのターゲット設定;ランディングページテスト
description: 要素セレクターは、1つ以上の要素を識別できるCSS式です。 Adobe [!DNL Target] Visual Experience Composer （VEC）でエレメントセレクターを使用する方法を説明します。
title: Visual Experience Composer （VEC）でエレメントセレクターを使用できますか？
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
TQID: 'https://experienceleague.adobe.com/sqvUyLFddt7HPHH62jwpOZmwTIMSg-hyLIUr8w-x7vg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 4%
---
# [!UICONTROL Visual Experience Composer]で使用されている要素セレクター {#vec-selectors}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、[!UICONTROL Visual Experience Composer] （VEC）での要素セレクターの動作、使用するセレクターの選択方法、[!DNL Target]が要素のセレクターを生成する方法について説明します。

>[!ENDSHADEBOX]

要素セレクターは、1つ以上の要素を識別できるCSS式です。 CSS セレクターに関する基本的な情報は、*[!DNL Mozilla Developer Network]* （MDN）の[&#x200B; セレクター](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) ドキュメントで入手できます。

エレメントのクラスまたはエレメント IDを使用するかどうかが、アカウントの環境設定で設定されます。 「**[!UICONTROL 管理]**」 > 「**[!UICONTROL Visual Experience Composer]**」をクリックし、次に優先するCSS セレクターを選択します。

* **[!UICONTROL 要素IDを使用]**：同じIDが複数の要素に使用されている場合や、ページ読み込み時に要素IDが変更される可能性がある場合は、無効にします。
* **[!UICONTROL 要素クラスを使用]**: ページ上の要素クラスが変更される可能性がある場合は無効にします。
* **[!UICONTROL 優先セレクターを使用]**: VECで一意のセレクターを使用して、web サイトの主要な領域を識別できるようにします。

>[!NOTE]
>
>Element クラスは、**[!UICONTROL A/B テスト]**、**[!UICONTROL Automated Personalization]**、**[!UICONTROL 多変量テスト]**&#x200B;の各アクティビティでセレクターとして使用できます。

CSS セレクターを使用するタイミングと一意のIDを使用するタイミングについて詳しくは、[Visual Experience Composerのベストプラクティスと制限事項](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#vec-best-practices)を参照してください。

## [!DNL Target]が要素のセレクターを生成する方法 {#generate-selector}

[!DNL Target]は、簡単なアルゴリズムを使用してセレクターを作成します。 生成ロジックは次のとおりです。

1. 要素にID （例：`id="container"`）がある場合、要素のセレクターは`#container`です。

   次に例を示します。

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

1. 要素にクラス属性が含まれている場合、[!DNL Target]は、要素に存在するクラスの最初のクラスを使用しようとします。

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

   この例では、セレクターは`#container` > `ul.navigation:eq(0)` > `li.item:eq(0)`です（「>」は直近の子を示します）。

   `eq`は、「tagName=UL」と最初のクラス `navigation`を持つ要素のインデックスを与えます。 したがって、`index`は 0 になります。 詳しくは、MDN の[セレクター](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors)についての記事を参照してください。

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

   セレクターは`#container` > `ul.navigation:eq(0)` > `li:nth-of-type(4)`です。

このプロセスでは：

* DOM内の要素を一意に識別できる限り、任意のCSS セレクターを使用できます。
* 上記の方法は、[!DNL Target]が使用する方法です。 [!DNL Target]はこのアプローチを強制しません。 要素を一意に識別できる限り、任意のセレクターを追加できます。
* 任意の属性をセレクターで使用できます。 この記事では、クラス名のみを例として使用します。
