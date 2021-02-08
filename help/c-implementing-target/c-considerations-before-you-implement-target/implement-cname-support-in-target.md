---
keywords: client care;cname;certificateプログラム;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: AdobeのClientCareと協力して、広告ブロッキングの問題やITP関連のCookieポリシーを処理するために、Adobe TargetでCNAME（正規名）のサポートを実装します。
title: ターゲットでのCNAMEの使用方法
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 0%

---


# CNAME と Adobe Target

AdobeのClientCareと協力して、[!DNL Adobe Target]にCNAME（正規名）サポートを実装する手順です。 広告ブロッキングの問題やITP関連のCookieポリシーを最も適切に処理するために、CNAMEを使用して、Adobeが所有するドメインではなく、顧客が所有するドメインに対して呼び出しが行われます。

## CNAMEサポートの要請

[!DNL Target]でCNAMEサポートをリクエストするには、次の手順を実行します。

1. SSL証明書に必要なホスト名のリストを決定します（FAQを参照）。

1. 各ホスト名に対して、DNS内に、通常の[!DNL Target]ホスト名`clientcode.tt.omtrdc.net`を指すCNAMEレコードを作成します。

   例えば、クライアントコードが「cnamecustomer」で、ホスト名を`target.example.com`と指定した場合、DNS CNAMEレコードは次のようになります。

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!NOTE]
   >
   >Adobeの認証機関であるDigiCertは、この手順が完了するまで証明書を発行できません。 したがって、この手順が完了するまで、AdobeはCNAMEの導入に対するリクエストを満たすことができません。

