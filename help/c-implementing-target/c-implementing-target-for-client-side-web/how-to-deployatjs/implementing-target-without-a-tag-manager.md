---
description: タグマネージャー（Adobe Launch または Dynamic Tag Management）を使用しないで Adobe Target を実装する方法について説明します。
keywords: 注文の確認;orderConfirmPage
seo-description: タグマネージャー（Adobe Launch または Dynamic Tag Management）を使用しないで Adobe Target を実装する方法について説明します。
seo-title: タグマネージャーを使用しない Target の実装
solution: 'Target '
subtopic: 導入
title: タグマネージャーを使用しない Target の実装
topic: Standard
uuid: 3ecc041a-42d8-40f8-90be-7856e1d3d080
translation-type: tm+mt
source-git-commit: ffa6585834b271838629d65ceb00d1770b37e80c

---


# タグマネージャーを使用しない Target の実装{#implement-target-without-a-tag-manager}

タグマネージャー（Adobe LaunchまたはDynamic Tag Management）を使用 [!DNL Adobe Target] せずに実装する方法について説明します。

## タグマネージャーを使用しない Target の実装 {#topic_397FFA3D6918456BBE02A9FBE9537894}

タグマネージャー（Adobe Launch または Dynamic Tag Management）を使用しないで Adobe Target を実装する方法について説明します。

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) は、Target および at.js ライブラリを実装するための推奨される方法です。次の情報は、Adobe Launch を使用して Target を実装する場合には適用されません。

## at.js の設定 {#concept_2FA0456607D04F82B0539C5BF5309812}

at.js の設定ページでいくつかの設定をおこなう方法を説明します。

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) は、Target および at.js ライブラリを実装するための推奨される方法です。次の情報は、Adobe Launch を使用して Target を実装する場合には適用されません。

>[!NOTE]
>
>Target Standard/Premium UI や REST API を使用して設定を構成する代わりに、at.js ライブラリで設定を上書きすることができます。詳しくは、[targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) を参照してください。

[!UICONTROL 設定]ページを開くには、次の手順を実行します。

1. 「**[!UICONTROL セットアップ]**」／「**[!UICONTROL 実装]**」の順にクリックします。
1. 「**[!UICONTROL at.js]**」／「**[!UICONTROL at.js 設定を編集]**」の順に選択します。

## コンテンツ配信設定 {#section_118D290DFC444509AD8E4AE86C9D92C0}

これらの設定を変更する前に、ClientCare にお問い合わせください。これらの設定はほとんどの実装で必要になります。

| 設定 | 説明 |
|--- |--- |
| グローバル mbox 自動作成 | 各ページが読み込まれると自動的に実行されるように、グローバル mbox 呼び出しを at.js ファイルに埋め込むかどうかを選択します。<br>この設定を変更すると、at.js と mbox.js の両方に影響します。 |
| グローバル mbox 名 | global mbox の名前を選択します。デフォルトでは、この名前は target-global-mbox です。<br>at.js を使用した mbox 名には、アンパサンド（&amp;）を含む特殊文字を使用できます。<br>この設定を変更すると、at.js と mbox.js の両方に影響します。 |

## 詳細設定 {#section_33B697B77BA64A01B5939D7EC75231F2}

