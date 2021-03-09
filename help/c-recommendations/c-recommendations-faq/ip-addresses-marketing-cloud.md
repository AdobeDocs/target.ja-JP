---
keywords: IPアドレス；IPアドレス；ホワイトリスト；許可リスト；ファイアウォール；recs；フィード；サーバー；adobe marketing cloud;recommendations
description: ターゲットRecommendationsのフィード処理サーバーで使用されるIPアドレスのリストを表示し、Adobeサーバーから送信されるIPアドレスを許可するようにファイアウォールを設定します。
title: Recommendationsのフィード処理サーバーが使用するIPアドレス
feature: Recommendations
translation-type: tm+mt
source-git-commit: 801a2717615a1f0ff2ce306cda59f68cc5c4a8f8
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 15%

---


# ![PREMIUM](/help/assets/premium.png) Recommendations フィード処理サーバーで使用される IP アドレス

Oregonデータセンターの[!DNL Adobe Target] [!DNL Recommendations]フィード処理サーバーで使用されるIPアドレスのリスト。AdobeサーバーからのIPアドレスを許可するようにファイアウォールを設定するのに役立ちます。

[!DNL Target]  Recommendationsアクティビティでは、お客様のFTPサーバーにアクセスする際に、Oregonデータセンターで以下のIPアドレスを使用します（最新情報については、下のリンクを必ず確認してください）。

| CIDR 表記 | 開始 IP | 終了 IP |
|---|---|---|
| 192.243.242.0/24 | 192.243.242.0 | 192.243.242.255 |

[!DNL Target]  RecommendationsAPIはOregonデータセンターで次のIPアドレスを使用します（最新の情報については、下のリンクを必ず確認してください）。

| CIDR 表記 | 開始 IP | 終了 IP |
|---|---|---|
| 192.243.224.0/20 | 192.243.224.0 | 192.243.239.255 |

>[!NOTE]
>
>完全で最新のリストについては、[Adobe Experience Cloud](https://helpx.adobe.com/analytics/kb/adobe-ip-addresses.html)で使用されているIPアドレスを参照してください。