1. [CNAMEサポートをリクエストするAdobeClientCareチケットを](https://experienceleague.adobe.com/docs/core-services/assets/FPC_Request_Form.xlsx?lang=en) 開いた場合は、次の [フォームに入力し、それを含めます](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

   * Adobe[!DNL Target]クライアントコード：
   * SSL証明書のホスト名(例：`target.example.com target.example.org`):
   * SSL証明書の購入者(Adobeを強くお勧めします。FAQを参照してください):Adobe/顧客
   * お客様が証明書(BYOC)を購入する場合は、次の追加情報を入力してください。
      * 証明書の組織(例：Example Inc):
      * 証明書の組織単位(オプション、例：マーケティング):
      * 証明書の国(例：US):
      * 証明書の状態/地域(例：カリフォルニア):
      * 証明書の市区町村(例：サンノゼ):

1. Adobeが証明書を購入する場合、AdobeはDigiCertと連携してAdobeの実稼働サーバーで証明書を購入およびデプロイします。

   お客様が証明書(BYOC)を購入すると、AdobeのClientCareから証明書署名要求(CSR)が送信されます。この要求は、任意の認証局によって証明書を購入する際に使用する必要があります。 証明書が発行されたら、証明書のコピーと中間証明書をAdobeのClientCareに送り返して、展開する必要があります。

   導入の準備が整ったら、AdobeのClientCareからお知らせします。

1. 前述のタスクを完了し、AdobeのClientCareから実装の準備が完了したことを通知されたら、at.jsの新しいCNAMEに`serverDomain`を更新する必要があります。

## よくある質問

次の情報は、[!DNL Target]でのCNAMEサポートのリクエストと導入に関するよくある質問と、その回答を示します。

### 自分の証明書を提供できますか（「持参者の証明書」と「BYOC」）。

はい、独自の証明書を提供できます。ただし、この方法は推奨されません。 SSL証明書のライフサイクルの管理は、AdobeとAdobeが証明書を購入および制御する場合に、きわめて簡単に行えます。 SSL証明書は毎年更新する必要があります。つまり、AdobeのClientCareから毎年、新しい証明書をAdobeにタイムリーに送信するように連絡する必要があります。 一部のお客様は、毎年更新された証明書をタイムリーに作成するのが困難な場合があり、その結果、[!DNL Target]の実装が損なわれる可能性があります。これは、証明書の期限が切れるとブラウザーが接続を拒否するからです。

>[!IMPORTANT]
>
>[!DNL Target]独自の証明書を持参するCNAMEの実装をリクエストする場合は、毎年AdobeのClientCareに新たに証明書を提供する責任があることに注意してください。 Adobeが更新された証明書をデプロイする前にCNAME証明書の有効期限を切れるようにすると、特定の[!DNL Target]実装を使用できなくなります。

### 新しいSSL証明書の有効期限が切れるまで、どのくらいの期間ですか？

2020年9月1日以前に発行された証明書は、2年間の証明書になります。 2020年9月1日以降に発行される証明書は、1年間の証明書になります。 1年間の証明書[](https://www.digicert.com/position-on-1-year-certificates)への移行について詳しくお読みください。

### どのホスト名を選択する必要がありますか。 ドメインごとにいくつのホスト名を選択する必要がありますか。

[!DNL Target] CNAMEの導入では、SSL証明書とお客様のDNSにドメインごとに1つのホスト名しか必要としないので、これをお勧めします。お客様によっては、独自の目的（ステージングでのテストなど）のために、ドメインごとに追加のホスト名が必要になる場合があります。これはサポートされています。

ほとんどのお客様は`target.example.com`のようなホスト名を選ぶので、お勧めしますが、最終的にはお客様のホスト名を選択します。 既存のDNSレコードのホスト名を要求しないでください。その場合、[!DNL Target] CNAME要求の解決までの競合と遅延時間が発生します。

### [!DNL Adobe Analytics]のCNAME実装は既にありますが、同じ証明書またはホスト名を使用できますか。

いいえ。[!DNL Target]には別のホスト名と証明書が必要です。

### 現在のターゲットの実装はITP 2.xの影響を受けているか。

Safariブラウザーで、ターゲットのJavaScriptライブラリがあるWebサイトに移動します。 `analytics.company.com`など、CNAMEのコンテキストにターゲットcookieが設定されている場合、ITP 2.xの影響を受けません。

ITPの問題は、Analytics CNAMEのみを使用したターゲットで解決できます。 ターゲットがブロックされる広告ブロッキングシナリオの場合にのみ、個別のターゲットCNAMEが必要になります。

ITPについて詳しくは、[Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)を参照してください。

### CNAME実装を導入した場合、どのような種類のサービスの中断が予想できますか。

証明書が展開されても（証明書の更新を含め）、サービスが中断されることはありません。 ただし、[!DNL Target]導入コード（at.jsの`serverDomain`）のホスト名を新しいCNAMEホスト名(`target.example.com`)に変更すると、Webブラウザーは、再訪問者を新しい訪問者として扱い、以前のホスト名(`clientcode.tt.omtrdc.net`)ではアクセスできなくなるので、プロファイルデータが失われます。 これは、新しいCNAMEへの最初の切り替えに対する1回限りの中断です。 ホスト名が変更されないので、証明書の更新は同じ効果を持ちません。

### CNAMEの実装には、どのキータイプと証明書署名アルゴリズムが使用されますか。

すべての証明書はRSA SHA-256で、キーはデフォルトでRSA 2048ビットです。 2048ビットを超えるキーサイズは現在サポートされていません。

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

1. 次に、次のコマンドを貼り付けます（`target.example.com`をホスト名に置き換えます）。

   ```
   validateEdgeFpsslSni target.example.com
   ```

   実装の準備が整ったら、次の出力が表示されます。 重要な点は、すべての行に`CN=target.example.com`が表示され、これが当社の希望のホスト名に一致することです。 いずれかが`CN=*.tt.omtrdc.net`と表示された場合、実装は&#x200B;****&#x200B;の準備ができていません。

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
   >このコマンドが失敗し、上記の`validateEdgeFpsslSni`コマンドが正常に実行された場合は、DNSの更新が完全に反映されるのを待つ必要がある場合があります。 DNSレコードには、[TTL (time-to-live)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records)が関連付けられています。これらのレコードのDNS応答のキャッシュ有効期限は、TTLの長さ以上待つ必要がある場合があります。 `dig target.example.com`コマンドまたは[G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME)を使用して、特定のTTLを検索できます。

## 既知の制限事項

* CNAMEとat.js 1.xをお持ちの場合、QAモードは固定されません。これは、サードパーティCookieに基づいているためです。 回避策は、ナビゲート先の各URLにプレビューパラメーターを追加することです。 CNAMEとat.js 2.xを使用している場合、QAモードは固定されます。
* 現在、at.js 1.8.2およびat.js 2.3.1より前のat.jsバージョンを使用する場合、`overrideMboxEdgeServer`設定はCNAMEでは正しく機能しません。古いバージョンのat.jsを使用する場合は、リクエストの失敗を防ぐために、`false`として設定する必要があります。 または、[at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を新しいサポート対象バージョンに更新することを検討してください。
* CNAMEを使用する場合、ターゲット呼び出しのcookieヘッダーのサイズが増加する可能性が高くなります。 Cookieのサイズは8 KB未満にすることをお勧めします。
