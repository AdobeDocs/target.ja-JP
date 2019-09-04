---
description: Adobe Client Care と連携しながら Adobe Target で CNAME（正規名）サポートを実装する方法について説明します。
keywords: ClientCare;CNAME;証明書プログラム;正規名;Cookie;証明書;;amc;adobe managed certificate
seo-description: Adobe Client Care と連携しながら Adobe Target で CNAME（正規名）サポートを実装する方法について説明します。
seo-title: CNAME と Adobe Target
solution: 'Target '
title: CNAME と Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: b7a80326b0b89f6fe3bac70ccc6941be09d14ac1

---


# CNAME と Adobe Target {#cname-and-adobe-target}

Information about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Target]. 広告ブロックの問題やITP関連のcookieポリシーを最適に取り扱うために、CNAMEは、アドビが所有するドメインではなく、顧客が所有するドメインに対して呼び出しが行われるように使用されます。

Perform the following steps to request CNAME support in [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. CNAMEレコードを作成します（下記の手順を参照）。

   チケットを受信すると、FPSSLスペシャリストはCNAMEレコードのペアを提供する必要があります。これらのレコードは、アドビが証明書を購入する前に、会社のDNSサーバー上で設定する必要があります。

   CNAMESは、次の例のようになります。

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. これらのCNAMEを設定すると、アドビの実稼働サーバーに証明書を購入してインストールするDigicgerと連携します。

1. 上記のタスクを完了したら、at. jsの新しいCNAME `serverDomain` に更新する必要があります。
