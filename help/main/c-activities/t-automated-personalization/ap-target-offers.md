---
keywords: Automated Personalization；オファー；ターゲット；オーディエンス；ターゲット設定ルール；ターゲット設定
description: を使用して、個々のオファーを特定のオーディエンスにターゲット設定する方法を説明します。 [!UICONTROL Automated Personalization] (AP) でのアクティビティ [!DNL Adobe Target].
title: ターゲット設定の方法 [!UICONTROL Automated Personalization] オファー？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: eacee6f353aa685d17b781ac82d3f79574384dfe
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 38%

---

# Target [!UICONTROL Automated Personalization] オファー

内、 [!DNL Adobe Target] [!DNL Automated Personalization] (AP) アクティビティでは、特定のオーディエンスに対してオファーをターゲット設定できます。

この機能を使用すると、特定の訪問者が閲覧できるオファーの数を減らすことができます。例えば、 [!UICONTROL Automated Personalization] 3 つのオファーを持つアクティビティ。 オファー 1 には、表示をオーディエンス A に限定するターゲットルールがあります。この アクティビティを 2 人の訪問者が閲覧します。

| | 訪問者 1 | 訪問者 2 |
|--- |--- |--- |
| オーディエンスの選定 | オーディエンス A | オーディエンス B |
| オファー 1 Target パーソナライゼーションモデルスコア | 90 | 90 |
| オファー 2 Target パーソナライゼーションモデルスコア | 50 | 70 |
| オファー 3 Target パーソナライゼーションモデルスコア | 80 | 60 |

このシナリオでは、訪問者 1 にはオファー 1 が表示されます（この訪問者はオーディエンス A の一部として認定されるので）。これは、訪問者の最高スコアです。 ただし、訪問者 2 はオーディエンス A に含まれていないので、最も高いスコアがオファー 1 であるにもかかわらず、訪問者 2 にはオファー 2 が表示されます。この例では、ビジネスニーズを満たすためにターゲットルールを慎重に使用する必要がある理由を示します。 これらのルールを追加すると、 [!DNL Target] パーソナライゼーションモデル。

## ターゲット設定ルールの設定

1. の作成 [Automated Personalizationアクティビティ](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) ターゲットに設定するオファーを含む。
1. アクティビティのオファーを [!UICONTROL Visual Experience Composer]をクリックし、 **[!UICONTROL コンテンツを管理]**.

   ![コンテンツを管理](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   The [!UICONTROL コンテンツを管理] ダイアログボックスが表示されます。

1. 次をクリック： **[!UICONTROL オファー]** タブをクリックします。

   ![オファーページ](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. 目的のオファーを選択してから、そのオファーを閲覧する資格を与えたいオーディエンスを選択します。

   1 つのオファー用にターゲットを設定するには、目的のオファーの上にマウスポインターを置いてから、「**[!UICONTROL ターゲット設定]**」アイコンをクリックします。

   複数のオファーのターゲティングを設定するには、目的のオファーのチェックボックスをオンにしてから、 **[!UICONTROL ターゲット設定]** リストの右上に表示されるアイコン。

1. Adobe Analytics の [!UICONTROL オーディエンスを選択] ダイアログボックスで、オファーに使用するオーディエンスを選択し、 **[!UICONTROL 完了]** に戻る [!UICONTROL コンテンツを管理] ダイアログボックス。

   >[!NOTE]
   >
   >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

1. 「 **[!UICONTROL 完了]**」をクリックします。

>[!NOTE]
>
>場所は 50 か所を設定でき、場所ごとに最大 250 個のオファーを設定できます。
