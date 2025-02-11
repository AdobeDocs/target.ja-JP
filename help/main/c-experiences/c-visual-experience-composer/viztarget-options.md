---
keywords: visual experience composer オプション；experience composer オプション；experience options；テキストの編集；html の編集；テキストまたは html の編集；背景色の編集；要素の挿入；リンクの編集；visual experience composer リンク；css クラスの編集；オファーの交換；画像の交換；画像の交換；項目の削除；項目の非表示；項目の非表示；項目の並べ替え；要素の移動；要素のサイズ変更；要素の拡大；選択；移動；移動；リンク；元ににする；やり直す；やりす/やりす；カスタムイベント；web コンポーネント；オファー決定；offer decisioning
description: ' [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）で利用できるオプションを確認します。'
title: '[!UICONTROL Visual Experience Composer] （VEC）オプションの使用方法？'
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: 457b02cb3cbaeee8ad9b56844891dd7e9f6f2d86
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 14%

---

# Visual Experience Composer のオプション

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）でページ要素をクリックすると、その要素タイプで使用できるオプションがメニューに表示されます。 さらに、ページの下部に DOM パスが表示されるので、ページ構造内を簡単に移動できます

>[!NOTE]
>
>[!DNL Target Standard/Premium] 25.2.1 （2025 年 2 月 11 日（PT））リリースには、VEC の更新バージョンが含まれています。 更新された VEC が以前のバージョンとどのように異なるかについて詳しくは、[Visual Experience Composer の変更点 ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md) を参照してください。


様々な [!UICONTROL Visual Experience Composer] （VEC）アクションが適切なメニューオプションにグループ化され、ジョブの迅速化と効率化を実現します。

![VEC オプションメニュー](/help/main/c-experiences/c-visual-experience-composer/assets/vec-options.png)

>[!NOTE]
>
>使用できるオプションは、作成または編集しているアクティビティタイプおよび要素によって異なります。 次の節では、画像とテキストの様々なオプションについて説明します。

## 画像オプション

[!UICONTROL A/B Test] アクティビティの画像をクリックすると、VEC は次の図のようになります。

![ 画像を選択した VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-image.png)

左側のコンポーネント フレームからコンポーネントを選択して、次の要素を挿入します。

* 基本（ディバイダー、HTML、画像）。
* テキスト（見出し、段落、リンク）。
* 動的（[ レコメンデーション ](/help/main/c-recommendations/recommendations-as-an-offer.md)、[ エクスペリエンスフラグメント ](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)、HTMLオファー）。

画像上部のメニューでは、次の操作を実行できます。

* リンクを挿入します（![ リンクを挿入アイコン ](/help/main/assets/icons/Link.svg)）。
* 画像を変更します（![ 画像アイコンを選択 ](/help/main/assets/icons/Images.svg)）。
* パーソナライゼーションを追加（![Personalizationを追加アイコン ](/help/main/assets/icons/PersonalizationField.svg)）。
* 画像を削除します（![ 削除アイコン ](/help/main/assets/icons/Delete.svg)）。

右側のフレームを使用すると、画像のプロパティをさらに設定できます。

フレームの上部にあるアイコンを使用すると、次の操作を実行できます。

