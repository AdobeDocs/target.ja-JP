---
keywords: レコメンデーションのデザイン;テンプレート;デザインの作成;配信;出力
description: Adobe [!DNL Target] Recommendationsでデザインを使用して、レコメンデーションがページ上でどのように表示されるかを定義する方法を説明します（1X4、1X6、2X2 など）。
title: Recommendationsでのデザインの使用方法
feature: Recommendations
exl-id: 348b1d77-49c9-4a6b-ba85-7ba051713d5b
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 19%

---

# デザインの概要

[!DNL Adobe Target Recommendations] のデザインは、ページ上でのレコメンデーションの表示方法を定義します。 デザインは、訪問者のエンゲージメント、コンバージョンおよび売上高を向上させるために、レコメンデーションのレイアウトと形式を定義します。

[!DNL Recommendations] くつかのデフォルト（ビルド前）デザインが用意されていますが、独自のデザインを作成することもできます。

次の図に示 [!DNL Target] ように、レコメンデーションの完全なルックアンドフィールを提供できます。 デザインには、HTML、JavaScript、CSS を含めることができます。 このデザインは 4 x 1 デザインと呼ばれ、1 行に 4 つのスペースがあります。

![velocity_example 画像 ](assets/velocity_example.png)

Target では、電子メールメッセージ、IoT（モノのインターネット）デバイス、コンソール、音声サービス（Amazon Alexa または Google Home）の用途で利用できる JSON オブジェクトとしてレコメンデーションを送信することもできます。

デザインは、次の項目を判断するのに役立ちます。

* レコメンデーションに表示する項目数
* 項目の表示方法（行、列、グリッド、またはテーブル）
* 指定した数の項目のみを表示するように訪問者を制限するか、複数の項目をスクロールできるようにするか。
