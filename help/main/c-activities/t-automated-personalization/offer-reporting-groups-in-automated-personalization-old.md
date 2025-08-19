---
keywords: automated personalization；オファー；レポート；グループ；レポートグループ；ap
description: ' [!DNL Adobe Target] [!UICONTROL Automated Personalization] アクティビティでオファーレポートグループを使用する方法を説明します。'
title: '[!UICONTROL Automated Personalization] アクティビティでオファーレポートグループを使用できますか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 16%

---

# [!UICONTROL Automated Personalization] のオファーレポートグループ

[!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) （AP）アクティビティでのレポートグループの使用に関する情報。

レポートグループは、次の 2 つの主要機能を実行します。

* レポートグループを使用すると、AP アクティビティレポートにグループ化されたオファーを表示できます。
* レポートグループは、[!DNL Target] パーソナライゼーションモデルの機能を果たす上で重要な役割を果たします。

レポートグループを使用する [!DNL Target]、そのグループ内のすべてのオファーのデータを使用して、レポートグループごとに 1 つのパーソナライゼーションモデルが作成されます。 レポートグループを使用 [!DNL Target] ない場合、AP アクティビティの各オファーに対して、パーソナライゼーションモデルが作成されます。

アクティビティの設定に、オファーごとに作成されるパーソナライゼーションモデルに十分なデータがない場合、レポートグループは、[!UICONTROL Automated Personalization] を使用するためのデータ要件を減らすのに役立ちます。 また、レポートグループは、類似するオファーをグループ化して新しいオファーの「コールドスタート」の問題を解決することもできるので、各モデルはより多くのデータを得ることができます。また、モデリンググループは、新しいオファーが AP アクティビティに定期的に導入されるアクティビティにも使用できます。

この方法は、訪問者がグループ内のすべてのオファーに同じ方法で応答する場合に便利です。ベストプラクティスは、類似する訪問者グループが同様の方法で応答するオファーをグループ化することです。つまり、同様のコンバージョン率を持つオファーをグループ化します。すべてのオファーを 1 つのレポートグループに入れるのは避けてください。すべてのオファーをグループ化するか、異なるコンバージョン率を持つオファーをグループ化すると、[!DNL Target] しいパーソナライゼーションモデルの有効性が低下する可能性があります。

>[!NOTE]
>
>オファーが特定のモデリンググループから削除または置換されると、その特定のオファーをモデリンググループからも削除した履歴トラフィックが表示されます。つまり、削除されたオファーは、学習するパーソナライゼーションモデルに使用するデータに影響を与え [!DNL Target] せん。

## レポートグループの設定

1. AP アクティビティの **[!UICONTROL Experiences]** ページで、**[!UICONTROL Manage Content]** アイコンをクリックします。

   ![ コンテンツを管理アイコン ](/help/main/c-reports/assets/ap_manage_content.png)

1. [**[!UICONTROL Offers]**] ダイアログ ボックスの上部にある [[!UICONTROL Manage Content]] タブをクリックします。
1. （条件付き）目的のオファーにカーソルを合わせ、**[!UICONTROL Reporting Group]** フォルダーアイコンをクリックすることで、特定のエクスペリエンスをレポートグループに追加します。

   ![ レポートグループアイコン ](/help/main/c-reports/assets/ap_manage_content_2.png)

1. （条件付き）バッチで、関連するエクスペリエンスのチェックボックスを選択したあと、ダイアログボックスの右上隅にある **[!UICONTROL Reporting Group]** フォルダーアイコンをクリックして、レポートグループにエクスペリエンスを含めます。

   ![ レポートグループアイコン ](/help/main/c-reports/assets/ap_manage_content_3.png)

1. 選択したオファーを既存のレポートグループに割り当てるには、「**[!UICONTROL Existing]**」を選択し、ドロップダウンリストから目的のレポートグループを選択して、「**[!UICONTROL Apply]**」をクリックします。

   または

   選択したオファーを割り当てるレポートグループを作成するには、「**[!UICONTROL New]**」を選択し、新しいレポートグループに名前を付けて、「**[!UICONTROL Apply]**」をクリックします。

   ![ 新しいレポートグループを作成するための新しいアイコン ](/help/main/c-reports/assets/ap_reporting_groups.png)

[!UICONTROL Location] リストを使用して、場所でオファーをフィルタリングできます。 [!UICONTROL Report Group] リストを使用すると、レポートグループでオファーをフィルタリングできます。 [!UICONTROL Report Group] リストを使用して [!UICONTROL Unassigned Offers] をフィルタリングし、現在どのレポートグループにも割り当てられていないオファーにレポートグループを割り当てることもできます。

特定のオーディエンスに対するオファーのターゲティングについては、[ オファーのターゲティング [!UICONTROL Automated Personalization] を参照し ](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E) ください。

## 注意事項

* レポートグループは、[!DNL Target] によるモデルの構築方法に影響を与えることを理解しておくことが重要です。 そのため、[!DNL Adobe] では、アクティビティのライブ中に新しいオファーを置き換えたり追加したりする予定がある場合にのみ、レポートグループを使用することをお勧めします。 新しいオファーがライブアクティビティに導入された場合、その新しいオファーを既存の類似オファーを含むグループに配置すると、マシンは、グループ内の他のオファーで既に収集されたデータを使用して、その新しいオファーについて学習できます。 すべてのオファーを 1 つのレポートグループに入れるのは避けてください。

* AP アクティビティには、場所とオファー（モデル可能）の組み合わせがあります。 [!DNL Target] がレポートにデータを記録する際、[!DNL Target] はこのような組み合わせを考慮し、オファーがどのイベント（表示、クリックなど）から来たかを明確にします。

  例えば、1 つのアクティビティに複数の場所と複数のオファーがあり、重複している場合があります。 訪問者が異なる場所でこれらのオファーを複数表示した場合、[!DNL Target] れらのオファーのデータのみを記録します。 同じ訪問者が後でオファーをクリックすると、[!DNL Target] はその組み合わせからのみイベントを記録します（すべての組み合わせについてではありません）。

  同様に、クリックが別の場所から発生し、その場所が指標に存在するが、オファーが表示されない場合、このイベントはアクティビティの下に記録されますが、オファーと場所の組み合わせには記録されません。 その結果、このオファーはオファーレポートグループに表示されません。

  この動作は、クリックが、オファーを提供した mbox ではなく、別の mbox から行われた可能性があるためです。 このため、指標はアクティビティに関連付けられていますが、オファーには関連付けられていません。

## レポートグループ内のオファーの表示

1. 「**[!UICONTROL Activities]**」をクリックし、リストから目的の [!UICONTROL Automated Personalization] アクティビティをクリックして、「**[!UICONTROL Reports]**」タブをクリックして [ オファーレベル ](/help/main/c-reports/personalization-reports/reports-ap.md) レポートを表示します。

   アクティビティが多数ある場合は、[!UICONTROL Show Filters] （ファネル）アイコンをクリックし、「[!UICONTROL Automated Personalization]」チェックボックスをオンにして、リストをフィルタリングして [!UICONTROL Automated Personalization] のアクティビティのみを表示します。

1. テーブルの **[!UICONTROL Control]** または **[!UICONTROL Targeted]** をクリックすると、グループ化されていないオファーとレポートグループ内のオファーが表示されます。

   ![ オファーグループ：コントロールとターゲット ](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

[!UICONTROL Automated Personalization] レポート （[!UICONTROL Offer Level] レポートを含む）の使用方法については、[Automated Personalizationの概要レポート ](/help/main/c-reports/personalization-reports/reports-ap.md) を参照してください。


