---
keywords: 自動パーソナライゼーション；オファー；ターゲット；オーディエンス；ターゲティングルール；ターゲティング
description: '[!UICONTROL Automated Personalization] （AP）アクティビティを使用して、特定のオーディエンスに個別のオファーをターゲティングする方法について説明します。'
title: '[!UICONTROL Automated Personalization]のオファーをターゲットにするにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
TQID: 'https://experienceleague.adobe.com/AVqyD-Von-gzuVXC09N9qHY5hEe1QLQwSavCE0mp7Ok'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 7eede3484d524e87127de9147aa786484fc87c7d
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 12%
---
# [!UICONTROL Automated Personalization]件のオファーをターゲット {#target-ap-offers}

>[!BEGINSHADEBOX]

**このページ：** **[!UICONTROL Automated Personalization]** アクティビティで、特定のオーディエンスに対する個々のオファーをターゲティングする方法について説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target] **[!UICONTROL Automated Personalization]** （AP）アクティビティでは、ターゲティングルールを使用してオファーを特定のオーディエンスに制限し、それらのオーディエンスに属する訪問者のみが表示できるようにします。 ターゲティングルールは、訪問者が参照できるオファーの数を減らし、[!DNL Target] パーソナライゼーションモデルの効果を低下させる可能性があるため、ターゲティングルールを控えめに使用し、ビジネスが必要とする場合にのみ使用します。

例えば、3つのオファーを持つAP アクティビティを考えてみましょう。 オファー1には、オーディエンス Aへの露出を制限するターゲティングルールがあります。2人の訪問者がこのアクティビティを見ています。

| | 訪問者 1 | 訪問者 2 |
|--- |--- |--- |
| オーディエンスの選定 | オーディエンス A | オーディエンス B |
| オファー1 [!DNL Target] パーソナライゼーションモデルスコア | 90 | 90 |
| オファー2 [!DNL Target] パーソナライゼーションモデルスコア | 50 | 70 |
| オファー3 [!DNL Target] パーソナライゼーションモデルスコア | 80 | 60 |

訪問者1はオーディエンス Aの一部として認定されるので、この訪問者には最もスコアの高いオファー1が表示されます。 訪問者2はオーディエンス Aに含まれていないので、この訪問者はオファー1のスコアが最も高いにもかかわらず、オファー2を見ることができます。

## ターゲティングルールの設定 {#set-up-targeting-rules}

<a id="task_F207ED7A41B84FD39BB6FCBFABF4B23E"></a>

オーディエンスのターゲティングルールにより、訪問者が各オファーを確認できるようにし、顧客セグメントに対するオファーの予約など、特定のビジネスニーズに対応できるようにします。 すべてのルールは、パーソナライゼーションモデルの選択肢を絞り込むため、ルールは、それらを必要とするオファーにのみ適用されます。

1. ターゲットにするオファーを含む[Automated Personalization アクティビティ ](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)を作成または編集します。

   場所は 50 か所を設定でき、場所ごとに最大 250 個のオファーを設定できます。

1. **[!UICONTROL Visual Experience Composer]**&#x200B;でアクティビティのオファーを設定したら、**[!UICONTROL コンテンツの管理]** アイコン（![ コンテンツの管理アイコン ](/help/main/assets/icons/Experience.svg)）をクリックします。 **[!UICONTROL コンテンツの管理]** ダイアログボックスが表示されます。

   ![ コンテンツの管理アイコン ](../assets/ap-offers-1.png)

1. 「**[!UICONTROL オファー]**」タブをクリックします。

1. ターゲットにするオファーを選択し、そのオファーを受け取る対象となるオーディエンスを選択します。

   * 1つのオファーのターゲティングを設定するには、オファーの横にある詳細情報（![詳細情報アイコン ](/help/main/assets/icons/MoreSmallList.svg)）アイコンをクリックし、**[!UICONTROL ターゲットオーディエンス]**&#x200B;をクリックして、**[!UICONTROL オーディエンスを追加]** ダイアログボックスを表示します。
   * 複数のオファーのターゲティングを設定するには、オファーのチェックボックスを選択し、リストの下部に表示される&#x200B;**[!UICONTROL ターゲットオーディエンス]** リンクをクリックします。

   ![ コンテンツの管理アイコン ](../assets/ap-offers-2.png)

1. **[!UICONTROL オーディエンスを追加]** ダイアログボックスで、オファーのオーディエンスを選択し、**[!UICONTROL オーディエンスを割り当て]**&#x200B;をクリックして、**[!UICONTROL コンテンツを管理]** ダイアログボックスに戻ります。

   >[!NOTE]
   >
   >新しいオーディエンスを作成する代わりに、複数のオーディエンスを既存のオーディエンスと組み合わせて、オンデマンドで組み合わせたオーディエンスを作成できます。 詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md)を参照してください。

1. 「**[!UICONTROL Done]**」をクリックします。

ターゲティングルールが選択したオファーに適用されるようになったため、割り当てられたオーディエンスに属する訪問者のみがターゲティングルールを表示できるようになりました。
