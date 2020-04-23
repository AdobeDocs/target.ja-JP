---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Adobe Client Care と連携しながら Adobe Target で CNAME（正規名）サポートを実装する方法について説明します。
title: CNAME と Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 8267de6c27566ec397651d3bfc88aad0818ed8d2

---


# CNAME と Adobe Target {#cname-and-adobe-target}

Instructions for working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. 広告ブロックの問題やITP関連のcookieポリシーを最も適切に処理するために、CNAMEを使用して、アドビが所有するドメインではなく、顧客が所有するドメインに対する呼び出しを行います。

## CNAMEサポートの要請

Perform the following steps to request CNAME support in [!DNL Target]:

1. アドビの認証局(DigiCert)は、お客様のドメインで証明書を生成する権限がアドビにあることを確認する必要があります。

   DigiCertはこのプロセス [Domain Control Validation(DCV)を呼び出します](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/)。次のDCVメソッドの少なくとも1つに対して、このプロセスが完了するまで、アドビはドメインの証明書を生成できません。

   * 最も高速なDCVメソッドは __DNS CNAMEメソッドです__。このメソッドでは、DigiCertのDCVホスト名(dcv.digicert.com)を指すDNS CNAMEレコード（トークンを含む）をドメインに追加します。 このCNAMEレコードは、アドビが証明書の生成を承認されたことをDigiCertに示します。 指示と必要なDNSレコードがAdobe ClientCareから送信されます。 例：

      ```
      3b0332e02daabf31651a5a0d81ba830a.target.example.com.  IN  CNAME  dcv.digicert.com.
      ```

      >[!NOTE]
      >
      >これらのDCVトークンは30日後に期限切れになり、その時点でAdobe ClientCareから更新されたトークンが提供されます。 CNAMEリクエストの解決に要する最も早い時間に備えて、リクエストを送信する前に、リクエストされたすべてのドメインに対してDNSの変更を行う準備をしてください。

      >[!NOTE]
      >
      >ドメインに [DNS CAAレコードが含まれている場合](https://en.wikipedia.org/wiki/DNS_Certification_Authority_Authorization)、まだ追加されていない場合は、 `digicert.com` 追加する必要があります。 このDNSレコードは、ドメインの証明書を発行する権限を持つ証明機関を示します。 結果のDNSレコードは次のようになります。 `example.com. IN CAA 0 issue "digicert.com"`. G Suiteツールボッ [クスを使用して](https://toolbox.googleapps.com/apps/dig/#CAA) 、ルートドメインに既存のCAAレコードがあるかどうかを確認できます。 DigiCertがCAAレコードを処理する方法について詳しくは、こちらを参照して [くださ](https://docs.digicert.com/manage-certificates/dns-caa-resource-record-check)い。

   * また、DigiCertは __email__(email)メソッドを試みます。このメソッドでは、ドメインのWHOIS情報に含まれるアドレスと、事前に決められた電子メールアドレス(admin、administrator、webmaster、hostmaster、postmaster `@[domain_name]`)に電子メールを送信します。 See the [DCV methods documentation](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) for more information.

      DCV電子メールプロセスを迅速に処理するため、DigiCertは次の推奨を提供します。

      「登録機関/WHOISプロバイダが関連する電子メールアドレスをマスクまたは削除していな [いことを確認してくださ]い。 認証機関がドメインのWHOISデータにアクセスする方法（匿名の電子メールアドレス、Webフォームなど）を提供している [] 。」

1. ドメインのDNS上に、通常のホスト名を指すCNAMEレコードを作成します `clientcode.tt.omtrdc.net`。 例えば、クライアントコードがcnamecustomerで、ホスト名を指定する場合、DNS CNAME `target.example.com`レコードは次のようになります。

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. 電話のCNAMEサポ [ートをリクエストするAdobe Client Careチケットを](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) 、開き [!DNL Target] ます。

   アドビはDigiCertと連携して、アドビの実稼働サーバーで証明書を購入し、デプロイします。 DigiCertはDCVプロセスを開始し、実装の準備ができたらAdobe ClientCareから通知されます。

1. 上記のタスクを完了し、Adobe ClientCareから実装の準備が完了したことを通知されたら、at.jsの新しいCNAME `serverDomain` にを更新する必要があります。

## よくある質問

次の情報は、でのCNAMEサポートのリクエストと実装に関するよくある質問と回答で [!DNL Target]す。

### 自分の証明書（「自分の証明書を持って来る」、「BYOC」）を提供できますか。 そうならどうする？

はい、独自の証明書を提供できますが、お __勧めしません__。 SSL証明書のライフサイクルの管理は、アドビが証明書を購入して管理する際に、アドビとお客様の両方にとって非常に簡単です。 SSL証明書は毎年更新する必要があります。つまり、アドビに新しい証明書を適時に送信するには、Adobe ClientCareから毎年ご連絡いただく必要があります。 一部のお客様は、毎年更新された証明書をタイムリーに作成するのが困難で、証明書の期限が切れると接続を拒否するので、 [!DNL Target] 実装が損なわれる可能性があります。

>[!NOTE]
>
>独自の証明書のCNAME実装をリクエストする [!DNL Target] 場合は、毎年Adobe ClientCareに新たに証明書を提供する責任があることに注意してください。 アドビが更新された証明書を展開する前にCNAME証明書の有効期限を切れるようにすると、特定の実装が停止し [!DNL Target] ます。

1. 上記の手順1をスキップし、手順2と3を実行します。 Adobe Client Careチケット（手順3）を開いたら、自分の証明書を提供することをユーザーに知らせます。

   アドビから証明書署名要求(CSR)が生成され、送信されます。

1. CSRを使用して、選択した認証局(CA)を通じて証明書を購入します。

1. 新しい公開証明書をアドビに送信します。 アドビの担当者が、実稼働サーバーに公開証明書をデプロイします。

1. Adobe ClientCareから実装の準備ができたことを通知されたら、手順4を実行します。

### 新しいSSL証明書の有効期限が切れるまで、どのくらいの期間ですか？

2020年9月1日以前に発行された証明書は、2年間の証明書となります。 2020年9月1日以降に発行された証明書は、1年間の証明書となります。 1年間の証明書への移行について詳しくは、こちらを参照してく [ださい](https://www.digicert.com/position-on-1-year-certificates)。

### どのホスト名を選択すべきか。 ドメインごとにいくつのホスト名を選択する必要がありますか。

[!DNL Target] CNAMEの実装に必要なホスト名は、SSL証明書とお客様のDNSで1つのドメインにつき1つだけなので、お勧めします。 一部のお客様は、独自の目的（例えば、ステージングでのテスト）のために、ドメインごとに追加のホスト名が必要になる場合があります。これはサポートされています。

ほとんどのお客様は、ホスト名のよ `target.example.com`うなホスト名を選択するので、お勧めしますが、最終的にはお客様のホスト名を選択します。 既存のDNSレコードのホスト名を要求しないでください。CNAME要求の解決に要する競合と遅延時間が発生する可能性があ [!DNL Target] ります。

### CNAMEの実装を既にお持ちですが、同じ [!DNL Adobe Analytics]証明書またはホスト名を使用できますか。

いいえ。別の [!DNL Target] ホスト名と証明書が必要です。

### 現在のターゲットの実装はITP 2.1または2.2の影響を受けていますか。

Safariブラウザーで、JavaScriptライブラリがあるWebサイトにターゲットします。 If you see a Target cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.1 or 2.2.

ITPに関する問題は、Analytics CNAMEのみを使用したターゲットで解決できます。 ターゲットがブロックされる広告ブロックシナリオの場合にのみ、個別のターゲットCNAMEが必要です。

ITPについて詳しくは、 [Apple Intelligent Tracking Prevention(ITP)2.xを参照してください](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### Adobe/DigiCertはDCV電子メールを別の電子メールアドレスに送信できます `<someone>@example.com`か。

いいえ。DigiCert（または任意の認証機関）は、ドメインのWHOISリストまたは事前に決定されたアドレスの情報（上記を参照）に含まれていない限り、ドメインの下の電子メールアドレスを持つユーザーだけが同じドメインのSSL証明書を承認することを許可しません。 これにより、権限を持つ個人のみが特定のドメインのDCVを承認できます。 これが実行できない場合は、DNS CNAME DCVメソッドを使用することをお勧めします（上記を参照）。

### CNAMEの実装がトラフィックに対して準備できていることを検証する方法を教えてください。

以下の一連のコマンド（MacOSまたはLinuxのコマンドライン端末では、bashとcurl 7.49+を使用）を使用します。

1. まず、このbash関数を端末に貼り付けます。

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..32},34,35,37,38}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 次に、次のコマンドを貼り付けます(ホ `target.example.com` スト名で置き換えます)。

   ```
   validateEdgeFpsslSni target.example.com
   ```

   実装の準備が整ったら、次のような出力が表示されます。 重要な点は、すべての行が表示され、これが `CN=target.example.com`目的のホスト名に一致することです。 いずれかが表示された場合 `CN=*.tt.omtrdc.net`は、実装の準備がで **きてい** ません。

   ```
   $ validateEdgeFpsslSni target.example.com
   mboxedge17.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge21.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge22.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge26.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge28.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge29.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge30.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge37.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge38.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. 新しいDNS CNAMEを別のcurl要求で検証します。次のような内容も表示されま `CN=target.example.com`す。

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >このコマンドが正常に実行され `validateEdgeFpsslSni` ない場合は、DNSの更新が完全に反映されるまで待つ必要がある可能性があります。 DNSレコードには [](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) TTL (time-to-live)が関連付けられています。これにより、DNS応答のキャッシュ有効期限が決まるので、TTL以上待つ必要が生じる場合があります。 コマンドまたはG Suiteツ `dig target.example.com` ールボッ [クスを使用して](https://toolbox.googleapps.com/apps/dig/#CNAME) 、特定のTTLを検索できます。
