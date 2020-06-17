---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Adobe Client Care と連携しながら Adobe Target で CNAME（正規名）サポートを実装する方法について説明します。
title: CNAME と Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 2880b9e06017cbf85036a7b37c4d9a2d750d01a5
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 2%

---


# CNAME と Adobe Target {#cname-and-adobe-target}

Instructions for working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. 広告ブロッキングの問題やITP関連のCookieポリシーを最も適切に処理するために、CNAMEを使用して、アドビが所有するドメインではなく、顧客が所有するドメインに対して呼び出しが行われます。

## CNAMEサポートの要請

Perform the following steps to request CNAME support in [!DNL Target]:

1. SSL証明書に必要なホスト名のリストを決定します（FAQを参照）。

1. 各ホスト名に対して、通常のホスト名を指すCNAMEレコードをDNSに作成し [!DNL Target]`clientcode.tt.omtrdc.net`ます。

   例えば、クライアントコードが「cnamecustomer」で、推奨されるホスト名がである場合 `target.example.com`、DNS CNAMEレコードは次のようになります。

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!NOTE]
   >
   >* アドビの認証局であるDigiCertは、この手順が完了するまで証明書を発行できません。 したがって、この手順が完了するまで、アドビはCNAMEの実装に対するリクエストを満たすことができません。


1. CNAMEサポートを要求するAdobe Client Careチケットを [開いた場合は、次のフォームに入力し、それを含めます](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

   * Adobe [!DNL Target] client code:
   * SSL証明書のホスト名(例： `target.example.com target.example.org`):
   * SSL証明書の購入者（アドビを強くお勧めします。よくある質問を参照してください）: アドビ/お客様
   * お客様が証明書(BYOC)を購入する場合は、次の追加情報を入力してください。
      * 証明書の組織(例： Example Inc):
      * 証明書の組織単位(オプション、例： マーケティング):
      * 証明書の国(例： US):
      * 証明書の状態/地域(例： カリフォルニア):
      * 証明書の市区町村(例： サンノゼ):

1. アドビが証明書を購入する場合、アドビはDigiCertと連携して、アドビの実稼働サーバーで証明書を購入およびデプロイします。

   お客様が証明書(BYOC)を購入する場合、Adobe ClientCareから証明書署名要求(CSR)が送信されます。この要求は、任意の認証局によって証明書を購入する際に使用する必要があります。 証明書が発行されたら、証明書のコピーと中間証明書をAdobe ClientCareに送信して、展開する必要があります。

   導入の準備が整ったら、Adobe ClientCareからお知らせします。

1. 前述のタスクを完了し、Adobe ClientCareから実装の準備が完了したことを通知された後、at.jsの新しいCNAME `serverDomain` に更新する必要があります。

## よくある質問

次の情報は、でのCNAMEサポートの要請と導入に関するよくある質問と、その回答を示し [!DNL Target]ます。

### 自分の証明書を提供できますか（「持参者の証明書」と「BYOC」）。

はい、独自の証明書を提供できます。 ただし、この方法は推奨されません。 SSL証明書のライフサイクルの管理は、アドビとアドビの両方が証明書を購入して制御する場合に、非常に簡単に行えます。 SSL証明書は毎年更新される必要があります。つまり、Adobe ClientCareから毎年、新しい証明書を適時にアドビに送信するように連絡する必要があります。 お客様によっては、毎年更新された証明書の作成がタイムリーに行えない場合があり、その場合、証明書の期限が切れると接続が拒否されるので、 [!DNL Target] 実装が損なわれる可能性があります。

>[!IMPORTANT]
>
>自分の証明書を [!DNL Target] 持参するCNAMEの実装をリクエストする場合は、更新された証明書を毎年Adobe ClientCareに提供する必要があります。 アドビが更新された証明書をデプロイする前にCNAME証明書の有効期限が切れるように設定すると、特定の [!DNL Target] 実装が停止します。

### 新しいSSL証明書の有効期限が切れるまで、どのくらいの期間ですか？

2020年9月1日以前に発行された証明書は、2年間の証明書になります。 2020年9月1日以降に発行される証明書は、1年間の証明書になります。 1年間の証明書への移行について詳しくは、 [こちらを参照してください](https://www.digicert.com/position-on-1-year-certificates)。

### どのホスト名を選択する必要がありますか。 ドメインごとにいくつのホスト名を選択する必要がありますか。

[!DNL Target] CNAMEの導入では、SSL証明書とお客様のDNSにドメインごとに1つのホスト名しか必要としないので、これをお勧めします。 お客様によっては、独自の目的（ステージングでのテストなど）のために、ドメインごとに追加のホスト名が必要になる場合があります。これはサポートされています。

ほとんどのお客様は、ホスト名のようなホスト名を選択 `target.example.com`するので、これが推奨されますが、最終的にはお客様のホスト名を選択できます。 既存のDNSレコードのホスト名をリクエストしないでください。その結果、競合と遅延時間が発生し、 [!DNL Target] CNAMEリクエストの解決に至ります。

### 既にCNAMEを実装しています [!DNL Adobe Analytics]が、同じ証明書またはホスト名を使用できますか。

いいえ。別のホスト名と証明書が [!DNL Target] 必要です。

### 現在のTargetの実装はITP 2.xの影響を受けているか。

Safariブラウザーで、TargetのJavaScriptライブラリがあるWebサイトに移動します。 If you see a Target cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.x.

ITPの問題は、AnalyticsCNAMEのみを使用したTargetで解決できます。 Targetがブロックされる広告ブロッキングシナリオの場合にのみ、個別のTargetCNAMEが必要になります。

ITPについて詳しくは、 [Apple Intelligent Tracking Prevention(ITP)2.xを参照してください](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### CNAME実装を導入した場合、どのような種類のサービスの中断が予想できますか。

証明書が展開されても（証明書の更新を含め）、サービスが中断されることはありません。 ただし、 [!DNL Target] 導入コード（at.js内）のホスト名を新しいCNAMEホスト名(`serverDomain` )に変更すると、Webブラウザーでは、古いホスト名(`target.example.com``clientcode.tt.omtrdc.net`)では以前のCookieにアクセスできないので、再訪問者が新しい訪問者として扱われ、プロファイルデータが失われます。 これは、新しいCNAMEへの最初の切り替えに対する1回限りの中断です。 ホスト名が変更されないので、証明書の更新は同じ効果を持ちません。

### CNAMEの実装には、どのキータイプと証明書署名アルゴリズムが使用されますか。

すべての証明書はRSA SHA-256で、キーはデフォルトでRSA 2048ビットです。 2048ビットを超えるキーサイズは現在サポートされていません。

### Adobe/DigiCertは、DCV電子メールを別の電子メールアドレスに送信でき `<someone>@example.com`ますか。

いいえ。DigiCert（または任意の認証機関）では、ドメインのWHOISリストまたは事前に決定されたアドレスの情報（上記を参照）にも電子メールアドレスが含まれていない限り、同じドメインのSSL証明書を承認することは許可されません。 これにより、承認された個人だけが特定のドメインのDCVを承認できます。 これが可能でない場合は、DNS CNAME DCVメソッドを使用することをお勧めします（上記を参照）。

### CNAME実装がトラフィックに対して準備できていることを検証するにはどうすればよいですか。

次のコマンドのセットを使用します（MacOsまたはLinuxのコマンドライン端末では、bashとcurl 7.49+を使用します）。

1. まず、このbash関数を端末に貼り付けます。

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
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
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge36.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
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
