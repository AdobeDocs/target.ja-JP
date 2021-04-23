---
keywords: IPアドレス；IPアドレス；ホワイトリスト；許可リスト；ファイアウォール；recs；フィード；サーバー；adobe marketing cloud;recommendations
description: ' [!DNL Target] Recommendationsフィード処理サーバーで使用するIPアドレスのリストを表示し、Adobeサーバーから送信されるIPアドレスを許可するようにファイアウォールを設定するのに役立ちます。'
title: Recommendationsのフィード処理サーバーが使用するIPアドレス
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 8%

---

# ![PREMIUM](/help/assets/premium.png) Recommendations フィード処理サーバーで使用される IP アドレス

[!DNL Adobe Target] [!DNL Recommendations]フィード処理サーバーで使用されるIPアドレスのリスト。AdobeサーバーからのIPアドレスを許可するようにファイアウォールを設定する場合に役立ちます。

[!DNL Target]  Recommendationsアクティビティは、お客様のFTPサーバーにアクセスする際に、以下のAWSホストを使用します。

| 場所 | ホスト |
| --- | --- |
| オレゴン | `44.241.237.28` |
| オレゴン | `44.232.167.82` |
| オレゴン | `52.41.252.205` |

[!DNL Target]  RecommendationsAPIも同じAWSホストを使用します。

>[!NOTE]
>
>これらのIPアドレスは、2021年3月16日に最終更新されました。 以前は、FTPサーバーにアクセスするサーバーは、192.243.242.0/24 IPアドレスCIDRブロックにありました。 RecommendationsAPIをホストするサーバーは、192.243.224.0/20のIPアドレスCIDRブロックに含まれていました。
