---
keywords: 自動パーソナライゼーション；オファー；ターゲット；オーディエンス；ターゲティングルール；ターゲティング
description: ' [!DNL Adobe Target]の[!UICONTROL Automated Personalization] （AP）アクティビティを使用して、特定のオーディエンスに個別のオファーをターゲティングする方法について説明します。'
title: '[!UICONTROL Automated Personalization]のオファーをターゲットにするにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 30%

---

# [!UICONTROL Automated Personalization]件のオファーをターゲット

[!DNL Adobe Target] [!DNL Automated Personalization] （AP）アクティビティでは、特定のオーディエンスに対するオファーをターゲットにできます。

この機能を使用すると、特定の訪問者が閲覧できるオファーの数を減らすことができます。 例えば、3つのオファーを持つ[!UICONTROL Automated Personalization] アクティビティを考えてみましょう。 オファー1には、オーディエンス Aへの露出を制限するターゲティングルールがあります。2人の訪問者がこのアクティビティを見ました。

| | 訪問者 1 | 訪問者 2 |
|--- |--- |--- |
| オーディエンスの選定 | オーディエンス A | オーディエンス B |
| オファー 1 Target パーソナライゼーションモデルスコア | 90 | 90 |
| オファー 2 Target パーソナライゼーションモデルスコア | 50 | 70 |
| オファー 3 Target パーソナライゼーションモデルスコア | 80 | 60 |

このシナリオでは、訪問者1はオファー1を見ます（この訪問者はオーディエンス Aの一部として適格であるため）。これは、その訪問者の最高スコアです。 ただし、訪問者2はオーディエンス Aに含まれていないため、訪問者2はオファー1のスコアが最も高くなってもオファー2を見ます。この例では、ターゲティングルールをビジネスニーズに合わせて控えめに使用すべき理由を示しています。 これらのルールを追加すると、[!DNL Target]個のパーソナライゼーションモデルの効果を低下させることができます。

## ターゲティングルールの設定

1. ターゲットにするオファーを含む[Automated Personalization アクティビティ ](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)を作成します。
1. [!UICONTROL Visual Experience Composer]でアクティビティのオファーを設定したら、**[!UICONTROL コンテンツの管理]**&#x200B;をクリックします。

   ![コンテンツを管理](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   [!UICONTROL  コンテンツの管理] ダイアログボックスが表示されます。

1. 「**[!UICONTROL オファー]**」タブをクリックします。

   ![オファーページ](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. 必要なオファーを選択し、そのオファーを表示する対象のオーディエンスを選択します。

   1つのオファーのターゲティングを設定するには、目的のオファーにカーソルを合わせ、**[!UICONTROL ターゲティング]** アイコンをクリックします。

   複数のオファーのターゲティングを設定するには、目的のオファーのチェックボックスを選択し、リストの右上に表示される&#x200B;**[!UICONTROL ターゲティング]** アイコンをクリックします。

1. [!UICONTROL  オーディエンスを選択] ダイアログボックスで、オファーに必要なオーディエンスを選択し、**[!UICONTROL 完了]**&#x200B;をクリックして[!UICONTROL  コンテンツを管理] ダイアログボックスに戻ります。

   >[!NOTE]
   >
   >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。 詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

1. 「**[!UICONTROL Done]**」をクリックします。

>[!NOTE]
>
>場所は 50 か所を設定でき、場所ごとに最大 250 個のオファーを設定できます。
