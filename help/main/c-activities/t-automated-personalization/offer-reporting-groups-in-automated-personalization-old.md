---
keywords: 自動パーソナライゼーション；オファー；レポート；グループ；レポートグループ；アプリ
description: ' [!DNL Adobe Target] [!UICONTROL Automated Personalization] アクティビティでオファーレポートグループを使用する方法について説明します。'
title: '[!UICONTROL Automated Personalization] アクティビティでオファーレポートグループを使用できますか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 27%

---

# [!UICONTROL Automated Personalization]のオファーレポートグループ

[!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) （AP）アクティビティでのレポートグループの使用に関する情報。

レポートグループは、次の 2 つの主要機能を実行します。

* レポートグループを使用すると、AP アクティビティレポートでグループ化されたオファーを確認できます。
* レポートグループは、[!DNL Target] パーソナライゼーションモデルがどのように機能するかにおいて重要な役割を果たします。

レポートグループを使用する場合、[!DNL Target]は、そのグループ内のすべてのオファーのデータを使用して、各レポートグループに1つのパーソナライゼーションモデルを作成します。 レポートグループを使用せずに、[!DNL Target]はAP アクティビティ内の各オファーのパーソナライゼーションモデルを作成します。

アクティビティの設定に、オファーごとに構築されるパーソナライゼーションモデルに十分なデータがない場合、レポートグループを使用すると、[!UICONTROL Automated Personalization]を使用するためのデータ要件を軽減できます。 また、レポートグループは、類似するオファーをグループ化して新しいオファーの「コールドスタート」の問題を解決することもできるので、各モデルはより多くのデータを得ることができます。 モデリンググループは、新しいオファーがAP アクティビティに定期的に導入されるアクティビティにも使用できます。

この方法は、訪問者がグループ内のすべてのオファーに同じ方法で応答する場合に便利です。 ベストプラクティスは、類似する訪問者グループが同様の方法で応答するオファーをグループ化することです。 つまり、同様のコンバージョン率を持つオファーをグループ化します。 すべてのオファーを 1 つのレポートグループに入れるのは避けてください。 すべてのオファーをグループ化するか、コンバージョン率が異なるオファーをグループ化すると、[!DNL Target] パーソナライゼーションモデルの効果が低下する可能性があります。

>[!NOTE]
>
>オファーが特定のモデリンググループから削除または置換されると、その特定のオファーをモデリンググループからも削除した履歴トラフィックが表示されます。 つまり、削除されたオファーは、[!DNL Target] パーソナライゼーションモデルで学習に使用されるデータに貢献しません。

## レポートグループの設定

