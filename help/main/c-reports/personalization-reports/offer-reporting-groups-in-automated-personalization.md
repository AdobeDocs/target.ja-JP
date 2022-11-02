---
keywords: 自動パーソナライゼーション、オファー、レポート、グループ、レポートグループ、ap
description: Adobeでのオファーレポートグループの使用方法を説明します [!DNL Target] [!UICONTROL Automated Personalization] アクティビティ。
title: Automated Personalization Activities でオファーレポートグループを使用できますか？
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: b3be11cda61b5bf54ee390a192d9f60273f8f12e
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 41%

---

# ![Automated Personalizationのプレミアム](/help/main/assets/premium.png)[!UICONTROL  オファーレポートグループ]

でのレポートグループの使用に関する情報 [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) アクティビティ

レポートグループは、次の 2 つの主要機能を実行します。

* レポートグループを使用すると、AP アクティビティレポートでグループ化されたオファーを表示できます。
* レポートグループは、 [!DNL Target] パーソナライゼーションモデル機能を使用します。

レポートグループを使用する場合、 [!DNL Target] は、そのグループ内のすべてのオファーのデータを使用して、各レポートグループに対して 1 つのパーソナライゼーションモデルを作成します。 レポートグループがない場合、 [!DNL Target] は、AP アクティビティの各オファーに対してパーソナライゼーションモデルを作成します。

アクティビティの設定で、オファーごとに作成するのに十分なデータがない場合、レポートグループは、 [!UICONTROL Automated Personalization]. また、レポートグループは、類似するオファーをグループ化して新しいオファーの「コールドスタート」の問題を解決することもできるので、各モデルはより多くのデータを得ることができます。モデリンググループは、AP アクティビティに新しいオファーが定期的に導入されるアクティビティにも使用できます。

この方法は、訪問者がグループ内のすべてのオファーに同じ方法で応答する場合に便利です。ベストプラクティスは、類似する訪問者グループが同様の方法で応答するオファーをグループ化することです。つまり、同様のコンバージョン率を持つオファーをグループ化します。すべてのオファーを 1 つのレポートグループに入れるのは避けてください。コンバージョン率の異なるすべてのオファーまたはオファーをグループ化すると、 [!DNL Target] パーソナライゼーションモデル。

>[!NOTE]
>
>オファーが特定のモデリンググループから削除または置換されると、その特定のオファーをモデリンググループからも削除した履歴トラフィックが表示されます。つまり、削除されたオファーは、 [!DNL Target] パーソナライゼーションモデルを参照してください。

## レポートグループの設定

1. の **[!UICONTROL エクスペリエンス]** AP アクティビティのページで、 **[!UICONTROL コンテンツを管理]** アイコン

   ![コンテンツを管理アイコン](/help/main/c-reports/assets/ap_manage_content.png)

1. 「**[!UICONTROL Manage Content]**」ダイアログボックス上部の「[!UICONTROL Offers]」タブをクリックします。
1. （条件付き）特定のオファーにマウスポインターを置いてから **[!UICONTROL Reporting Group]** のフォルダーアイコンをクリックして、特定のエクスペリエンスをレポートグループに追加します。

   ![レポートグループアイコン](/help/main/c-reports/assets/ap_manage_content_2.png)

1. （条件付き）複数のエクスペリエンスのチェックボックスをオンにしてから **[!UICONTROL レポートグループ]** ダイアログボックスの右上隅にあるフォルダーアイコン。

   ![レポートグループアイコン](/help/main/c-reports/assets/ap_manage_content_3.png)

1. 選択したオファーを既存のレポートグループに割り当てるには、「**[!UICONTROL 既存]**」を選択し、ドロップダウンリストから目的のレポートグループを選択して、「**[!UICONTROL 適用]**」をクリックします。

   または

   選択したオファーを割り当てる新しいレポートグループを作成するには、「****」を選択し、新しいレポートグループに名前を付けて「**[!UICONTROL Apply]**」をクリックします。

   ![新しいレポートグループを作成するための新しいアイコン](/help/main/c-reports/assets/ap_reporting_groups.png)

以下を使用して、 [!UICONTROL 場所] 場所でオファーをフィルターするリスト。 レポートグループを基準にしてオファーをフィルターするには、[!UICONTROL レポートグループ]リストを使用します。また、[!UICONTROL レポートグループ]では、[!UICONTROL 割り当てられていないオファー]をフィルターして、現在どのレポートグループにも割り当てられていないオファーにレポートグループを割り当てることもできます。

特定のオーディエンスに対するオファーのターゲット設定について詳しくは、「[AP オファーのターゲット設定](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E)」を参照してください。

## 注意事項

* レポートグループが [!DNL Target] モデルを構築します。 その結果、 [!DNL Adobe] では、アクティビティがライブ状態のときに新しいオファーを置き換えたり追加したりする予定がある場合にのみ、レポートグループを使用することをお勧めします。 ライブアクティビティに新しいオファーが導入された場合、既存の類似のオファーを含むグループに新しいオファーを配置すると、マシンは、グループ内の他のオファーで既に収集されているデータを使用して、新しいオファーについて学習できます。 すべてのオファーを 1 つのレポートグループに入れるのは避けてください。

## レポートグループのオファーを表示

1. クリック **[!UICONTROL アクティビティ]**、目的の [!UICONTROL Automated Personalization] 「 」アクティビティを選択し、 **[!UICONTROL レポート]** タブを使用して、 [オファーレベル](/help/main/c-reports/personalization-reports/reports-ap.md) レポート。

   多くのアクティビティがある場合、[!UICONTROL タイプ]ドロップダウンリストから [!UICONTROL Automated Personalization] を選択することで、リストをフィルターできます。

1. クリック **[!UICONTROL 制御]** または **[!UICONTROL ターゲット]** をテーブルに表示して、レポートグループ内のグループ化されていないオファーおよびオファーを表示します。

   ![オファーグループ：コントロールとターゲット](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

の使用に関する情報 [!UICONTROL Automated Personalization] レポート ( [!UICONTROL オファーレベル] レポートを参照 )、 [Automated Personalizationサマリレポート](/help/main/c-reports/personalization-reports/reports-ap.md).