* HTMLを編集します（![HTMLを挿入アイコン ](/help/main/assets/icons/Code.svg)）。 詳しくは、以下の [HTMLを編集 ](#html) を参照してください。
* 画像を複製します（![ 複製アイコン ](/help/main/assets/icons/Code.svg)）。
* 画像を削除します（![ 削除アイコン ](/help/main/assets/icons/Delete.svg)）。
* 画像を非表示にします（![ 非表示アイコン ](/help/main/assets/icons/VisibilityOff.svg)）。

右側のフレームのオプションを使用すると、次の操作を実行できます。

* CSS クラスを編集します。
* 画像のプロパティ（ソース、タイトル、代替テキスト）を設定します。
* リンク URL を編集します。
* 画像のサイズ（高さと幅）を設定します。 「[!UICONTROL Show Advanced Options]」をクリックして、画像の最小および最大サイズ、幅、高さ、オーバーフロー、オブジェクトのフィットを設定します。
* ページ上の画像の位置（絶対パス、固定パス、相対パス、静的パス、スティッキーの各パス）を設定します。
* 余白やパディングを含む、要素の間隔を設定します。
* 要素の効果（不透明度）を設定します。 「[!UICONTROL Show Advanced Options]」をクリックして、画像のセピア、グレースケール、コントラスト、明るさ、ブラーの値を設定します。 また、画像を反転または回転させることもできます。
* 画像のインラインスタイルを設定します。

## テキストオプション

[!UICONTROL A/B Test] アクティビティでテキストをクリックすると、VEC は次の図のようになります。

![ テキストを選択した VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-text.png)

左側の [!UICONTROL Components] フレームからコンポーネントを選択して、次の要素を挿入します。

* 基本（ディバイダー、HTML、画像）。
* テキスト（見出し、段落、リンク）。
* 動的（[ レコメンデーション ](/help/main/c-recommendations/recommendations-as-an-offer.md)、[ エクスペリエンスフラグメント ](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)、HTMLオファー）。

[!UICONTROL Show Modifications] アイコン（![ 変更を表示アイコン ](/help/main/assets/icons/History.svg)）をクリックして、エクスペリエンスの変更を表示します。

テキスト要素の上部にあるメニューを使用すると、次の操作を実行できます。

* テキストのプロパティ（見出しレベル、段落、ブロック引用、等幅）を設定する
* テキストのカラーを選択します（![ テキストカラーアイコン ](/help/main/assets/icons/TextColor.svg)）
* テキストの属性（太字、斜体、下線、取り消し線）を設定します（![ テキスト属性を選択アイコン ](/help/main/assets/icons/Text.svg)）。
* テキストの整列（左、中央、右、両端揃え）（![ テキストの整列アイコン ](/help/main/assets/icons/TextAlignCenter.svg)）を設定します。
* リンクを挿入します（![ リンクを挿入アイコン ](/help/main/assets/icons/Link.svg)）。
* コンテンツをHTMLオファー、[ エクスペリエンスフラグメント ](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) または [Recommendation]/help/main/c-recommendations/recommendations-as-an-offer.md）に置き換えます。
* HTMLを編集します（![HTMLを挿入アイコン ](/help/main/assets/icons/Code.svg)）。
* パーソナライゼーションを追加（![Personalizationを追加アイコン ](/help/main/assets/icons/PersonalizationField.svg)）。
* 画像を削除します（![ 削除アイコン ](/help/main/assets/icons/Delete.svg)）。

右側のフレームを使用すると、テキストのプロパティをさらに設定できます。

フレームの上部にあるアイコンを使用すると、次の操作を実行できます。

* HTMLを編集します（![HTMLを挿入アイコン ](/help/main/assets/icons/Code.svg)）。 詳しくは、以下の [HTMLを編集 ](#html) を参照してください。
* テキストを複製します（![ 複製アイコン ](/help/main/assets/icons/Code.svg)）。
* テキストを削除します ![ 削除アイコン ](/help/main/assets/icons/Delete.svg)）。
* テキストを非表示にします（![ 非表示アイコン ](/help/main/assets/icons/VisibilityOff.svg)）。

右側のフレームのオプションを使用すると、次の操作を実行できます。

* CSS クラスを編集します。
* テキストの背景色と画像を設定します。
* テキストのタイポグラフィ（見出しスタイル、フォントサイズ、フォントの太さ、行の高さ、配置、テキストカラー、テキストスタイル（太字、斜体、下線、取り消し線））を設定します。
* 箇条書き、番号付き、A、B、C などのリストを設定します。
* 境界線のカラーを選択します。
* テキストボックスのサイズ（高さと幅）を設定します。 テキスト ボックスの最小サイズ、最大サイズ、幅、高さ、オーバーフロー、およびオブジェクトの自動調整を設定するには、[[!UICONTROL Show Advanced Options]] をクリックします。
* ページ上のテキストボックスの位置（絶対、固定、相対、静的、固定）を設定し、上、右、下、左からのピクセル数を設定します。
* 余白やパディングを含む、要素の間隔を設定します。
* 要素の効果（不透明度）を設定します。 「[!UICONTROL Show Advanced Options]」をクリックして、画像のセピア、グレースケール、コントラスト、明るさ、ブラーの値を設定します。 テキストを反転または回転することもできます。
* インラインスタイルを設定します。

## HTMLを編集 {#html}

HTML コードだけでなく、カスタム JavaScript を編集および挿入することもできます。

[!UICONTROL A/B] アクティビティと [!UICONTROL Experience Targeting] アクティビティでテキストとHTMLを編集する場合は、いくつかのリッチテキスト書式設定オプションを使用できます。 フォントの選択、フォントスタイルの選択、テキストの整列方法の変更およびその他の標準的なテキスト書式オプションの設定が可能です。HTMLを変更する際に、HTMLのコードビューとリッチ編集ビューを切り替えることができます。

次の HTML5 タグをネストできます。

| タグ | ネスト可能なタグ |
| --- | --- |
| `<a>` | `<h1-h6>`、`<p>`、`<ul>`、`<ol>`、`<menu>`、`<div>`、`<figure>`、`<figcaption>` |
| `<ins>` | `<h1-h6>`、`<p>`、`<ul>`、`<ol>`、`<menu>` |
| `<del>` | `<ul>`、`<ol>`、`<menu>`、`<h1-h6>`、`<p>` |
| `<label>` | `<p>` |

## DOM パスを使用して要素をナビゲートする {#dom-path}

ページで要素をクリックすると、VEC オプションメニューが表示されます。さらに、要素をクリックすると、対応する DOM パスがページの下部に表示されます。

![DOM パス](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path-refresh.png)

DOM パスが表示されていない場合は、[!UICONTROL Show DOM] アイコン（![DOM アイコンを表示 ](/help/main/assets/icons/LayersBringToFront.svg)）をクリックします。

DOM パスを使用すると、選択した要素に関する情報（タイプ、ID、クラス）をすばやく確認したり、DOM パスを上下に移動して目的の要素を選択したりできます。

<!--When you hover over the DOM path, a blue box highlights the corresponding element in the VEC. When you click the element, an orange box highlights the element and the VEC options menu displays, as explained above.-->

DOM パスを使用すれば、VEC 内で任意の親要素、兄弟要素、子要素に容易に移動できます。

DOM パス機能は、[クリックの追跡](/help/main/c-activities/r-success-metrics/click-tracking.md)を設定するときにも使用できます。

<!--## [!UICONTROL Edit]

The following options are available:

### [!UICONTROL Text/HTML] {#edit-text-html}

Change the HTML code for the element, such as the text for a text area, button, or link.

In addition to HTML code, you can edit and inject custom JavaScript.

Several rich text formatting options are available when editing text and HTML for [!UICONTROL A/B] and [!UICONTROL Experience Targeting] activities. You can choose a font, select a font style, change text alignment, and other standard text formatting options. When modifying HTML, you can toggle between the code view and rich-editing view of the HTML.

The following HTML5 tags can be nested:

|Tag|Allowed Nested Tags|
| --- | --- |
|`<a>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>`|
|`<ins>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`|
|`<del>`|`<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>`|
|`<label>`|`<p>`|

### [!UICONTROL Background Color]

Use the color picker to select or configure a background color. You can select a color swatch, and adjust it using RGB values or color hex codes. The red x in the color picker makes the background transparent.

**Note:** This option is not available for an element where a background image is set. 

### [!UICONTROL Styles] {#styles}

Use the [!UICONTROL Styles] panel to view or edit the value of existing styles for the selected element. You can also add additional styling.

To access the [!UICONTROL Styles] panel, click a page element from within the VEC, then click **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

The [!UICONTROL Styles] panel displays on the right side of the VEC. The panel contains a list of styles that lets you edit or add to the selected element. A real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

![Styles panel](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

As you apply different styles, you can always revert your changes by clicking the [!UICONTROL Revert] icon that displays at the top-right corner of the [!UICONTROL Styles] panel after you change any section. Clicking the [!UICONTROL Revert] icon reverts all changes on the current section's panel.

Expand each section to edit or add styles, as explained below. To save your changes, click the [!UICONTROL Back] icon at the top of the panel to return to the panel's main display, then click **[!UICONTROL Save]**. 

Blue dots on the main panel and next to each option on the various section panels indicate that you have changed the corresponding styles. This visual indicator makes it easy for you to review your changes before clicking [!UICONTROL Save].

>[!NOTE]
>
>Quick actions for layout changes, background color, resizing, and move are also available as separate actions in the VEC menu. These options can be used as separate actions or you can use the Styles menu, as explained here.

* **[!UICONTROL Background]**

  Change the background color and image.

  * Color (specify the color code or use the color picker)
  * Image (select an image from the image picker)
  * Image source (specify an external URL)
  * Attachment
    * Click the top drop-down list to select scroll, fixed, or local
    * Click the bottom drop-down list to select repeat, repeat-x, repeat-y, no-repeat, space, or round
  * Clip
    * Click the top drop-down list to select border-box, padding-box, content-box, or text
    * Click the bottom drop-down list to select auto audio or audio

* **[!UICONTROL Typography]**

  Change the typography of an element. Typography edits are quick and easy. 

  Although the rich text editor (Edit Text/HTML) is available for fine tuning, quick actions to change the entire element is available via this option. If you want to apply typography changes to only a part of the text (not to the full text), use the [rich text editor](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md). 

  You can edit the following typography styles:

  * [!UICONTROL Font size]
  * [!UICONTROL Font weight]
  * [!UICONTROL Font style]
  * [!UICONTROL Color] (specify the color code or use the color picker)
  * [!UICONTROL Word spacing]
  * [!UICONTROL Line height]
  * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  Change the margin for the selected element. You can change the left, right, bottom, and top margins.

  Click the drop-down icon for each margin to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to set the margin or specify the number of pixels for each margin)

  Margin supports positive and negative values.

  Target also supports other size units, such as rem, pc, em. For more information about these units, see [Web Style Sheets CSS Tips and Tricks](https://www.w3.org/Style/Examples/007/units.en.html).

* **[!UICONTROL Padding]**

  Change the padding for the selected element. You can change the left, right, bottom, and top padding.

  Drag the slider to set the padding or specify the number of pixels for padding.

  Padding supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Border]**

  Click the border icons at the top of the panel to change the selected element's border.

  You can edit the following styles for each border (top, right, bottom, and left):

  * [!UICONTROL Border style] (none, hidden, dotted, dashed, solid, or double)
  * [!UICONTROL Border color] (specify the color code or use the color picker)
  * [!UICONTROL Border width] (drag the slider to select a border width or specify the width in pixels)

  Border supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Position]**

  Move the selected element from its current position. You can change the element's top, bottom, left, right, and [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) position.

  Click the [!UICONTROL Static] drop-down list to choose from the following position options:

  * [!UICONTROL Static]
  * [!UICONTROL Relative]
  * [!UICONTROL Absolute]
  * [!UICONTROL Sticky]
  * [!UICONTROL Fixed]

  Click the drop-down icon for each position to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to position the element or specify the number of pixels you want to move the element)

  Position supports positive and negative values.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Size]**

  Change the selected element's width and height.

  Click the drop-down icon next to [!UICONTROL Width] and [!UICONTROL Height] to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to size the element or specify the number of pixels for each dimension)