| 設定 | 説明 |
|--- |--- |
| クライアントコード | クライアントコードは、Target API を使用する際に必要になることの多い、クライアント固有の一連の文字です。<br>この設定は変更できません。 |
| IMS 組織 ID | この ID は、実装を [!DNL Adobe Experience Cloud] アカウントと結び付けます。<br>この設定は変更できません。 |
| プロファイルの有効期間 | この設定は、訪問者プロファイルが保存される期間を決定します。デフォルトでは、プロファイルは 2 週間保存されます。この期間は最大で 90 日まで延長することができます。<br>プロファイルの有効期間設定を変更するには、[ClientCare](https://helpx.adobe.com/contact/enterprise-support.ec.html) にお問い合わせください。 |
| X-Domain | ブラウザーで Cookie を設定する場合、お客様独自のドメインで設定するか（ファーストパーティ Cookie）、Target のドメインで設定するか、またはその両方で設定するかどうかを指定します。<br>この設定を変更すると、at.js と mbox.js の両方に影響します。 |
| タイムアウト | [!DNL Target] が定義された期間内にコンテンツの応答をしない場合、サーバー呼び出しはタイムアウトし、デフォルトコンテンツが表示されます。訪問者のセッション中、追加の呼び出しが引き続き試行されます。デフォルト値は 5 秒です。<br>この設定を変更すると、at.js と mbox.js の両方に影響します。<br>at.js ライブラリは、`XMLHttpRequest` のタイムアウト設定を使用します。タイムアウトは、リクエストが実行されると開始され、Target がサーバーから応答を受け取ると停止します。詳しくは、Mozilla Developer Network の [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout) を参照してください。<br>応答を受け取る前に指定されたタイムアウトが発生すると、デフォルトのコンテンツが表示され、訪問者はアクティビティの参加者としてカウントされる可能性があります。これは、[!DNL Target] エッジですべてのデータ収集がおこなわれるためです。リクエストが [!DNL Target] エッジに到達すると、訪問者はカウントされます。<br>タイムアウト設定を構成する際は、次の点を考慮してください。<ul><li>値が低すぎると、訪問者はアクティビティの参加者としてカウントされるものの、ほとんどの時間デフォルトのコンテンツが表示される可能性があります。</li><li>値が高すぎると、Web ページに空白の領域が表示されるか、長時間の本文の非表示を使用している場合は空白のページが表示される可能性があります。</li></ul>mbox の応答時間をよりよく把握するには、ブラウザーの開発者ツールの「ネットワーク」タブを確認してください。また、Catchpoint など、サードパーティの Web パフォーマンス監視ツールを使用することもできます。<br>**注意：**[visitorApiTimeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) 設定では、[!DNL Target] が訪問者 API の応答を長時間待たないようにします。この設定と、ここで説明している at.js のタイムアウト設定は相互に影響しません。 |
| レガシーブラウザーのサポート | **注意：**「レガシーブラウザーのサポート」オプションは、at.js バージョン 0.9.3 以前で使用できます。このオプションは、at.js バージョン 0.9.4 で削除されました。at.js でサポートされているブラウザーのリストについては、「[サポートされているブラウザー](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)」を参照してください。<br>レガシーブラウザーは、CORS（クロスオリジンリソース共有）を完全にはサポートしない古いブラウザーです。こうしたブラウザーには、バージョン 11 より前の Internet Explorer およびバージョン 6 以下の Safari が含まれます。「レガシーブラウザーのサポート」を無効にすると、Target はコンテンツを配信しないか、そうしたブラウザーのレポートで訪問者をカウントします。このオプションを有効にする場合、古いブラウザーで品質保証をおこない、優れた顧客エクスペリエンスが得られるようにします。 |

## コード設定 {#section_D41C905D0F8149949F525C85F2CCFF7F}

| 設定 | 説明 |
|--- |--- |
| ライブラリのヘッダー | ライブラリの最上部に含めるカスタム JavaScript を追加します。 |
| ライブラリのフッター | ライブラリの最下部に含めるカスタム JavaScript を追加します。 |

## at.js のダウンロード {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

Target インターフェイスまたはダウンロード API を使用した ライブラリのダウンロード手順について説明します。

<!-- 

ov2/c_target-configure-atjs.xml

 -->

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) は、Target および at.js ライブラリを実装するための推奨される方法です。次の情報は、Adobe Launch を使用して Target を実装する場合には適用されません。

>[!IMPORTANT]
>
>Target チームがサポートを提供しているのは、[!DNL at.js] の最新バージョンとその 1 つ前のバージョンの 2 つのみです。必要に応じて [!DNL at.js] をアップグレードし、サポート対象のバージョンを使用するようにしてください。各バージョンに関する詳細については、「[at.js のバージョンの詳細](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)」を参照してください。

