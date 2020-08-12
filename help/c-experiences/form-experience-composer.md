---
keywords: form-based experience composer;form-based composer;refinements
description: フォームベースの Experience Composer は、非視覚的なエクスペリエンス作成機能を提供します。
title: フォームベースの Experience Composer
feature: null
topic: Standard
uuid: 6791ed6f-69d0-4ec4-9ea4-47aa92b2a4c9
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 79%

---


# フォームベースの Experience Composer{#form-based-experience-composer} 

フォームベースの Experience Composer は、Visual Experience Composer が使用できない、または使用が実用的でない場合に、A/B テスト、エクスペリエンスターゲット設定、自動パーソナライゼーション、Recommendations アクティビティで使用するエクスペリエンスを作成するのに便利な、非視覚的なエクスペリエンスおよびオファー作成インターフェイスです。例えば、フォームベースのコンポーザーを使用して、電子メールの配信、キオスクおよび音声アシスタント用のエクスペリエンスおよびオファーを作成できます。

Recommendations アクティビティを作成している場合、エクスペリエンスはありません。条件およびデザインを選択します。複数の条件またはデザインを選択する場合、Target は自動的にエクスペリエンスを生成します。

1. 「**[!UICONTROL アクティビティを作成]**」をクリックして、作成するアクティビティのタイプを選択します。

   フォームベースの Experience Composer は、A/B テスト、エクスペリエンスのターゲット設定、自動パーソナライゼーションおよび Recommendations アクティビティで利用できます。
1. **[!UICONTROL 新しいアクティビティ]**&#x200B;ダイアログボックスで、「[!UICONTROL フォームベースの Experience Composer]」を選択します。

   フォームベースの Experience Composer が表示されます。

   ![](assets/location_refinements.png)

   Recommendations アクティビティを作成している場合、この画面は異なります。Recommendations アクティビティには、エクスペリエンスは含まれません。
1. アクティビティの名前を設定します。
1. 場所を選択します。

   When you click in the [!UICONTROL Select Location] box, a list of available locations appears. いずれかの場所を選択します。target.js によって提供されるグローバルな場所を選択するには、「target-global-mbox」を選択します。

   ここに表示されていない場所を入力することもできます。これは、mbox がまだページで作成または表示されていない場合に便利です。場所の名前を入力します。まだ存在していない場所を入力する場合は、注意が必要です。mbox の呼び出し時に、スペルや大文字／小文字が一致していないと、アクティビティが配信されません。手動で入力した場所は、使用可能な場所のリストに保存されます。 次に手動で入力した場所を選択すると、そのアクティビティの「場所を [!UICONTROL 選択] 」ドロップダウンリストからその場所を使用できます。

   >[!NOTE]
   >
   >アクティビティの作成時に手動で入力した場所を作成しても、新しい場所が自動的に作成されるわけではありません。 場所名は、アクティビティのコンテキストにのみ保存されます。 場所は、コンテンツ配信呼び出しがある場合に作成されます。 作成された場所に続いて、他のアクティビティで使用したり、オーディエンスの作成などに使用したりできます。 」をクリックします。

1. 「**[!UICONTROL 絞り込み条件を追加]**」をクリックし、このアクティビティ用の[オーディエンス](../c-target/target.md#concept_A782F8481A5041EBA75103CB26376522)を 1 つ以上選択します。

   ![](assets/location_refinements_2.png)

   フォームベースの Experience Composer で、絞り込みが完全なオーディエンス機能で置き換えられました。既存のアクティビティの絞り込みが、[アクティビティのみのオーディエンス](../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)に移行されました。
1. その場所に表示するコンテンツのタイプを選択します。

   ![](assets/form_content.png)

1. 選択したコンテンツタイプに対して、コンテンツを指定します。

   **HTML オファーの変更：** HTML オファーを選択します。

   **画像オファーの変更：** Target のコンテンツライブラリに保存された画像を選択します。

   また、画像にリンク（クリックスルー、宛先、ランディングなど）を追加することもできます。

   1. 「[!UICONTROL 画像オファーの変更]」をクリックします。
   1. 希望する画像を選択してから、「[!UICONTROL リンクの編集]」をクリックします。
   1. 希望する URL またはサイトのページを指定して、「[!UICONTROL 更新]」をクリックします。

   **JSON オファーの変更：** JSON オファーを選択します。

   **エクスペリエンスフラグメントの変更：**&#x200B;エクスペリエンスフラグメントを選択します。

   **リダイレクトオファーの変更：**&#x200B;リダイレクトオファーを選択します。

   **リモートオファーの変更：**&#x200B;リモートオファーを選択します。

   **HTML オファーを作成:**

   1. 「[!UICONTROL オファー]」をクリックしてから、「[!UICONTROL コードオファー]」タブを選択します。
   1. [!UICONTROL 作成]／[!UICONTROL HTML オファー]をクリックします。
   1. オファー名を入力します。
   1. 「コード」ボックスに HTML コードを入力するか貼り付けます。
   1. 「[!UICONTROL 保存]」をクリックします。

   **JSON オファーの作成：**

   1. 「[!UICONTROL オファー]」をクリックしてから、「[!UICONTROL コードオファー]」タブを選択します。
   1. [!UICONTROL 作成]／[!UICONTROL JSON オファー]をクリックします。
   1. オファー名を入力します。
   1. 「コード」ボックスに JSON コードを入力するか貼り付けます。
   1. 「[!UICONTROL 保存]」をクリックします。

   Recommendations アクティビティでは、コンテンツドロップダウンに「Recommendation を追加」オプションが表示されます。「**[!UICONTROL Recommendation を追加]**」をクリックして、ページタイプを選択します。次に、[Recommendations アクティビティを作成する](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md)ためにインターフェイスで定義した通常の手順に従います。

   フォームベースの Experience Composer で Recommendations の条件を選択する際には、選択した条件カードへの直接リンクが追加されるようになったので、条件をすばやく容易に編集できます。

   ![](assets/change_criteria.png)

   Target の 3 つの手順から成るガイド付きワークフローのターゲット設定ページから：

   ![](assets/change_criteria_2.png)

1. (Optional, for AB activities, Automated Personalization, and Experience Targeting) To repeat this process for additional locations, click **[!UICONTROL Add Location]** and configure the location and content.
1. Click **[!UICONTROL Next]**, then complete the activity creation steps as usual for your activity type.

* [A/B テストの作成](../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
* [エクスペリエンスのターゲット設定アクティビティの作成](../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Recommendations アクティビティの作成](../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## トレーニングビデオ：フォームベースのコンポーザー ![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオは、フォームベースのコンポーザーのデモを紹介します。

* フォームベースの Experience Composer を使用したアクティビティの作成
* フォームベースの Experience Composer と Visual Experience Composer のどちらを使用するかの理解
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)