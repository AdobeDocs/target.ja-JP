---
keywords: cloud instances;public suffix list;public suffix;cookie;first-party cookie;1st-party cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: クラウドベースのインスタンスを使用して Adobe Target をテストする際の問題に関する情報をまとめています。
title: Target でのクラウドベースのインスタンスの使用
feature: null
uuid: dcaba49e-7567-4970-bb9a-19377aff7d38
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 95%

---


# Target でのクラウドベースのインスタンスの使用{#use-cloud-based-instances-with-target}

クラウドベースのインスタンスを使用して [!DNL Adobe Target] をテストする際の問題に関する情報をまとめています。

 のお客様は、[!DNL Target]Target でクラウドベースのインスタンスを使用してテストをおこなったり、簡単な概念実証に利用したりする場合があります。このインスタンスに含まれるドメインの例を次に示します。

`azurewebsites.net`、`cloudapp.net`、`amazonaws.com`、`cloudfront.net`、`herokuapp.com`、または `firebaseapp.com`

これらのドメインは、他の多くのドメインと同様に[パブリックサフィックスリスト](https://publicsuffix.org/list/public_suffix_list.dat)に含まれています。

**問題：**&#x200B;最新型のブラウザーでは、これらのドメインを使用していると Cookie が保存されません。

[!DNL at.js] と [!DNL mbox.js] JavaScript ライブラリでは、Cookie を使用してユーザーを追跡し、[!DNL Target] で常に一貫性のあるエクスペリエンスを提供できるようにしています。[!DNL Target] の JavaScript ライブラリで Cookie を保存できないと、[!DNL Target] のリクエストが無効になります。

**解決策：**&#x200B;パブリックサフィックスリストに含まれているドメインを使用してクラウドベースのインスタンスを利用する必要がある場合は、`cookieDomain` 設定をカスタマイズすることをお勧めします。詳しくは、[targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) を参照してください。
