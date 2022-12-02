---
keywords: IP アドレス;IP アドレス;許可リスト;ファイアウォール;recs;フィード;サーバー;Adobe Experience Cloud;Recommendations
description: ' [!DNL Target]  Recommendations のフィード処理サーバーで使用される IP アドレスのリストが表示されるので、アドビのサーバーから生じる IP アドレスを許可するようにファイアウォールを設定する際に役立ちます。'
title: Recommendations のフィード処理サーバーが使用する IP アドレス
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 100%

---

# ![PREMIUM](/help/main/assets/premium.png) Recommendations フィード処理サーバーで使用される IP アドレス

[!DNL Adobe Target] [!DNL Recommendations]のフィード処理サーバーで使用される IP アドレスのリストが表示されるので、アドビのサーバーから生じる IP アドレスを許可するようにファイアウォールを設定する際に役立ちます。

[!DNL Target] [!UICONTROL Recommendations] アクティビティでは、顧客の FTP サーバーにアクセスする際に、以下の AWS ホストを使用します。

| 場所 | ホスト |
| --- | --- |
| オレゴン | `44.241.237.28` |
| オレゴン | `44.232.167.82` |
| オレゴン | `52.41.252.205` |

[!DNL Target] [!UICONTROL Recommendations] API も同じ AWS ホストを使用します。

>[!NOTE]
>
>これらの IP アドレスの最終更新日は、2021 年 3 月 16 日（PT）です。 以前は、FTP サーバーにアクセスするサーバーは、192.243.242.0/24 の IP アドレスの CIDR ブロックにありました。 Recommendations API をホストするサーバーは、192.243.224.0/20 の IP アドレスの CIDR ブロックに含まれていました。
