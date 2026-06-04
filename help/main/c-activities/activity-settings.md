---
keywords: 目標と設定；目的；優先度；期間
description: Adobe [!DNL Target] のアクティビティ設定を使用して、アクティビティの目的、優先度、期間を管理する方法について説明します。
title: アクティビティ設定を指定するにはどうすればよいですか？
feature: Activities
exl-id: 7f34080b-d2ed-4fe5-80ff-3aba16961223
TQID: https://experienceleague.adobe.com/tCKQJJOfsU1XkeHwFHNF33XP4tYvxlE0Hv01u0CBr7o
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 432
ht-degree: 77%

---

# アクティビティの設定

[!DNL Adobe Target]の[!UICONTROL &#x200B; アクティビティ設定]を使用して、アクティビティの目的、優先度、期間を管理します。

1. アクティビティの目標に関するメモを入力します。

   アクティビティに関して、自分自身または他のチームメンバーにとって手元にあると便利な情報を入力します。 [!UICONTROL 目標]フィールドをドラッグして、サイズを変更します。
1. アクティビティの優先度を設定します。

   [!UICONTROL 優先度]の UI とオプションは、設定によって変わります。 従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。

   優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。 ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。

   このオプションが[!UICONTROL Administration] > [!UICONTROL Reporting] （デフォルト）で有効になっていない場合は、優先度をLow、Medium、Highに指定します。

   きめ細かい優先度を有効にするには、[!UICONTROL 管理] > [!UICONTROL &#x200B; レポート &#x200B;]をクリックし、[!UICONTROL きめ細かい優先度を有効にする] オプションを「オン」の位置に切り替えます。

   このオプションを有効にした場合は、0～999 の値を指定します。

   * 0 = 低
   * 999 = 高

   [!DNL Target Standard/Premium] の以前のバージョンで作成されたアクティビティについては、低の優先度は 0 に、中は 5 に、高は 10 に変換されます。 これらの値は必要に応じて調整できます。

   >[!NOTE]
   >
   >優先度の詳細設定を使用した後でこのオプションを無効にするには、すべての優先度を 0、5、10 に戻す必要があります。

1. アクティビティの期間を設定します。

   アクティビティを手動でアクティブ化または非アクティブ化したり、アクティビティを配信する日時を指定したりできます。 タイムコントロールでは、00:00が午前0時の24時間時計を使用します。 タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。 別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。

   >[!NOTE]
   >
   >アクティビティのスケジュールはアクティビティの配信期間を制御します。ただし、アクティビティは、特定のスケジュールに従って配信される前に、明示的にアクティブ化されている必要があります。

[!UICONTROL 目標と設定]ページには、作成するアクティビティのタイプに基づいて異なる追加の設定が含まれています。 これらの設定について詳しくは、アクティビティのタイプを参照してください。

* [A/B テスト](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)
* [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [レコメンデーション](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)

## トレーニングビデオ：アクティビティ設定![&#x200B; チュートリアルバッジ &#x200B;](/help/main/assets/tutorial.png)

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

  >[!VIDEO](https://video.tv.adobe.com/v/17381)
