---
description: Visual Experience Composer（VEC）は、エクスペリエンスターゲット設定（XT）アクティビティでページ上のエクスペリエンスを編集するための視覚的なインターフェイスです。
keywords: エクスペリエンスの作成;エクスペリエンス作成;優先度;オーディエンス;エクスペリエンス;Visual Experience Composer
seo-description: Adobe Target Visual Experience Composer（VEC）は、エクスペリエンスターゲット設定（XT）アクティビティでページ上のエクスペリエンスを編集するための視覚的なインターフェイスです。
seo-title: エクスペリエンスを作成
solution: 'Target '
title: エクスペリエンスを作成
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 6911a91aba8505e8f91a7ab9723c54bd8e7082b7

---


# Create experience{#create-experience}

[!UICONTROL Visual Experience Composer] （VEC）は [!UICONTROL 、エクスペリエンスターゲット設定] （XT）アクティビティでページ上のエクスペリエンスを編集するための視覚的なインターフェイスです。

1. 変更する要素を選択し、必要な変更をおこないます。

   While [creating an XT activity](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), step one of the three-part guided workflow ([!UICONTROL Experiences]) displays the default [!UICONTROL Experience A] with an [!UICONTROL All Visitors] audience.

   ![すべての訪問者オーディエンス](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Any changes you make now apply to Experience A. In a step below, you'll click **[!UICONTROL Add Experience Targeting]** to create additional experiences.

   ページ上の要素にマウスカーソルを重ねると、その要素が強調表示されます。ハイライトされている要素は、VECを使用して変更できます。For a list of actions that can be performed on an element to change the experience, see [Visual Experience Composer Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   If you created an mbox on the page using [!DNL Target Classic], that mbox appears as an element that shows the mbox name, and can be modified like any other element.

   >[!NOTE]
   >
   >デフォルトでは、バナーの回転などJavaScriptを含む要素に対する変更は許可されません。JavaScriptを無効にして、VECを使用してこれらのエレメントを変更することができます。

1. To create additional experiences, click **[!UICONTROL Add Experience Targeting]**.

   ![エクスペリエンスターゲット設定のリンクの追加](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   The [!UICONTROL Choose Audience] dialog box displays. オーディエンスにエクスペリエンスをターゲット設定するには、エクスペリエンスを追加する前にオーディエンスを選択する必要があります。

   The audience library contains audiences that have previously been defined, including some common audiences that are pre-built as a part of [!DNL Target]. You can select an audience from the library or [create a new audience](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   >[!NOTE]
   >
   >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

   オーディエンスの作成時に、場所（mbox）を選択して、その場所のパラメーターを指定できます。[!UICONTROL 「カスタム] （オーディエンスを作成/ルールを追加/カスタム）」で、mboxを選択し、目的のパラメーターを指定します。

   >[!NOTE]
   >
   >オーディエンスリストを開いたときに、インポートされたオーディエンスが 10 分以上経っている場合は、オーディエンスがバックグラウンドで自動的にインポートされます。

1. Select one or more audiences to target with the experience, then click **[!UICONTROL Done]**.

   ![エクスペリエンス B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   エクスペリエンスBが前の図に表示され、このエクスペリエンスが米国の訪問者のオーディエンスをターゲットにしていることがわかります。

1. このエクスペリエンスに変更する要素を選択し、上記の手順1で説明した変更を行います。

1. 上記の手順を繰り返して、必要に応じてターゲット設定したエクスペリエンスを追加します。

1. Click **[!UICONTROL Next]** when you are finished designing your experiences.

   アクティビティ図が表示されます。

   ![XTターゲティング図](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >If you deliver an image from a source other than your main page (such as an image hosted on `akamai.net` and delivered on `adobe.com`), that image does not display in the thumbnail of the page shown in the flow diagram.

1. （オプション） XTアクティビティを作成または編集中にオーディエンス/エクスペリエンスのペアをドラッグ&amp;ドロップして、ペアを目的の順序で並べ替えます。

   訪問者は、上から下に順にエクスペリエンスの評価を行います。

   ![エクスペリエンスの移動](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL エクスペリエンスのターゲット設定では、この順番が重要です。]訪問者が最初のオーディエンス／エクスペリエンスのペアに該当する場合は、その最初のエクスペリエンスが配信されます。

   例えば、順番が重要であることを知らずに、XT アクティビティを作成したとします。その場合、エクスペリエンス B または C の条件に該当すると思っていた訪問者が、エクスペリエンス A に該当することになっていることに後で気が付くことがあります。こうした問題が生じるのは、各オーディエンスが相互に排他的ではなく、適切な順番になっていないことが原因です。例えば、エクスペリエンス A が米国、エクスペリエンス B がサンフランシスコ、エクスペリエンス C がカリフォルニアになっているとします。この例では、米国のユーザーは、サンフランシスコ在住でもカリフォルニアの他の地域在住でも、すべてエクスペリエンス A に該当することになります。オーディエンス／エクスペリエンスのペアは、アクティビティ全体を作り直さなくても、条件が狭い方から順に並べ替えることができます（この例では、サンフランシスコ &gt; カリフォルニア &gt; 米国）。

   [!UICONTROL すべての訪問者] のオーディエンスがある場合は、図の最初のオーディエンスではないことを確認してください。ターゲット設定アクティビティで最後のエクスペリエンスとして「すべての訪問者」をターゲットに設定しているエクスペリエンスを使用すると、他のどのエクスペリエンスにも該当しない訪問者を「捕捉」することができます。

## エクスペリエンスの名前変更または編集

You can click the [!UICONTROL Edit] icon (three vertical ellipses) on an experience in an XT activity and choose from the following options, as necessary:

* 名前変更
* 編集

![名前変更および編集オプション](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## エクスペリエンスの削除

**[!UICONTROL エクスペリエンス]** ページ（3ステップガイドのワークフローの最初の手順）で、3つの垂直方向の楕円/ **[!UICONTROL 削除をクリック]**&#x200B;します。

![エクスペリエンスの削除](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## エクスペリエンスの複製

エクスペリエンスをXTアクティビティでコピーすると、エクスペリエンスをゼロから再作成することなく、わずかな変更を加えることができます。

**[!UICONTROL エクスペリエンス]**&#x200B;ページ（3 ステップのガイドによるワークフローの最初の手順）で、縦並びの省略記号／**[!UICONTROL 複製]**&#x200B;をクリックします。

![エクスペリエンスの複製](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## トレーニングビデオ：

以下のビデオは、この記事で説明する概念についてさらに詳しく説明しています。

### A/B テストからエクスペリエンスのターゲット設定へ

このビデオでは、エクスペリエンスのターゲット設定（XT）で A/B テストを次の段階に進める方法について説明します。

* XT アクティビティを設定するための、3 つの手順から成るガイド付きのワークフローを説明します。
* 場所に特有のコンテンツを様々な地域のオーディエンスに配信する方法を説明します。
* 適確なコンテンツが適切なオーディエンスに配信されるように、エクスペリエンスを並べ替える方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/22418/?captions=jpn)

### アクティビティのタイプ（9:03）

このビデオでは、Target Standard／Premium で利用できるアクティビティのタイプについて説明しています。エクスペリエンスのターゲット設定に関する説明は、5:15 から始まります。

* [!DNL Adobe Target] に含まれるアクティビティのタイプの説明
* 目標達成に適したアクティビティのタイプの選択
* すべてのアクティビティのタイプに適用される 3 ステップのガイドによるワークフローについての説明

>[!VIDEO](https://video.tv.adobe.com/v/17386?captions=jpn)

### Visual Experience Composerの使用

このビデオでは、Visual Experience Composer のオプションの使用に関する情報を提供しています。

* ページのコンテンツの変更
* ページのレイアウトの変更

>[!VIDEO](https://video.tv.adobe.com/v/17399?captions=jpn)