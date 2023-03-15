---
keywords: Automated Personalization；オファー；ターゲット；オーディエンス；ターゲット設定ルール；ターゲット設定
description: Adobe TargetのAutomated Personalization(AP) アクティビティを使用して、個々のオファーを特定のオーディエンスにターゲット設定する方法について説明します。
title: 使用方法 [!DNL Target] Automated Personalization?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 87%

---

# [!DNL Target] Automated Personalizationオファー

内 [!DNL Adobe Target] [!DNL Automated Personalization] (AP) アクティビティでは、特定のオーディエンスに対してオファーをターゲット設定できます。

この機能を使用すると、特定の訪問者が閲覧できるオファーの数を減らすことができます。例えば、3 つのオファーを含む AP アクティビティがあるとします。オファー 1 には、表示をオーディエンス A に限定するターゲットルールがあります。この AP アクティビティを 2 人の訪問者が閲覧します。

|  | 訪問者 1 | 訪問者 2 |
|--- |--- |--- |
| オーディエンス資格認定 | オーディエンス A | オーディエンス B |
| オファー 1 Target パーソナライゼーションモデルスコア | 90 | 90 |
| オファー 2 Target パーソナライゼーションモデルスコア | 50 | 70 |
| オファー 3 Target パーソナライゼーションモデルスコア | 80 | 60 |

このシナリオでは、訪問者 1は（オーディエンス A に属すると認定されているので）、オファー 1 を閲覧します。それがこの訪問者の最高スコアになります。一方、訪問者 2 は（オーディエンス A に属していないので）、オファー 1 の場合に最高スコアになるとしても、オファー 2 を閲覧します。この例は、ビジネスニーズに応えるにはターゲットルールを慎重に使用する必要がある理由を示しています。これらのルールを追加すると、Target のパーソナライゼーションモデルの有効性が弱まるおそれがあります。

## ターゲット設定ルールの設定

1. ターゲット設定したいオファーを含む[Automated Personalizationアクティビティ](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)を作成します。
1. Visual Experience Composer でアクティビティのオファーを設定したら、「**[!UICONTROL コンテンツを管理]**」をクリックします。

   ![コンテンツを管理](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   コンテンツを管理ダイアログボックスが開きます。

1. 「オファー」タブをクリックします。

   ![オファーページ](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. 目的のオファーを選択して、そのオファーを閲覧する資格を与えたいオーディエンスを選択します。

   1 つのオファー用にターゲットを設定するには、目的のオファーの上にマウスポインターを置いてから、「**[!UICONTROL ターゲット設定]**」アイコンをクリックします。

   複数のオファー用にターゲットを設定するには、目的のオファーのチェックボックスをオンにしてから、リストの右上に表示される **「[!UICONTROL ターゲット]」アイコンをクリックします。

1. [!UICONTROL オーディエンスを選択]ダイアログボックスで、オファー用の目的のオーディエンスを選択してから、「**[!UICONTROL 完了]**」をクリックして[!UICONTROL コンテンツを管理]ダイアログボックスに戻ります。

   >[!NOTE]
   >
   >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

1. 「 **[!UICONTROL 完了]**」をクリックします。

>[!NOTE]
>
>場所は 50 か所を設定でき、場所ごとに最大 250 個のオファーを設定できます。
