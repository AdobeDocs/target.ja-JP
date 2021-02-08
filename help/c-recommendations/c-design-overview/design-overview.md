---
keywords: レコメンデーションのデザイン;テンプレート;デザインの作成;配信;出力
description: Adobe TargetRecommendationsのデザインを使用して、レコメンデーションがページ上でどのように表示されるかを定義する方法を説明します（1X4、1X6、2X2など）。
title: Recommendationsのデザインの使い方
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 32%

---


# デザインの概要{#design-overview}

[!DNL Adobe Target Recommendations]のデザインは、レコメンデーションがページ上でどのように表示されるかを定義します。 デザインは、レコメンデーションのレイアウトと形式を定義して、訪問者の関与、コンバージョン、売上高を改善します。

[!DNL Recommendations] にはいくつかのデフォルト（ビルド前）のデザインが付属していますが、独自のデザインを作成することもできます。

[!DNL Target] では、次の画像のように、レコメンデーションの詳細なデザインを配信できます。このデザインには HTML、JavaScript、CSS などが含まれます。この設計は4 x 1設計と呼ばれます。1行に4つのスペース。

![](assets/velocity_example.png)

Target では、電子メールメッセージ、IoT（モノのインターネット）デバイス、コンソール、音声サービス（Amazon Alexa または Google Home）の用途で利用できる JSON オブジェクトとしてレコメンデーションを送信することもできます。

デザインは、次の事項を決定するのに役立ちます。

* レコメンデーションに表示する品目の数
* 行、列、グリッド、またはテーブル内の項目の表示方法
* 訪問者の表示数を指定した数に制限するか、訪問者が複数の項目をスクロールできるようにするかを指定します。

