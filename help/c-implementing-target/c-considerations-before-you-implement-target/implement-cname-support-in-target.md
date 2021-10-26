---
keywords: クライアントケア、cname、証明書プログラム、標準名、cookie、証明書、amc、adobe managed certificate、digicert; ドメイン制御検証、dcv
description: で  [!DNL Adobe] Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]  は、広告ブロッキングの問題を処理することができます。
title: ターゲットで CNAME を使用するにはどうすればよいですか?
feature: Privacy & Security
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: 3e15b8d06cb8185be27a8e0210ecfcfc5002b7e7
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 1%

---

# CNAME と [!DNL Target]

[!DNL Adobe]では、で CNAME (正規名) のサポートを実装するためのクライアントケアについて説明 [!DNL Adobe Target] しています。CNAME を使用すると、広告のブロックに関する問題や ITP に関連する (インテリジェント追跡防止) cookie ポリシーを処理することができます。 CNAME を使用すると、ユーザーが所有しているドメインではなく、が所有しているドメインに対して呼び出しが実行され [!DNL Adobe] ます。

## での CNAME サポートの要求 [!DNL Target]

1. SSL 証明書に必要なホスト名のリストを指定します (以下の FAQ を参照してください)。

1. 各ホスト名について、レギュラーホスト名を指定する CNAME レコードを DNS に作成 [!DNL Target] `clientcode.tt.omtrdc.net` します。

   例えば、クライアントのコードが &quot;cnamecustomer&quot; で、ホストされているホスト名が次のようになっているとし `target.example.com` ます。

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >[!DNL Adobe]の証明機関である DigiCert は、この手順が完了するまで証明書を発行することはできません。 そのため、 [!DNL Adobe] この手順が完了するまでは、CNAME 実装の要求を実行できません。

1. [このフォームにご記入のうえ、 ](/help/assets/FPC_Request_Form.xlsx) [ クライアントケアチケットを使用して  [!DNL Adobe]  CNAME サポートを依頼して ](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) ください。

   * [!DNL Adobe Target] client code:
   * SSL 証明書ホスト名 (例: `target.example.com target.example.org` ):
   * SSL 証明書購入者 ( [!DNL Adobe] 推奨): Adobe、カスタマー
   * お客様が証明書を購入している場合は、「独自の証明書を取得する」 (BYOC) として、次の追加情報を記入します。
      * 証明書の構成 (例: Company Inc):
      * 証明書の組織単位 (オプション、例: マーケティング):
      * 証明書の国 (例: 米国):
      * 証明書の状態/地域 (例: カリフォルニア):
      * 証明書の市区町村 (例: サンノゼ):

1. [!DNL Adobe]が証明書を購入している場合は、 [!DNL Adobe] DigiCert と連携して、証明書を実働サーバー上に購入してデプロイし [!DNL Adobe] ます。

   ユーザーが証明書を購入した場合 (BYOC) は、 [!DNL Adobe] クライアントケアによって証明書署名要求 (CSR) が送信されます。 証明書を選択して証明書を購入した場合は、CSR を使用します。 証明書の発行後に、証明書のコピーと、すべての中間証明書をクライアントケアに送信して、デプロイすることが [!DNL Adobe] できます。

   [!DNL Adobe] 実装が準備できたら、クライアントケアによって通知されます。

