---
keywords: visual experience composer;vec;wysiwyg
description: Adobe Target 25.2.1 リリース（2025年2月17日（PT））のVisual Experience Composer （VEC）で導入された変更点について説明します。
title: 新しいVisual Experience Composer （VEC）にはどのような変更が加えられましたか？
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
TQID: https://experienceleague.adobe.com/PZaKHKs1-GPnR1U-E0d3YQVNWhinmt9ctjOSnIbNrE0
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 884
ht-degree: 17%

---

# [!UICONTROL Visual Experience Composer]の変更点

[!DNL Adobe Target Standard/Premium] 25.2.1 リリース（2015年2月17日（PT））では、更新された[!UICONTROL Visual Experience Composer] （VEC）が導入されています。 この記事では、VECの以前のバージョンと更新されたバージョンの違いについて説明します。

>[!IMPORTANT]
>
>更新された[!UICONTROL Visual Editing Composer]には、[!DNL Chrome Web Store]で利用できる[!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper]拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)が必要です。

VECは、既存のアクティビティを作成または編集するときに表示されます。

![Visual Experience Composer（VEC）](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## VECの主な変更点

以下の節では、更新されたVECの主な変更点を以前のバージョンと比較して説明します。

### [!UICONTROL Experiences] パネル

以前のバージョンと同様に、[!UICONTROL Experiences] レールはVECの左側に残ります。 [!UICONTROL Experiences] レールを折りたたむことはできません。

![ エクスペリエンス パネル ](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

[!UICONTROL Experiences] パネルを使用して、エクスペリエンスを作成、名前変更または削除できます。 **[!UICONTROL Add]** アイコン（![ アイコンを追加](/help/main/assets/icons/Add.svg)）をクリックして、新しいエクスペリエンスを追加します。 [!UICONTROL More Actions] アイコン（![詳細アクションアイコン ](/help/main/assets/icons/MoreSmall.svg)）をクリックして、エクスペリエンスを複製、削除、またはリダイレクトします。

### [!UICONTROL Components] パネル （新規）

新しい[!UICONTROL Components] パネルを使用して、web ページに多数のコンポーネントを追加し、必要に応じて編集できます。

![ コンポーネントパネル ](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

新しいコンポーネントを追加するには、[!UICONTROL Components] パネルから目的のコンポーネントを選択し、ページ内の既存の要素にカーソルを合わせ、選択した要素の前にの後にコンポーネントを挿入するように選択します。

>[!NOTE]
>
>[!UICONTROL Components] パネルではなく[!UICONTROL Modifications] パネルがこの領域に表示されている場合は、**[!UICONTROL Show Components]** アイコン （![ コンポーネントを表示アイコン ](/help/main/assets/icons/Add.svg)）をクリックします。 [!UICONTROL Show Components] アイコン （![ コンポーネントを表示アイコン ](/help/main/assets/icons/Add.svg)）と[!UICONTROL Show Modifications] アイコン （![変更を表示パネル ](/help/main/assets/icons/History.svg)）は、適切なオプションを表示するための切り替えスイッチとして機能します。
>
>[!UICONTROL Components] パネルを折りたたんで[!UICONTROL Design] キャンバスを拡大し、[!UICONTROL Components] パネルを開いている間に、（![ コンポーネントを表示アイコン ](/help/main/assets/icons/Add.svg)）アイコンをクリックします。

### [!UICONTROL Modifications] パネル

[!UICONTROL Modifications] パネルを開くには、[!UICONTROL Components] パネルの[!UICONTROL Show Modifications] アイコン（![変更パネルを表示](/help/main/assets/icons/History.svg)）をクリックします。 [!UICONTROL Modifications] パネルの位置が、編集キャンバスの右側から左側に変更されました。

![変更パネル ](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

>[!NOTE]
>
>[!UICONTROL Show Components] アイコン （![ コンポーネントを表示アイコン ](/help/main/assets/icons/Add.svg)）と[!UICONTROL Show Modifications] アイコン （![変更を表示パネル ](/help/main/assets/icons/History.svg)）は、適切なオプションを表示するための切り替えスイッチとして機能します。
>
>[!UICONTROL Modifications] パネルを折りたたんで[!UICONTROL Design] キャンバスを拡大し、[!UICONTROL Modifications] パネルを開いている間に、[!UICONTROL Show Modifications] アイコン （![変更パネルを表示](/help/main/assets/icons/History.svg)）をクリックします。

[!UICONTROL Modifications] パネルには、VECでページに加えられたすべての変更が表示され、追加の変更（CSS セレクター、Mbox、カスタムコードなど）を行うことができます。

[!UICONTROL More Options] アイコン（![その他のアクション アイコン ](/help/main/assets/icons/MoreSmall.svg)）をクリックして、変更を追加するか、すべての変更を削除するか、無効なすべての変更を削除します。 [!UICONTROL Select]をクリックして一括操作を実行します：[!UICONTROL Apply to All Pages]または[!UICONTROL Delete]。

[!UICONTROL Modifications] パネルをもう一度表示するには、[!UICONTROL Modifications] パネルの[!UICONTROL Hide Modifications] アイコン（![変更パネルを表示](/help/main/assets/icons/History.svg)）をクリックします。

### [!UICONTROL Properties] パネル （新規）

[!UICONTROL Properties] パネルを使用すると、選択した要素がHTMLの要素であるか、レコメンデーションやオファーなど、[!DNL Target]に固有のオブジェクトであるかを問わず、ページ上の選択した要素のプロパティを変更できます。

![ プロパティ パネル ](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

パネルの上部にあるアイコンをクリックして、HTML コードを編集したり、エレメントを削除、複製、非表示にしたりできます。 変更が[!UICONTROL Modifications] パネルに表示されます。

![ プロパティアイコン ](/help/main/c-experiences/c-visual-experience-composer/assets/options-icons.png)

[!UICONTROL Properties] パネルは、右側のパネルで折りたたむことができます。 パネルの右側にある[!UICONTROL Show/Hide Properties] アイコン（![ プロパティアイコン ](/help/main/assets/icons/Propertie.svg)）をクリックして、[!UICONTROL Properties] パネルを折りたたんだり表示したりします。

### アクティビティ設定/設定

デザインキャンバスの上に表示されている[!UICONTROL Configure] アイコン（![設定アイコン ](/help/main/assets/icons/Setting.svg)）をクリックして、アクティビティプロパティメニューを表示します。

![ アクティビティ設定オプション ](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

様々なオプションを使用すると、プロパティの割り当て、ページ配信ルールの編集、サイトの環境設定の指定、追加ページの追加、複数ページまたは複数のオーディエンスアクティビティの有効化または無効化を行うことができます。 割り当て[!UICONTROL Properties]は[[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)機能です。

位置と機能は、以前のVEC UIと似ています。

### [!UICONTROL Design]/[!UICONTROL Browse] モード

[!UICONTROL Properties] パネルの上に表示される[!UICONTROL Design]/[!UICONTROL Browse]の切り替えスイッチを使用して、デザイン モードと参照モードを切り替えます。

![ デザインと参照の切り替え](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

[!UICONTROL Browse] モードを使用してサイトを移動し、更新するビューまたはページを選択します。 変更を追加または編集するには、[!UICONTROL Design] モードに切り替えます。

### [!UICONTROL Undo]／[!UICONTROL Redo]

[!UICONTROL Undo] アイコン（![取り消しアイコン ](/help/main/assets/icons/Undo.svg)）をクリックして行った変更を取り消すことができます。

VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)の![取り消しアイコン

アクションをやり直すには、取り消し/[!UICONTROL Redo] ボタン グループを展開し、[!UICONTROL Redo]を選択します。

### [!UICONTROL Design]個のキャンバス

[!UICONTROL Design] キャンバスを使用すると、画面に合うビューポート、[!UICONTROL Desktop]、[!UICONTROL Tablet]、[!UICONTROL Mobile Landscape]および[!UICONTROL Mobile Portrait]を含むビューポートを選択できます。

![ ビューポートオプション ](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

更新されたVECでは、適切なアイコン（![ ズームインアイコン ](/help/main/assets/icons/ZoomIn.svg)または![ ズームアウトアイコン ](/help/main/assets/icons/ZoomOut.svg)）をクリックしてズームインまたはズームアウトすることもできます。

## UIの変更を示すビジュアルイラスト

次の図は、更新されたVECに対して行われた高レベル UIの変更を示しています。 図の上部には更新されたVEC UIが表示され、下部には前のUIが表示されます。 矢印はさまざまな要素が移動した場所を示しています。

（画像をクリックして、ブラウザーの全幅に展開します）。

![VECの比較 – 前のUI](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png){width="600" zoomable="yes"}に新しく追加

## 更新された UI に関する詳細情報

* [[!DNL Target Standard/Premium]  25.2.1（2025年2月17日（PT））リリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：[!UICONTROL Activities]、[!UICONTROL Recommendations]、[!UICONTROL Visual Experience Composer]（VEC）の [!DNL Target] での主な UI の変更の概要について説明します。

* [[!DNL Target Standard/Premium]  25.1.1（2025年1月9日（PT））リリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：[!UICONTROL Offers Library] の [!DNL Target] での主な UI の変更の概要について説明します。

* [ [!DNL Target]  UI ](/help/main/c-intro/understand-the-target-ui.md)について：[!DNL Target] に慣れるための概要と、より詳細な情報と手順を説明するリンクを提供します。

* [[!UICONTROL Visual Experience Composer] の変更](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)：[!DNL Adobe Target Standard/Premium] 25.2.1 リリース（2025年2月17日（PT））では、更新された [!UICONTROL Visual Experience Composer]（VEC）が導入されています。 この記事では、VEC のレガシーバージョンと更新されたバージョンの違いについて説明します。

* [[!UICONTROL Visual Experience Composer] オプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：この記事では、更新された VEC UI とそのオプションについて説明します。

* [[!DNL Target] UI の更新に関する FAQ](/help/main/c-intro/updated-ui-faq.md)：この FAQ では、ナビゲーションの変更、機能の場所、一時的な UI バージョンの切替スイッチの非推奨（廃止予定）など、新しい [!DNL Target] UI と [!UICONTROL Visual Experience Composer]（VEC）に関するよくある質問について説明します。 マーケター、開発者、管理者のいずれであっても、この FAQ はスムーズに移行し、更新された UI を最大限に活用するのに役立ちます。