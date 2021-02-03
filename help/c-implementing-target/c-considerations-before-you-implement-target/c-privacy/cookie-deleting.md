---
keywords: cookie;cookie;cookieの削除；ターゲットcookieの削除；google chrome;chrome;mozilla;firefox;microsoft edge;safari
description: すべてのエクスペリエンスを検証できるようにするには、ブラウザーの Target の Cookie を削除します。
title: Target の Cookie の削除
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 9%

---


# Target の Cookie の削除

[!DNL Adobe Target]ブラウザーのCookie(mbox)を削除して、テスト中にすべてのエクスペリエンスを検証できます。

[!DNL Target] cookie(mbox)がない場合、新しい訪問者と見なされ、新しいエクスペリエンスが表示されます。 ブラウザーの をすべて削除しないで、mbox Cookie を削除する方法はいくつかあります。

>[!NOTE]
>
>以下の手順は、リストに表示されているブラウザーとバージョンに対して正しく行われます。 特定のブラウザーまたはバージョンの手順については、インターネットを検索してください。

## Google ChromeでのターゲットCookieの削除

バージョン 84.0.4147.105

1. **Chrome**&#x200B;メニュー/**環境設定**&#x200B;をクリックします。
1. 「**プライバシーとセキュリティ**」タブをクリックします。
1. 「**Cookieと他のサイトデータ**」をクリックします。
1. 「**すべてのCookieとサイトデータを表示**」をクリックします。
1. `adobe.com`セクションを展開し、**mbox** cookieを選択して、削除アイコン(X)をクリックします。

## Mozilla FirefoxからのターゲットCookieの削除

バージョン 79.0

### `adobe.com`に関連付けられているすべてのcookieを削除する

1. **Firefox**&#x200B;メニュー/**環境設定**&#x200B;をクリックします。
1. 「**プライバシーとセキュリティ**」タブをクリックします。
1. 「**Cookieとサイトデータ**」で、「**データの管理**」をクリックします。
1. `adobe.com`サイトを選択し、「**選択した項目を削除**」をクリックします。

   >[!NOTE]
   >
   >これにより、`adobe.com`サイトに関連付けられているすべてのcookieが削除されます。 サイトの個々のCookieを削除する場合は、次の手順に従ってください。

### 個々のCookieの削除(mbox)

1. Firefoxで、**ツール**/**Web開発者**/**ストレージインスペクタ**&#x200B;をクリックします。
1. 「**詳細**」タブをクリックします。
1. 削除するCookieが含まれているWebページに移動します。
1. 「**Cookies**」セクションを展開し、「`https://experience.adobe.com`」をクリックします。
1. **mbox** cookieを右クリックし、「**削除**」をクリックします。

## Microsoft EdgeからのターゲットCookieの削除

バージョン 84.0.522.52

1. **Microsoft Edge**&#x200B;メニュー/**環境設定**&#x200B;をクリックします。
1. 「**サイト権限**」タブをクリックします。
1. 「**Cookieとサイトデータ**」をクリックします。
1. 「**すべてのCookieとサイトデータを表示**」をクリックします。
1. `adobe.com`セクションを展開し、**mbox** cookieを選択して、削除アイコン(X)をクリックします。

## Apple Safariからのターゲットcookieの削除

バージョン 13.1.2

### `adobe.com`に関連付けられているすべてのcookieを削除する

1. **Safari**&#x200B;メニュー/**環境設定**&#x200B;をクリックします。
1. 「**プライバシー**」タブをクリックします。
1. 「**Webサイトデータの管理**」をクリックします。
1. 削除するCookieのサイトを選択し、[**削除**]をクリックします。

   >[!NOTE]
   >
   >これにより、`adobe.com`サイトに関連付けられているすべてのcookieが削除されます。 サイトの個々のCookieを削除する場合は、次の手順に従ってください。

### 個々のCookieの削除(mbox)

1. **Safari**&#x200B;メニュー/**環境設定**&#x200B;をクリックします。
1. 「**詳細**」タブをクリックします。
1. メニューバー&#x200B;**の「開発メニューを表示」を選択します。**
1. 削除するCookieが含まれているWebページに移動します。
1. **開発**&#x200B;メニュー/**Webインスペクタを表示**&#x200B;をクリックします。
1. 「**ストレージ**」タブをクリックします。
1. 「**Cookies**」セクションを展開し、「`www.adobe.com`」をクリックします。
1. **mbox** cookieを右クリックし、「**削除**」をクリックします。
