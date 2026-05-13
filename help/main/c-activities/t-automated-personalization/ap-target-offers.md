---
keywords: 自動パーソナライゼーション；オファー；ターゲット；オーディエンス；ターゲティングルール；ターゲティング
description: '[!UICONTROL Automated Personalization] （AP）アクティビティを使用して、特定のオーディエンスに個々のオファーをターゲティングする方法について説明します。'
title: '[!UICONTROL Automated Personalization]件のオファーをターゲットするにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
TQID: https://experienceleague.adobe.com/AVqyD-Von-gzuVXC09N9qHY5hEe1QLQwSavCE0mp7Ok
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 380
ht-degree: 24%

---

# ターゲット [!UICONTROL Automated Personalization]のオファー

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

1. ターゲットにするオファーを含む[Automated Personalization アクティビティ &#x200B;](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)を作成または編集します。
1. [!UICONTROL Visual Experience Composer]でアクティビティのオファーを設定したら、**[!UICONTROL Manage Content]** アイコン（![&#x200B; コンテンツの管理アイコン &#x200B;](/help/main/assets/icons/Experience.svg)）をクリックします。

   [!UICONTROL Manage Content] ダイアログボックスが表示されます。

1. 「**[!UICONTROL Offers]**」タブをクリックします。

1. 必要なオファーを選択し、そのオファーを表示する対象のオーディエンスを選択します。

   1つのオファーのターゲティングを設定するには、目的のオファーの横にある詳細情報（![詳細情報アイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）アイコンをクリックし、**[!UICONTROL Target Audience]**&#x200B;をクリックして[!UICONTROL Add Audiences] ダイアログボックスを表示します。

   複数のオファーのターゲティングを設定するには、目的のオファーのチェックボックスを選択し、リストの下部に表示される&#x200B;**[!UICONTROL Target Audience]** リンクをクリックします。

1. [!UICONTROL Add Audiences] ダイアログボックスで、オファーに必要なオーディエンスを選択し、**[!UICONTROL Assign Audience]**&#x200B;をクリックして[!UICONTROL Manage Content] ダイアログボックスに戻ります。

   >[!NOTE]
   >
   >既存のオーディエンスを選択するだけでなく、複数のオーディエンスを組み合わせて、新しいオーディエンスを作成するのではなく、オンデマンドで組み合わされたオーディエンスを作成できます。 詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

1. **[!UICONTROL Done]** をクリックします。

>[!NOTE]
>
>場所は 50 か所を設定でき、場所ごとに最大 250 個のオファーを設定できます。
