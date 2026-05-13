---
keywords: IP アドレス;IP アドレス;許可リスト;ファイアウォール;recs;フィード;サーバー;Adobe Experience Cloud;レコメンデーション
description: ' [!DNL Target]  レコメンデーションのフィード処理サーバーで使用される IP アドレスのリストが表示されるので、アドビのサーバーから生じる IP アドレスを許可するようにファイアウォールを設定する際に役立ちます。'
title: レコメンデーションのフィード処理サーバーが使用する IP アドレス
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
TQID: https://experienceleague.adobe.com/-EhfjK6jTuHX33utQig-XYhf-nzkWlxb58VRmK9fLWo
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 66%

---

# [!DNL Recommendations]個のフィード処理サーバーで使用されるIP アドレス

[!DNL Adobe] サーバーからのIP アドレスを許可するようにファイアウォールを構成するために、[!DNL Adobe Target] [!DNL Recommendations] フィード処理サーバーで使用されるIP アドレスのリスト。

>[!IMPORTANT]
>
>[!DNL Target] チームは現在、[!DNL Recommendations] フィードのダウンロード用にNAT ゲートウェイ アドレスを更新しています。 IP 許可リストを実装する場合は、次の新しい AWS ホストを必ず許可リストに登録してください。 既存のホストは 2024年6月30日（PT）に廃止される予定です。 スムーズな移行を実現するには、9 つのアドレスをすべて許可リストに登録します。 既存のアドレスを緊急に削除する必要はありません。

[!DNL Target] [!UICONTROL Recommendations] アクティビティでは、顧客のFTP サーバーにアクセスする際に、次のAWS ホストを使用します。

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

[!DNL Target] [!UICONTROL Recommendations] APIでも、同じAWS ホストを使用します。
