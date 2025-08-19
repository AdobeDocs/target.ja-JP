---
keywords: フォームベースの experience composer; フォームベースのコンポーザー; 調整
description: 非視覚的なエクスペリエンスを作成する場合にAdobe [!DNL Target]  フォームベースの Experience Composer を使用する方法を説明します。 このコンポーザーは、VEC が使用できない場合や、実用的でない場合に使用します。
title: フォームベースの Experience Composer の使用方法
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 2f86c9ee89b4e1698180f6b3dc9df393733eb780
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 37%

---

# フォームベースの Experience Composer

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] は、[!UICONTROL A/B Test] （VEC）が使用できない、または使用が実用的でない場合に、[!UICONTROL Experience Targeting]、[!UICONTROL Automated Personalization]、[!UICONTROL Recommendations] および [!UICONTROL Visual Experience Composer] アクティビティで使用するエクスペリエンスを作成するのに便利な、非視覚的なエクスペリエンスおよびオファー作成インターフェイスです。 例えば、フォームベースの Experience Composer を使用して、電子メール、キオスクおよび音声アシスタントで配信するためのエクスペリエンスとオファーを作成できます。

[!UICONTROL Recommendations] アクティビティを作成する場合、エクスペリエンスはありません。 条件およびデザインを選択します。複数の条件またはデザインを選択した場合は、エクスペリエンス [!UICONTROL Target] 自動的に生成されます。

1. 「**[!UICONTROL Create Activity]**」をクリックして、作成するアクティビティのタイプを選択します。

   [!UICONTROL Form-Based Experience Composer] は、[!UICONTROL A/B Test]、[!UICONTROL Experience Targeting]、[!UICONTROL Automated Personalization] および [!UICONTROL Recommendations] の各アクティビティで使用できます。

1. **[!UICONTROL Form]** ダイアログボックスで「[!UICONTROL Create Activity]」を選択します。

1. （条件付き）ワークスペースとプロパティを選択します。

1. **[!UICONTROL Next]** をクリックします。

   [!UICONTROL Form-Based Experience Composer] が開きます。

   ![location_refinements 画像 ](assets/location_refinements.png)

   この画面は、[!UICONTROL Recommendations] しいアクティビティを作成している場合は異なります。 [!UICONTROL Recommendations] アクティビティには、エクスペリエンスは含まれません。

1. 「[!UICONTROL Untitled Activity]」をクリックして、アクティビティに名前を付けます。
1. 場所を選択します。

   [!UICONTROL Select Location] ボックス内をクリックすると、使用可能な場所のリストが表示されます。 これらの場所のいずれかを選択します。

   ここに表示されていない場所を入力することもできます。これは、mbox がまだページで作成または表示されていない場合に便利です。場所の名前を入力します。まだ存在していない場所を入力する場合は、注意が必要です。mbox の呼び出し時に、スペルや大文字／小文字が一致していないと、アクティビティが配信されません。手動で入力した場所は、使用可能な場所のリストに保存されます。 次回、手動で入力した場所を選択しようとすると、そのアクティビティの「[!UICONTROL Select Location]」ドロップダウンリストから使用できるようになります。

   >[!NOTE]
   >
   >アクティビティの作成時に手動で入力した位置を作成しても、新しい位置は自動的には作成されません。 場所の名前は、アクティビティのコンテキストでのみ保存されます。 コンテンツ配信呼び出しがある場合、ロケーションは作成されます。 場所を作成した後は、他のアクティビティやオーディエンスの作成などに使用できるようになります。 使用可能な場所のドロップダウンリストから。

1. 「**[!UICONTROL Add Audience Refinements]**」をクリックし、このアクティビティに 1 つ以上の [ オーディエンス ](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) を選択して、「**[!UICONTROL Done]**」をクリックします。

   ![location_refinements_2 画像 ](assets/location_refinements_2.png)

   [!UICONTROL Form-based Experience Composer] では、絞り込みは、完全なオーディエンス機能に置き換えられました。 既存のアクティビティの絞り込みが、[ アクティビティのみのオーディエンス ](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) に移行されました。

1. その場所に表示するコンテンツのタイプを選択します。

   ![form_content image](assets/form_content.png)

