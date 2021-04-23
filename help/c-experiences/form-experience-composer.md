---
keywords: フォームベースの experience composer; フォームベースのコンポーザー; 調整
description: Adobe [!DNL Target] フォームベースのExperience Composerを使用して、非視覚的なエクスペリエンスを作成する方法を学びます。 VECが使用できない場合、または実用的でない場合は、このコンポーザーを使用します。
title: フォームベースのExperience Composerの使用方法を教えてください。
feature: フォームベースの Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 66%

---

# フォームベースの Experience Composer

[!DNL Adobe Target] [!UICONTROL フォームベースのExperience Composer]は、ビジュアルエクスペリエンスが使用できない場合、または実用的でない場合に、A/Bテスト、Experience Targeting、Automated Personalization、Recommendationsの各アクティビティで使用するエクスペリエンスを作成するのに役立つ、非ビジュアルなエクスペリエンスおよびオファー作成インターフェイスです。 例えば、フォームベースのコンポーザーを使用して、電子メールの配信、キオスクおよび音声アシスタント用のエクスペリエンスおよびオファーを作成できます。

Recommendations アクティビティを作成している場合、エクスペリエンスはありません。条件およびデザインを選択します。複数の条件またはデザインを選択する場合、Target は自動的にエクスペリエンスを生成します。

1. 「**[!UICONTROL アクティビティを作成]**」をクリックして、作成するアクティビティのタイプを選択します。

   フォームベースの Experience Composer は、A/B テスト、エクスペリエンスのターゲット設定、自動パーソナライゼーションおよび Recommendations アクティビティで利用できます。
1. [!UICONTROL アクティビティを作成]ダイアログボックスから「**[!UICONTROL フォームベースのExperience Composer]**」を選択します。

1. （条件付き）ワークスペースとプロパティを選択します。

1. 「**[!UICONTROL 次へ]**」をクリックします。

   フォームベースの Experience Composer が表示されます。

   ![](assets/location_refinements.png)

   Recommendations アクティビティを作成している場合、この画面は異なります。Recommendations アクティビティには、エクスペリエンスは含まれません。
1. 「[!UICONTROL 無題のアクティビティ]」をクリックして、アクティビティに名前を付けます。
1. 場所を選択します。

   「[!UICONTROL 場所を選択]」ボックスをクリックすると、使用可能な場所のリストが表示されます。 いずれかの場所を選択します。target.js によって提供されるグローバルな場所を選択するには、「target-global-mbox」を選択します。

   ここに表示されていない場所を入力することもできます。これは、mbox がまだページで作成または表示されていない場合に便利です。場所の名前を入力します。まだ存在していない場所を入力する場合は、注意が必要です。mbox の呼び出し時に、スペルや大文字／小文字が一致していないと、アクティビティが配信されません。手動で入力した場所は、使用可能な場所のリストに保存されます。 次に手動で入力した場所を選択しようとすると、そのアクティビティの[!UICONTROL 場所を選択]ドロップダウンリストからその場所を使用できます。

   >[!NOTE]
   >
   >アクティビティの作成時に手動で入力した場所を作成しても、新しい場所が自動的に作成されるわけではありません。 場所名は、アクティビティのコンテキストにのみ保存されます。 場所は、コンテンツ配信呼び出しがある場合に作成されます。 作成された場所に続いて、他のアクティビティで使用したり、オーディエンスの作成などに使用したりできます。 」をクリックします。

1. 「**[!UICONTROL 絞り込み条件を追加]**」をクリックし、このアクティビティ用の[オーディエンス](/help/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522)を 1 つ以上選択します。

   ![](assets/location_refinements_2.png)

   フォームベースの Experience Composer で、絞り込みが完全なオーディエンス機能で置き換えられました。既存のアクティビティの絞り込みが、[アクティビティのみのオーディエンス](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)に移行されました。
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

   **リダイレクトオファーの変更：**&#x200B;リダイレクトオファーを選択します。詳しくは、[リダイレクトオファーの作成](/help/c-experiences/c-manage-content/offer-redirect.md)を参照してください。

   **リモートオファーの変更：**&#x200B;リモートオファーを選択します。詳しくは、[リモートオファーの作成](/help/c-experiences/c-manage-content/about-remote-offers.md)を参照してください。

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

1. (オプション、ABアクティビティ、Automated Personalization、エクスペリエンスのターゲット設定の場合)追加の場所に対してこのプロセスを繰り返すには、「**[!UICONTROL 場所]**」をクリックし、場所とコンテンツを設定します。
1. 「**[!UICONTROL 次へ]**」をクリックし、アクティビティタイプに対して通常どおりアクティビティの作成手順を完了します。

* [A/B テストの作成](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [エクスペリエンスのターゲット設定アクティビティの作成](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Recommendations アクティビティの作成](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## トレーニングビデオ：フォームベースのコンポーザー  ![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオは、フォームベースのコンポーザーのデモを紹介します。

* フォームベースの Experience Composer を使用したアクティビティの作成
* フォームベースの Experience Composer と Visual Experience Composer のどちらを使用するかの理解
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)
