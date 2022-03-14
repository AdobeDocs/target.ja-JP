---
keywords: serverstate;targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings;global settings;at.js;functions;function;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders;Hybrid Personalization;deviceIdLifetime
description: Adobe [!DNL Target] at.js JavaScript ライブラリを使用して、 [!DNL Target] UI または REST API。
title: targetGlobalSettings() 関数の使用方法
feature: at.js
role: Developer
exl-id: 14080cf6-6a15-4829-b95d-62c068898564
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '2364'
ht-degree: 98%

---

# targetGlobalSettings()

[!DNL Target] Standard/Premium UI や REST API を使用して設定を構成する代わりに、`targetGlobalSettings()` を使用して at.js ライブラリで設定を上書きできます。

## 設定 {#section_42C759AE9B524A43B8659018677224B8}

次の設定を上書きできます。

### bodyHiddenStyle

* **型**：String
* **デフォルト値**：body { opacity:0 }
* **説明**：`globalMboxAutocreate === true` の場合にのみ使用して、ちらつきの発生を最小限に抑えます。

   詳しくは、「[at.js によるちらつきの制御方法](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md)」を参照してください。

### bodyHidingEnabled

* **タイプ**：ブール値
* **デフォルト値**：true
* **説明**：Visual Experience Composer で作成されたオファー（）の配信に `target-global-mbox` が使用される場合に、ちらつきの制御に使用します。

### clientCode

* **型**：String
* **デフォルト値**：UI で設定された値。
* **説明**：クライアントコードを表します。

### cookieDomain

* **型**：String
* **デフォルト値**：可能であれば、トップレベルドメインに設定します。
* **説明**：Cookie の保存時に使用するドメインを表します。

### crossDomain

* **型**：String
* **デフォルト値**：UI で設定された値。
* **説明**：クロスドメイントラッキングが有効になっているかどうかを表します。使用できる値は、disabled、enabled または x-only です。

### cspScriptNonce

