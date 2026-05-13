---
keywords: 自動パーソナライゼーション；オファー；レポート；グループ；レポートグループ；アプリ
description: ' [!DNL Adobe Target] [!UICONTROL Automated Personalization] アクティビティでオファーレポートグループを使用する方法について説明します。'
title: '[!UICONTROL Automated Personalization] アクティビティでオファーレポートグループを使用できますか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
TQID: https://experienceleague.adobe.com/VW3zVGXb3IuQMDaRyidbkjsbUrojvwFsvwP3yRVeHp4
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 827
ht-degree: 17%

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

1. AP アクティビティの&#x200B;**[!UICONTROL Experiences]** ページで、**[!UICONTROL Manage Content]** アイコン （![ コンテンツ管理アイコン ](/help/main/assets/icons/Experience.svg)）をクリックします
1. [!UICONTROL Manage Content] ダイアログボックスの上部にある「**[!UICONTROL Offers]**」タブをクリックします。
1. （条件付き）目的のオファーの[!UICONTROL More Actions] アイコン （![詳細アクションアイコン ](/help/main/assets/icons/MoreSmall.svg)）をクリックし、**[!UICONTROL Reporting Group]**&#x200B;をクリックして、レポートグループに特定のエクスペリエンスを追加します。

1. （条件付き）関連するエクスペリエンスのチェックボックスを選択し、ダイアログボックスの下部にある「**[!UICONTROL Reporting Group]**」をクリックして、レポートグループにエクスペリエンスを一括含めます。

1. 選択したオファーを既存のレポートグループに割り当てるには、**[!UICONTROL Existing]**&#x200B;を選択し、ドロップダウンリストから目的のレポートグループを選択して、**[!UICONTROL Confirm]**&#x200B;をクリックします。

   または

   選択したオファーを割り当てるレポートグループを作成するには、**[!UICONTROL New]**&#x200B;を選択し、新しいレポートグループに名前を付けて、**[!UICONTROL Confirm]**&#x200B;をクリックします。

[!UICONTROL Location] リストを使用して、場所ごとにオファーをフィルタリングできます。 [!UICONTROL Report Group] リストを使用して、レポートグループでオファーをフィルタリングします。 また、[!UICONTROL Report Group] リストを使用して[!UICONTROL Unassigned Offers]をフィルタリングし、現在どのレポートグループにも割り当てられていないオファーにレポートグループを割り当てることもできます。

特定のオーディエンスに対するオファーのターゲティングについて詳しくは、[Target [!UICONTROL Automated Personalization] オファー](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E)を参照してください。

## 注意事項

* レポートグループは、[!DNL Target]がモデルを構築する方法に影響を与えることを理解することが重要です。 そのため、[!DNL Adobe]では、アクティビティの公開中に新しいオファーを置き換えたり追加したりする予定がある場合にのみ、レポートグループを使用することをお勧めします。 新しいオファーがライブアクティビティに導入された場合、新しいオファーを既存の類似オファーを含むグループに入れると、グループ内の他のオファーに対して既に収集されているデータを使用して、新しいオファーについて学習できます。 すべてのオファーを 1 つのレポートグループに入れるのは避けてください。

* AP アクティビティには、場所とオファー（モジュール可能）の組み合わせがあります。 [!DNL Target]がレポートにデータを記録する場合、[!DNL Target]は、そのような組み合わせを考慮するので、オファーがどのイベント（表示、クリックなど）から来たのかが明確になります。

  例えば、アクティビティに複数の場所と複数のオファーがあり、重複している場合があります。 訪問者が異なる場所でこれらのオファーを複数見た場合、[!DNL Target]はこれらのオファーのデータのみを記録します。 後で同じ訪問者がオファーをクリックした場合、[!DNL Target]はその組み合わせからのイベントのみを記録します（すべての組み合わせについては記録しません）。

  同様に、クリックが別の場所から来て、指標に存在するがオファーが表示されない場合、このイベントはアクティビティの下に記録されますが、オファーと場所の組み合わせについては記録されません。 その結果、このオファーはオファーレポートグループに表示されません。

  この動作は、オファーを提供したmboxではなく、別のmboxからクリックされる可能性があるためです。 このため、指標はアクティビティに関連付けられますが、オファーには関連付けられません。

## レポートグループでのオファーの表示

1. **[!UICONTROL Activities]**&#x200B;をクリックし、リストから目的の[!UICONTROL Automated Personalization] アクティビティをクリックし、**[!UICONTROL Reports]** タブをクリックして[ オファーレベル ](/help/main/c-reports/personalization-reports/reports-ap.md) レポートを表示します。

   アクティビティが多い場合は、[!UICONTROL Show Filters] （funnel）アイコンをクリックし、「[!UICONTROL Automated Personalization]」チェックボックスを選択して、リストをフィルタリングして[!UICONTROL Automated Personalization] アクティビティのみを表示します。

1. テーブルの&#x200B;**[!UICONTROL Control]**&#x200B;または&#x200B;**[!UICONTROL Targeted]**&#x200B;をクリックして、グループ化されていないオファーとオファーをレポートグループ内に表示します。

   ![ オファーグループ：コントロールとターゲット設定](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

[!UICONTROL Automated Personalization]件のレポート（[!UICONTROL Offer Level]件のレポートを含む）の使用方法について詳しくは、[Automated Personalization概要レポート ](/help/main/c-reports/personalization-reports/reports-ap.md)を参照してください。