* **[!UICONTROL Filter]**

  Drag the slider for each filter option or specify the desired percentage:

  * [!UICONTROL Sepia]
  * [!UICONTROL Contrast]
  * [!UICONTROL Brightness]
  * [!UICONTROL GrayScale]
  * [!UICONTROL Blur]
  * [!UICONTROL Opacity]
  * [!UICONTROL Invert]
  *[!UICONTROL  Hue-rotate]
  * [!UICONTROL Saturate]

* **[!UICONTROL CSS Editor]**

  The real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

  The CSS Editor displays any changes that you make in the Styles panel. As shown in the illustration below, the font size, top border, and image size have been changed:

  ![CSS editor with changes](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  Notice the blue dots next to the [!UICONTROL Typography], [!UICONTROL Border], and [!UICONTROL Size] options in the preceding illustration. These dots indicate that you have changed these sections. If you open these section panels, blue dots display next to the specific options that you changed.

  You can type your own code if your desired style is not available by default in the [!UICONTROL Styles].

  The CSS Editor shows details for the current session only. If you save changes and then reopen the editor, details about your previous change do not display in the editor, even if you select the same element again.

  >[!IMPORTANT]
  >
  >You can apply a background image using the CSS Editor, but it might cause flicker. Test your changes before deployment.

### [!UICONTROL CSS Class]

Specify the predefined CSS class used for the element. If more than one element is selected, separate multiple CSS classes with a space.

Available for [!UICONTROL A/B], [!UICONTROL Automated Personalization], and [!UICONTROL Multivariate Test] activities.

### [!UICONTROL Link]

Change the URL in the link.

Use Edit Link to update the selector to point to the same image element. However, linking to a different image element is not supported. To link to a different image element, delete the original action from the code editor and use the [!UICONTROL Visual Experience Composer] to apply the action on the other image element.

## [!UICONTROL Insert Before]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML], and [!UICONTROL Text]

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert Before] and choose whether you want to insert an image, HTML, or text. The inserted element appears before the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert Before] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Insert After]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML], and [!UICONTROL Text]

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert After] and choose whether you want to insert an image, HTML, or text. The inserted element appears after the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert After] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Replace Content]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image]