1. AP アクティビティの&#x200B;**[!UICONTROL エクスペリエンス]** ページで、**[!UICONTROL コンテンツの管理]** アイコンをクリックします。

   ![&#x200B; コンテンツの管理アイコン &#x200B;](/help/main/c-reports/assets/ap_manage_content.png)

1. **[!UICONTROL Manage Content]** ダイアログボックス上部の「[!UICONTROL Offers]」タブをクリックします。
1. （条件付き）特定のオファーにカーソルを合わせてから **[!UICONTROL Reporting Group]** のフォルダーアイコンをクリックして、特定のエクスペリエンスをレポートグループに追加します。

   ![&#x200B; レポートグループアイコン &#x200B;](/help/main/c-reports/assets/ap_manage_content_2.png)

1. （条件付き）関連するエクスペリエンスのチェックボックスを選択し、ダイアログボックスの右上隅にある「**[!UICONTROL レポートグループ]**」フォルダーアイコンをクリックして、レポートグループにエクスペリエンスを一括含めます。

   ![&#x200B; レポートグループアイコン &#x200B;](/help/main/c-reports/assets/ap_manage_content_3.png)

1. 選択したオファーを既存のレポートグループに割り当てるには、「**[!UICONTROL Existing]**」を選択し、ドロップダウンリストから特定のレポートグループを選択して、「**[!UICONTROL Apply]**」をクリックします。

   または

   選択したオファーを割り当てるレポートグループを作成するには、**[!UICONTROL 新規]**&#x200B;を選択し、新しいレポートグループに名前を付けて、**[!UICONTROL 適用]**&#x200B;をクリックします。

   ![新しいレポートグループを作成するための新しいアイコン &#x200B;](/help/main/c-reports/assets/ap_reporting_groups.png)

[!UICONTROL 場所] リストを使用して、場所ごとにオファーをフィルタリングできます。 レポートグループを基準にしてオファーをフィルターするには、[!UICONTROL レポートグループ]リストを使用します。 また、[!UICONTROL レポートグループ]では、[!UICONTROL 割り当てられていないオファー]をフィルターして、現在どのレポートグループにも割り当てられていないオファーにレポートグループを割り当てることもできます。

特定のオーディエンスに対するオファーのターゲティングについて詳しくは、[Target [!UICONTROL Automated Personalization]のオファー](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E)を参照してください。

## 注意事項

* レポートグループは、[!DNL Target]がモデルを構築する方法に影響を与えることを理解することが重要です。 そのため、[!DNL Adobe]では、アクティビティの公開中に新しいオファーを置き換えたり追加したりする予定がある場合にのみ、レポートグループを使用することをお勧めします。 新しいオファーがライブアクティビティに導入された場合、新しいオファーを既存の類似オファーを含むグループに入れると、グループ内の他のオファーに対して既に収集されているデータを使用して、新しいオファーについて学習できます。 すべてのオファーを 1 つのレポートグループに入れるのは避けてください。

* AP アクティビティには、場所とオファー（モジュール可能）の組み合わせがあります。 [!DNL Target]がレポートにデータを記録する場合、[!DNL Target]は、そのような組み合わせを考慮するので、オファーがどのイベント（表示、クリックなど）から来たのかが明確になります。

  例えば、アクティビティに複数の場所と複数のオファーがあり、重複している場合があります。 訪問者が異なる場所でこれらのオファーを複数見た場合、[!DNL Target]はこれらのオファーのデータのみを記録します。 後で同じ訪問者がオファーをクリックした場合、[!DNL Target]はその組み合わせからのイベントのみを記録します（すべての組み合わせについては記録しません）。

  同様に、クリックが別の場所から来て、指標に存在するがオファーが表示されない場合、このイベントはアクティビティの下に記録されますが、オファーと場所の組み合わせについては記録されません。 その結果、このオファーはオファーレポートグループに表示されません。

  この動作は、オファーを提供したmboxではなく、別のmboxからクリックされる可能性があるためです。 このため、指標はアクティビティに関連付けられますが、オファーには関連付けられません。

## レポートグループでのオファーの表示

1. 「**[!UICONTROL アクティビティ]**」をクリックし、リストから目的の[!UICONTROL Automated Personalization] アクティビティをクリックし、「**[!UICONTROL レポート]**」タブをクリックして[&#x200B; オファーレベル &#x200B;](/help/main/c-reports/personalization-reports/reports-ap.md) レポートを表示します。

   アクティビティが多い場合は、「[!UICONTROL &#x200B; フィルターを表示] （funnel）」アイコンをクリックし、「[!UICONTROL Automated Personalization]」チェックボックスを選択して、リストをフィルタリングして[!UICONTROL Automated Personalization] アクティビティのみを表示します。

1. テーブルの&#x200B;**[!UICONTROL コントロール]**&#x200B;または&#x200B;**[!UICONTROL ターゲット設定]**&#x200B;をクリックすると、レポートグループ内のグループ化されていないオファーとオファーが表示されます。

   ![&#x200B; オファーグループ：コントロールとターゲット設定](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

[!UICONTROL Automated Personalization] レポート（[!UICONTROL &#x200B; オファーレベル &#x200B;] レポートを含む）の使用方法について詳しくは、[Automated Personalization概要レポート &#x200B;](/help/main/c-reports/personalization-reports/reports-ap.md)を参照してください。


