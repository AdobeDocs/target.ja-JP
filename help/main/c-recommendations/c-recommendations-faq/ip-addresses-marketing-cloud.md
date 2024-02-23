---
keywords: IP アドレス;IP アドレス;許可リスト;ファイアウォール;recs;フィード;サーバー;Adobe Experience Cloud;Recommendations
description: ' [!DNL Target]  Recommendations のフィード処理サーバーで使用される IP アドレスのリストが表示されるので、アドビのサーバーから生じる IP アドレスを許可するようにファイアウォールを設定する際に役立ちます。'
title: Recommendations のフィード処理サーバーが使用する IP アドレス
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: be5b3158c758fa08802c1dc0541c9e989a2c7740
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 51%

---

# が使用する IP アドレス [!DNL Recommendations] フィード処理サーバー

で使用される IP アドレスのリスト [!DNL Adobe Target] [!DNL Recommendations] フィード処理サーバーを使用して、次の場所から発生した IP アドレスを許可するようにファイアウォールを設定する [!DNL Adobe] サーバー。

>[!IMPORTANT]
>
>The [!DNL Target] チームは現在、ダウンロード用に NAT ゲートウェイアドレスを更新しています [!DNL Recommendations] フィード。 IP許可リストに加えるを実装する場合は、次の新しいAWSホ許可リストに加えるストを必ずしてください。 既存のホストは 2024 年 6 月 30 日に廃止される予定です。 スムーズな移行を実現するには、9 つのアド許可リストに加えるレスをすべてします。 既存のアドレスを削除する緊急度はありません。

[!DNL Target] [!UICONTROL Recommendations] アクティビティでは、顧客の FTP サーバーにアクセスする際に、以下の AWS ホストを使用します。

**新しいホスト**:

| 場所 | ホスト |
| --- | --- |
| オレゴン | `52.40.124.129` |
| オレゴン | `54.148.219.69` |
| オレゴン | `54.189.208.212` |
| オレゴン | `44.230.236.35` |
| オレゴン | `54.190.78.243` |
| オレゴン | `52.41.73.133` |

**既存のホスト**:

| 場所 | ホスト |
| --- | --- |
| オレゴン | `44.241.237.28` |
| オレゴン | `44.232.167.82` |
| オレゴン | `52.41.252.205` |

[!DNL Target] [!UICONTROL Recommendations] API も同じ AWS ホストを使用します。
