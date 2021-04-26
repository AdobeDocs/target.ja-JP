---
keywords: client care;cname;certificateプログラム;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: AdobeのClientCareと協力して、Adobe [!DNL Target] にCNAME（正規名）サポートを実装し、広告ブロッキングの問題やITP関連のCookieポリシーを処理します。
title: ターゲットでのCNAMEの使用方法
feature: プライバシーとセキュリティ
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
translation-type: tm+mt
source-git-commit: 85a17944c7d5924edb1bbabb7531274249ceaaa8
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 2%

---

# CNAME と Adobe Target

[!DNL Adobe] ClientCareと連携して、[!DNL Adobe Target]でCNAME（正規名）サポートを実装する方法について説明します。 CNAMEを使用して、広告ブロッキングの問題やITP関連（インテリジェントトラッキング防止）cookieのポリシーを処理します。 CNAMEを使用すると、[!DNL Adobe]が所有するドメインではなく、顧客が所有するドメインに対して呼び出しが行われます。

## ターゲットでのCNAMEサポートの要請

1. SSL証明書に必要なホスト名のリストを決定します（下記のFAQを参照）。

1. 各ホスト名に対して、DNS内に、通常の[!DNL Target]ホスト名`clientcode.tt.omtrdc.net`を指すCNAMEレコードを作成します。

   例えば、クライアントコードが「cnamecustomer」で、ホスト名が`target.example.com`の場合、DNS CNAMEレコードは次のようになります。

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >Adobeの認証機関であるDigiCertは、この手順が完了するまで証明書を発行できません。 したがって、[!DNL Adobe]は、この手順が完了するまでCNAMEの実装に対するリクエストを満たすことができません。

