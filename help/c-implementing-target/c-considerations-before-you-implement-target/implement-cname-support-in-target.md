---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Adobe Client Care と連携しながら Adobe Target で CNAME（正規名）サポートを実装する方法について説明します。
title: CNAME と Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: a2e4a4d1036d2c56d752d808054f6f4b4ab1d411

---


# CNAME と Adobe Target {#cname-and-adobe-target}

Instructions about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. 広告ブロッキングの問題やITP関連のcookieポリシーを最も適切に処理するために、CNAMEを使用して、アドビが所有するドメインではなく、顧客が所有するドメインに対する呼び出しを行います。

## CNAMEのサポートの要請

Perform the following steps to request CNAME support in [!DNL Target]:

1. アドビの認証局(DigiCert)は、お客様のドメインで証明書を生成する権限がアドビにあることを確認する必要があります。

   DigiCertは、このプロセス [Domain Control Validation](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) (DCV)を呼び出します。このプロセスが完了するまで、アドビはドメインの下で証明書を生成できません。

   DCVではいくつかの方法が使用され、Adobe ClientCareチケットを開く前に、次のいくつかの方法を実行できます（手順3）。DCVプロセスの迅速な処理に役立ちます。

   * DigiCertはまず電子メール方式を試み、ドメインのWHOIS情報に含まれるアドレスと、事前に決められた電子メールアドレス(admin、administrator、webmaster、hostmaster、postmaster `@[domain_name]`)に電子メールを送信します。 See the [DCV methods documentation](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) for more information.

      DCV電子メールプロセスを迅速に処理するために、DigiCertは次の推奨を提供します。

      「登録機関/WHOISプロバイダが関連する電子メールアドレスをマスクまたは削除していな [いことを確認してくださ]い。 認証機関がドメインのWHOISデータにアクセスできる方法（匿名の電子メールアドレス、Webフォームなど）があるか [ど] うかを調べます。

   * DCV電子メールの方法が選択肢でない場合、次の方法はDNS TXTの方法です。ここでは、DNS TXTレコードをハッシュ値でドメインに追加します。 このTXTレコードは、アドビが証明書の生成を承認されたことをDigiCertに示します。 この方法を使用する必要がある場合は、チケットを開いたときにAdobe clientCareに知らせます（手順3）。 これは、DCVプロセスの迅速化に役立ちます。

1. ドメインのDNS上に、通常のホスト名を指すCNAMEレコードを作成します `clientcode.tt.omtrdc.net`。 例えば、クライアントコードがcnamecustomerで、推奨ホスト名が次の場合、DNS CNAME `target.example.com`レコードは次のようになります。

   ```
   target.example.com  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. 通話のCNAMEサポ [ートを要求するAdobe ClientCareチケットを開き](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C)[!DNL Target] ます。

   アドビはDigiCertと連携して、アドビの実稼働サーバーで証明書を購入し、デプロイします。 DigiCertはDCVプロセスを開始し、実装の準備ができたらAdobe clientCareから通知されます。

1. 前述のタスクを完了し、Adobe clientCareから実装の準備が完了したことを通知された後、at.jsの新しいCNAME `serverDomain` に更新する必要があります。

## よくある質問

次の情報は、でのCNAMサポートの要請と導入に関するよくある質問と、その回答で [!DNL Target]す。

### 自分の証明書を提供できますか。 もしそうなら、そのプロセスは何ですか。

はい、独自の証明書を指定して、次の操作を行うことができます。

1. 上記の手順1をスキップし、手順2と3を実行します。 Adobe ClientCareチケットを開いたら（手順3）、自分の証明書を提供することをユーザーに知らせます。

   アドビは、証明書署名要求(CSR)を生成し、送信します。

1. CSRを使用して、選択した認証局(CA)を通じて証明書を購入します。

1. 新しい公開証明書をアドビに送信します。 アドビの担当者が、実稼働サーバーに公開証明書をデプロイします。

1. Adobe clientCareから実装の準備ができたことが通知されたら、手順4を実行します。

### 既にCNAME実装をお持ちですが、同じ証 [!DNL Adobe Analytics]明書またはホスト名を使用できますか。

いいえ。別の [!DNL Target] ホスト名と証明書が必要です。

### 現在のTargetの実装はITP 2.1または2.2の影響を受けていますか。

Safariブラウザーで、Target javaScriptライブラリがあるWebサイトに移動します。 If you see a Target cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.1 or 2.2.

Analytics CNAMEを使用するだけで、Targetに関するITPの問題を解決できます。 Targetがブロックされる広告ブロッキングシナリオの場合にのみ、個別のTarget CNAMEが必要になります。

ITPについて詳しくは、 [Apple Intelligent Tracking Prevention(ITP)2.xを参照してください](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### CNAME実装がトラフィックに対して準備できていることを検証する方法を教えてください。

以下の一連のコマンド（MacOsまたはLinuxのコマンドライン端末では、bashとcurl 7.49+を使用）を使用します。

1. まず、このbash関数を端末に貼り付けます。

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..33}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 次に、次のコマンドを貼り付けます( `target.example.com` ホスト名で置き換えます)。

   ```
   validateEdgeFpsslSni target.example.com
   ```

   実装の準備が整ったら、次のような出力が表示されます。 重要な点は、すべての行が表示され、目的のホ `CN=target.example.com`スト名に一致することです。 いずれかが表示される場合 `CN=*.tt.omtrdc.net`は、実装の準備がで **きてい** ません。

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
   mboxedge33.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. 新しいDNS CNAMEを別のcurl要求で検証します。これは、次の項目も表示する必要がありま `CN=target.example.com`す。

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >このコマンドが失敗して上記のコ `validateEdgeFpsslSni` マンドが正常に実行された場合は、DNSの更新が完全に反映されるまで待つ必要がある場合があります。