## Target インターフェイスを使用した at.js のダウンロード {#section_1F5EE401C2314338910FC57F9592894E}

[!DNL at.js] インターフェイスから [!DNL Target] をダウンロードするには：

1. **[!UICONTROL セットアップ]**／**[!UICONTROL 実装]**をクリックします。
1. 「**[!UICONTROL at.js]**」を選択します。
1. 「**[!UICONTROL at.js をダウンロード]**」をクリックします。

## Target ダウンロード API を使用した at.js のダウンロード {#section_C0D9D2A9068144708D08526BA5CA10D0}

API を使用して [!DNL at.js] をダウンロードするには：

1. クライアントコードを取得します。

   クライアントコードは、[!DNL Target] インターフェイスの「**[!UICONTROL セットアップ]**」／「**[!UICONTROL 実装]**」／「**[!UICONTROL at.js 設定を編集]」**ページの最上部にあります。

1. 管理番号を取得します。

   次の URL を読み込みます。

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   ` < *`client code`*>` を手順 1 のクライアントコードで置き換えます。

   この URL を読み込んだ結果は、次の例のようになります。

   ```
   { 
     "api": "https://admin6.testandtarget.omniture.com/admin/rest/v1" 
   }
   ```

   この例では、「6」が管理番号です。

1. ダウンロード [!DNL at.js].

   この URL を次の構造で読み込みます。

   ```
   https://admin<varname>admin number</varname>>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code </varname>version=<version number>
   ```

   * ` < *`admin number`*>` を管理番号で置き換えます。
   * ` < *`client code`*>` を手順 1 のクライアントコードで置き換えます。
   * ` < *`version number`*>` を目的の [[!DNL at.js] バージョン番号](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)（例： 1.6.2）で置き換えます。
   >[!IMPORTANT]
   >
   >Target チームがサポートを提供しているのは、[!DNL at.js] の最新バージョンとその 1 つ前のバージョンの 2 つのみです。必要に応じて [!DNL at.js] をアップグレードし、サポート対象のバージョンを使用するようにしてください。各バージョンについて詳しくは、 [at.js のバージョンの詳細](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)を参照してください。

   この URL を読み込むと、カスタマイズされた [!DNL at.js] ファイルのダウンロードが開始されます。

## at.js の実装 {#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js は、Web サイトのすべてのページの `<head>` 要素で実装する必要があります。