* **タイプ**：以下の[コンテンツセキュリティポリシー](#content-security)を参照してください。
* **デフォルト値**：以下の[コンテンツセキュリティポリシー](#content-security)を参照してください。
* **説明**：以下の[コンテンツセキュリティポリシー](#content-security)を参照してください。

### cspStyleNonce

* **タイプ**：以下の[コンテンツセキュリティポリシー](#content-security)を参照してください。
* **デフォルト値**：以下の[コンテンツセキュリティポリシー](#content-security)を参照してください。
* **説明**：以下の[コンテンツセキュリティポリシー](#content-security)を参照してください。

### dataProviders

* **タイプ**：以下の[データプロバイダー](#data-providers)を参照してください。
* **デフォルト値**：以下の[データプロバイダー](#data-providers)を参照してください。
* **説明**：以下の[データプロバイダー](#data-providers)を参照してください。

### decisioningMethod {#on-device-decisioning}

* **型**：String
* **デフォルト値**：server-side
* **その他の値**：on-device、hybrid
* **説明**：以下の「判定方法」を参照してください。

   **判定方法**

   オンデバイス判定で Target は、at.js でのエクスペリエンスの提供方法を指示する[!UICONTROL 判定方法]という新しい設定を導入します。`decisioningMethod` には、server-side（サーバー側のみ）、on-device（オンデバイスのみ）、hybrid（ハイブリッド）の 3 つの値があります。`decisioningMethod` が `targetGlobalSettings()` で設定されると、[!DNL Target] のあらゆる決定のデフォルトの判定方法として機能します。

   **[!UICONTROL サーバー側のみ]**：

   at.js 2.5 以降が実装され web プロパティにデプロイされる場合に標準で設定されているデフォルトの判定方法は[!UICONTROL サーバー側のみ]です。

   [!UICONTROL サーバー側のみ ]をデフォルト設定として使用すると、すべての決定は [!DNL Target] エッジネットワーク上で行われます。これにはブロッキングサーバーコールが必要になります。このアプローチでは、待ち時間が徐々に増えるおそれがありますが、[Recommendations](/help/main/c-recommendations/recommendations.md)、[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)（AP）および[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)の各アクティビティなど、Target の機械学習機能を適用する機能を提供するなど、大きなメリットもあります。

   さらに、すべてのセッションやチャネルにわたって永続化された Target のユーザープロファイルを使用して、パーソナライズされたエクスペリエンスを強化することで、ビジネスに大きな成果をもたらすことができます。

   最後に、[!UICONTROL サーバー側のみ ]では、Adobe Experience Cloud を使用して、Audience Manager セグメントや Adobe Analytics セグメントを介してターゲティングできるオーディエンスを微調整できます。

   **[!UICONTROL オンデバイスのみ]**：

   [!UICONTROL オンデバイスのみ]は、オンデバイス判定を web ページ全体でのみ使用する場合に at.js 2.5 以降で設定する必要がある判定方法です。

   オンデバイス判定では、オンデバイス判定の対象となるすべてのアクティビティを含んだ、キャッシュされたルールアーティファクトから決定が行われるので、エクスペリエンスとパーソナライゼーションアクティビティを超高速で配信できます。

   どのアクティビティがオンデバイス判定の対象となるかについて詳しくは、サポートされている機能の節を参照してください。

   この判定方法は、[!DNL Target] からの決定を必要とするすべてのページでパフォーマンスが非常に重要な場合にのみ使用してください。さらに、この判定方法を選択した場合、オンデバイス判定の対象とならない [!DNL Target] アクティビティは配信も実行もされないことに注意してください。at.js ライブラリ 2.5 以降は、キャッシュされたルールアーティファクトのみを探して決定を下すように設定されています。

   **ハイブリッド**：

   [!UICONTROL ハイブリッド]は、オンデバイス判定アクティビティと、Adobe Target Edge ネットワークへのネットワーク呼び出しを必要とするアクティビティの両方を実行する必要がある場合に、at.js 2.5 以降で設定する必要がある判定方法です。

   オンデバイス判定アクティビティとサーバー側アクティビティの両方を管理している場合は、ページに [!DNL Target] をデプロイしてプロビジョニングする方法を考える際に、少し複雑で面倒な場合があります。ハイブリッド判定方法では、サーバー側実行が必要なアクティビティについて Adobe Target Edge ネットワークに対してサーバーコールを行う必要がある場合と、オンデバイス判定のみを実行する必要がある場合を [!DNL Target] が把握しています。

   JSON ルールアーティファクトには、mbox がサーバー側アクティビティを実行しているか、オンデバイス判定アクティビティを実行しているかを at.js に通知するメタデータが含まれています。この判定方法では、迅速に配信すべきアクティビティをオンデバイス判定を通じて行い、機械学習によるより強力なパーソナライゼーションを必要とするアクティビティについては、Adobe Target Edge ネットワークを介して行います。

### defaultContentHiddenStyle

* **型**：String
* **デフォルト値**：visibility: hidden
* **説明**：クラス名が「mboxDefault」である DIV を使用し、`mboxCreate()`、`mboxUpdate()` または `mboxDefine()` から実行される mbox のラッピングにのみ使用されて、デフォルトコンテンツを非表示にします。

### defaultContentVisibleStyle

* **型**：String
* **デフォルト値**：visibility: visible
* **Description**：クラス名が「mboxDefault」である DIV を使用し、`mboxCreate()`、`mboxUpdate()` または `mboxDefine()` から実行される mbox のラッピングにのみ使用されて、適用されたオファー（存在する場合）またはデフォルトコンテンツを表示します。

### deviceIdLifetime

* **タイプ**：数値
* **デフォルト値**：63244800000 ミリ秒 = 2 年
* **説明**：`deviceId` が Cookie に保持される時間。

>[!NOTE]
>
>deviceIdLifetime 設定は、at.js バージョン 2.3.1 以降で上書きできます。

### 有効

* **タイプ**：ブール値
* **デフォルト値**：true
* **説明**：有効にすると、エクスペリエンスおよびエクスペリエンスをレンダリングする DOM 操作を取得する [!DNL Target] リクエストが自動的に実行されます。さらに、[!DNL Target] 呼び出しは、`getOffer(s)`／`applyOffer(s)` を介して手動で実行できます。

   無効にした場合、[!DNL Target] リクエストは自動でも手動でも実行されません。

### globalMboxAutoCreate

* **タイプ**：数値
* **デフォルト値**：UI で設定された値。
* **説明**：グローバル mbox リクエストをトリガーするかどうかを示します。

### imsOrgId

* **タイプ**：文字列
* **デフォルト値**：true
* **説明**：IMS ORG ID を表します。

### optinEnabled

* **タイプ**：ブール値
* **デフォルト値**：false
* **説明**：[!DNL Target] では、ユーザーの同意管理戦略を支援できるように、[!DNL Adobe Experience Platform] を介したオプトイン機能がサポートされています。オプトイン機能を使用すると、[!DNL Target] タグを実行する方法とタイミングを制御できます。また、[!DNL Adobe Experience Platform] を介して [!DNL Target] タグを事前に承認するオプションも提供されています。[!DNL Target] の at.js ライブラリでオプトインを使用する機能を有効にするには、`optinEnabled=true` 設定を追加する必要があります。[!DNL Adobe Experience Platform] で、 拡張機能インストール表示の「[!UICONTROL GDPR オプトイン]」ドロップダウンリストから「有効」を選択する必要があります。詳しくは、[Adobe Experience Platform ドキュメント ](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)を参照してください。 この設定は、EU 一般データ保護規則（GDPR）やカリフォルニア州消費者プライバシー法（CCPA）など、プライバシーおよびデータ保護規則に関連するので、詳しくは[プライバシーおよびデータ保護規則](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)を参照してください。

### optoutEnabled

* **タイプ**：ブール値
* **デフォルト値**：false
* **説明**：Target が訪問者 API の `isOptedOut()` 関数を呼び出す必要があるかどうかを示します。これは、デバイスグラフ有効化の一部です。

### overrideMboxEdgeServer

* **タイプ**：ブール値
* **デフォルト値**：true（at.js バージョン 1.6.2 以降）
* **説明**：`<clientCode>.tt.omtrdc.net`ドメインまたは `mboxedge<clusterNumber>.tt.omtrdc.net` ドメインを使用する必要があるかどうかを示します。

   この値が true の場合、`mboxedge<clusterNumber>.tt.omtrdc.net` ドメインは Cookie に保存されます。at.js 1.8.2 および at.js 2.3.1 より前のバージョンの at.js を使用している場合、現時点では、[CNAME](/help/main/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) が機能しません。この問題が発生する場合は、[at.js を新しいサポート対象バージョンに更新](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)することを検討してください。

### overrideMboxEdgeServerTimeout

* **タイプ**：数値
* **デフォルト値**：1860000 => 31 分
* **説明**：`mboxedge<clusterNumber>.tt.omtrdc.net` 値を含んだ Cookie の有効期間を示します。

### pageLoadEnabled

* **タイプ**：ブール値
* **デフォルト値**：true
* **説明**：有効にすると、ページ読み込み時に返す必要のあるエクスペリエンスが自動的に取得されます。

### secureOnly

* **タイプ**：ブール値
* **デフォルト値**：false
* **説明**：at.js で HTTPS のみを使用するか、ページのプロトコルに基づいて HTTP と HTTPS を切り替えることができるかを示します。true に設定した場合、secureOnly は Secure 属性と SameSite 属性も mbox Cookie に設定します。

### selectorsPollingTimeout

* **タイプ**：数値
* **デフォルト値**：5000 ミリ秒 = 5 秒
* **説明**：at.js 0.9.6 では、`targetGlobalSettings` で上書きできるこの新しい設定が [!DNL Target] に導入されました。

   `selectorsPollingTimeout` 設定は、セレクターで識別されたすべての要素がページに表示されるまでクライアントが待機できる時間を表します。

   Visual Experience Composer（VEC）によって作成されたアクティビティには、セレクターが含まれたオファーがあります。

### serverDomain

* **型**：String
* **デフォルト値**：UI で設定された値。
* **説明**：Target エッジサーバーを表します。

### serverState

* **タイプ**：以下の[ハイブリッドパーソナライゼーション](#server-state)を参照してください。
* **デフォルト値**：以下の[ハイブリッドパーソナライゼーション](#server-state)を参照してください。
* **説明**：以下の[ハイブリッドパーソナライゼーション](#server-state)を参照してください。

### telemetryEnabled {#telemetry}

* **タイプ**：ブール値
* **デフォルト値**：true
* **説明**:有効にした場合、 [!DNL Adobe] は、SDK 機能の使用状況とパフォーマンスのテレメトリデータを収集します。 個人データは収集されません。 

### timeout

* **タイプ**：数値
* **デフォルト値**：UI で設定された値。
* **説明**：[!DNL Target] エッジリクエストのタイムアウトを表します。

### viewsEnabled

* **タイプ**：ブール値
* **デフォルト値**：true
* **説明**：有効な場合、ページ読み込み時に返す必要があるビューを自動的に取得します。ビューは at.js 2 でサポートされています。*x* のみで使用できます。

### visitorApiTimeout

* **タイプ**：数値
* **デフォルト値**：2000 ms = 2 秒
* **説明**：[!UICONTROL 訪問者 API] リクエストのタイムアウトを表します。

## 使用方法 {#section_9AD6FA3690364F7480C872CB55567FB0}

この関数は、at.js が読み込まれる前か、**[!UICONTROL 管理]**／**[!UICONTROL 実装]**／**[!UICONTROL at.js 設定を編集]**／**[!UICONTROL コード設定]**／**[!UICONTROL ライブラリヘッダー]**&#x200B;で定義できます。

「ライブラリのヘッダー」フィールドでは、JavaScript を自由形式で入力できます。カスタマイズコードは次の例のようになります。

```javascript
window.targetGlobalSettings = {  
   timeout: 200, // using custom timeout  
   visitorApiTimeout: 500, // using custom API timeout  
   enabled: document.location.href.indexOf('https://www.adobe.com') >= 0 // enabled ONLY on adobe.com  
};
```

## データプロバイダー {#data-providers}

この設定では、Demandbase、BlueKai、カスタムサービスなどのサードパーティのデータプロバイダーからデータを収集し、そのデータをグローバル mbox リクエストで mbox パラメーターとして渡すことができます。非同期および同期リクエストを介した複数のプロバイダーからのデータ収集もサポートしています。この手法では、デフォルトのページコンテンツのちらつきを制御しながら、プロバイダーごとに個別のタイムアウトを指定し、ページのパフォーマンスへの影響を抑制することが簡単にできます。

>[!NOTE]
>
>データプロバイダーは、[!DNL at.js] 1.3 以降を必要とします。

詳細は次のビデオで説明されています。

| ビデオ | 説明 |
|--- |--- |
| [Adobe Target でのデータプロバイダーの使用](https://helpx.adobe.com/jp/target/kt/using/dataProviders-atjs-feature-video-use.html) | データプロバイダーは、サードパーティから Target へデータを簡単に渡すことのできる機能です。サードパーティとしては、気象予報サービス、DMP、自社の Web サービスなども利用可能です。このデータを利用して、オーディエンスやターゲットコンテンツを構築したり、訪問者プロファイルを充実させることができます。 |
| [Adobe Target でのデータプロバイダーの実装](https://helpx.adobe.com/jp/target/kt/using/dataProviders-atjs-technical-video-implement.html) | サードパーティデータプロバイダーからデータを回収し Target リクエストで渡す、Adobe Target のデータプロバイダー機能の使用方法の実装詳細と例。 |

`window.targetGlobalSettings.dataProviders` 設定は、データプロバイダーの配列です。

各データプロバイダーの構造は次のとおりです。

| キー | タイプ | 説明 |
|--- |--- |--- |
| name | 文字列 | プロバイダーの名前。 |
| version | 文字列 | プロバイダーのバージョン。このキーはプロバイダーの展開に使用されます。 |
| timeout | 数値 | ネットワークリクエストの場合は、プロバイダーのタイムアウトを表します。このキーはオプションです。 |
| provider | 関数 | プロバイダーデータの取得ロジックを含む関数。<br>この関数の必須パラメーターは `callback` のみです。この callback パラメーターは、データを適切に取得した場合またはエラーが発生した場合にのみ呼び出す必要があります。<br>このコールバックは、次の 2 つのパラメーターを受け取ります。<ul><li>error：エラーの有無を表します。エラーがない場合、このパラメーターは null に設定されます。</li><li>params：Target リクエストで送信されるパラメーターを表す JSON オブジェクト。</li></ul> |

データプロバイダーで同期実行を使用する場合の例は次のとおりです。

```javascript
var syncDataProvider = { 
  name: "simpleDataProvider", 
  version: "1.0.0", 
  provider: function(callback) { 
    callback(null, {t1: 1}); 
  } 
}; 
  
window.targetGlobalSettings = { 
  dataProviders: [ 
    syncDataProvider 
  ] 
};
```

at.js によって `window.targetGlobalSettings.dataProviders` が処理されると、Target リクエストには `t1=1` という新しいパラメーターが含まれます。

Target のリクエストに追加するパラメーターを、BlueKai、Demandbase などのサードパーティサービスから取得する場合の例は次のとおりです。

```javascript
var blueKaiDataProvider = { 
   name: "blueKai", 
   version: "1.0.0", 
   provider: function(callback) { 
      // simulating network request 
     setTimeout(function() { 
       callback(null, {t1: 1, t2: 2, t3: 3}); 
     }, 1000); 
   } 
} 
  
window.targetGlobalSettings = { 
   dataProviders: [ 
      blueKaiDataProvider 
   ] 
};
```

at.js によって `window.targetGlobalSettings.dataProviders` が処理されると、Target のリクエストには、`t2=2`、`t1=1`、および `t3=3` という追加パラメーターが含まれます。

次の例では、データプロバイダーを使用して weather API データを取得し、Target リクエストでパラメーターとして送信します。Target リクエストには、`country`、`weatherCondition` などのパラメーターも追加されます。

```javascript
var weatherProvider = { 
      name: "weather-api", 
      version: "1.0.0", 
      timeout: 2000, 
      provider: function(callback) { 
        var API_KEY = "caa84fc6f5dc77b6372d2570458b8699"; 
        var lat = 44.426767399999996; 
        var lon = 26.1025384; 
        var url = "//api.openweathermap.org/data/2.5/weather?lang=en"; 
        var data = { 
          lat: lat, 
          lon: lon, 
          appId: API_KEY 
        } 
 
        $.ajax({ 
          type: "GET", 
                url: url, 
          dataType: "json", 
          data: data, 
          success: function(data) { 
            console.log("Weather data", data); 
            callback(null, { 
              country: data.sys.country, 
              weatherCondition: data.weather[0].main 
            }); 
          }, 
          error: function(err) { 
            console.log("Error", err); 
            callback(err); 
          } 
        });         
      } 
    }; 
 
    window.targetGlobalSettings = { 
      dataProviders: [weatherProvider] 
    };
```

`dataProviders` 設定を使用する際は、次の点に注意してください。

* `window.targetGlobalSettings.dataProviders` に追加されたデータプロバイダーが非同期の場合は、同時並行で実行されます。訪問者 API リクエストは、待ち時間を最小限に抑えるために、`window.targetGlobalSettings.dataProviders` に追加された関数と同時に実行されます。
* at.js では、データはキャッシュされません。データプロバイダーが 1 回だけデータを取得する場合は、データをキャッシュし、そのプロバイダーの関数が呼び出されたら、2 回目の呼び出しでキャッシュデータを配信できるようにする必要があります。

## コンテンツセキュリティポリシー {#content-security}

at.js 2.3.0 以降では、配信された Target オファーの適用時にページ DOM に追加される SCRIPT タグと STYLE タグに対するコンテンツセキュリティポリシーの Nonce の設定がサポートされています。

at.js 2.3.0 以降の読み込みに先立って、SCRIPT と STYLE の Nonce を `targetGlobalSettings.cspScriptNonce` と `targetGlobalSettings.cspStyleNonce` で設定する必要があります。 以下の例を参照してください。

```javascript
...
<head>
 <script nonce="<script_nonce_value>">
window.targetGlobalSettings = {
  cspScriptNonce: "<csp_script_nonce_value>",
  cspStyleNonce: "<csp_style_nonce_value>"
};
 </script>
 <script nonce="<script_nonce_value>" src="at.js"></script>
...
</head>
...
```

`cspScriptNonce` と `cspStyleNonce` の設定を指定した後、at.js 2.3.0 以降では、Target オファーの適用時に DOM に追加するすべての SCRIPT タグと STYLE タグに対して、これらを Nonce 属性に設定します。

## ハイブリッドパーソナライゼーション {#server-state}

`serverState` は at.js v2.2 以降で使用できる設定です。Target のハイブリッド統合が実装されている場合に、ページのパフォーマンスを最適化するために使用できます。ハイブリッド統合とは、at.js v2.2 以降（クライアントサイド）と、配信 API または Target SDK（サーバーサイド）の両方を使用してエクスペリエンスを提供することを意味します。`serverState` には、at.js v2.2 以降で、サーバーサイドで取得したコンテンツからエクスペリエンスを直接適用し、提供されるページの一部としてクライアントに返す機能が備わっています。

### 前提条件

[!DNL Target] のハイブリッド統合が必要です。

* **サーバー側**：新しい[配信 API](https://developers.adobetarget.com/api/delivery-api/) または [Target SDK](https://developers.adobetarget.com/api/delivery-api/#section/SDKs) を使用する必要があります。
* **クライアント側**：[at.js バージョン 2.2 以降](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を使用する必要があります。

### コードサンプル

この仕組みをより深く理解するには、サーバー上にある以下のコード例を参照してください。 このコードは、[Target Node.js SDK](https://github.com/adobe/target-nodejs-sdk) の使用を前提としています。

```javascript
// First, we fetch the offers via Target Node.js SDK API, as usual
const targetResponse = await targetClient.getOffers(options);
// A successfull response will contain Target Delivery API request and response objects, which we need to set as serverState
const serverState = {
  request: targetResponse.request,
  response: targetResponse.response
};
// Finally, we should set window.targetGlobalSettings.serverState in the returned page, by replacing it in a page template, for example
const PAGE_TEMPLATE = `
<!doctype html>
<html>
<head>
  ...
  <script>
    window.targetGlobalSettings = {
      overrideMboxEdgeServer: true,
      serverState: ${JSON.stringify(serverState, null, " ")}
    };
  </script>
  <script src="at.js"></script>
</head>
...
</html>
`;
// Return PAGE_TEMPLATE to the client ...
```

ビュー事前読み込みの `serverState` オブジェクト JSON の例を次に示します。

```
{
 "request": {
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "context": {
   "channel": "web",
   "timeOffsetInMinutes": 0
  },
  "experienceCloud": {
   "analytics": {
    "logging": "server_side",
    "supplementalDataId": "7D3AA246CC99FD7F-1B3DD2E75595498E"
   }
  },
  "prefetch": {
   "views": [
    {
     "address": {
      "url": "my.testsite.com/"
     }
    }
   ]
  }
 },
 "response": {
  "status": 200,
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "client": "testclient",
  "edgeHost": "mboxedge21.tt.omtrdc.net",
  "prefetch": {
   "views": [
    {
     "name": "home",
     "key": "home",
     "options": [
      {
       "type": "actions",
       "content": [
        {
         "type": "setHtml",
         "selector": "#app > DIV.app-container:eq(0) > DIV.page-container:eq(0) > DIV:nth-of-type(2) > SECTION.section:eq(0) > DIV.container:eq(1) > DIV.heading:eq(0) > H1.title:eq(0)",
         "cssSelector": "#app > DIV:nth-of-type(1) > DIV:nth-of-type(1) > DIV:nth-of-type(2) > SECTION:nth-of-type(1) > DIV:nth-of-type(2) > DIV:nth-of-type(1) > H1:nth-of-type(1)",
         "content": "<span style=\"color:#FF0000;\">Latest</span> Products for 2020"
        }
       ],
       "eventToken": "t0FRvoWosOqHmYL5G18QCZNWHtnQtQrJfmRrQugEa2qCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
       "responseTokens": {
        "profile.memberlevel": "0",
        "geo.city": "dublin",
        "activity.id": "302740",
        "experience.name": "Experience B",
        "geo.country": "ireland"
       }
      }
     ],
     "state": "J+W1Fq18hxliDDJonTPfV0S+mzxapAO3d14M43EsM9f12A6QaqL+E3XKkRFlmq9U"
    }
   ]
  }
 }
}
```

ページがブラウザーに読み込まれた後、at.js は [!DNL Target] エッジに対するネットワーク呼び出しを実行せずに、`serverState` からのすべての [!DNL Target] オファーを直ちに適用します。さらに、at.js は、コンテンツが取得されたサーバー側で [!DNL Target] オファーが使用可能な DOM 要素のみを事前に非表示にするので、ページ読み込みのパフォーマンスとエンドユーザーエクスペリエンスに好影響を及ぼします。

### 重要事項

`serverState` を使用する場合は、以下の事項を考慮してください。

* 現時点で、at.js v2.2 は、以下に対してのみ serverState を介したエクスペリエンスの配信をサポートしています。

   * ページの読み込み時に実行される、VEC で作成されたアクティビティ。
   * 事前読み込みされたビュー。

      at.js API で [!DNL Target] ビューと `triggerView()` を使用している SPA の場合、at.js v2.2 は、サーバー側で事前読み込みされたすべてのビューのコンテンツをキャッシュし、`triggerView()` を介して各ビューがトリガーされるとすぐに適用されます。この場合もやはり、Target に対する追加のコンテンツ取得呼び出しはトリガーされません。

   * **注意**：現在、サーバー側で取得された mbox は、`serverState` ではサポートされていません。

* `serverState ` オファーを適用する場合、at.js では `pageLoadEnabled` と `viewsEnabled` の設定を考慮します。例えば、`pageLoadEnabled` 設定が false の場合、ページ読み込みオファーは適用されません。

   これらの設定をオンにするには、**[!UICONTROL 管理]／[!UICONTROL 実装]／[!UICONTROL 編集]／[!UICONTROL ページ読み込みが有効]**&#x200B;で有効に切り替えます。

   ![「ページ読み込みが有効」設定](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* `serverState` を使用し、返されるコンテンツで `<script>` タグを使用する場合は、HTML コンテンツで `</script>` の代わりに `<\/script>` が使用されていることを確認してください。`</script>` を使用すると、ブラウザーが `</script>` をインライン SCRIPT の終わりと解釈して、HTML ページが破損する可能性があります。

### その他のリソース

`serverState` の仕組みについて詳しくは、次のリソースを参照してください。

* [サンプルコード](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [`serverState` を使用した単一ページアプリケーション（SPA）サンプルアプリケーション](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo)。
