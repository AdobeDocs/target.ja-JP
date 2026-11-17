---
keywords: 自動パーソナライゼーション；オファー；レポート；グループ；レポートグループ；アプリ
description: '[!DNL Adobe Target] [!UICONTROL Automated Personalization] アクティビティでオファーレポートグループを使用する方法について説明します。'
title: '[!UICONTROL Automated Personalization] アクティビティでオファーレポートグループを使用できますか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
TQID: 'https://experienceleague.adobe.com/VW3zVGXb3IuQMDaRyidbkjsbUrojvwFsvwP3yRVeHp4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: e8a43148-398f-56c7-9433-6564f96999c2
    internal-label: Reports
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 5%
---
# [!UICONTROL Automated Personalization]のオファーレポートグループ {#offer-reporting-groups}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、オファーレポートグループが&#x200B;**[!UICONTROL Automated Personalization]** アクティビティでどのように機能するか、それらを設定する方法、レポートで表示する方法について説明します。

>[!ENDSHADEBOX]

レポートグループを使用すると、[!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) （AP）アクティビティのオファーをグループに整理できます。 レポートグループは、次の 2 つの主要機能を実行します。

* AP アクティビティレポートでグループ化されたオファーを表示できます。
* これらは、[!DNL Target] パーソナライゼーションモデルがどのように機能するかに重要な役割を果たします。

レポートグループを使用する場合、[!DNL Target]は、そのグループ内のすべてのオファーのデータを使用して、各レポートグループに1つのパーソナライゼーションモデルを作成します。 レポートグループを使用せずに、[!DNL Target]はAP アクティビティ内の各オファーのパーソナライゼーションモデルを作成します。

また、アクティビティの設定でオファーごとにパーソナライゼーションモデルを構築するのに十分なデータがない場合に、**[!UICONTROL Automated Personalization]**&#x200B;を使用するためのデータ要件もレポートグループによって削減されます。 新しいオファーの「コールドスタート」という問題を解決します。この問題は、類似のオファーでグループ化することで、各モデルがより多くのデータを学習できるようにします。

このアプローチは、訪問者がグループ内のすべてのオファーに同じ方法で応答するため、コンバージョン率が類似したグループのオファーを送信する場合に適しています。 すべてのオファーを単一のレポートグループに入れたり、コンバージョン率が異なるオファーをグループ化したりしないでください。両方の選択肢は、[!DNL Target] パーソナライゼーションモデルの効果を低下させる可能性が高くなります。

>[!NOTE]
>
>レポート グループからオファーが削除されるか、レポート グループ内で置き換えられた場合、そのオファーを見た過去のトラフィックもグループから削除されるため、削除されたオファーは、[!DNL Target] パーソナライゼーション モデルが学習に使用するデータに貢献しません。


## 注意点

### ライブアクティビティにレポートグループを使用する

レポート グループは、[!DNL Target]がモデルを構築する方法に影響します。 そのため、[!DNL Adobe]では、アクティビティの公開中にオファーを置き換えたり追加したりする予定がある場合にのみ、レポートグループを使用することをお勧めします。 新しいオファーがライブアクティビティに導入された場合、新しいオファーを既存の類似オファーを含むグループに入れることで、[!DNL Target]は、グループ内の他のオファーに対して既に収集されたデータを使用して、新しいオファーについて学習できます。

### オファーと場所のデータの記録方法

AP アクティビティには、場所とオファー（モジュール可能）の組み合わせがあります。 [!DNL Target]がレポートにデータを記録すると、これらの組み合わせが考慮されるので、オファーがどのイベント（表示、クリックなど）から来たのかが明確になります。

例えば、アクティビティに複数の場所と複数のオファーがあり、重複している場合があります。 訪問者が異なる場所でこれらのオファーを複数見た場合、[!DNL Target]はこれらのオファーのデータのみを記録します。 後で同じ訪問者がオファーをクリックした場合、[!DNL Target]はその組み合わせからのイベントのみを記録します（すべての組み合わせについては記録しません）。

