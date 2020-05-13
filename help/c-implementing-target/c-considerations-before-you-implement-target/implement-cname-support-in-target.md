---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Adobe Client Care と連携しながら Adobe Target で CNAME（正規名）サポートを実装する方法について説明します。
title: CNAME と Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 1bcfa02632a13cf1f20a618abb07cae41b49d5ec
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 2%

---


# CNAME と Adobe Target {#cname-and-adobe-target}

Instructions for working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. 広告ブロッキングの問題やITP関連のCookieポリシーを最も適切に処理するために、CNAMEを使用して、アドビが所有するドメインではなく、顧客が所有するドメインに対して呼び出しが行われます。

## CNAMEサポートの要請

Perform the following steps to request CNAME support in [!DNL Target]:

1. アドビの認証局(DigiCert)は、お客様のドメインで証明書を生成する権限がアドビにあることを確認する必要があります。

   DigiCertはこのプロセスの [ドメイン制御検証(DCV)を呼び出します](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/)。次のDCVメソッドの少なくとも1つに対してこのプロセスが完了するまで、アドビはドメインの下に証明書を生成できません。

   * 最も高速なDCVメソッドはDNS CNAMEメソッドです。このメソッドでは、DigiCertのDCVホスト名(`dcv.digicert.com`)を指すDNS CNAMEレコード（トークンを含む）をドメインに追加します。 このCNAMEレコードは、アドビが証明書の生成を承認されたことをDigiCertに示します。 Adobe ClientCareから、必要なDNSレコードと共に指示が送信されます。 例：

      ```
      3b0332e02daabf31651a5a0d81ba830a.target.example.com.  IN  CNAME  dcv.digicert.com.
      ```

      >[!NOTE]
      >
      >* これらのDCVトークンは、30日後に期限切れになります。この時点で、Adobe ClientCareから更新されたトークンが提供されます。 CNAMEリクエストを解決するのに最も短時間で済むように、リクエストを送信する前に、リクエストされたすべてのドメインに対してDNSの変更を行う準備をしてください。
         >
         >
      * ドメインに [DNS CAレコードが含まれている場合](https://en.wikipedia.org/wiki/DNS_Certification_Authority_Authorization)、まだ追加されていない `digicert.com` 場合は、を追加する必要があります。 このDNSレコードは、ドメインの証明書を発行する権限を持つ証明機関を示します。 結果のDNSレコードは次のようになります。 `example.com. IN CAA 0 issue "digicert.com"`. 「G Suite Toolbox [](https://toolbox.googleapps.com/apps/dig/#CAA) 」を使用すると、ルートドメインに既存のCAAレコードが存在するかどうかを確認できます。 DigiCertがCAAレコードを処理する方法について詳しくは、 [ここを参照してください](https://docs.digicert.com/manage-certificates/dns-caa-resource-record-check)。


   * また、DigiCertは電子メールメソッドを試行し、ドメインのWHOIS情報に含まれるアドレスに電子メールメッセージを送信し、事前に決定された電子メールアドレス(admin、administrator、webmaster、hostmaster、postmaster `@[domain_name]`)に送信します。 See the [DCV methods documentation](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) for more information.

      DCV電子メールプロセスを迅速に処理するために、DigiCertは次の推奨を提供します。

      「登録機関/WHOISプロバイダが [関連する電子メールアドレスをマスクまたは削除していないことを確認してください]。 認証機関がドメインのWHOISデータにアクセスできる方法（匿名の電子メールアドレス、Webフォームなど）が [証明機関] に提供されているかどうかを確認します。」

1. 通常のホスト名を指すCNAMEレコードを、ドメインのDNSに作成し `clientcode.tt.omtrdc.net`ます。 例えば、クライアントコードがcnamecustomerで、ホスト名を指定する場合 `target.example.com`、DNS CNAMEレコードは次のようになります。

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. 通話のCNAMEサポートを要求する [Adobe Client Careチケットを開き](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) 、 [!DNL Target] 電話に対してCNAMEサポートを要請します。

   アドビはDigiCertと連携して、アドビの実稼働サーバーで証明書を購入し、デプロイします。 DigiCertによってDCVプロセスが開始され、実装の準備ができたらAdobe ClientCareから通知されます。

1. 前述のタスクを完了し、Adobe ClientCareから実装の準備が完了したことを通知された後、at.jsの新しいCNAME `serverDomain` に更新する必要があります。

## よくある質問

次の情報は、でのCNAMEサポートの要請と導入に関するよくある質問と、その回答を示し [!DNL Target]ます。

### 自分の証明書を提供できますか（「持参者の証明書」と「BYOC」）。 そうならどうする？

はい、独自の証明書を提供できます。 ただし、この方法は推奨されません。 SSL証明書のライフサイクルの管理は、アドビとアドビの両方が証明書を購入して制御する場合に、非常に簡単に行えます。 SSL証明書は毎年更新される必要があります。つまり、Adobe ClientCareから毎年、新しい証明書を適時にアドビに送信するように連絡する必要があります。 お客様によっては、毎年更新された証明書の作成がタイムリーに行えない場合があり、その場合、証明書の期限が切れると接続が拒否されるので、 [!DNL Target] 実装が損なわれる可能性があります。

>[!IMPORTANT]
>
>自分の証明書を [!DNL Target] 持参するCNAMEの実装をリクエストする場合は、更新された証明書を毎年Adobe ClientCareに提供する必要があります。 アドビが更新された証明書をデプロイする前にCNAME証明書の有効期限が切れるように設定すると、特定の [!DNL Target] 実装が停止します。

1. 上記の手順1をスキップし、手順2と3を完了します。 Adobe ClientCareチケットを開いたら（手順3）、自分の証明書を提供することをユーザーに知らせます。

   アドビから証明書署名要求(CSR)が生成され、送信されます。

1. CSRを使用して、選択した認証局(CA)で証明書を購入します。

1. 新しい公開証明書をアドビに送信します。 アドビの担当者が、実稼働サーバーに公開証明書をデプロイします。

1. Adobe ClientCareから実装の準備ができたことが通知されたら、手順4を実行します。

### 新しいSSL証明書の有効期限が切れるまで、どのくらいの期間ですか？

2020年9月1日以前に発行された証明書は、2年間の証明書になります。 2020年9月1日以降に発行される証明書は、1年間の証明書になります。 1年間の証明書への移行について詳しくは、 [こちらを参照してください](https://www.digicert.com/position-on-1-year-certificates)。

### どのホスト名を選択する必要がありますか。 ドメインごとにいくつのホスト名を選択する必要がありますか。

[!DNL Target] CNAMEの導入では、SSL証明書とお客様のDNSにドメインごとに1つのホスト名しか必要としないので、これをお勧めします。 お客様によっては、独自の目的（ステージングでのテストなど）のために、ドメインごとに追加のホスト名が必要になる場合があります。これはサポートされています。

ほとんどのお客様は、ホスト名のようなホスト名を選択 `target.example.com`するので、これが推奨されますが、最終的にはお客様のホスト名を選択できます。 既存のDNSレコードのホスト名をリクエストしないでください。その結果、競合と遅延時間が発生し、 [!DNL Target] CNAMEリクエストの解決に至ります。

### 既にCNAMEを実装しています [!DNL Adobe Analytics]が、同じ証明書またはホスト名を使用できますか。

いいえ。別のホスト名と証明書が [!DNL Target] 必要です。

### 現在のターゲットの実装はITP 2.xの影響を受けているか。

Safariブラウザーで、ターゲットのJavaScriptライブラリがあるWebサイトに移動します。 If you see a Target cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.x.

ITPの問題は、Analytics CNAMEのみを使用したターゲットで解決できます。 ターゲットがブロックされる広告ブロッキングシナリオの場合にのみ、個別のターゲットCNAMEが必要になります。

ITPについて詳しくは、 [Apple Intelligent Tracking Prevention(ITP)2.xを参照してください](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### Adobe/DigiCertはDCV電子メールを別の電子メールアドレスに送信でき `<someone>@example.com`ますか。

いいえ。DigiCert（または任意の認証機関）では、ドメインのWHOISリストまたは事前に決定されたアドレスの情報（上記を参照）にも電子メールアドレスが含まれていない限り、同じドメインのSSL証明書を承認することは許可されません。 これにより、承認された個人だけが特定のドメインのDCVを承認できます。 これが可能でない場合は、DNS CNAME DCVメソッドを使用することをお勧めします（上記を参照）。

### CNAME実装がトラフィックに対して準備できていることを検証するにはどうすればよいですか。

次のコマンドのセットを使用します（MacOsまたはLinuxのコマンドライン端末では、bashとcurl 7.49+を使用します）。

1. まず、このbash関数を端末に貼り付けます。

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..32},34,35,37,38}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 次に、次のコマンドを貼り付けます(ホスト名 `target.example.com` で置き換えます)。

   ```
   validateEdgeFpsslSni target.example.com
   ```

   実装の準備が整ったら、次の出力が表示されます。 重要な点は、すべての行が表示され、これが必要なホスト名 `CN=target.example.com`に一致することです。 いずれかに表示される場合 `CN=*.tt.omtrdc.net`は、実装の **準備ができていません** 。

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

1. 新しいDNS CNAMEを別のcurlリクエストで検証します。これは、次の項目も表示する必要があり `CN=target.example.com`ます。

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >このコマンドが失敗し、上記の `validateEdgeFpsslSni` コマンドが正常に実行された場合は、DNSの更新が完全に伝播されるのを待つ必要があります。 DNSレコードには、TTL(time-to-live)が関連付けられています [](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) 。これは、これらのレコードのDNS応答のキャッシュ有効期限を指示するものなので、TTL以上の時間を待つ必要がある場合があります。 この `dig target.example.com` コマンドまたはG Suite Toolbox [を使用して、特定のTTLを検索できます](https://toolbox.googleapps.com/apps/dig/#CNAME) 。

## 既知の制限事項

* CNAMEとat.js 1.xをお持ちの場合、QAモードは固定されません。これは、サードパーティCookieに基づいているためです。 回避策は、ナビゲート先の各URLにプレビューパラメーターを追加することです。 CNAMEとat.js 2.xを使用している場合、QAモードは固定されます。
* 現在、この `overrideMboxEdgeServer` 設定はCNAMEでは適切に機能しません。 失敗する要求を避けるため `false` に、この値をに設定する必要があります。
