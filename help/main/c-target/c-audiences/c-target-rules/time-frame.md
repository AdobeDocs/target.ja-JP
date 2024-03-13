---
keywords: time frame、start date、終了日、開始日/終了日、時間枠、ターゲットスケジュール、週間の分割、日分割、分割
description: 開始日時と終了日時を使用して、特定の期間にサイトを訪問したユーザーをターゲットにする方法を説明します。
title: 特定の時間にサイトを訪問した訪問者をターゲットに設定することはできますか？
feature: Audiences
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
source-git-commit: 0e4698935b90cc0236abe6a47a6183c7fd2a7b20
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 35%

---

# [!UICONTROL Time Frame]

開始日時と終了日時は、 [!DNL Adobe Target] を使用して、特定の期間内にサイトを訪問したユーザーをターゲットに設定できます。 また、「週と日付の分割」オプションを設定して、オーディエンスのターゲット設定の繰り返しパターンを作成できます。

例えば、 [組み合わせアドホックオーディエンス機能](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を使用すると、ブラックフライデーまでの 3 日間の特定のコンテンツと、ブラックフライデーの後の他のコンテンツを持つ低スペンダーをターゲットにすることができます。

1. Adobe Analytics の [!DNL Target] インタフェース、クリック **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. ドラッグ&amp;ドロップ **[!UICONTROL Time Frame]** を audience builder パネルにドラッグします。

   ![target_timeframe_dialog image](assets/target_timeframe_dialog.png)

1. 次を指定します。 [!UICONTROL Start] および [!UICONTROL End] オーディエンスの日付と時間。

   アクティビティのスケジュールによってターゲティングを開始するには、開始日を空欄にしておきます。アクティビティの停止日時までターゲティングを続けるには停止日を空欄にしておきます。

   開始日と終了日を両方とも空欄にしておくこともできます。この機能を使用すると、開始日と終了日をアクティビティレベルで制御しながら、同じオーディエンスを複数のアクティビティで（オーディエンスのコピーを作成せずに）使用できます。

   >[!NOTE]
   >
   >次の点に留意してください。
   >
   >* 開始日/終了日のタイムゾーンは、GMT+/- NNとして表示されます。NN（ここでNN: NNはGMTからのオフセットであり、訪問者のタイムゾーンではなくアカウントレベルのタイムゾーンを反映しています。例えば、カリフォルニアのタイムゾーンは、GMT -08:00 と表示されます。
   >
   >* [!DNL Target] 時間オーディエンスは、夏時間 (DST) の変更を考慮しません。 DST の変更を考慮するには、オーディエンスを手動で再保存する必要があります。

1. （条件付き）クリック **[!UICONTROL Set frequency]** を使用して、繰り返しパターンを設定します（曜日と時刻を含む）。

   ![週と日付の分割](assets/week_and_day_parting.png)

   以下を使用できます。 [!UICONTROL Frequency] 例えば、コールセンターに人員が配置されている日時のみ訪問者に「今すぐチャット」オプションを表示する場合などです。

   1 つ以上の曜日を選択して、開始および終了時間を設定します。クリック **[!UICONTROL Add frequency]** 必要に応じて、追加のパターンを指定します。

   >[!NOTE]
   >
   >のタイムゾーン [!UICONTROL Week and Day Parting] は GMT +/- NN:NN（ここで NN: NN は GMT からのオフセットで、訪問者のタイムゾーンではなくアカウントレベルのタイムゾーンを反映しています）として表示されます。 例えば、カリフォルニアの太平洋夏時間のタイムゾーンは、GMT -07:00 と表示されます。

1. （オプション）オーディエンス用の追加のルールを設定します。

   必要に応じて、各ルールに対して手順 5 を繰り返すことができます。

1. **[!UICONTROL Done]** をクリックします。

## トレーニングビデオ：オーディエンスの作成 ![概要バッジ](/help/main/assets/overview.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