同様に、指標に存在するがオファーを表示しない別の場所からクリックした場合、イベントはアクティビティの下に記録されますが、オファーと場所の組み合わせについては記録されません。 その結果、このオファーはオファーレポートグループに表示されません。 この動作は、クリックが、オファーを提供したmboxとは異なるmboxから行われる可能性があるために発生します。 この場合、指標はアクティビティに関連付けられますが、オファーには関連付けられません。

## レポートグループの設定

レポートグループにオファーを割り当てることで、[!DNL Target]がパーソナライゼーションモデルを構築する方法と、アクティビティレポートでのオファーの表示方法が決まります。 アクティビティの構築中、または新しいオファーをライブアクティビティに追加した場合は、グループを設定します。

1. AP アクティビティの&#x200B;**[!UICONTROL エクスペリエンス]** ページで、**[!UICONTROL コンテンツの管理]** アイコン （![ コンテンツの管理アイコン ](/help/main/assets/icons/Experience.svg)）をクリックします。

1. **[!UICONTROL Manage Content]** ダイアログボックス上部の「**[!UICONTROL Offers]**」タブをクリックします。

   ![ アイコンの設定](../assets/ap-offers-2.png)

1. （条件付き）レポートグループに追加するオファーを選択します。

   * 1つのオファーを追加するには、そのオファーの&#x200B;**[!UICONTROL 詳細アクション]** アイコン （![詳細アクション アイコン ](/help/main/assets/icons/MoreSmall.svg)）をクリックし、**[!UICONTROL レポート グループ]**&#x200B;をクリックします。
   * 一度に複数のオファーを追加するには、オファーのチェックボックスを選択し、ダイアログボックスの下部にある&#x200B;**[!UICONTROL レポートグループ]**&#x200B;をクリックします。

1. 選択したオファーをレポートグループに割り当てます。

   * 既存のレポートグループにオファーを割り当てるには、**[!UICONTROL Existing]**&#x200B;を選択し、ドロップダウンリストからレポートグループを選択して、**[!UICONTROL Confirm]**&#x200B;をクリックします。
   * オファーのレポートグループを作成するには、**[!UICONTROL 新規]**&#x200B;を選択し、新しいレポートグループに名前を付けて、**[!UICONTROL 確認]**&#x200B;をクリックします。

オファーのリストを絞り込むには、**[!UICONTROL 場所]** リストで場所を指定するか、**[!UICONTROL レポートグループ]** リストでレポートグループを指定してフィルターを実行します。 **[!UICONTROL レポートグループ]**&#x200B;のリストには、**[!UICONTROL 未割り当てオファー]** オプションも用意されています。このオプションには、まだレポートグループに属していないオファーが表示され、1つに割り当てることができます。

特定のオーディエンスに対するオファーのターゲティングについて詳しくは、[Target **[!UICONTROL Automated Personalization]**&#x200B;のオファー](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#set-up-targeting-rules)を参照してください。

## レポートグループでのオファーの表示

**[!UICONTROL オファーレベル]** レポートは、アクティビティのオファーのパフォーマンスをレポートグループごとにグループ化して示します。これにより、グループと個々のオファーを比較できます。

1. 「**[!UICONTROL アクティビティ]**」をクリックし、リストの「**[!UICONTROL Automated Personalization]**」アクティビティをクリックしてから、「**[!UICONTROL レポート]**」タブをクリックして、[ オファーレベル ](/help/main/c-reports/personalization-reports/reports-ap.md) レポートを表示します。

   アクティビティが多い場合は、「**[!UICONTROL フィルターを表示]** （funnel）」アイコンをクリックし、「**[!UICONTROL Automated Personalization]**」チェックボックスを選択して、**[!UICONTROL Automated Personalization]** アクティビティのみを表示します。

1. テーブルの&#x200B;**[!UICONTROL コントロール]**&#x200B;または&#x200B;**[!UICONTROL ターゲット設定]**&#x200B;をクリックして、グループ化されていないオファーとレポートグループ内のオファーを表示します。

   ![ オファーグループ：コントロールとターゲット設定](/help/main/c-reports/assets/offer-groups.png)

**[!UICONTROL Automated Personalization]** レポート（**[!UICONTROL オファーレベル]** レポートを含む）の使用方法について詳しくは、[Automated Personalization概要レポート ](/help/main/c-reports/personalization-reports/reports-ap.md)を参照してください。
