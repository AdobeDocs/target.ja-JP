---
keywords: 自動パーソナライゼーション、オファー、レポート、グループ、レポートグループ、ap
description: Adobeでのオファーレポートグループの使用方法を説明します [!DNL Target] [!UICONTROL Automated Personalization] アクティビティ。
title: Automated Personalization Activities でオファーレポートグループを使用できますか？
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: 60655a93b515095bd8c67a4af2193d36789ab96e
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 52%

---

# ![Automated Personalizationのプレミアム](/help/main/assets/premium.png)[!UICONTROL  オファーレポートグループ]

でのレポートグループの使用に関する情報 [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) アクティビティ

レポートグループは、次の 2 つの主要機能を実行します。

* レポートグループを使用すると、AP アクティビティレポートでグループ化されたオファーを表示できます。
* レポートグループは、 [!DNL Target] パーソナライゼーションモデル機能を使用します。

レポートグループを使用する場合、 [!DNL Target] は、そのグループ内のすべてのオファーのデータを使用して、各レポートグループに対して 1 つのパーソナライゼーションモデルを作成します。 レポートグループがない場合、 [!DNL Target] は、AP アクティビティの各オファーに対してパーソナライゼーションモデルを作成します。

アクティビティの設定で、オファーごとに作成するのに十分なデータがない場合、レポートグループは、 [!UICONTROL Automated Personalization]. また、レポートグループは、類似するオファーをグループ化して新しいオファーの「コールドスタート」の問題を解決することもできるので、各モデルはより多くのデータを得ることができます。モデリンググループは、AP アクティビティに新しいオファーが定期的に導入されるアクティビティにも使用できます。

この方法は、訪問者がグループ内のすべてのオファーに同じ方法で応答する場合に便利です。ベストプラクティスは、類似する訪問者グループが同様の方法で応答するオファーをグループ化することです。つまり、同様のコンバージョン率を持つオファーをグループ化します。すべてのオファーを 1 つのレポートグループに入れるのは避けてください。すべてのオファーをグループ化するか、コンバージョン率が非常に異なるオファーをグループ化すると、 [!DNL Target] パーソナライゼーションモデル。

>[!NOTE]
>
>オファーが特定のモデリンググループから削除または置換されると、その特定のオファーをモデリンググループからも削除した履歴トラフィックが表示されます。つまり、削除されたオファーは、 [!DNL Target] パーソナライゼーションモデルを参照してください。

**レポートグループを設定するには：**

1. の **[!UICONTROL エクスペリエンス]** AP アクティビティのページで、 **[!UICONTROL コンテンツを管理]** アイコン

   ![コンテンツを管理アイコン](/help/main/c-reports/assets/ap_manage_content.png)

1. 「**[!UICONTROL Manage Content]**」ダイアログボックス上部の「[!UICONTROL Offers]」タブをクリックします。
1. （条件付き）特定のオファーにマウスポインターを置いてから **[!UICONTROL Reporting Group]** のフォルダーアイコンをクリックして、特定のエクスペリエンスをレポートグループに追加します。

   ![レポートグループアイコン](/help/main/c-reports/assets/ap_manage_content_2.png)

1. （条件付き）複数のエクスペリエンスのチェックボックスをオンにしてからダイアログボックスの右上隅にある **[!UICONTROL Reporting Group]** のフォルダーアイコンをクリックして、エクスペリエンスを一括でレポートグループに追加します。

   ![レポートグループアイコン](/help/main/c-reports/assets/ap_manage_content_3.png)

1. 選択したオファーを既存のレポートグループに割り当てるには、「**[!UICONTROL 既存]**」を選択し、ドロップダウンリストから目的のレポートグループを選択して、「**[!UICONTROL 適用]**」をクリックします。

   または

   選択したオファーをアサインする新しいレポートグループを作成するには、 「**[!UICONTROL 新規]**」を選択し、新しいレポートグループに名前を付けて、「**[!UICONTROL 適用]**」をクリックします。

   ![新しいレポートグループを作成するための新しいアイコン](/help/main/c-reports/assets/ap_reporting_groups.png)