1. [CNAMEサポートをリクエストするAdobeClientCareチケットを](/help/assets/FPC_Request_Form.xlsx) 開いた場合は、次の [フォームに入力し、それを含めます](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

   * Adobe[!DNL Target]クライアントコード：
   * SSL証明書のホスト名(例：`target.example.com target.example.org`):
   * SSL証明書の購入者(Adobeを強くお勧めします。FAQを参照してください):Adobe/顧客
   * 顧客が証明書(「Bring Your Own Certificate」(BYOC)とも呼ばれる)を購入する場合は、次の追加情報を入力します。
      * 証明書の組織(例：Example Inc):
      * 証明書の組織単位(オプション、例：マーケティング):
      * 証明書の国(例：US):
      * 証明書の状態/地域(例：カリフォルニア):
      * 証明書の市区町村(例：サンノゼ):

1. [!DNL Adobe]が証明書を購入する場合、[!DNL Adobe]はDigiCertと連携して、Adobeの実稼働サーバーで証明書を購入しデプロイします。

   お客様が証明書(BYOC)を購入する場合、[!DNL Adobe] ClientCareから証明書署名要求(CSR)が送信されます。 CSRは、任意の認証機関で証明書を購入する場合に使用します。 証明書が発行されたら、証明書のコピーと中間証明書を[!DNL Adobe] ClientCareに送信して、展開します。

   [!DNL Adobe] 導入の準備が整ったら、ClientCareからお知らせします。

1. at.jsの新しいCNAMEに`serverDomain`を更新します。

## よくある質問

次の情報は、[!DNL Target]でのCNAMEサポートのリクエストと導入に関するよくある質問と、その回答を示します。

### 自分の証明書を提供できますか（「自分の証明書を持って来る」または「BYOC」）。

独自の証明書を指定できます。 ただし、[!DNL Adobe]はこの方法を推奨しません。 [!DNL Adobe]と[!DNL Adobe]が証明書を購入して制御する場合の両方で、SSL証明書のライフサイクルの管理が容易になります。 SSL証明書は、毎年更新する必要があります。 したがって、[!DNL Adobe] ClientCareから毎年連絡を受けて、新しい証明書を適時に取得する必要があります。 お客様によっては、更新された証明書をタイムリーに作成するのが困難な場合があります。 [!DNL Target]の実装は、ブラウザーが接続を拒否しているので、証明書の有効期限が切れると脅かされます。

>[!IMPORTANT]
>
>[!DNL Target]独自の証明書を持参するCNAMEの実装をリクエストする場合は、毎年[!DNL Adobe] ClientCareに新たに証明書を提供する責任があります。 [!DNL Adobe]が更新された証明書を導入できる前にCNAME証明書の有効期限を切れるようにすると、特定の[!DNL Target]の導入が停止します。

### 新しいSSL証明書の有効期限が切れるまで、どのくらいの期間ですか？

2020年9月1日以前に発行された証明書は2年間の証明書です。 2020年9月1日以降に発行された証明書は1年間の証明書です。 1年間の証明書[](https://www.digicert.com/position-on-1-year-certificates)への移行について詳しくお読みください。

### どのホスト名を選択する必要がありますか。 ドメインごとにいくつのホスト名を選択する必要がありますか。

[!DNL Target] CNAMEの導入では、SSL証明書とお客様のDNSにおいて、ドメインごとに1つのホスト名のみが必要です。Adobeでは、1つのホスト名を推奨します。 お客様によっては、独自の目的（ステージングでのテストなど）のために、ドメインごとにより多くのホスト名が必要になる場合があります。これはサポートされています。

ほとんどのお客様は`target.example.com`のようなホスト名を選択します。 Adobeはこの方法に従うことを推奨しますが、最終的には自分の選択になります。 既存のDNSレコードのホスト名を要求しないでください。 これを行うと、競合が発生し、[!DNL Target] CNAMEリクエストの解決に遅延が発生します。

### [!DNL Adobe Analytics]のCNAME実装は既にありますが、同じ証明書またはホスト名を使用できますか。

いいえ。[!DNL Target]には別のホスト名と証明書が必要です。

### 現在の[!DNL Target]の実装はITP 2.xの影響を受けているか。

Safari ブラウザーでは、[!DNL Target] JavaScript ライブラリを持つ Web サイトにナビゲートします。`analytics.company.com`など、CNAMEのコンテキストに[!DNL Target] cookieが設定されている場合、ITP 2.xの影響を受けません。

[!DNL Analytics] CNAMEのみを使用して、[!DNL Target]のITPの問題を解決できます。 [!DNL Target]がブロックされる広告ブロッキングシナリオでのみ、個別の[!DNL Target] CNAMEが必要です。

ITPについて詳しくは、[Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)を参照してください。

### CNAME実装を導入した場合、どのような種類のサービスの中断が予想できますか。

証明書が展開されても（証明書の更新を含め）、サービスが中断されることはありません。

ただし、[!DNL Target]導入コードのホスト名（at.jsの`serverDomain`）を新しいCNAMEホスト名(`target.example.com`)に変更すると、Webブラウザーでは、再訪問者は新しい訪問者として扱われます。 以前のホスト名(`clientcode.tt.omtrdc.net`)で以前のCookieにアクセスできないので、訪問者を返すプロファイルデータは失われます。 ブラウザーのセキュリティモデルが原因で、以前のCookieにアクセスできない場合。 この障害は、新しいCNAMEへの最初の切り替え時にのみ発生します。 ホスト名が変更されないので、証明書の更新でも同じ効果はありません。

### CNAMEの実装に使用するキータイプと証明書署名アルゴリズムは何ですか。

すべての証明書はRSA SHA-256で、キーはデフォルトでRSA 2048ビットです。 2048ビットを超えるキーサイズは現在サポートされていません。

### CNAMEの実装がトラフィックに対して準備できていることを検証する方法を教えてください。

次のコマンドのセットを使用します（macOSまたはLinuxのコマンドライン端末では、bashとcurl 7.49+を使用）。

1. このbash関数を端末に貼り付けます。

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 次のコマンドを貼り付けます（`target.example.com`をホスト名に置き換えます）。

   ```
   validateEdgeFpsslSni target.example.com
   ```

   実装の準備が整ったら、次の出力が表示されます。 重要な点は、すべての行に`CN=target.example.com`が含まれ、これが目的のホスト名に一致することです。 行に`CN=*.tt.omtrdc.net`が含まれる場合、実装は&#x200B;**準備ができていません**。

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

1. 別のcurlリクエストで新しいDNS CNAMEを検証します。これは`CN=target.example.com`も表示する必要があります。

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >このコマンドが失敗し、上記の`validateEdgeFpsslSni`コマンドが正常に実行された場合は、DNSの更新が完全に反映されるまで待ちます。 DNSレコードには、[TTL (time-to-live)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records)が関連付けられており、これらのレコードのDNS応答のキャッシュ有効期限を指示します。 そのため、少なくともTTLで待つ必要が生じる場合があります。 `dig target.example.com`コマンドまたは[G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME)を使用して、特定のTTLを検索できます。

## 既知の制限事項

* CNAMEとat.js 1.xをお持ちの場合、QAモードはサードパーティCookieに基づいているので、定着しません。 回避策は、ナビゲート先の各URLにプレビューパラメーターを追加することです。 CNAMEとat.js 2.xを使用している場合、QAモードは固定されます。
* 現在、at.js 1.8.2およびat.js 2.3.1より前のat.jsバージョンを使用する場合、`overrideMboxEdgeServer`設定はCNAMEで正しく機能しません。古いバージョンのat.jsを使用する場合は、リクエストの失敗を防ぐために、この設定を`false`に設定する必要があります。 または、[at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を新しいサポート対象バージョンに更新することを検討してください。
* CNAMEを使用する場合、[!DNL Target]呼び出しのcookieヘッダーのサイズが増える可能性が高くなります。 [!DNL Adobe] cookieのサイズを8 KB未満に保つことを推奨します。
