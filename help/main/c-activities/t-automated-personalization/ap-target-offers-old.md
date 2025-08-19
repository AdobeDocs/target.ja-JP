---
keywords: automated personalization；オファー；ターゲット；オーディエンス；ターゲティングルール；ターゲティング
description: '[!UICONTROL Automated Personalization] の  [!DNL Adobe Target] （AP）アクティビティを使用して、特定のオーディエンスに対して個々のオファーをターゲットにする方法を説明します。'
title: '[!UICONTROL Automated Personalization] のオファーをターゲットにするにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 30%

---

# Target [!UICONTROL Automated Personalization] オファー

[!DNL Adobe Target] [!DNL Automated Personalization] （AP）アクティビティで、特定のオーディエンスに対してオファーをターゲット設定できます。

この機能を使用すると、特定の訪問者が閲覧できるオファーの数を減らすことができます。例えば、3 つのオファーを持つ [!UICONTROL Automated Personalization] アクティビティについて考えてみましょう。 オファー 1 には、オーディエンス A への露出を制限するターゲティングルールがあります。このアクティビティは 2 人の訪問者が閲覧しました。

| | 訪問者 1 | 訪問者 2 |
|--- |--- |--- |
| オーディエンスの選定 | オーディエンス A | オーディエンス B |
| オファー 1 Target パーソナライゼーションモデルスコア | 90 | 90 |
| オファー 2 Target パーソナライゼーションモデルスコア | 50 | 70 |
| オファー 3 Target パーソナライゼーションモデルスコア | 80 | 60 |

このシナリオでは、訪問者 1 は（この訪問者はオーディエンス A の一部と認定されるため）、その訪問者の最高スコアであるオファー 1 を表示します。 ただし、訪問者 2 はオーディエンス A に含まれていないので、最も高いスコアがオファー 1 に関するものであっても、訪問者 2 にはオファー 2 が表示されます。この例は、ビジネスニーズを満たすためにターゲティングルールを慎重に使用する理由を示しています。 これらのルールを追加すると、パーソナライゼーションモデルの効果 [!DNL Target] 低下する可能性があります。

## ターゲット設定ルールの設定

1. ターゲット設定したいオファーを含む [0}Automated Personalization アクティビティ } を作成します。](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)
1. [!UICONTROL Visual Experience Composer] ール内のアクティビティに対してオファーを設定したら、「設 **[!UICONTROL Manage Content]**」をクリックします。

   ![コンテンツを管理](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   [!UICONTROL Manage Content] ダイアログボックスが表示されます。

1. 「**[!UICONTROL Offers]**」タブをクリックします。

   ![オファーページ](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. 目的のオファーを選択し、そのオファーを表示するために選定するオーディエンスを選択します。

   1 つのオファーに対してターゲティングを設定するには、目的のオファーにポインタを合わせて、「**[!UICONTROL Targeting]**」アイコンをクリックします。

   複数のオファーに対してターゲティングを設定するには、目的のオファーのチェックボックスを選択し、リストの右上に表示される **[!UICONTROL Targeting]** アイコンをクリックします。

1. [!UICONTROL Choose Audience] ダイアログボックスで、オファーに必要なオーディエンスを選択し、「**[!UICONTROL Done]**」をクリックして [!UICONTROL Manage Content] ダイアログボックスに戻ります。

   >[!NOTE]
   >
   >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

1. **[!UICONTROL Done]** をクリックします。

>[!NOTE]
>
>場所は 50 か所を設定でき、場所ごとに最大 250 個のオファーを設定できます。
