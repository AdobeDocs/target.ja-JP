---
keywords: モバイルアプリ;モバイルアプリ sdk;ターゲットモバイルアプリ;モバイルターゲット sdk;モバイルアプリ sdk;sdk での target の有効化
description: モバイルアプリにAdobeMobile Services SDK を追加する方法について説明します。
title: 有効にする方法 [!DNL Target] (AdobeMobile SDK?)
feature: Implement Mobile
role: Developer
exl-id: c34bd50c-e17f-4dfb-8470-8f4c8639ee9f
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 80%

---

# 有効にする [!DNL Target] （SDK 内）

アプリに Adobe Mobile Services SDK を追加します。

1. Adobe Mobile Services SDK をアプリにインストールしていない場合は、Analytics または Experience Cloud の資格情報を使用して、 [Adobe Mobile Services](https://mobilemarketing.adobe.com/) の Web サイトから SDK をダウンロードします。

1. アプリに Adobe Mobile Services SDK を追加します。

   [コア実装とライフサイクル](https://experienceleague.adobe.com/docs/mobile-services/ios/getting-started-ios/dev-qs.html)の説明を参照してください。

1. クライアントコードとタイムアウトを追加し、SSL を有効にします。

   Experience Cloud で、Mobile Services を開き、**[!UICONTROL アプリ設定]**／**[!UICONTROL Target SDK の設定]**&#x200B;に移動します。

   Target クライアントコードとタイムアウトを追加します。クライアントコードは、それぞれのアカウントまたは会社で一意になります。タイムアウトは、Target がデフォルトのコンテンツを表示する前に応答を待つ時間を秒数で示したものです。Adobe Mobile Services のアプリ設定ページで「**[!UICONTROL HTTPS を使用]**」オプションがチェックされていることを確認します。HTTPS が有効になっていない場合、Target サーバーをiOSしない限り、9 以降のすべての呼び出しがブ許可リストロックされます。

   ![](assets/mobile-clientcode.png)

1. アプリを作成、設置した後、アプリ設定を探し、目的の SDK をダウンロードします。

   ![](assets/download-sdk.png)

>[!IMPORTANT]
>
> モバイルマーケティングインターフェイスにアクセスできない場合、アプリコードの設定ファイルで直接変更できます。ただし、ユーザーインターフェイスの設定ページと同期されません。
