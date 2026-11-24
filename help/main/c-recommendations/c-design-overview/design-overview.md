---
keywords: レコメンデーションのデザイン;テンプレート;デザインの作成;配信;出力
description: Adobe [!DNL Target] Recommendationsのデザインを使用して、レコメンデーションがページ上でどのように表示されるかを定義する方法（1X4、1X6、2X2など）について説明します。
title: デザインを始める
feature: Recommendations
exl-id: 348b1d77-49c9-4a6b-ba85-7ba051713d5b
TQID: 'https://experienceleague.adobe.com/08jboJLkp6MhgXiISjkVzh2kVze5DRrxO8BbQBFLeA4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: f9c9c7b2b78ec020fcabae420686b8955e350a0e
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 9%
---
# デザインを始める {#design-overview}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、デザインが[!DNL Adobe Target Recommendations]のレコメンデーションのレイアウトと形式をどのように定義しているかを説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target Recommendations]のデザインは、ページ上でのレコメンデーションの表示方法を定義します。 デザインは、レコメンデーションのレイアウトと形式を定義します。

[!DNL Recommendations]には、いくつかのデフォルト（事前定義済み）のデザインが付属しており、カスタムデザインも作成できます。 詳しくは、[デザインの作成](/help/main/c-recommendations/c-design-overview/create-design.md)を参照してください。

次の図に示すように、[!DNL Target]はレコメンデーションの完全な外観を提供できます。 このデザインには HTML、JavaScript、CSS などが含まれます。 このデザインは4 x 1のデザインと呼ばれています：1行に4つのスペース。

![写真、名前、価格、評価、距離を示す4つのアイテムを含む、「その他の楽しいアクティビティ」と題された4 x 1のデザインの例](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

[!DNL Target]は、電子メール メッセージ、IoT （モノのインターネット） デバイス、コンソール、または音声のユースケース （Amazon AlexaまたはGoogle ホーム）で使用できるJSON オブジェクトとしてレコメンデーションを送信することもできます。

デザインの決定：

* レコメンデーションに表示される項目の数
* 項目の表示方法（行、列、グリッドまたはテーブル内）
* 訪問者が指定された数の項目のみを表示するか、複数の項目をスクロールできるか
