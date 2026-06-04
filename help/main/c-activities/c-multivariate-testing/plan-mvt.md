---
keywords: 多変量分析テスト;mvt;mvt プラン;多変量分析テストプラン
description: ' [!DNL Adobe Target] で[!UICONTROL 多変量テスト &#x200B;]を計画して、テストを成功させる方法を説明します。'
title: '[!UICONTROL 多変量テスト &#x200B;]を計画するにはどうすればよいですか？'
feature: Multivariate Tests
exl-id: 130718d5-7bd9-4b1a-b81a-7a146f0ffd0d
TQID: https://experienceleague.adobe.com/Fg9jOrPlkLxpbJdG-AKoWHD3YvIGEJPu7Os-RdfXvQA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 295
ht-degree: 63%

---

# [!UICONTROL 多変量テストの計画]

[!DNL Adobe Target]の[!UICONTROL 多変量テスト &#x200B;] （MVT）アクティビティでは、テストを成功させるためにいくつかの計画が必要です。

MVTでは、有益な結果を生成するのに十分なトラフィックが必要です。 テストを設定する前に、インプレッションおよびコンバージョンの数を含む、通常発生するトラフィック量を把握しておく必要があります。 このような情報があれば、サイトのトラフィックを上回る要件を満たすテストを設計する可能性を減らすことができます。

要素は互いに独立しています。 例えば、同じテスト内でレイアウトとコンテンツをテストしないでください。

テストするページのHTML コードを調べます。 サイトの HTML 要素が重複する DOM ID を持っていないことを確認します。 重複した ID を持っていると、同じコンテンツが複数の場所に配信されることがあります。

有意な結果を生むと考えられる、ページ上の要素をテストするよう計画します。 例えば、バナーやヒーロー画像は、フッターを変更するよりも多くのコンバージョンにつながる可能性があります。 テストに効果の低い要素を組み込むと、ページ上のより効果の高い要素をテストするのに必要なトラフィック量や時間が増えることになります。

最後に、テストを作成する前に、テストするコンテンツを作成する必要があります。 各オファーのコンテンツの差異を把握し、テストで使用する画像、テキストおよび HTML オファーを作成します。

## トレーニングビデオ：多変量テストの作成（9:25） ![&#x200B; チュートリアルバッジ &#x200B;](/help/main/assets/tutorial.png)

このビデオでは、[!DNL Target] 3段階のガイド付きワークフローを使用して、多変量テストを計画および作成する方法を説明します。

* 多変量分析テストの定義と設計
* 多変量分析テストの作成

>[!VIDEO](https://video.tv.adobe.com/v/29957?captions=jpn)
