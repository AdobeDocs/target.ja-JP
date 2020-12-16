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

[!DNL Adobe Target] では、個々のユーザーごとにプロファイルが作成され、管理されます。このプロファイルは[!DNL Target]エッジクラスターに保存され、訪問のたびにリアルタイムで更新されます。ただし、APIを使用してプロファイルを個別に、または一括で更新できます。

セキュリティ強化のために、バルク更新 API を呼び出す際にリクエストのヘッダーで有効なアクセストークンを渡すことを要求するよう設定できます。

**Target UI で認証を必須に設定し、アクセストークンを生成する手順は次のとおりです。**

1. **[!UICONTROL 管理]**/**[!UICONTROL 実装]**&#x200B;をクリックします。
1. **[!UICONTROL プロファイルAPI]**&#x200B;の下で、**[!UICONTROL 認証を要求]**&#x200B;を有効または無効の位置に切り替えます。

   ![](assets/profile_api_settings.png)

1. （条件付き）認証要件を有効にした場合は、「**[!UICONTROL 新しいプロファイル認証トークンを生成]**」をクリックします。

   ![](assets/profile_api_settings_2.png)

   トークンの有効期限は、[!UICONTROL 残り有効期間]ボックスに記載されている日時です。

   認証トークンを生成するには、次のいずれかのユーザー権限が必要です。

   * [!UICONTROL エディター]権限（または[!UICONTROL 承認者]）以上

      [!DNL Target Standard]ユーザーの詳細については、*ユーザー*&#x200B;の[役割と権限の指定](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)を参照してください。 [!DNL Target Premium]ユーザーの詳細については、[エンタープライズ権限の設定](/help/administrating-target/c-user-management/property-channel/properties-overview.md)を参照してください。

   * ワークスペース/製品プロファイルレベルの管理者ロール

      ワークスペースは[!DNL Target Premium]のお客様のみ利用できます。 詳しくは、[エンタープライズ権限の設定](/help/administrating-target/c-user-management/property-channel/properties-overview.md)を参照してください。

   * [!DNL Adobe Target]製品レベルの管理権限（Sysadmin権限）
   >[!NOTE]
   >
   >API を使用してプロファイル認証トークンを生成もできます。詳しくは、[Adobe Target Developers の Web サイト](https://developers.adobetarget.com/)の[プロファイル](https://developers.adobetarget.com/api/#profiles)を参照してください。

1. トークンをコピーし、リクエストのヘッダーに追加します（形式は &quot;Authorization&quot; : &quot;Bearer&quot;）。

「[!UICONTROL 新しいプロファイル認証トークンを生成]」をクリックして、必要に応じてトークンを再生成します。

>[!IMPORTANT]
>
>このトークンをリセットすると、現在のトークンを使用した API 呼び出しに失敗します。その場合は、このトークンを使用するすべてのスクリプトとアプリを更新する必要があります。
