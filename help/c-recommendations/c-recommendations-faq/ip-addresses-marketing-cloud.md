---
keywords: IPアドレス；IPアドレス；ホワイトリスト；許可リスト；ファイアウォール；recs；フィード；サーバー；adobe marketing cloud;recommendations
description: ターゲットRecommendationsのフィード処理サーバーで使用されるIPアドレスのリストを表示し、Adobeサーバーから送信されるIPアドレスを許可するようにファイアウォールを設定します。
title: Recommendationsのフィード処理サーバーが使用するIPアドレス
feature: Recommendations
translation-type: tm+mt
source-git-commit: 55b246f5f0d660e6c4f71352c5b638347d55ac28
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 13%

---


# ![PREMIUM](/help/assets/premium.png) Recommendations フィード処理サーバーで使用される IP アドレス

[!DNL Adobe Target] [!DNL Recommendations]フィード処理サーバーで使用されるIPアドレスのリスト。AdobeサーバーからのIPアドレスを許可するようにファイアウォールを設定する場合に役立ちます。

[!DNL Target]  Recommendationsアクティビティでは、お客様のFTPサーバーにアクセスする際に、次のIPアドレスを使用します。

| CIDR 表記 |
|---|
| 44.241.237.28/32 |
| 44.232.167.82/32 |
| 52.41.252.205/32 |

[!DNL Target]  RecommendationsAPIは次のIPアドレスを使用します。

| CIDR 表記 |
|---|
| 44.241.237.28/32 |
| 44.232.167.82/32 |
| 52.41.252.205/32 |

>[!NOTE]
>
>これらのIPアドレスは、2021年3月16日に最終更新されました。 以前は、FTPサーバーにアクセスするサーバーは、192.243.242.0/24 IPアドレスCIDRブロックにありました。 RecommendationsAPIをホストするサーバーは、192.243.224.0/20のIPアドレスCIDRブロックに含まれていました。