Select a different image from the Content Library. The images available for swapping include the images uploaded to the Experience Cloud assets folder or uploaded in the Content Library in Target.

During initial activity creation, the URL displayed is not the URL used for delivery. Upon activity synching, that URL is updated to a production Scene7 URL.

For example, the initial URL might look like the following example:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

After activity syncing, the delivery URL might look like the following example:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations supports Replace With in DIV, SECTION, and ARTICLE tags.

**Note:** Swapping images requires an Adobe Scene7 Publishing System Account.

### [!UICONTROL HTML Offer]

Select a different offer from the [!UICONTROL Content Library].

**Note:** HTML Offers are stored on [!DNL Target] servers.

An HTML offer can be up to 256 KB.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Layout]

The following options are available:

### [!UICONTROL Rearrange]

Drag the element to another location inside the same parent element or DIV. Other elements shift location to make space for the rearranged element.

**Note**: Click-tracking does not work on rearranged items.

Currently, certain VEC actions, such as [!UICONTROL Rearrange] and [!UICONTROL Move], assume that the sibling elements of the source and destination parent elements are completely loaded. If lazy loading occurs under the parent DOM elements (source or destination), these VEC actions can cause inconsistent behavior. We are working on a more reliable approach to make VEC actions work in lazy-loaded DOM elements. As a temporary workaround, you can use [!UICONTROL Custom Code] in these scenarios to render your experiences.

