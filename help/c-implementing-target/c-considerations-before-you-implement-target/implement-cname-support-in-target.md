---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate
description: Adobe Client Care と連携しながら Adobe Target で CNAME（正規名）サポートを実装する方法について説明します。
title: CNAME と Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# CNAME と Adobe Target {#cname-and-adobe-target}

Information about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Target]. 広告ブロッキングの問題やITP関連のcookieポリシーを最も適切に処理するために、CNAMEを使用して、アドビが所有するドメインではなく、顧客が所有するドメインに対する呼び出しを行います。

Perform the following steps to request CNAME support in [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. CNAMEレコードを作成します（以下の手順を参照）。

   チケットを受け取ったら、FPSSLスペシャリストからCNAMEレコードのペアが提供されます。 アドビがお客様に代わって証明書を購入する前に、これらのレコードをお客様のDNSサーバー上で設定する必要があります。

   CNAMESは次の例のようになります。

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. これらのCNAMESが導入されると、アドビはDigiCertと連携して、アドビの実稼働サーバーに証明書を購入してインストールします。

1. ここまでのタスクを完了したら、`serverDomain` を at.js の新しい CNAME に更新する必要があります。
