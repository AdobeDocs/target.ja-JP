---
keywords: IPアドレス；IPアドレス；ホワイトリスト；許可リスト；ファイアウォール；recs；フィード；サーバー；adobe marketing cloud;recommendations
description: ターゲットRecommendationsのフィード処理サーバーで使用されるIPアドレスのリストを表示し、Adobeサーバーから送信されるIPアドレスを許可するようにファイアウォールを設定します。
title: Recommendationsのフィード処理サーバーが使用するIPアドレス
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 61%

---


# ![PREMIUM](/help/assets/premium.png) Recommendations フィード処理サーバーで使用される IP アドレス{#ip-addresses-used-by-recommendations-feed-processing-servers}

ファイアウォールを設定してアドビサーバーからの IP アドレスを許可するのに役立つ、オレゴンデータセンターにある Recommendations フィード処理サーバーで使用される IP アドレスのリスト。

[!DNL Target][!UICONTROL  Recommendations] アクティビティは、顧客の FTP サーバーにアクセスする際に、オレゴンデータセンターにある以下の IP アドレスを使用します（最新情報については、下記のリンクを参照してください）。

| CIDR 表記 | 開始 IP | 終了 IP |
|---|---|---|
| 192.243.242.0/24 | 192.243.242.0 | 192.243.242.255 |

[!DNL Target][!UICONTROL  Recommendations] API は、オレゴンデータセンターにある以下の IP アドレスを使用します（最新情報については、下記のリンクを参照してください）。

| CIDR 表記 | 開始 IP | 終了 IP |
|---|---|---|
| 192.243.224.0/20 | 192.243.224.0 | 192.243.239.255 |

>[!NOTE]
>
>完全で最新のリストについては、[Adobe Experience Cloud](https://helpx.adobe.com/analytics/kb/adobe-ip-addresses.html)で使用されているIPアドレスを参照してください。