### [!UICONTROL Resize]

Resize an element on your page. When you select [!UICONTROL Resize], a handle appears in the bottom-right corner of the element that lets you drag that corner to resize. Hold the Shift key to retain the same aspect ratio.

**Note:** Inline elements cannot be resized.

### [!UICONTROL Move] {#move}

Move elements on your page. Unlike the [!UICONTROL Rearrange] option, [!UICONTROL Move] does not shift other elements to make room for the element being moved. Use the arrow keys to fine tune the move. (Planned enhancement: support to ensure moved elements are not hidden behind other elements.)

In certain situations, such as when a CSS restriction requires an element to remain inside its parent element, you cannot move the element outside its parent. An element cannot be moved outside of a container that has following CSS property: `overflow: hidden`.

See [!UICONTROL Rearrange] above for more information about inconsistent behavior with the [!UICONTROL Move] and [!UICONTROL Rearrange] actions due to lazy loading of DOM elements.

### [!UICONTROL Hide]

Hide the element. The white space remains, but the content is removed.

### [!UICONTROL Remove]

Remove the element. The white space behind the image is removed and the space where the element was is collapsed.

**Note:** Items within a "classic" mbox (an mbox created within a Target Classic campaign) cannot be removed using this option.

## [!UICONTROL Expand Section]

Select the parent element in addition to the originally selected element. When you select any parent element, all children of that element are automatically selected. You can expand the selection multiple times.

## [!UICONTROL Navigate to Link]

Open the destination of the link.

## [!UICONTROL Undo]/[!UICONTROL Redo]

Undo changes you make to your activities during an editing session. You can also redo changes that have been previously undone.

## Considerations {#considerations}

* If an offer contains HTML content, see "How at.js renders offers with HTML content" in [How at.js works](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank} for more information.

## Custom element support {#custom}

The VEC supports [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) to let you create and test personalized experiences and offers on custom elements and on elements inside custom elements. This functionality is available in the VEC for all [!DNL Target] activity types.

>[!NOTE]
>
>VEC support for custom elements is supported in [at.js version](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} 2.7.0 (or later){target=_blank}. Ensure that your website has the required version deployed. If you are using the [Visual Experience Composer helper extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), it must also have the required version of at.js deployed. The VEC options described above are not visible and available for use with non-supported versions of at.js.
>
>VEC support for custom elements is currently not supported with the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

Most VEC actions are supported on custom events and inside custom events, with the following exceptions: 

The following actions are not available on custom elements:

* [!UICONTROL Edit]
  * [!UICONTROL Text/HTML]
  * [!UICONTROL Link]
  * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

The following action is not available inside custom elements:

* [!UICONTROL Layout]
  * [!UICONTROL Rearrange]-->
