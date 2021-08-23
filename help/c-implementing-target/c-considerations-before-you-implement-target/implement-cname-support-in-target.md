---
keywords: ClientCare;CNAME；証明書プログラム；正規名；Cookie；証明書；amc;adobe管理証明書；digicert；ドメイン制御の検証；DCV
description: AdobeのClientCareと協力して、Adobe [!DNL Target] でCNAME（正規名）サポートを実装し、広告ブロッキングの問題やITP関連のCookieポリシーを処理します。
title: TargetでのCNAMEの使用方法を教えてください。
feature: プライバシーとセキュリティ
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: c78598da8f13f1e2c4489a317ce151779ca4be61
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 2%

---

# CNAMEとTarget

[!DNL Adobe] ClientCareと連携して、[!DNL Adobe Target]でCNAME（正規名）サポートを実装する手順。 CNAMEを使用して、広告ブロックの問題やITP関連(Intelligent Tracking Prevention)Cookieポリシーを処理します。 CNAMEを使用すると、[!DNL Adobe]が所有するドメインではなく、顧客が所有するドメインが呼び出されます。

## TargetでのCNAMEサポートのリクエスト

1. SSL証明書に必要なホスト名のリストを決定します（以下のFAQを参照）。

1. 各ホスト名に対して、通常の[!DNL Target]ホスト名`clientcode.tt.omtrdc.net`を指すCNAMEレコードをDNSに作成します。

   例えば、クライアントコードが「cnamecustomer」で、指定したホスト名が`target.example.com`の場合、DNS CNAMEレコードは次のようになります。

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >Adobeの認証局であるDigiCertは、この手順が完了するまで証明書を発行できません。 したがって、この手順が完了するまで、[!DNL Adobe]はCNAME実装のリクエストを満たすことができません。

