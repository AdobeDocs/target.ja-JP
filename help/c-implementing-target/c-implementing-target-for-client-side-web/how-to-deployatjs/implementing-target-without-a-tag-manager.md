---
keywords: implement target;implementation;implement at.js;tag manager
description: タグマネージャー（Adobe Launch または Dynamic Tag Management）を使用しないで Adobe Target を実装する方法について説明します。
title: タグマネージャーを使用しない Target の実装
subtopic: Getting Started
topic: Standard
uuid: 3ecc041a-42d8-40f8-90be-7856e1d3d080
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '1537'
ht-degree: 64%

---


# タグマネージャーを使用しない Target の実装{#implement-target-without-a-tag-manager}

Information about implementing [!DNL Adobe Target] without using a tag manager ([!DNL Adobe Launch] or [!DNL Dynamic Tag Manager]).

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) は、Target および at.js ライブラリを実装するための推奨される方法です。次の情報は、Adobe Launch を使用して Target を実装する場合には適用されません。

[!UICONTROL 実装] ページにアクセスするには、 **[!UICONTROL 管理]** / **[!UICONTROL 実装]**&#x200B;をクリックします。

このページでは、次の設定を指定できます。

* アカウントの詳細
* 導入方法
* プロファイルAPI
* デバッガツール
* プライバシー

>[!NOTE]
>
>Target Standard/Premium UI や REST API を使用して設定を構成する代わりに、at.js ライブラリで設定を上書きすることができます。詳しくは、[targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) を参照してください。

## アカウントの詳細

次のアカウントの詳細を表示できます。 これらの設定は変更できません。

| 設定 | 説明 |
| --- | --- |
| クライアントコード | クライアントコードは、Target API を使用する際に必要になることの多い、クライアント固有の一連の文字です。 |
| IMS 組織 ID | この ID は、実装を [!DNL Adobe Experience Cloud] アカウントと結び付けます。 |

## 導入方法

以下の設定は、Implementation methodsパネルで設定できます。

### グローバル設定

>[!NOTE]
>
>これらの設定は、すべての [!DNL Target] .jsライブラリに適用されます。 「 [!UICONTROL 実装方法] 」セクションの変更を実行した後、ライブラリをダウンロードして、実装で更新する必要があります。

