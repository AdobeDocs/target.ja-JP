---
keywords: 目標と設定；目的；優先度；期間
description: Adobeのアクティビティ設定の使用方法を説明します [!DNL Target] ：アクティビティの目標、優先度および期間を管理します。
title: アクティビティの設定を指定する方法を教えてください。
feature: Activities
exl-id: 7f34080b-d2ed-4fe5-80ff-3aba16961223
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 79%

---

# アクティビティの設定

用途 [!UICONTROL アクティビティの設定] in [!DNL Adobe Target] ：アクティビティの目標、優先度および期間を管理します。

1. アクティビティの目標に関するメモを入力します。

   アクティビティに関して、自分自身または他のチームメンバーにとって手元にあると便利な情報を入力します。[!UICONTROL 目標]フィールドをドラッグして、サイズを変更します。
1. アクティビティの優先度を設定します。

   [!UICONTROL 優先度]の UI とオプションは、設定によって変わります。従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。

   優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。

   このオプションが [!UICONTROL 管理] > [!UICONTROL レポート] （デフォルト）次の優先度を指定します。「低」、「中」、「高」のいずれか。

   優先度の詳細設定を有効にするには、 [!UICONTROL 管理] > [!UICONTROL レポート]、次に [!UICONTROL 詳細な優先度の有効化] オプションを「オン」位置に設定します。

   このオプションを有効にした場合は、0～999 の値を指定します。

   * 0 = 低
   * 999 = 高

   [!DNL Target Standard/Premium] の以前のバージョンで作成されたアクティビティについては、低の優先度は 0 に、中は 5 に、高は 10 に変換されます。これらの値は必要に応じて調整できます。

   >[!NOTE]
   >
   >優先度の詳細設定を使用した後でこのオプションを無効にするには、すべての優先度を 0、5、10 に戻す必要があります。

1. アクティビティの期間を設定します。

   アクティビティを手動でアクティブ化または非アクティブ化したり、アクティビティを配信する日時を指定したりできます。タイムコントロールは 24 時間の時計を使用します。00:00 は真夜中です。タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。

   >[!NOTE]
   >
   >アクティビティのスケジュールはアクティビティの配信期間を制御します。ただし、アクティビティは、特定のスケジュールに従って配信される前に、明示的にアクティブ化されている必要があります。

[!UICONTROL 目標と設定]ページには、作成するアクティビティのタイプに基づいて異なる追加の設定が含まれています。これらの設定について詳しくは、アクティビティのタイプを参照してください。

* [A/B テスト](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [自動パーソナライゼーション](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)
* [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Recommendations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)

## トレーニングビデオ：アクティビティの設定 ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

   >[!VIDEO](https://video.tv.adobe.com/v/17381)
