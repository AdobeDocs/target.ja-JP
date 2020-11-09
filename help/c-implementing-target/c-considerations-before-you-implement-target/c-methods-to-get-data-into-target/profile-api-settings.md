---
keywords: implementation;api;profile;profile api settings;authentication token
description: Adobe TargetAPIを使用したバッチ更新の認証を有効または無効にし、プロファイル認証トークンを生成します。
title: Adobe TargetのプロファイルAPI設定
feature: api
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 40%

---


# プロファイル API 設定

Adobe TargetAPIを使用したバッチ更新の認証を有効または無効にし、プロファイル認証トークンを生成します。

[!DNL Adobe Target] では、個々のユーザーごとにプロファイルが作成され、管理されます。This profile is stored on the [!DNL Target] edge cluster and is updated in real time after every visit; however, you can update a profile individually or in bulk via API.

セキュリティ強化のために、バルク更新 API を呼び出す際にリクエストのヘッダーで有効なアクセストークンを渡すことを要求するよう設定できます。

**Target UI で認証を必須に設定し、アクセストークンを生成する手順は次のとおりです。**

1. [ **[!UICONTROL 管理]** ] > [ **[!UICONTROL 実装]**]の順にクリックします。
1. 「 **[!UICONTROL プロファイルAPI]** 」の下の「認証を **** 要求」を、「有効」または「無効」の位置に切り替えます。

   ![](assets/profile_api_settings.png)

1. (Conditional) If you enabled authentication requirements, click **[!UICONTROL Generate New Profile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   トークンの有効期限は、[!UICONTROL 残り有効期間]ボックスに記載されている日時です。

   認証トークンを生成するには、次のいずれかのユーザー権限が必要です。

   * 少なくとも [!UICONTROL エディタ権限] (または [!UICONTROL 承認者])

      お客様の詳細については、 [!DNL Target Standard] 「ユー [ザーのロールと権限の](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) 指定 **」を参照してください。 お客様について詳しくは、 [!DNL Target Premium] Enterprise権限の [設定を参照してください](/help/administrating-target/c-user-management/property-channel/properties-overview.md)。

   * ワークスペース/製品プロファイルレベルの管理者ロール

      ワークスペースは、 [!DNL Target Premium] お客様のみ利用できます。 For more information, see [Configure enterprise permissions](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

   * 製品レベルの管理権限（Sysadmin権限） [!DNL Adobe Target]
   >[!NOTE]
   >
   >API を使用してプロファイル認証トークンを生成もできます。詳しくは、[Adobe Target Developers の Web サイト](https://developers.adobetarget.com/)の[プロファイル](https://developers.adobetarget.com/api/#profiles)を参照してください。

1. トークンをコピーし、リクエストのヘッダーに追加します（形式は &quot;Authorization&quot; : &quot;Bearer&quot;）。

Click [!UICONTROL Generate New Profile Authentication Token] to regenerate the token as needed.

>[!IMPORTANT]
>
>このトークンをリセットすると、現在のトークンを使用した API 呼び出しに失敗します。その場合は、このトークンを使用するすべてのスクリプトとアプリを更新する必要があります。
