---
keywords: ClientCare;CNAME；証明書プログラム；正規名；Cookie；証明書；amc；アドビが管理する証明書；digicert；ドメイン制御の検証；dcv
description: の操作 [!DNL Adobe] に CNAME（正規名）サポートを実装するための ClientCare [!DNL Adobe Target] を使用して、広告ブロッキングの問題を処理できます。
title: Target での CNAME の使用方法を教えてください。
feature: Privacy & Security
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 1%

---

# CNAME と [!DNL Target]

操作の手順 [!DNL Adobe] に CNAME（正規名）サポートを実装するための ClientCare [!DNL Adobe Target]. CNAME を使用して、広告ブロックの問題や ITP 関連 (Intelligent Tracking Prevention)Cookie ポリシーを処理します。 CNAME を使用すると、が所有するドメインではなく、お客様が所有するドメインに対して呼び出しがおこなわれます。 [!DNL Adobe].

## での CNAME サポートのリクエスト [!DNL Target]

1. SSL 証明書に必要なホスト名のリストを決定します（下記の FAQ を参照）。

1. 各ホスト名に対して、DNS に通常の [!DNL Target] hostname `clientcode.tt.omtrdc.net`.

   例えば、クライアントコードが「顧客名」で、提案したホスト名が `target.example.com`に設定すると、DNS CNAME レコードは次のようになります。

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >[!DNL Adobe]の認証局である DigiCert は、この手順が完了するまで証明書を発行できません。 したがって [!DNL Adobe] は、この手順が完了するまで CNAME 実装のリクエストを満たすことができません。

