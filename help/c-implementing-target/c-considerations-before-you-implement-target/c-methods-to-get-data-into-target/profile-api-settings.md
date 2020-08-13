---
keywords: implementation;api;profile;profile api settings;authentication token
description: API による一括更新の認証を有効または無効にし、プロファイル認証トークンを生成します。
title: プロファイル API 設定
feature: api
subtopic: Getting Started
topic: Standard
uuid: 481b4a14-f10f-47cd-988d-9e6b8c4d5c00
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 64%

---


# プロファイル API 設定{#profile-api-settings}

API による一括更新の認証を有効または無効にし、プロファイル認証トークンを生成します。

[!DNL Adobe Target] では、個々のユーザーごとにプロファイルが作成され、管理されます。This profile is stored on the [!DNL Target] edge cluster and is updated in real time after every visit, however, you can update a profile individually or in bulk via API.

セキュリティ強化のために、バルク更新 API を呼び出す際にリクエストのヘッダーで有効なアクセストークンを渡すことを要求するよう設定できます。Users with [!UICONTROL Approver] permissions can generate and enable profile API authentication tokens.

**Target UI で認証を必須に設定し、アクセストークンを生成する手順は次のとおりです。**

1. [ **[!UICONTROL 管理]** ] > [ **[!UICONTROL 実装]**]の順にクリックします。
1. 「 **[!UICONTROL プロファイルAPI]** 」の下の「認証を **** 要求」を、「有効」または「無効」の位置に切り替えます。

   ![](assets/profile_api_settings.png)

1. (Conditional) If you enabled authentication requirements, click **[!UICONTROL Generate New Pfofile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   トークンの有効期限は、[!UICONTROL 残り有効期間]ボックスに記載されている日時です。

   >[!NOTE]
   >
   >API を使用してプロファイル認証トークンを生成もできます。詳しくは、[Adobe Target Developers の Web サイト](https://developers.adobetarget.com/)の[プロファイル](https://developers.adobetarget.com/api/#profiles)を参照してください。

1. トークンをコピーし、リクエストのヘッダーに追加します（形式は &quot;Authorization&quot; : &quot;Bearer&quot;）。

Click [!UICONTROL Generate New Profile Authentication Token] to regenerate the token as needed.

>[!IMPORTANT]
>
>このトークンをリセットすると、現在のトークンを使用した API 呼び出しに失敗します。その場合は、このトークンを使用するすべてのスクリプトとアプリを更新する必要があります。
