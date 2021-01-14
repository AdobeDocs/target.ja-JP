---
keywords: automated personalization;offer;reporting;group;reporting group
description: Adobe TargetのAutomated Personalization(AP)アクティビティでのレポートグループの使用に関する情報です。
title: Adobe TargetのAutomated Personalization(AP)アクティビティのオファーレポートグループ
feature: Reports
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 64%

---


# ![Automated Personalizationのプレミアム](/help/assets/premium.png) オファーレポートグループ{#offer-reporting-groups-in-automated-personalization}

[Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)(AP)アクティビティでのレポートグループの使用に関する情報です。

レポートグループは、次の 2 つの主要機能を実行します。

* AP アクティビティレポートでグループ化されたオファーを表示できます。
* [!DNL Target]パーソナライゼーションモデルの機能に関して、主な役割を果たします。

レポートグループを使用する場合、[!DNL Target]は、APアクティビティ内の各オファーの代わりに、そのグループ内のすべてのオファーのデータを使用して、各レポートグループに対して1つのパーソナライゼーションモデルのみを作成します。

アクティビティ設定で、オファーごとに作成する必要のあるパーソナライゼーションモデルに十分なデータがない場合、レポートグループは Automated Personalization を使用するためのデータ要件を軽減するのに役立ちます。また、レポートグループは、類似するオファーをグループ化して新しいオファーの「コールドスタート」の問題を解決することもできるので、各モデルはより多くのデータを得ることができます。モデルグループは、新しいオファーが定期的に AP アクティビティに導入されるアクティビティにも使用できます。

この方法は、訪問者がグループ内のすべてのオファーに同じ方法で応答する場合に便利です。ベストプラクティスは、類似する訪問者グループが同様の方法で応答するオファーをグループ化することです。つまり、同様のコンバージョン率を持つオファーをグループ化します。すべてのオファーを 1 つのレポートグループに入れるのは避けてください。すべてのオファーをグループ化したり、オファーを非常に異なるコンバージョン率でグループ化したりすると、[!DNL Target]パーソナライゼーションモデルの効果が低下する可能性が高くなります。

>[!NOTE]
>
>オファーが特定のモデリンググループから削除または置換されると、その特定のオファーをモデリンググループからも削除した履歴トラフィックが表示されます。つまり、削除されたオファーは、[!DNL Target]パーソナライゼーションモデルが学習するために使用するデータには影響しません。

**レポートグループを設定するには：**

1. APアクティビティの[!UICONTROL エクスペリエンス]ページで、**[!UICONTROL コンテンツを管理]**&#x200B;アイコンをクリックします。

   ![](assets/ap_manage_content.png)

1. 「**[!UICONTROL Manage Content]**」ダイアログボックス上部の「[!UICONTROL Offers]」タブをクリックします。
1. （条件付き）特定のオファーにマウスポインターを置いてから **[!UICONTROL Reporting Group]** のフォルダーアイコンをクリックして、特定のエクスペリエンスをレポートグループに追加します。

   ![](assets/ap_manage_content_2.png)

1. （条件付き）複数のエクスペリエンスのチェックボックスをオンにしてからダイアログボックスの右上隅にある **[!UICONTROL Reporting Group]** のフォルダーアイコンをクリックして、エクスペリエンスを一括でレポートグループに追加します。

   ![](assets/ap_manage_content_3.png)

1. （条件付き）選択したオファーを既存のレポートグループに割り当てるには、「**[!UICONTROL 既存]**」を選択し、ドロップダウンリストから目的のレポートグループを選択して、「**[!UICONTROL 適用]**」をクリックします。

   または

   選択したオファーをアサインする新しいレポートグループを作成するには、 「**[!UICONTROL 新規]**」を選択し、新しいレポートグループに名前を付けて、「**[!UICONTROL 適用]**」をクリックします。

   ![](assets/ap_reporting_groups.png)

