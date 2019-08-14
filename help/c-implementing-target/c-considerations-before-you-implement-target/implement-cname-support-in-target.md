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
source-git-commit: d21838bdf17327b394f6e3106ea5ce4bc72605e6

---


# CNAME と Adobe Target{#cname-and-adobe-target}

Adobe Client Care と連携しながら Adobe Target で CNAME（正規名）サポートを実装する方法について説明します。広告ブロッキングの問題を最大限に扱うために、CNAMEは、アドビが所有するドメインではなく、顧客が所有するドメインに対して呼び出しが行われるように使用されます。

Target で CNAME サポートを要求するには、次の手順を実行します。

1. 「[カスタマーケアチケット](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)」を開いて、Adobe Target 呼び出しの CNAME サポートを要求します。
1. [Adobe Managed Certificate（AMC）Program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) に登録し、『[!DNL Adobe Analytics]*ファーストパーティ Cookie*』ガイドに記載されている実装手順に従います。[!DNL Target] は [!DNL Analytics] 、CNAMEサポートと同じメソッドを使用します。

   AMC Program を利用することで、ファーストパーティ Cookie を実装する際の労力と混乱を回避できます。このプログラムに登録すると、証明書の購入と発行や、セキュアサーバーへの証明書のインストールがアドビ側でおこなわれます。

   >[!NOTE]
   >
   >AMC Program に登録する前に、CNAME を設定する必要があります。

1. 上記のタスクを完了したら、at. jsの新しいCNAME `serverDomain` に更新する必要があります。

## トレーニングビデオ:ファーストパーティcookieとAdobe Managed Certificates

This video is a recording of [Office Hours](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7), an initiative led by the Adobe Customer Care team. Adobe Managed Certificateプログラムのディスカッションは10:21から開始します。

[Adobe Analytics:ファーストパーティcookieとAdobe Managed Certificatesの使用](https://helpx.adobe.com/customer-care-office-hours/analytics/first-party-cookies-adobe-managed-certificates.html)