1. `serverDomain`( [ ドキュメント ](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#serverDomain) ) を新しい CNAME ホストに更新し、 `overrideMboxEdgeServer` `false` [ ](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#overridemboxedgeserver) at .js 設定で「(ドキュメント)」に設定します。

## よくある質問

以下に示すのは、CNAME サポートの依頼と実装についてよく寄せられる質問 (faq) を掲載してい [!DNL Target] ます。

### 独自の証明書を提供する (証明書または BYOC) ことはできますか?

独自の証明書を指定することもできます。 ただし、 [!DNL Adobe] この方法はお勧めしません。 [!DNL Adobe]証明書を購入して管理している場合は、SSL 証明書ライフサイクルの管理が容易になり [!DNL Adobe] ます。SSL 証明書は毎年更新する必要があります。 そのため、 [!DNL Adobe] クライアントケアが毎年連絡して新しい証明書をタイムリーに取得する必要があります。 お客様によっては、更新された証明書を適時に作成することができない場合があります。 ブラウザーによって [!DNL Target] 接続が拒否されるので、証明書の期限が切れた場合には、実装が jeopardized ます。

>[!IMPORTANT]
>
>独自の証明書の CNAME 実装を要求した場合 [!DNL Target] は、毎年クライアントケアに更新された証明書を提供する必要があり [!DNL Adobe] ます。 CNAME 証明書の有効期限が切れる前に、 [!DNL Adobe] 更新された証明書を展開すると、特定の実装に対する停止が発生 [!DNL Target] します。

### 新しく作成した SSL 証明書の有効期限が切れるまでの時間を入力してください。

すべて [!DNL Adobe] 購入した証明書は、1年についてのみ有効です。 [詳細については、DigiCert の「1年の証明書」を参照してください ](https://www.digicert.com/blog/position-on-1-year-certificates) 。

### どのホスト名を選択する必要がありますか? 1つのドメインに対して選択すべきホストホスト数を指定してください。

[!DNL Target] CNAME 実装に必要なホスト名は、SSL 証明書と顧客の DNS において、ドメインごとに1つだけです。 [!DNL Adobe] 各ドメインに1つのホスト名を推奨します。 サポートされているのは、ドメインごとに、1つの目的のためにより多くのホスト名が必要になる場合があります (ステージングでテストするなど)。

ほとんどのお客様は、次のようなホスト名を選択し `target.example.com` ます。 [!DNL Adobe] この練習では以下のようにお勧めしますが、結局はこれから選択することが推奨されます。 既存の DNS レコードのホスト名を要求しないでください。 これにより、競合が発生し、CNAME 要求の解決に時間がかかるようになり [!DNL Target] ます。

### 既に CNAME を実装しているのは [!DNL Adobe Analytics] 、同じ証明書またはホスト名を使用できるかどうかを確認することができます。

いいえ、 [!DNL Target] 個別のホスト名と証明書が必要です。

### 現在実装され [!DNL Target] ている ITP 2. x?

Apple インテリジェントトラッキング防止 (ITP) バージョン2.3 は、CNAME 実装を検出 [!DNL Adobe Target] し、cookie の有効期限を7日に減らすことができる、Cname クローク緩和の機能が導入されました。 現時点 [!DNL Target] では、ITP の CNAME のクローク緩和については回避策はありません。 ITP について詳しくは、 [ Apple インテリジェントトラッキング防止 (ITP) x を参照してください ](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) 。

### CNAME 実装が展開されている場合、どのような種類のサービスの停止が予想されるか。

証明書が展開されている場合は、証明書の書き換えを含むサービスが中断されることはありません。

ただし、 [!DNL Target] () .js の実装コードでホスト名 `serverDomain` を新しい CNAME ホスト名 () に変更すると、 `target.example.com` web ブラウザーでは訪問者が新しい訪問者として扱われます。 古いホスト名 () で前のクッキーにアクセスできないので、訪問者のプロファイルデータは失われ `clientcode.tt.omtrdc.net` ます。 前の cookie は、ブラウザーのセキュリティモデルによってアクセスできなくなります。 このような中断は、新しい CNAME に最初にカットされたときにのみ発生します。 ホスト名は変更されないので、証明書の書き換えには影響はありません。

### CNAME 実装に使用されるキータイプと証明書署名アルゴリズムは、どのようになりますか。

デフォルトでは、すべての証明書が RSA SHA-256 およびキーが RSA 2048 ビットです。 2048ビットよりも大きいキーサイズは、現在サポートされていません。

### CNAME 実装にトラフィックが適しているかどうかを検証するには、どうすればよいですか。

以下の一連のコマンドを使用します (macOS および curl の > = 7.49 を使用します)。

1. この bash 関数を端末にコピー &amp; ペーストします。この関数は、通常は、または、 `~/.bash_profile` `~/.bashrc` 端末セッション全体で使用可能なように、bash の起動スクリプトファイルにペーストできます。

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

1. 次のコマンドをペースト `target.example.com` します (ホスト名に置き換えます)。

   ```
   adobeTargetCnameValidation target.example.com
   ```

   実装の準備ができている場合は、次のような出力が表示されます。 重要な点は、ではなくすべての検証ステータス行が表示されることです `✅` `🚫` 。 各 [!DNL Target] 境界線 CNAME が表示 `CN=target.example.com` されます。これは、要求された証明書のプライマリホスト名に一致します (この証明書に追加された SAN ホスト名は、この出力には印刷されません)。

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
   >この検証コマンドが DNS 検証で失敗しても、必要な DNS 変更が既に行われている場合は、DNS の更新が完全に伝播されるまで待つ必要がある場合もあります。 DNS レコードには TTL (time-to-live) が関連付けられています。これにより、 [ ](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) これらのレコードに対する dns 応答のキャッシュの有効期限を設定することができます。 そのため、少なくとも Ttl が経過しているということが必要な場合があります。 この `dig target.example.com` コマンドまたは「 [ G Suite」ツールボックスを使用して、特定の TTLs を検索することができ ](https://toolbox.googleapps.com/apps/dig/#CNAME) ます。 世界中の DNS 伝達を確認するには、whatsmydns.net を参照してください [ ](https://whatsmydns.net/#CNAME) 。

### CNAME でのオプトアウトリンクの使用方法

CNAME を使用している場合は、脱退リンクに「client =」というように入力し `clientcode` ます。
`https://my.cname.domain/optout?client=clientcode`.

`clientcode`クライアントコードで置き換え、脱退 URL にリンクするテキストまたはイメージを追加し [ ](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#reference_E7A62B7B99C94B3A806CB262D16E27FC) ます。

## 既知の制限事項

* QA モードが適用されていないのは、CNAME および .js 1. x を使用している場合です。このモードは、サードパーティの cookie に基づいているためです。 この回避策は、移動先の各 URL にプレビューパラメーターを追加することです。 QA モードは、CNAME と .js 3. x の場合は、固定されています。
* CNAME を使用すると、呼び出しによって cookie ヘッダーのサイズが大きくなる可能性が高くなり [!DNL Target] ます。 [!DNL Adobe] cookie のサイズは 8 KB 未満にしておくことをお勧めします。
