---
keywords: IP アドレス;IP アドレス;許可リスト;ファイアウォール;recs;フィード;サーバー;Adobe Experience Cloud;レコメンデーション
description: '[!DNL Target]件のRecommendations フィード処理サーバーで使用されているIP アドレスのリストを表示して、Adobe サーバーから送信されるIP アドレスを許可するようにファイアウォールを構成します。'
title: レコメンデーションのフィード処理サーバーが使用する IP アドレス
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
TQID: 'https://experienceleague.adobe.com/-EhfjK6jTuHX33utQig-XYhf-nzkWlxb58VRmK9fLWo'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 44%
---
# [!DNL Recommendations]個のフィード処理サーバーで使用されるIP アドレス {#recs-ip-addresses}

>[!BEGINSHADEBOX]

**このページ：** [!DNL Adobe Target] [!DNL Recommendations] フィード処理サーバーが使用するIP アドレスを検索して、[!DNL Adobe] サーバーからのIP アドレスを許可するファイアウォールを構成します。

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>[!DNL Target] チームは現在、[!DNL Recommendations] フィードのダウンロード用にNAT ゲートウェイ アドレスを更新しています。 IP許可リストに加えるが実装されている場合は、次の新しいAWS ホストを許可リストに加えるします。 既存のホストは 2024年6月30日（PT）に廃止される予定です。 スムーズな移行を実現するには、9 つのアドレスをすべて許可リストに登録します。 既存のアドレスを緊急に削除する必要はありません。

[!DNL Target] [!UICONTROL Recommendations]のアクティビティでは、お客様のFTP サーバーにアクセスする際に、次のAWS ホストを使用します。

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

[!DNL Target] [!UICONTROL Recommendations] APIでも、同じAWS ホストを使用しています。
