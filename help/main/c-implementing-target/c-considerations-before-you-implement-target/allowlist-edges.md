---
keywords: 実装；実装する；ホワイトリスト；ホワイトリスト；許可リスト;許可リスト；エッジ；エッジ
description: ホストのリストを表示してAdobeを許可リスト [!DNL Target] エッジ（エンドユーザーの応答時間を最適化する、地理的に分散された配信ノード）
title: 方法をす許可リストる [!DNL Target] エッジノード？
feature: Privacy & Security
role: Developer
exl-id: 2d8399b9-eec8-40b0-8b35-2812f83ff4dc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# 許可リスト [!DNL Target] エッジノード

に役立つ、ホストの情報と最新のリスト許可リスト [!DNL Adobe Target] エッジ

エッジとは、コンテンツを要求するエンドユーザーが、その場所に関係なく、最適な応答時間を確保できる、地理的に分散された配信アーキテクチャです。 各エッジノードには、ユーザーのコンテンツリクエストに応答し、そのリクエストに関する分析データを追跡するために必要なすべての情報が含まれています。 ユーザーリクエストは最も近いエッジノードにルーティングされます。 詳しくは、 [エッジネットワーク](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934) in *Adobe [!DNL Target] 動作*.

次をでき許可リストます [!DNL Target] 必要に応じて、エッジノードに設定します。

## Network Address Translation（NAT；ネットワークアドレス変換）：の IP アドレス [!DNL Target] エッジ

のエグレス IP アドレスのリスト [!DNL Target] エッジ Target で許可リストサービスに連絡を取る予定がある場合は、これらの IP をします。

| エッジの位置 | エグレス IP アドレス |
| --- | --- |
| Edge31（ムンバイ） | 13.126.131.246<br>13.234.229.8 |
| Edge32（東京） | 3.115.154.28<br>3.115.227.146 |
| Edge34（米国東海岸） | 34.232.149.249<br>52.21.139.93 |
| Edge35（米国西海岸） | 52.10.11.139<br>44.231.171.161 |
| Edge36（シドニー） | 13.237.227.20<br>13.210.93.142 |
| Edge37（アイルランド） | 54.72.21.68<br>52.208.139.19 |
| Edge38（シンガポール） | 18.141.132.96<br>54.179.187.167 |

## Target エッジ IP アドレス

の IP アドレスのリスト [!DNL Target] エッジ Target エッ許可リストジに対して API 呼び出しをおこなう場合は、これらの IP をします。

| エッジの位置 | ドメイン | IP アドレス |
| --- | --- | --- |
|  | `CLIENTCODE.tt.omtrdc.net`<br>(CLIENTCODE は [!DNL Target] クライアント ID) |  |
| Edge31（ムンバイ） | `mboxedge31.tt.omtrdc.net` | 15.207.157.131<br>15.206.8.201 |
| Edge32（東京） | `mboxedge32.tt.omtrdc.net` | 54.199.66.101<br>54.64.93.37 |
| Edge34（米国東海岸） | `mboxedge34.tt.omtrdc.net` | 3.225.56.36<br>3.230.207.249<br>34.198.55.51<br>52.3.14.12<br>52.21.222.93<br>52.55.235.132<br>52.70.52.52<br>54.165.204.89 |
| Edge35（米国西海岸） | `mboxedge35.tt.omtrdc.net` | 52.10.244.20<br>52.36.232.38<br>52.88.209.29<br>54.214.180.56<br>35.162.74.35<br>34.214.12.211<br>52.42.35.202<br>54.148.71.13 |
| Edge36（シドニー） | `mboxedge36.tt.omtrdc.net` | 13.238.34.185<br>3.24.250.17<br>3.104.234.91<br>13.211.248.241 |
| Edge37（アイルランド） | `mboxedge37.tt.omtrdc.net` | 52.212.193.208<br>52.19.133.54<br>52.51.251.137<br>34.252.156.174<br>52.213.168.74<br>34.252.166.160<br>52.18.150.20<br>18.203.205.32 |
| Edge38（シンガポール） | `mboxedge38.tt.omtrdc.net` | 52.221.145.65<br>52.220.44.99<br>13.250.75.226<br>54.151.139.123 |