タグマネージャー（[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25)、[Dynamic Tag Management](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md#concept_3A40AF6FFC0E4FD2AA81B303A79D0B96) など）を使用しない Target の一般的な実装は次のようになります。

```
<!doctype html> 
<html> 
 
<head> 
    <meta charset="utf-8"> 
    <title>Title of the Page</title> 
    <!--Preconnect and DNS-Prefetch to improve page load time--> 
    <link rel="preconnect" href="//<client code>.tt.omtrdc.net"> 
    <link rel="dns-prefetch" href="//<client code>.tt.omtrdc.net"> 
    <!--/Preconnect and DNS-Prefetch--> 
    <!--Data Layer to enable rich data collection and targeting--> 
    <script> 
        var digitalData = { 
            "page": { 
                "pageInfo": { 
                    "pageName": "Home" 
                } 
            } 
        }; 
    </script> 
    <!--/Data Layer--> 
    <!-- targetPageParams(), targetPageParamsAll(), Data Providers or targetGlobalSettings() functions to enrich the visitor profile or modify the library settings--> 
    <script> 
        targetPageParams = function() { 
            return { 
                "a": 1, 
                "b": 2, 
                "pageName": digitalData.page.pageInfo.pageName, 
                "profile": { 
                    "age": 26, 
                    "country": { 
                        "city": "San Francisco" 
                    } 
                } 
            }; 
        }; 
    </script> 
    <!--/targetPageParams()--> 
 
    <!--jQuery or other helper libraries should be implemented before at.js if you would like to use their methods in Target--> 
    <script src="jquery-3.3.1.min.js"></script> 
    <!--/jQuery--> 
    <!--Target's JavaScript SDK, at.js--> 
    <script src="at.js"></script> 
    <!--/at.js--> 
</head> 
 
<body> 
    The default content of the page 
</body> 
 
</html>
```

次の重要な注意点を考慮してください。

* HTML5 doctype（例えば、`<!doctype html>`）を使用する必要があります。サポートされていない doctype や古い doctype を使用すると、Target がリクエストを送信できなくなる可能性があります。
* 事前接続とプリフェッチのオプションは、Web ページの読み込みを高速化するのに役立ちます。これらの設定を使用する場合、`<client code>` を独自のクライアントコードに置き換えてください。このコードは、「**[!UICONTROL セットアップ]**」／「**[!UICONTROL 実装]**」／「**[!UICONTROL at.js 設定を編集]」**ページから取得できます。
* データレイヤーがある場合、at.js が読み込まれる前にページの `<head>` でデータレイヤーについてできるだけ多く定義することが最適です。これにより、Target でこの情報をパーソナライゼーションのために最大限に利用できるようになります。
* 特殊な Target 関数（`targetPageParams()`、`targetPageParamsAll()`、データプロバイダー、および `targetGlobalSettings()` など）は、データレイヤーの後で、at.js が読み込まれる前に定義する必要があります。あるいは、[!UICONTROL at.js 設定を編集]ページの「[!UICONTROL ライブラリヘッダー]」セクションでこれらを保存して、at.js ライブラリ自体の一部として保存することもできます。これらの関数について詳しくは、[at.js 関数](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).
* jQuery などの JavaScript ヘルパーライブラリを使用する場合は、Target の前にそれらをインクルードすることで、Target エクスペリエンスを構築するときにそれらの構文とメソッドを活用できます。
* at.js はページの `<head>` に含めます。

## コンバージョンの追跡 {#task_E85D2F64FEB84201A594F2288FABF053}

注文の確認 mbox では、サイトでの注文に関する詳細が記録され、売上高および注文に基づくレポートが可能になります。また、注文の確認 mbox は、「商品 x および商品 y を購入した人」などのレコメンデーションアルゴリズムを駆動できます。

<!-- 

ov/t_create_orderconfirm-page-mbox-atjs.xml

 -->

>[!NOTE]
>
>ユーザーが Web サイトで買い物をする場合、レポートに Analytics for Target（A4T）を使用している場合でも、注文の確認 mbox を実装することをお勧めします。

1. 注文の詳細ページで、以下のモデルに示す mbox スクリプトを挿入します。
1. 大文字のテキストを、カタログの動的値または静的値に置き換えます。

   >[!NOTE]
   >
   >複数の製品 ID を区切るには、コンマを使用してください。

   **ヒント：**任意の mbox に注文情報を渡すこともできます（`orderConfirmPage` という名前にする必要はありません）。また、同じキャンペーン内の複数の mbox に注文情報を渡すこともできます。

   ```
   <script type="text/javascript"> 
   adobe.target.trackEvent({ 
       "mbox": "orderConfirmPage", 
       "params":{  
           "orderId": "ORDER ID FROM YOUR ORDER PAGE",  
           "orderTotal": "ORDER TOTAL FROM YOUR ORDER PAGE",  
           "productPurchasedId": "PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3"  
       } 
   }); 
   </script> 
   ```

注文の確認 mbox では、次のパラメーターを使用します。

| パラメーター | 説明 |
|--- |--- |
| orderId | 注文を識別する一意の値（コンバージョンのカウントに使用）。<br>`orderId` は一意である必要があります。重複する注文はレポートで無視されます。 |
| orderTotal | 購入金額。<br>通貨記号を渡さないでください。（コンマではなく）小数点を使用して、10 進数値を示します。 |
| productPurchasedId（オプション） | この注文で購入された製品 ID のコンマ区切りのリスト。<br>これらの製品 ID は監査レポートに表示され、さらに詳細なレポート分析ができます。 |