1. [CNAMEサポートをリクエ](/help/assets/FPC_Request_Form.xlsx) ストする [AdobeClientCareチケットを開く際は、次のフォームに入力して含めてください](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

   * Adobe[!DNL Target]クライアントコード：
   * SSL証明書ホスト名(例：`target.example.com target.example.org`):
   * SSL証明書の購入者(Adobeを強くお勧めします。FAQを参照してください):Adobe/顧客
   * 顧客が証明書(「自分の証明書を持ち込む」(BYOC)とも呼ばれる)を購入する場合は、次の追加情報を入力します。
      * 証明書の組織(例：Example Company Inc):
      * 証明書の組織単位(オプション、例：マーケティング):
      * 証明書の国(例：米国):
      * 証明書の状態/地域(例：（カリフォルニア州）:
      * 証明書の市区町村(例：サンノゼ):

1. [!DNL Adobe]が証明書を購入する場合、[!DNL Adobe]はDigiCertと連携して証明書を購入し、Adobeの実稼動サーバーにデプロイします。

   顧客が証明書(BYOC)を購入している場合は、[!DNL Adobe] ClientCareから証明書署名要求(CSR)が送信されます。 CSRは、任意の認証局から証明書を購入する場合に使用します。 証明書が発行されたら、証明書と中間証明書のコピーを[!DNL Adobe] Client Careに送信してデプロイします。

   [!DNL Adobe] 実装の準備が整うと、ClientCareから通知されます。

1. at.jsの新しいCNAMEに`serverDomain`を更新します。

## よくある質問

次の情報は、[!DNL Target]でのCNAMEサポートのリクエストと実装に関するよくある質問に回答します。

### 私は自分の証明書を提供することはできますか（Bring Your Own CertificateまたはBYOC）?

独自の証明書を指定できます。 ただし、[!DNL Adobe]はこの方法を推奨しません。 [!DNL Adobe]と[!DNL Adobe]が証明書を購入して制御する場合に、SSL証明書のライフサイクルを管理する方が簡単です。 SSL証明書は、毎年更新する必要があります。 したがって、新しい証明書を適時に入手するには、[!DNL Adobe] ClientCareから毎年ご連絡いただく必要があります。 更新された証明書をタイムリーに作成するのが困難な場合があります。 ブラウザーが接続を拒否するので、証明書の有効期限が切れると[!DNL Target]実装が危険にさらされます。

>[!IMPORTANT]
>
>[!DNL Target] bring-your-own-certificate CNAME実装をリクエストする場合、お客様は、毎年[!DNL Adobe] Client Careに新しくなった証明書を提供する責任を負います。 [!DNL Adobe]が更新された証明書をデプロイできる前にCNAME証明書の有効期限が切れるようにすると、特定の[!DNL Target]実装が停止します。

### 新しいSSL証明書の有効期限が切れるまで、どれくらいかかりますか？

2020年9月1日より前に発行された証明書は、2年間の証明書です。 2020年9月1日以降に発行された証明書は1年間の証明書です。

### どのホスト名を選択する必要がありますか。 ドメインごとにホスト名をいくつ選択すればよいですか。

[!DNL Target] CNAME実装では、SSL証明書およびお客様のDNSで、ドメインごとに1つのホスト名のみが必要です。Adobeでは、1つのホスト名を推奨します。 独自の目的（例えば、ステージングでのテスト）のために、ドメインごとにより多くのホスト名が必要なお客様もいます。これはサポートされています。

ほとんどのお客様は`target.example.com`のようなホスト名を選択します。 Adobeはこの方法に従うことをお勧めしますが、最終的にはお客様の選択になります。 既存のDNSレコードのホスト名を要求しないでください。 この場合、競合が発生し、[!DNL Target] CNAMEリクエストの解決に時間がかかります。

### [!DNL Adobe Analytics]のCNAME実装は既にありますが、同じ証明書またはホスト名を使用できますか。

いいえ。[!DNL Target]には別のホスト名と証明書が必要です。

### 現在の[!DNL Target]の実装はITP 2.xの影響を受けますか？

Safari ブラウザーでは、[!DNL Target] JavaScript ライブラリを持つ Web サイトにナビゲートします。[!DNL Target] CookieがCNAMEのコンテキストで設定されている（例：`analytics.company.com`）場合、ITP 2.xの影響は受けません。

[!DNL Analytics] CNAMEのみを使用して、[!DNL Target]のITPの問題を解決できます。 [!DNL Target]がブロックされる広告ブロックシナリオでのみ、別の[!DNL Target] CNAMEが必要です。

ITPについて詳しくは、[Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)を参照してください。

### CNAME実装がデプロイされると、どのようなサービス中断が予想されますか。

証明書がデプロイされた際に、サービスの中断は発生しません（証明書の更新を含む）。

ただし、[!DNL Target]実装コード（at.jsの`serverDomain`）のホスト名を新しいCNAMEホスト名(`target.example.com`)に変更すると、Webブラウザーでは再訪問者が新しい訪問者として扱われます。 以前のホスト名(`clientcode.tt.omtrdc.net`)で以前のCookieにアクセスできないので、再訪問者のプロファイルデータは失われます。 ブラウザーのセキュリティモデルにより、以前のCookieにアクセスできなくなります。 この中断は、新しいCNAMEへの最初の切り替え時にのみ発生します。 ホスト名が変更されないので、証明書の更新は同じ効果を持ちません。

### CNAME実装で使用されるキータイプと証明書署名アルゴリズムは何ですか？

すべての証明書はRSA SHA-256で、キーはデフォルトでRSA 2048ビットです。 2048ビットを超えるキーサイズは、現在サポートされていません。

### CNAME実装のトラフィックに対する準備ができていることを検証するには、どうすればよいですか。

次のコマンドセットを使用します（macOSまたはLinuxのコマンドライン端末では、bashとcurl 7.49+を使用）。

1. このbash関数をターミナルに貼り付けます。

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

   実装の準備が整ったら、次の出力が表示されます。 重要な点は、すべての行に`CN=target.example.com`が含まれ、これは目的のホスト名に一致します。 行に`CN=*.tt.omtrdc.net`が含まれる場合、実装は&#x200B;**対応していません**。

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

1. 別のcurlリクエストを使用して新しいDNS CNAMEを検証します。このリクエストには`CN=target.example.com`も表示されます。

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >このコマンドが失敗し、上記の`validateEdgeFpsslSni`コマンドが正常に実行された場合は、DNSの更新が完全に反映されるまで待ちます。 DNSレコードには、TTL（有効期間）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records)が関連付けられており、これらのレコードのDNS応答のキャッシュ有効期限を指定します。 [その結果、少なくともTTLが設定されている間は待つ必要が生じる場合があります。 `dig target.example.com`コマンドまたは[G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME)を使用して、特定のTTLを検索できます。

### CNAME でのオプトアウトリンクの使用方法

CNAMEを使用している場合、オプトアウトリンクには次のように「client=`clientcode`」パラメーターを含める必要があります。
`https://my.cname.domain/optout?client=clientcode`.

`clientcode`をクライアントコードに置き換え、[オプトアウトURL](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#reference_E7A62B7B99C94B3A806CB262D16E27FC)にリンクするテキストまたは画像を追加します。

## 既知の制限事項

* CNAMEとat.js 1.xがサードパーティCookieに基づいているので、QAモードは定着ではありません。 回避策は、移動先の各URLにプレビューパラメーターを追加することです。 CNAMEとat.js 2.xを使用している場合、QAモードは定着です。
* 現在、at.js 1.8.2およびat.js 2.3.1より前のバージョンを使用している場合、`overrideMboxEdgeServer`設定はCNAMEでは正しく機能しません。古いバージョンのat.jsを使用している場合は、リクエストの失敗を防ぐために、この設定を`false`にする必要があります。 または、[at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を新しいサポート対象バージョンに更新することを検討してください。
* CNAMEを使用すると、[!DNL Target]呼び出しのCookieヘッダーのサイズが大きくなる可能性が高くなります。 [!DNL Adobe] cookieのサイズを8 KB未満に保つことをお勧めします。
