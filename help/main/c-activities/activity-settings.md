---
keywords: 目標と設定；目標；優先度；期間
description: Adobeのアクティビティ設定を使用して  [!DNL Target]  アクティビティの目的、優先度、期間を管理する方法について説明します。
title: アクティビティ設定の指定方法
feature: Activities
exl-id: 7f34080b-d2ed-4fe5-80ff-3aba16961223
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 71%

---

# アクティビティの設定

[!UICONTROL Activity Settings] の [!DNL Adobe Target] を使用して、アクティビティの目的、優先度、期間を管理します。

1. アクティビティの目標に関するメモを入力します。

   アクティビティに関して、自分自身または他のチームメンバーにとって手元にあると便利な情報を入力します。ドラッグして [!UICONTROL Objective] フィールドのサイズを変更します。
1. アクティビティの優先度を設定します。

   の UI とオプションは、設定によっ [!UICONTROL Priority] 異なります。 従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。

   優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。

   [!UICONTROL Administration] > [!UICONTROL Reporting] （デフォルト）でこのオプションが有効になっていない場合は、優先度を「低」、「Medium」、「高」から指定します。

   詳細な優先度を有効にするには、[!UICONTROL Administration]/[!UICONTROL Reporting] をクリックし、「[!UICONTROL Enable Fine-Grained Priorities]」オプションを「オン」の位置に切り替えます。

   このオプションを有効にした場合は、0～999 の値を指定します。

   * 0 = 低
   * 999 = 高

   [!DNL Target Standard/Premium] の以前のバージョンで作成されたアクティビティについては、低の優先度は 0 に、中は 5 に、高は 10 に変換されます。これらの値は必要に応じて調整できます。

   >[!NOTE]
   >
   >優先度の詳細設定を使用した後でこのオプションを無効にするには、すべての優先度を 0、5、10 に戻す必要があります。

1. アクティビティの期間を設定します。

   アクティビティを手動でアクティブ化または非アクティブ化したり、アクティビティを配信する日時を指定したりできます。時間コントロールでは、00:00 が午前 0 時の 24 時間制を使用します。 タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。

   >[!NOTE]
   >
   >アクティビティのスケジュールはアクティビティの配信期間を制御します。ただし、アクティビティは、特定のスケジュールに従って配信される前に、明示的にアクティブ化されている必要があります。

[!UICONTROL Goal & Settings] のページには、作成するアクティビティのタイプに応じて異なる追加設定が含まれています。 これらの設定について詳しくは、アクティビティのタイプを参照してください。

* [A/B テスト](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)
* [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [レコメンデーション](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)

## トレーニングビデオ：アクティビティ設定 ![&#x200B; チュートリアルバッジ &#x200B;](/help/main/assets/tutorial.png)

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

  >[!VIDEO](https://video.tv.adobe.com/v/17381)
