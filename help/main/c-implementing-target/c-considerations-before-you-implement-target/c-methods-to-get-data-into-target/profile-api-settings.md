---
keywords: 実装；API；プロファイル；プロファイル API 設定；認証トークン
description: Adobeを使用した一括更新の認証を設定する方法を説明します [!DNL Target] API を作成し、プロファイル認証トークンを生成します。
title: プロファイル API 設定を使用してバッチ更新を有効または無効にする方法を教えてください。
feature: APIs/SDKs
role: Developer
exl-id: 6346e11b-0853-47f1-9706-69e8635a6f25
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 61%

---

# プロファイル API 設定

次を介した一括更新の認証を有効または無効にします： [!DNL Adobe Target] API を作成し、プロファイル認証トークンを生成します。

[!DNL Adobe Target] では、個々のユーザーごとにプロファイルが作成され、管理されます。このプロファイルは、 [!DNL Target] エッジクラスターに含まれ、訪問のたびにリアルタイムで更新されます。ただし、API を使用して、プロファイルを個別に、または一括で更新できます。

セキュリティ強化のために、バルク更新 API を呼び出す際にリクエストのヘッダーで有効なアクセストークンを渡すことを要求するよう設定できます。

**Target UI で認証を必須に設定し、アクセストークンを生成する手順は次のとおりです。**

1. **[!UICONTROL 管理]**／**[!UICONTROL 実装]**&#x200B;をクリックします。
1. の下 **[!UICONTROL プロファイル API]** スライドさせる **[!UICONTROL 認証が必要]** 有効または無効の位置に切り替えます。

   ![](assets/profile_api_settings.png)

1. （条件付き）認証の要件を有効にした場合、 **[!UICONTROL 新しいプロファイル認証トークンを生成]**.

   ![](assets/profile_api_settings_2.png)

   トークンの有効期限は、[!UICONTROL 残り有効期間]ボックスに記載されている日時です。

   認証トークンを生成するには、次のいずれかのユーザー権限が必要です。

   * [!UICONTROL エディター]権限（または[!UICONTROL 承認者]）以上

      [!DNL Target Standard]ユーザーの詳細については、*ユーザー*&#x200B;の[役割と権限の指定](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)を参照してください。[!DNL Target Premium]ユーザーの詳細については、[エンタープライズ権限の設定](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)を参照してください。

   * ワークスペース／製品プロファイルレベルでの管理者の役割

      Workspaces は[!DNL Target Premium]のお客様のみが利用できます。詳しくは、 [エンタープライズの権限の設定](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)を参照してください。

   * [!DNL Adobe Target]製品レベルの管理者権限（Sysadmin 権限）
   >[!NOTE]
   >
   >API を使用してプロファイル認証トークンを生成もできます。詳しくは、[Adobe Target Developers の Web サイト](https://developers.adobetarget.com/)の[プロファイル](https://developers.adobetarget.com/api/#profiles)を参照してください。

1. トークンをコピーし、リクエストのヘッダーに追加します（形式は &quot;Authorization&quot; : &quot;Bearer&quot;）。

クリック [!UICONTROL 新しいプロファイル認証トークンを生成] 必要に応じてトークンを再生成します。

>[!IMPORTANT]
>
>このトークンをリセットすると、現在のトークンを使用した API 呼び出しに失敗します。その場合は、このトークンを使用するすべてのスクリプトとアプリを更新する必要があります。
