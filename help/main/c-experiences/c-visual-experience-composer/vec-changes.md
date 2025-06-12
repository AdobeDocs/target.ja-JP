---
keywords: visual experience composer;vec;wysiwyg
description: Adobe Target 25.2.1 リリース（2025 年 2 月 17 日（PT））の Visual Experience Composer （VEC）で導入された変更点について説明します。
title: 新しい Visual Experience Composer （VEC）には、どのような変更が導入されていますか。
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: 3dab3c070eecb415136d880ab1a4326dfe8856d8
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer]の変更点

[!DNL Adobe Target Standard/Premium] 25.2.1 リリース（2015 年 2 月 17 日（PT））では、更新された [!UICONTROL Visual Experience Composer] （VEC）が導入されています。 この記事では、VEC の以前のバージョンと更新されたバージョンの違いについて説明します。

>[!IMPORTANT]
>
>更新された [!UICONTROL Visual Editing Composer] には、[!DNL Chrome Web Store] で使用できる [!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper] 拡張機能 ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) 必要です。

VEC は、既存のアクティビティを作成または編集すると表示されます。

![Visual Experience Composer（VEC）](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## VEC の大幅な変更

以下の節では、以前のバージョンと比較して、更新された VEC の主な変更点について説明します。

### [!UICONTROL Experiences] レール

以前のバージョンと同様に、[!UICONTROL Experiences] レールは VEC の左側に残ります。 [!UICONTROL Experiences] レールを折りたたむことはできません。

![ エクスペリエンスパネル ](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

[!UICONTROL Experiences] パネルを使用して、エクスペリエンスを作成、名前変更または削除できます。 **[!UICONTROL Add]** アイコン（![ 追加アイコン ](/help/main/assets/icons/Add.svg)）をクリックして、新しいエクスペリエンスを追加します。 エクスペリ [!UICONTROL More Actions] ンスを複製、削除、リダイレクトするには、アクショ ](/help/main/assets/icons/MoreSmall.svg) アイコン（その他のアクションアイコン ![）をクリックします。

### [!UICONTROL Components] レール（新規）

Web ページに多数のコンポーネントを追加し、必要に応じて新しい [!UICONTROL Components] パネルを使用して編集できます。

![ コンポーネントパネル ](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

新しいコンポーネントを追加するには、挿入するコンポーネントを [!UICONTROL Components] パネルから [!UICONTROL Design] キャンバス内の既存のページ要素にドラッグします。 次に、を選択して、選択した要素のの前にコンポーネントを挿入します。

以前の VEC バージョンと比較して、選択した要素をコンポーネントで置き換えることはできません。

### [!UICONTROL Modifications] レール

[!UICONTROL Modifications] レールを開くには、[!UICONTROL Components] レールの [!UICONTROL Show Modifications] アイコン（![ 変更レールを表示 ](/help/main/assets/icons/History.svg)）をクリックします。 [!UICONTROL Modifications] レールの位置が、編集キャンバスの右側から左側に変更されました。

![ 変更パネル ](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

[!UICONTROL Modifications] レールには、VEC でページに加えられたすべての変更が表示され、追加の変更（CSS セレクター、mbox、カスタムコードなど）を行うことができます。

[!UICONTROL More Options] のアイコン（その他のアクションアイコン ![）をクリックして ](/help/main/assets/icons/MoreSmall.svg) 変更を追加、すべての変更を削除、またはすべての無効な変更を削除します。 一括操作を実行するには、「[!UICONTROL Select]」をクリックします（[!UICONTROL Apply to All Pages] または [!UICONTROL Delete]）。

[!UICONTROL Modifications] レールを再度表示するには、[!UICONTROL Modifications] レールの [!UICONTROL Hide Modifications] アイコン（![ 変更レールを表示 ](/help/main/assets/icons/History.svg)）をクリックします。

### [!UICONTROL Properties] レール（新規）

[!UICONTROL Properties] パネルを使用すると、ページ上で選択した要素のプロパティを変更できます。これらの要素がHTMLの要素であるか、レコメンデーションやオファーなど、[!DNL Target] ージに固有のオブジェクトであるかに関係なく、プロパティを変更できます。

![ プロパティパネル ](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

パネルの上部にあるアイコンをクリックして、HTML コードを編集したり、要素を削除、複製、非表示にしたりします。 変更が [!UICONTROL Modifications] パネルに表示されます。

![ プロパティアイコン ](/help/main/c-experiences/c-visual-experience-composer/assets/options-icons.png)

[!UICONTROL Properties] パネルは、右側のパネルで折りたたみ可能です。 パネルの右側にある [!UICONTROL Show/Hide Properties] アイコン ![ プロパティアイコン ](/help/main/assets/icons/Propertie.svg)）をクリックして、[!UICONTROL Properties] のパネルを折りたたんだり表示したりします。

### アクティビティの設定/設定

デザインキャンバスの上部に表示されている [!UICONTROL Configure] アイコン ![ 設定アイコン ](/help/main/assets/icons/Setting.svg)）をクリックして、アクティビティのプロパティメニューを表示します。

![ アクティビティ設定オプション ](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

様々なオプションによって、プロパティの割り当て、ページ配信ルールの編集、サイトの環境設定の指定、追加ページの追加、複数ページまたは複数のオーディエンスアクティビティの有効化または無効化を行うことができます。 [!UICONTROL Properties] の割り当ては、[[!DNL Target Premium]](/help/main/c-intro/intro.md#premium) の機能です。

位置と機能は、以前の VEC UI と同様です。

### [!UICONTROL Design]/[!UICONTROL Browse] モード

デザイ [!UICONTROL Properties] レールの上部に表示されている [!UICONTROL Design]/[!UICONTROL Browse] の切り替えを使用して、デザインモードと参照モードを切り替えます。

![ デザインと参照の切り替え ](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

[!UICONTROL Browse] モードを使用してサイトを移動し、更新するビューまたはページを選択します。 [!UICONTROL Design] モードに戻って、変更を追加または編集します。

### [!UICONTROL Undo]／[!UICONTROL Redo]

取り消しアイコン（![ 取り [!UICONTROL Undo] しアイコン ](/help/main/assets/icons/Undo.svg)）をクリックして、加えた変更を取り消すことができます。

![VEC の取り消しアイコン ](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

アクションをやり直すには、「 取り消し/取り [!UICONTROL Redo] し」ボタングループを展開し、「取り [!UICONTROL Redo] し」を選択します。

### [!UICONTROL Design] キャンバス

[!UICONTROL Design] キャンバスでは、画面に合わせる、[!UICONTROL Desktop]、[!UICONTROL Tablet]、[!UICONTROL Mobile Landscape]、[!UICONTROL Mobile Portrait] などのビューポートを選択できます。

![ ビューポート オプション ](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

更新された VEC では、適切なアイコン（![ ズームインアイコン ](/help/main/assets/icons/ZoomIn.svg) または ![ ズームアウトアイコン ](/help/main/assets/icons/ZoomOut.svg)）をクリックして、ズームインまたはズームアウトすることもできます。

## UI の変更を示す視覚的な図

更新された VEC に対して行われた UI の概要を次の図に示します。 上の図は更新された VEC UI を示し、下の図は前の UI を示しています。 矢印は、様々な要素が移動した場所を示します。

（画像をクリックすると、ブラウザーの全幅に展開できます）。

![VEC の比較 – 以前の UI と新しい ](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png){width="600" zoomable="yes"}

## 更新された UI に関する詳細情報

* [[!DNL Target Standard/Premium] 25.2.1 （2025 年 2 月 17 日（PT））リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2):[!UICONTROL Activities]、[!UICONTROL Recommendations] および [!UICONTROL Visual Experience Composer] （VEC）の [!DNL Target] の主な UI の変更点の概要を説明します。

* [[!DNL Target Standard/Premium] 25.1.1 （2025 年 1 月 9 日（PT））リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1):[!UICONTROL Offers Library] の [!DNL Target] での主な UI の変更点の概要を説明します。

* [ [!DNL Target] UI について ](/help/main/c-intro/understand-the-target-ui.md):[!DNL Target] に慣れるのに役立つ概要と、より詳細な情報と手順を説明するリンクを提供します。

* [[!UICONTROL Visual Experience Composer] の変更点 ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1 リリース（2015 年 2 月 17 日（PT））では、更新された [!UICONTROL Visual Experience Composer] （VEC）が導入されています。 この記事では、VEC のレガシーバージョンと更新バージョンの違いについて説明します。

* [[!UICONTROL Visual Experience Composer] options](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：この記事では、更新された VEC UI とそのオプションについて説明します。

* [[!DNL Target] UI 更新 FAQ](/help/main/c-intro/updated-ui-faq.md)：この FAQ は、ナビゲーションの変更、機能の場所、一時的な UI バージョンの切り替えスイッチの廃止など、新しい [!DNL Target] UI と [!UICONTROL Visual Experience Composer] （VEC）に関するよくある質問に対応しています。 マーケター、開発者、管理者を問わず、この FAQ はスムーズに移行し、更新された UI を最大限に活用するのに役立ちます。