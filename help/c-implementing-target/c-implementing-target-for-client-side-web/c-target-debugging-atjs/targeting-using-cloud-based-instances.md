---
keywords: クラウドインスタンス;パブリックサフィックスリスト;パブリックサフィックス;Cookie;ファーストパーティ Cookie;ファーストパーティ Cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: 'クラウドベースのインスタンスを使用してAdobeをテストする場合や、概念実証の目的で直面する問題を（ソリューションで）検討します。 [!DNL Target] '
title: クラウドベースのインスタンスで [!DNL Target] を使用できますか？
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 67%

---

# Target でのクラウドベースのインスタンスの使用

クラウドベースのインスタンスを使用して [!DNL Adobe Target] をテストする際の問題に関する情報をまとめています。

 のお客様は、[!DNL Target]Target でクラウドベースのインスタンスを使用してテストをおこなったり、簡単な概念実証に利用したりする場合があります。このインスタンスに含まれるドメインの例を次に示します。

`azurewebsites.net`、`cloudapp.net`、`amazonaws.com`、`cloudfront.net`、`herokuapp.com`、または `firebaseapp.com`

これらのドメインは、他の多くのドメインと同様に[パブリックサフィックスリスト](https://publicsuffix.org/list/public_suffix_list.dat)に含まれています。

**問題：**&#x200B;最新型のブラウザーでは、これらのドメインを使用していると Cookie が保存されません。

[!DNL at.js] JavaScriptライブラリは、Cookieを使用してユーザーを追跡し、[!DNL Target]で常に一貫性のあるエクスペリエンスを提供できるようにします。 [!DNL Target] JavaScriptライブラリでCookieを保存できない場合、[!DNL Target]リクエストは無効になります。

**解決策：**&#x200B;パブリックサフィックスリストに含まれているドメインを使用してクラウドベースのインスタンスを利用する必要がある場合は、`cookieDomain` 設定をカスタマイズすることをお勧めします。詳しくは、[targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) を参照してください。