|ページの読み込みが有効です(グローバルmboxを自動作成|各ページの読み込み時に自動的に実行されるように、グローバルmbox呼び出しをat.jsファイルに埋め込むかどうかを選択します。|
|グローバルmbox|グローバルmboxの名前を選択します。 デフォルトでは、この名前は target-global-mbox です。<br>at.js を使用した mbox 名には、アンパサンド（&amp;）を含む特殊文字を使用できます。|
|Timeout (seconds)|If [!DNL Target] does not respond with content within the defined period, the server call times out and default content is displayed. 訪問者のセッション中、追加の呼び出しが引き続き試行されます。デフォルト値は 5 秒です。<br>at.js ライブラリは、`XMLHttpRequest` のタイムアウト設定を使用します。タイムアウトは、リクエストが実行されると開始され、[!DNL Target] がサーバーから応答を受け取ると停止します。詳しくは、Mozilla Developer Network の [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout) を参照してください。<br>応答を受け取る前に指定されたタイムアウトが発生すると、デフォルトのコンテンツが表示され、訪問者はアクティビティの参加者としてカウントされる可能性があります。これは、[!DNL Target] エッジですべてのデータ収集がおこなわれるためです。リクエストが [!DNL Target] エッジに到達すると、訪問者はカウントされます。<br>タイムアウト設定を構成する際は、次の点を考慮してください。<ul><li>値が低すぎると、訪問者はアクティビティの参加者としてカウントされるものの、ほとんどの時間デフォルトのコンテンツが表示される可能性があります。</li><li>値が高すぎると、Web ページに空白の領域が表示されるか、長時間の本文の非表示を使用している場合は空白のページが表示される可能性があります。</li></ul>mbox の応答時間をよりよく把握するには、ブラウザーの開発者ツールの「ネットワーク」タブを確認してください。また、Catchpoint など、サードパーティの Web パフォーマンス監視ツールを使用することもできます。<br>**注意： **[visitorApiTimeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)設定では、[!DNL Target]が訪問者 API の応答を長時間待たないようにします。この設定と、ここで説明している at.js のタイムアウト設定は相互に影響しません。|
|プロファイルの有効期間|この設定は、訪問者プロファイルの保存期間を決定します。 デフォルトでは、プロファイルは 2 週間保存されます。この期間は最大で 90 日まで延長することができます。<br>プロファイルの有効期間の設定を変更する場合は、[ClientCareにお問い合わせください](https://helpx.adobe.com/jp/contact/enterprise-support.ec.html)。|

### 主な実装方法

>[!IMPORTANT]
>
>Targetチームは、at.js 1の両方をサポートしています。*x* と at.js 2.*x* 間のマッピングについて説明します。サポートされているバージョンを実行していることを確認するには、at.jsのメジャーバージョンのいずれかを最新のアップデートにアップグレードしてください。

目的のat.jsバージョンをダウンロードするには、該当する「 **[!UICONTROL ダウンロード]** 」ボタンをクリックします。

at.jsの設定を編集するには、目的のat.jsバージョンの横にある「 **[!UICONTROL 編集]** 」をクリックします。

>[!IMPORTANT]
>
>これらのデフォルト設定を変更する前に、現在の実装に影響を与えないように、 [ClientCare](/help/cmp-resources-and-contact-information.md) にお問い合わせください。

上記の設定に加えて、次のat.js固有の設定も使用できます。

| 設定 | 説明 |
|--- |--- |
| カスタムライブラリヘッダー | ライブラリの最上部に含めるカスタム JavaScript を追加します。 |
| カスタムライブラリフッター | ライブラリの最下部に含めるカスタム JavaScript を追加します。 |

### プロファイルAPI

API による一括更新の認証を有効または無効にし、プロファイル認証トークンを生成します。

For more information, see [Profile API settings](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/profile-api-settings.md).

### デバッガツール

高度な [!DNL Target] デバッグツールを使用するための認証トークンを生成します。 Click **[!UICONTROL Generate New Authentication Token]**.

![新しい認証トークンの生成](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

### プライバシー

これらの設定は、プライバシーに関する法律に準拠し [!DNL Target] た方法でを使用できます。

「訪問者のIPアドレスを不明化」ドロップダウンリストから目的の設定を選択します。

* 最終オクテットの不明化
* IPの全体的な不明化
* None

詳しくは、[プライバシー](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md)を参照してください。

>[!NOTE]
>
>「レガシーブラウザーのサポート」オプションは、at.jsバージョン0.9.3以前で使用可能でした。 This option was removed in at.js version 0.9.4. For a list of browsers supported by at.js, see [Supported Browsers](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).<br>レガシーブラウザーは、CORS（クロスオリジンリソース共有）を完全にはサポートしない古いブラウザーです。こうしたブラウザーには、バージョン 11 より前の Internet Explorer およびバージョン 6 以下の Safari が含まれます。「レガシーブラウザーのサポート」を無効にした場合、Targetーはコンテンツを配信しなかったか、これらのブラウザーのレポートで訪問者をカウントしていました。 このオプションを有効にした場合、古いブラウザーで品質保証を行い、優れたカスタマーエクスペリエンスを確実に得ることをお勧めします。

## at.js のダウンロード {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

Instructions to download the library using the [!DNL Target] interface or the Download API.

>[!NOTE]
>
>* [Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) は、Target および at.js ライブラリを実装するための推奨される方法です。次の情報は、Adobe Launch を使用して Target を実装する場合には適用されません。
   >
   >
* Targetチームは、at.js 1の両方をサポートしています。*x* と at.js 2.*x* 間のマッピングについて説明します。サポートされているバージョンを実行していることを確認するには、at.jsのメジャーバージョンのいずれかを最新のアップデートにアップグレードしてください。 各バージョンについて詳しくは、 [at.js のバージョンの詳細](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)を参照してください。


### Download at.js using the Target interface {#section_1F5EE401C2314338910FC57F9592894E}

[!DNL at.js] インターフェイスから [!DNL Target] をダウンロードするには：

1. [ **[!UICONTROL 管理]** ] > [ **[!UICONTROL 実装]**]の順にクリックします。
1. 「 [!UICONTROL 実装方法] 」セクションで、目的のat.jsバージョンの横にある「 **[!UICONTROL ダウンロード]** 」ボタンをクリックします。

### Download at.js using the Target Download API {#section_C0D9D2A9068144708D08526BA5CA10D0}

API を使用して [!DNL at.js] をダウンロードするには：

1. クライアントコードを取得します。

   Your client code is available at the top of the **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** page of the [!DNL Target] interface.

1. 管理番号を取得します。

   次の URL を読み込みます。

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   Replace `client code` with the client code from Step 1.

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
   https://admin<varname>admin number</varname>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code</varname>&version=<version number>
   ```

   * Replace `admin number` with your admin number.
   * Replace `client code` with the client code from Step 1.
   * Replace `version number` with the desired at.js version number (for example, 2.2).

   >[!IMPORTANT]
   >
   >Target チームがサポートを提供しているのは、[!DNL at.js] の最新バージョンとその 1 つ前のバージョンの 2 つのみです。必要に応じて [!DNL at.js] をアップグレードし、サポート対象のバージョンを使用するようにしてください。各バージョンについて詳しくは、 [at.js のバージョンの詳細](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)を参照してください。

   この URL を読み込むと、カスタマイズされた [!DNL at.js] ファイルのダウンロードが開始されます。

## at.js implementation {#concept_03CFA86973A147839BEB48A06FEE5E5A}

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
* 事前接続とプリフェッチのオプションは、Web ページの読み込みを高速化するのに役立ちます。If you use these configurations, ensure that you replace `<client code>` with your own client code, which you can obtain from the **[!UICONTROL Administration]** > **[!UICONTROL Implementation] page.
* データレイヤーがある場合、at.js が読み込まれる前にページの `<head>` でデータレイヤーについてできるだけ多く定義することが最適です。これにより、Target でこの情報をパーソナライゼーションのために最大限に利用できるようになります。
* 特殊な Target 関数（`targetPageParams()`、`targetPageParamsAll()`、データプロバイダー、および `targetGlobalSettings()` など）は、データレイヤーの後で、at.js が読み込まれる前に定義する必要があります。あるいは、[!UICONTROL at.js 設定を編集]ページの「[!UICONTROL ライブラリヘッダー]」セクションでこれらを保存して、at.js ライブラリ自体の一部として保存することもできます。これらの関数について詳しくは、[at.js 関数](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).
* jQuery などの JavaScript ヘルパーライブラリを使用する場合は、Target の前にそれらをインクルードすることで、Target エクスペリエンスを構築するときにそれらの構文とメソッドを活用できます。
* at.js はページの `<head>` に含めます。

## Track conversions {#task_E85D2F64FEB84201A594F2288FABF053}

注文の確認 mbox では、サイトでの注文に関する詳細が記録され、売上高および注文に基づくレポートが可能になります。また、注文の確認 mbox は、「商品 x および商品 y を購入した人」などのレコメンデーションアルゴリズムを駆動できます。

>[!NOTE]
>
>ユーザーが Web サイトで買い物をする場合、レポートに Analytics for Target（A4T）を使用している場合でも、注文の確認 mbox を実装することをお勧めします。

1. 注文の詳細ページで、以下のモデルに示す mbox スクリプトを挿入します。
1. 大文字のテキストを、カタログの動的値または静的値に置き換えます。

   >[!NOTE]
   >
   >複数の製品 ID を区切るには、コンマを使用してください。

   **ヒント：**&#x200B;任意の mbox に注文情報を渡すこともできます（`orderConfirmPage` という名前にする必要はありません）。また、同じキャンペーン内の複数の mbox に注文情報を渡すこともできます。

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