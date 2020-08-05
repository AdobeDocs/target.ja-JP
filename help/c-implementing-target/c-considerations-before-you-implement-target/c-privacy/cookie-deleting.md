---
description: すべてのエクスペリエンスを検証できるようにするには、ブラウザーの Target の Cookie を削除します。
title: Adobe TargetCookieの削除
topic: Standard
uuid: 6e95ee4d-dbf2-4432-8abe-cfd9bc928f0c
translation-type: tm+mt
source-git-commit: 79bcd452a9faa0883272d2e686efd7c4ddfa34a2
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%

---


# Target の Cookie の削除{#delete-the-target-cookie}

ブラウザーのCookie(mbox)を削除して、テスト中にすべてのエクスペリエンスを検証できます。 [!DNL Target]

If there is no [!DNL Target] cookie (mbox), you are considered a new visitor and shown a new experience. There are several ways to delete your [!DNL Target] cookies without deleting all of your browser cookies.

>[!NOTE]
>
>以下の手順は、リストに表示されているブラウザーとバージョンに対して正しく行われます。 特定のブラウザーまたはバージョンの手順については、インターネットを検索してください。

## Google ChromeでのターゲットCookieの削除

バージョン 84.0.4147.105

1. **Chrome** メニュー/ **環境設定をクリックします**。
1. 「 **プライバシーとセキュリティ** 」タブをクリックします。
1. 「 **cookieと他のサイトデータ**」をクリックします。
1. 「すべてのCookieとサイトデータを **表示**」をクリックします。
1. セクションを展開し、 `adobe.com` mbox **** cookieを選択して、削除アイコン(X)をクリックします。

## Mozilla FirefoxからのターゲットCookieの削除

バージョン 79.0

1. **Firefox** メニュー/ **環境設定をクリックします**。
1. 「 **プライバシーとセキュリティ** 」タブをクリックします。
1. 「 **Cookieとサイトデータ**」で、「データの **管理**」をクリックします。
1. サイトを選択し `adobe.com` 、「選択した項目を **削除**」をクリックします。

   >[!NOTE]
   >
   >これにより、 `adobe.com` サイトに関連付けられているすべてのcookieが削除されます。 サイトの個々のCookieを削除または編集する場合は、開発者ツールの [ストレージ検査で行うことができます](https://developer.mozilla.org/en-US/docs/Tools/Storage_Inspector)。 削除する必要がある特定のCookieには、「mbox」という名前が付けられます。

## Microsoft EdgeからのターゲットCookieの削除

バージョン 84.0.522.52

1. 「 **Microsoft Edge** 」メニュー/「 **環境設定**」をクリックします。
1. Click the **Site Permissions** tab.
1. 「 **cookieとサイトデータ**」をクリックします。
1. 「すべてのCookieとサイトデータを **表示**」をクリックします。
1. セクションを展開し、 `adobe.com` mbox **** cookieを選択して、削除アイコン(X)をクリックします。

## Apple Safariからのターゲットcookieの削除

バージョン 13.1.2

1. Safari **メニュー/** 環境設定をクリックします ****。
1. Click the **Privacy** tab.
1. 「Webサイトデータ **の管理**」をクリックします。
1. 削除するCookieのサイトを選択し、「 **削除**」をクリックします。

>[!NOTE]
>
>これにより、 `adobe.com` サイトに関連付けられているすべてのcookieが削除されます。 サイトの個々のCookieを削除する場合は、次の手順に従います。

1. Safari **メニュー/** 環境設定をクリックします ****。
1. Click the **Advanced** tab.
1. メニューバーの「 **開発を表示」メニューを選択し** ます。
1. 削除するCookieが含まれているWebページに移動します。
1. **開発** メニュー/Webインスペクタを **表示をクリックします**。
1. Click the **Storage** tab.
1. 「 **Cookie** 」セクションを展開し、をクリックし `www.adobe.com`ます。
1. mbox **cookieを右クリックし、「** 削除 ****」をクリックします。