1. 選択したコンテンツタイプに対して、コンテンツを指定します。

   **HTML オファーの変更：** HTML オファーを選択します。

   **画像オファーの変更：** Target のコンテンツライブラリに保存された画像を選択します。

   また、画像にリンク（クリックスルー、宛先、ランディングなど）を追加することもできます。

   1. [!UICONTROL Change Image Offer] をクリックします。
   1. 目的の画像を選択し、「[!UICONTROL Edit Links]」をクリックします。
   1. サイトで目的の URL またはページを指定し、「[!UICONTROL Update]」をクリックします。

   **JSON オファーの変更：** JSON オファーを選択します。

   **エクスペリエンスフラグメントを変更：** エクスペリエンスフラグメントを選択します。 詳しくは、[ エクスペリエンスフラグメント ](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) を参照してください。

   **リダイレクトオファーの変更：** リダイレクトオファーを選択します。 詳しくは、「[ リダイレクトオファーの作成 ](/help/main/c-experiences/c-manage-content/offer-redirect.md) を参照してください。

   **リモートオファーを変更：** リモートオファーを選択します。 詳しくは、[ リモートオファーの作成 ](/help/main/c-experiences/c-manage-content/about-remote-offers.md) を参照してください。

   **HTML オファーを作成:**

   1. 「[!UICONTROL Offers]」をクリックして、「[!UICONTROL Code Offers]」タブを選択します。
   1. [!UICONTROL Create]／[!UICONTROL HTML Offer]をクリックします。
   1. オファー名を入力します。
   1. 「コード」ボックスに HTML コードを入力するか貼り付けます。
   1. [!UICONTROL Save] をクリックします。

   **JSON オファーの作成：**

   1. 「[!UICONTROL Offers]」をクリックして、「[!UICONTROL Code Offers]」タブを選択します。
   1. [!UICONTROL Create]／[!UICONTROL JSON Offer]をクリックします。
   1. オファー名を入力します。
   1. 「コード」ボックスに JSON コードを入力するか貼り付けます。
   1. [!UICONTROL Save] をクリックします。

   **レコメンデーションを追加：**

   Recommendations アクティビティの場合は、「コンテンツ」ドロップダウンに [!UICONTROL Add Recommendation] のオプションが表示されます。 「**[!UICONTROL Add Recommendation]**」をクリックして、ページタイプを選択します。 次に、[Recommendations アクティビティを作成する](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)ためにインターフェイスで定義した通常の手順に従います。

   フォームベースの Experience Composer で Recommendations の条件を選択する際には、選択した条件カードへの直接リンクが追加されるようになったので、条件をすばやく容易に編集できます。

   ![change_criteria 画像 ](assets/change_criteria.png)

   Target の 3 つの手順から成るガイド付きワークフローのターゲット設定ページから：

   ![change_criteria_2 画像 ](assets/change_criteria_2.png)

   **オファーの決定を追加：**

   [!DNL Adobe Journey Optimizer] （AJO）で作成したオファーを [!DNL Adobe Target] アクティビティに追加し、Offer Decisioning を使用して、web サイトまたはモバイルサイト上の訪問者に最適な動的なオファーとエクスペリエンスを提示します。 このオプションは、手動の [!UICONTROL A/B Test] および [!UICONTROL Experience Targeting] （XT）アクティビティでのみ使用できます。

   詳しくは、「[ オファー決定の使用 ](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md) を参照してください。

1. （[!UICONTROL A/B Test]、[!UICONTROL Automated Personalization]、[!UICONTROL Experience Targeting] のアクティビティの場合はオプション）このプロセスをその他の場所に対して繰り返すには、「**[!UICONTROL Add Location]**」をクリックして場所とコンテンツを設定します。
1. 「**[!UICONTROL Next]**」をクリックし、アクティビティタイプに応じて通常どおりにアクティビティ作成手順を完了します。

* [A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [エクスペリエンスのターゲット設定アクティビティの作成](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Recommendations アクティビティの作成](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## トレーニングビデオ：フォームベースの Composer![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオは、フォームベースのコンポーザーのデモを紹介します。

* フォームベースの Experience Composer を使用したアクティビティの作成
* フォームベースの Experience Composer と Visual Experience Composer のどちらを使用するかの理解
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)