1. [このフォームに入力](/help/main/assets/FPC_Request_Form.xlsx) を含め、 [開く [!DNL Adobe] CNAME サポートをリクエストする ClientCare チケット](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * [!DNL Adobe Target] client code:
   * SSL 証明書ホスト名 ( 例： `target.example.com target.example.org`):
   * SSL 証明書購入者 ([!DNL Adobe] を強くお勧めします（FAQ を参照）。Adobe/顧客
   * 顧客が証明書 (「Bring Your Own Certificate」(BYOC) とも呼ばれる ) を購入している場合は、次の追加情報を入力します。
      * 証明書の組織 ( 例：Example Company Inc):
      * 証明書の組織単位 ( オプション、例：マーケティング ):
      * 証明書の国 ( 例：米国 ):
      * 証明書の状態/地域 ( 例：（カリフォルニア）:
      * 証明書の市区町村 ( 例：（サンノゼ）:

1. If [!DNL Adobe] は証明書を購入しています [!DNL Adobe] は DigiCert と連携して証明書を購入し、にデプロイします。 [!DNL Adobe]の実稼動サーバー。

   顧客が証明書 (BYOC) を購入している場合、 [!DNL Adobe] ClientCare から証明書署名要求 (CSR) が送信されます。 CSR は、選択した証明機関を通じて証明書を購入する際に使用します。 証明書が発行されたら、証明書と中間証明書のコピーをに送信します。 [!DNL Adobe] 導入に関する ClientCare。

   [!DNL Adobe] 実装の準備が整うと、ClientCare から通知が届きます。

1. を更新します。 `serverDomain` ([ドキュメント](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)){target=_blank} を新しい CNAME ホスト名に設定し、 `overrideMboxEdgeServer` から `false` ([ドキュメント](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)){target=_blank} を at.js 設定に追加します。

## よくある質問

次の情報は、での CNAME サポートのリクエストと実装に関するよくある質問に回答します。 [!DNL Target]:

### 自分の証明書を提供することはできますか（自分の証明書を持って来るか、BYOC か）?

独自の証明書を指定できます。 しかし、 [!DNL Adobe] では、この方法をお勧めしません。 SSL 証明書のライフサイクルの管理が、 [!DNL Adobe] そして [!DNL Adobe] 証明書を購入して制御します。 SSL 証明書は、毎年更新される必要があります。 したがって [!DNL Adobe] 新しい証明書を適時に取得するには、ClientCare から毎年お客様に連絡を取る必要があります。 更新された証明書を適時に作成するのが困難な場合があります。 お使いの [!DNL Target] ブラウザーは接続を拒否するので、証明書の有効期限が切れると実装が危険化されます。

>[!IMPORTANT]
>
>次をリクエストする場合、 [!DNL Target] bring-your-certificate CNAME 実装を使用する場合、お客様はに新たに証明書を提供する必要があります。 [!DNL Adobe] ClientCare を毎年ご利用いただけます。 CNAME 証明書の有効期限が [!DNL Adobe] 更新された証明書をデプロイすると、特定の [!DNL Target] 実装。

### 新しい SSL 証明書の有効期限が切れるまで、どのくらいですか？

すべて [!DNL Adobe] — 購入した証明書は 1 年間有効です。 詳しくは、 [1 年間の証明書に関する DigiCert の記事](https://www.digicert.com/blog/position-on-1-year-certificates) を参照してください。

### どのホスト名を選択する必要がありますか？ 1 つのドメインにつき、ホスト名をいくつ選択すればよいですか。

[!DNL Target] CNAME 実装では、SSL 証明書およびお客様の DNS で、ドメインごとに 1 つのホスト名のみが必要です。 [!DNL Adobe] では、ドメインごとに 1 つのホスト名を推奨します。 お客様によっては、独自の目的（ステージング環境でのテストなど）のために、ドメインごとにより多くのホスト名が必要となる場合がありますが、これはサポートされています。

ほとんどのお客様は、次のようなホスト名を選択します。 `target.example.com`. [!DNL Adobe] ではこの方法に従うことをお勧めしますが、最終的にはお客様の選択になります。 既存の DNS レコードのホスト名をリクエストしないでください。 これを行うと競合が発生し、解決に要する時間が遅れます [!DNL Target] CNAME リクエスト。

### の CNAME 実装は既にあります。 [!DNL Adobe Analytics]、同じ証明書またはホスト名を使用できますか。

いいえ、 [!DNL Target] には、別のホスト名と証明書が必要です。

### は現在の [!DNL Target] ITP 2.x の影響を受けますか？

Apple Intelligent Tracking Prevention(ITP) バージョン 2.3 では、次の項目を検出できる CNAME Cloaking Mitigation 機能が導入されました。 [!DNL Adobe Target] CNAME 実装を参照し、cookie の有効期限を 7 日に短縮します。 現在 [!DNL Target] には、ITP の CNAME クローキング緩和の回避策はありません。 ITP について詳しくは、 [Apple Intelligent Tracking Prevention(ITP)2.x](https://developer.adobe.com/target/before-implement/privacy/apple-itp-2x/).

### CNAME 実装がデプロイされると、どのようなサービス中断が予想されますか？

証明書がデプロイされた際に、サービスの中断は発生しません（証明書の更新を含む）。

ただし、 [!DNL Target] 実装コード (`serverDomain` （at.js の）新しい CNAME ホスト名 (`target.example.com`)、Web ブラウザーでは、再訪問者が新規訪問者として扱われます。 以前のホスト名 (`clientcode.tt.omtrdc.net`) をクリックします。 ブラウザーのセキュリティモデルにより、以前の Cookie にアクセスできなくなります。 この中断は、新しい CNAME への最初の切り替え時にのみ発生します。 ホスト名は変更されないので、証明書の更新は同じ効果を持ちません。

### CNAME 実装で使用される鍵の種類と証明書署名アルゴリズムは何ですか？

すべての証明書は RSA SHA-256 で、キーはデフォルトでは RSA 2048 ビットです。 2048 ビットを超えるキーサイズは、現在サポートされていません。

### CNAME 実装でトラフィックに対する準備ができていることを検証するには、どうすればよいですか？

次のコマンドセットを使用します (macOSまたは Linux のコマンドライン端末で、bash と curl >=7.49 を使用 )。

1. この bash 関数を端末にコピーして貼り付けるか、またはその関数を bash 起動スクリプトファイルに貼り付けます ( 通常は `~/.bash_profile` または `~/.bashrc`) を使用して、関数をターミナルセッション全体で使用できるようになります。

   ```
   function adobeTargetCnameValidation {
     local hostname="$1"
     if [ -z "$hostname" ]; then
       echo "ERROR: no hostname specified"
       return 1
     fi
   
     local service="Adobe Target CNAME implementation"
     local edges="31 32 34 35 36 37 38"
     local edgeDomain="tt.omtrdc.net"
     local edgeFormat="mboxedge%d%s.$edgeDomain"
     local shardFormat="-alb%02d"
     local shards=5
     local shardsFoundCount=0
     local shardsFound
     local shardsFoundOutput
     local curlRegex="subject:.*CN=|expire date:|issuer:"
     local curlValidation="SSL certificate verify ok"
     local curlResponseValidation='"OK"'
     local curlEndpoint="/uptime?mboxClient=uptime3"
     local url="https://$hostname$curlEndpoint"
     local sslLabsUrl="https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=$hostname"
     local success="✅"
     local failure="🚫"
     local info="🔎"
     local rule="="
     local horizontalRule="$(seq ${COLUMNS:-30} | xargs printf "$rule%.0s")"
     local miniRule="$(seq 5 | xargs printf "$rule%.0s")"
     local curlVersion="$(curl --version | head -1 | cut -d' ' -f2 )"
     local curlVersionRequired=">=7.49"
     local edgeCount="$(wc -w <<< "$edges" | tr -d ' ')"
     local edge
     local shard
     local currEdgeShard
     local dnsOutput
     local cnameExists
     local endToEndTestSucceeded
     local curlResult
   
     for shard in $(seq $shards); do
       if [ "$shardsFoundCount" -eq 0 ]; then
         for edge in $edges; do
           if [ "$shard" -eq 1 ]; then
             currEdgeShard="$(printf "$edgeFormat" "$edge" "")"
           else
             currEdgeShard="$(
               printf "$edgeFormat" "$edge" "$(
                 printf -- "$shardFormat" "$shard"
               )"
             )"
           fi
           curlResult="$(curl -vsm20 --connect-to "$hostname:443:$currEdgeShard:443" "$url" 2>&1)"
           if grep -q "$curlValidation" <<< "$curlResult"; then
             shardsFound+=" $currEdgeShard"
             if grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundCount=$((shardsFoundCount+1))
               shardsFoundOutput+="\n\n$miniRule $success $hostname [edge shard: $currEdgeShard] $miniRule\n"
             else
               shardsFoundOutput+="\n\n$miniRule $failure $hostname [edge shard: $currEdgeShard] $miniRule\n"
             fi
             shardsFoundOutput+="$(grep -E "$curlRegex" <<< "$curlResult" | sort)"
             if ! grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundOutput+="\nERROR: unexpected HTTP response from this shard using $url"
             fi
           fi
         done
       fi
     done
   
     echo
     echo "$horizontalRule"
     echo
     echo "$service validation for hostname $hostname:"
     dnsOutput="$(dig -t CNAME +short "$hostname" 2>&1)"
     if grep -qFi ".$edgeDomain" <<< "$dnsOutput"; then
       echo "$success $hostname passes DNS CNAME validation"
       cnameExists=true
     else
       echo -n "$failure $hostname FAILED DNS CNAME validation -- "
       if [ -n "$dnsOutput" ]; then
         echo -e "$dnsOutput is not in the subdomain $edgeDomain"
       else
         echo "required DNS CNAME record pointing to <target-client-code>.$edgeDomain not found"
       fi
     fi
   
     curlResult="$(curl -vsm20 "$url" 2>&1)"
     if grep -q "$curlValidation" <<< "$curlResult"; then
       if grep -q "$curlResponseValidation" <<< "$curlResult"; then
         echo -en "$success $hostname passes TLS and HTTP response validation"
         if [ -n "$cnameExists" ]; then
           echo
         else
           echo " -- the DNS CNAME is not pointing to the correct subdomain for ${service}s with Adobe-managed certificates" \
             "(bring-your-own-certificate implementations don't have this requirement), but this test passes as configured"
         fi
         endToEndTestSucceeded=true
       else
         echo -n "$failure $hostname FAILED HTTP response validation --" \
           "unexpected response from $url -- "
         if [ -n "$cnameExists" ]; then
           echo "DNS is NOT pointing to the correct shard, notify Adobe Client Care"
         else
           echo "the required DNS CNAME record is missing, see above"
         fi
       fi
     else
   
       echo -n "$failure $hostname FAILED TLS validation -- "
       if [ -n "$cnameExists" ]; then
         echo "DNS is likely NOT pointing to the correct shard or there's a validation issue with the certificate or" \
           "protocols, see curl output below and optionally SSL Labs ($sslLabsUrl):"
         echo ""
         echo "$horizontalRule"
         echo "$curlResult" | sed 's/^/    /g'
         echo "$horizontalRule"
         echo ""
       else
         echo "the required DNS CNAME record is missing, see above"
       fi
     fi
   
     if [ "$shardsFoundCount" -ge "$edgeCount" ]; then
       echo -n "$success $hostname passes shard validation for the following $shardsFoundCount edge shards:"
       echo -e "$shardsFoundOutput"
       echo
   
       if [ -n "$cnameExists" ] && [ -n "$endToEndTestSucceeded" ]; then
         echo "$horizontalRule"
         echo ""
         echo "  For additional TLS/SSL validation, including detailed browser/client support,"
         echo "  see SSL Labs (click the first IP address if prompted):"
         echo ""
         echo "    $info  $sslLabsUrl"
         echo ""
         echo "  To check DNS propagation around the world, see whatsmydns.net:"
         echo ""
         echo "    $info  DNS A records:     https://whatsmydns.net/#A/$hostname"
         echo "    $info  DNS CNAME record:  https://whatsmydns.net/#CNAME/$hostname"
       fi
     else
       echo -n "$failure $hostname FAILED shard validation -- shards found: $shardsFoundCount," \
         "expected: $edgeCount"
       if bc -l <<< "$(cut -d. -f1,2 <<< "$curlVersion") $curlVersionRequired" 2>/dev/null | grep -q 0; then
         echo -n " -- insufficient curl version installed: $curlVersion, but this script requires curl version" \
           "$curlVersionRequired because it uses the curl --connect-to flag to bypass DNS and directly test" \
           "each Adobe Target edge shards' SNI confirguation for $hostname"
       fi
       if [ -n "$shardsFoundOutput" ]; then
         echo -e ":\n$shardsFoundOutput"
       fi
       echo
     fi
     echo
     echo "$horizontalRule"
     echo
   }
   ```

1. このコマンドを貼り付けます ( 置換 `target.example.com` をホスト名に置き換えます )。

   ```
   adobeTargetCnameValidation target.example.com
   ```

   実装の準備が整ったら、次のような出力が表示されます。 重要な点は、すべての検証ステータス行が表示される点です `✅` ではなく `🚫`. 各 [!DNL Target] edge CNAME シャードが表示される `CN=target.example.com`：要求された証明書のプライマリホスト名に一致します（この出力では、証明書の追加の SAN ホスト名は印刷されません）。

   ```
   $ adobeTargetCnameValidation target.example.com
   
   ==========================================================
   
   Adobe Target CNAME implementation validation for hostname target.example.com:
   ✅ target.example.com passes DNS CNAME validation
   ✅ target.example.com passes TLS and HTTP response validation
   ✅ target.example.com passes shard validation for the following 7 edge shards:
   
   ===== ✅ target.example.com [edge shard: mboxedge31-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge32-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge34-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge35-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge36-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge37-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge38-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ==========================================================
   
     For additional TLS/SSL validation, including detailed browser/client support,
     see SSL Labs (click the first IP address if prompted):
   
       🔎  https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=target.example.com
   
     To check DNS propagation around the world, see whatsmydns.net:
   
       🔎  DNS A records:     https://whatsmydns.net/#A/target.example.com
       🔎  DNS CNAME record:  https://whatsmydns.net/#CNAME/target.example.com
   
   ==========================================================
   ```

   >[!NOTE]
   >
   >この検証コマンドが DNS 検証で失敗したが、必要な DNS の変更を既に行っている場合は、DNS の更新が完全に反映されるまで待つ必要がある場合があります。 DNS レコードに関連付けられた [TTL (time-to-live)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) は、これらのレコードの DNS 応答のキャッシュ有効期限を示します。 その結果、少なくとも TTL が設定されている間は、待つ必要が生じる場合があります。 以下を使用して、 `dig target.example.com` コマンドまたは [G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME) を使用して特定の TTL を調べます。 世界中での DNS 伝播を確認するには、 [whatsmydns.net](https://whatsmydns.net/#CNAME).

### CNAME でのオプトアウトリンクの使用方法

CNAME を使用している場合、オプトアウトリンクには次のコードが含まれている必要があります。 &quot;client=`clientcode` 次に例を示します。
`https://my.cname.domain/optout?client=clientcode`.

置換 `clientcode` クライアントコードを使用して、 [オプトアウト URL](https://developer.adobe.com/target/before-implement/privacy/privacy/).

## 既知の制限事項

* CNAME および at.js 1.x を使用している場合、QA モードは固定ではありません。これは、サードパーティ Cookie に基づいているからです。 回避策として、移動先の各 URL にプレビューパラメーターを追加します。 CNAME と at.js 2.x を使用している場合、QA モードは定着です。
* CNAME を使用する場合、 [!DNL Target] 呼び出しが増加します。 [!DNL Adobe] では、cookie のサイズを 8 KB 未満に保つことをお勧めします。
