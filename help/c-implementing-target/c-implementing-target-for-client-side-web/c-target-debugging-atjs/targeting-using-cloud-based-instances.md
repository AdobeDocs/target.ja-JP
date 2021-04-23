---
keywords: クラウドインスタンス;パブリックサフィックスリスト;パブリックサフィックス;Cookie;ファーストパーティ Cookie;ファーストパーティ Cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Adobe [!DNL Target] をテストする場合や、概念の配達確認を目的として、クラウドベースのインスタンスを使用する場合に、（ソリューションと共に）お客様が直面する問題を調査します。
title: クラウドベースのインスタンスで [!DNL Target] を使用できますか？
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 82%

---

# Target でのクラウドベースのインスタンスの使用

クラウドベースのインスタンスを使用して [!DNL Adobe Target] をテストする際の問題に関する情報をまとめています。

 のお客様は、[!DNL Target]Target でクラウドベースのインスタンスを使用してテストをおこなったり、簡単な概念実証に利用したりする場合があります。このインスタンスに含まれるドメインの例を次に示します。

`azurewebsites.net`、`cloudapp.net`、`amazonaws.com`、`cloudfront.net`、`herokuapp.com`、または `firebaseapp.com`

これらのドメインは、他の多くのドメインと同様に[パブリックサフィックスリスト](https://publicsuffix.org/list/public_suffix_list.dat)に含まれています。

**問題：**&#x200B;最新型のブラウザーでは、これらのドメインを使用していると Cookie が保存されません。

[!DNL at.js] と [!DNL mbox.js] JavaScript ライブラリでは、Cookie を使用してユーザーを追跡し、[!DNL Target] で常に一貫性のあるエクスペリエンスを提供できるようにしています。[!DNL Target] の JavaScript ライブラリで Cookie を保存できないと、[!DNL Target] のリクエストが無効になります。

**解決策：**&#x200B;パブリックサフィックスリストに含まれているドメインを使用してクラウドベースのインスタンスを利用する必要がある場合は、`cookieDomain` 設定をカスタマイズすることをお勧めします。詳しくは、[targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) を参照してください。
