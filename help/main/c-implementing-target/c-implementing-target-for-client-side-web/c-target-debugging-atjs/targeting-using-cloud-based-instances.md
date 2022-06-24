---
keywords: クラウドインスタンス;パブリックサフィックスリスト;パブリックサフィックス;Cookie;ファーストパーティ Cookie;ファーストパーティ Cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: クラウドベースのインスタンスを使用してAdobeをテストする際に（ソリューションで）お客様が直面する問題を調査する [!DNL Target] または概念実証用にも使用できます。
title: 使用可能な [!DNL Target] クラウドベースのインスタンスの場合
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 63%

---

# Target でのクラウドベースのインスタンスの使用

クラウドベースのインスタンスを使用して [!DNL Adobe Target] をテストする際の問題に関する情報をまとめています。

 のお客様は、[!DNL Target]Target でクラウドベースのインスタンスを使用してテストをおこなったり、簡単な概念実証に利用したりする場合があります。このインスタンスに含まれるドメインの例を次に示します。

`azurewebsites.net`、`cloudapp.net`、`amazonaws.com`、`cloudfront.net`、`herokuapp.com`、または `firebaseapp.com`

これらのドメインは、他の多くのドメインと同様に[パブリックサフィックスリスト](https://publicsuffix.org/list/public_suffix_list.dat)に含まれています。

**問題：**&#x200B;最新型のブラウザーでは、これらのドメインを使用していると Cookie が保存されません。

この [!DNL at.js] JavaScript ライブラリでは、Cookie を使用してユーザーを追跡し、 [!DNL Target] は常に一貫したエクスペリエンスを提供します。 この [!DNL Target] JavaScript ライブラリが cookie を保存できない [!DNL Target] のリクエストが無効になっています。

**解決策：**&#x200B;パブリックサフィックスリストに含まれているドメインを使用してクラウドベースのインスタンスを利用する必要がある場合は、`cookieDomain` 設定をカスタマイズすることをお勧めします。詳しくは、 [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}。
