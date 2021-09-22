---
keywords: serverstate;targetGlobalSettings;targetglobalSettings;globalSettings;globalSettings；グローバル設定；at.js；関数；clientCode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHidenStyle;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeTimeout;optout;selectorsPollingTimeout;dataProvidersパーソナライゼーション；deviceIdLifetime
description: Adobe [!DNL Target] at.js JavaScript library to override settings instead of using the [!DNL Target] UIまたはREST APIには、 targetGlobalSettings()関数を使用します。
title: targetGlobalSettings()関数の使用方法を教えてください。
feature: at.js
role: Developer
exl-id: 14080cf6-6a15-4829-b95d-62c068898564
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: tm+mt
source-wordcount: '2332'
ht-degree: 30%

---

# targetGlobalSettings()

[!DNL Target] Standard/Premium UI や REST API を使用して設定を構成する代わりに、`targetGlobalSettings()` を使用して at.js ライブラリで設定を上書きできます。

## 設定 {#section_42C759AE9B524A43B8659018677224B8}

次の設定を上書きできます。

### bodyHiddenStyle

* **型**：String
* **デフォルト値**:body { opacity:0 }
* **説明**:の場合にのみ使 `globalMboxAutocreate === true` 用され、ちらつきの発生を最小限に抑えます。

   詳しくは、「[at.js によるちらつきの制御方法](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md)」を参照してください。

### bodyHidingEnabled

* **型**:Boolean
* **デフォルト値**:true
* **説明**:Visual Experience Composerで作成されたオファー( `target-global-mbox` ビジュアルオファー)の配信にが使用されている場合に、ちらつきの制御に使用します。

### clientCode

* **型**：String
* **デフォルト値**:UIを使用して設定された値。
* **説明**:クライアントコードを表します。

### cookieDomain

* **型**：String
* **デフォルト値**:可能であれば、トップレベルドメインに設定します。
* **説明**:Cookieの保存時に使用されるドメインを表します。

### crossDomain

* **型**：String
* **デフォルト値**:UIを使用して設定された値。
* **説明**:クロスドメイントラッキングが有効になっているかどうかを示します。使用できる値は次のとおりです。無効、有効、またはxのみ。

### cspScriptNonce

* **型**:以下の「コン [テンツセキュリティポリシ](#content-security) ー」を参照してください。
* **デフォルト値**:以下の「コン [テンツセキュリティポリシ](#content-security) ー」を参照してください。
* **説明**:以下の「コン [テンツセキュリティポリシ](#content-security) ー」を参照してください。

### cspStyleNonce

* **型**:以下の「コン [テンツセキュリティポリシ](#content-security) ー」を参照してください。
* **デフォルト値**:以下の「コン [テンツセキュリティポリシ](#content-security) ー」を参照してください。
* **説明**:以下の「コン [テンツセキュリティポリシ](#content-security) ー」を参照してください。

### dataProviders

* **型**:以下の「デー [タプロバイダ](#data-providers) ー」を参照してください。
* **デフォルト値**:以下の「デー [タプロバイダ](#data-providers) ー」を参照してください。
* **説明**:以下の「デー [タプロバイダ](#data-providers) ー」を参照してください。

### decisioningMethod {#on-device-decisioning}

* **型**：String
* **デフォルト値**:サーバーサイド
* **その他の値**:オンデバイス、ハイブリッド
* **説明**:以下の「判定メソッド」を参照してください。

   **判定メソッド**

   オンデバイス判定機能を使用すると、Targetは、at.jsによるエクスペリエンスの配信方法を指示する[!UICONTROL 判定方法]という新しい設定を導入します。 `decisioningMethod`には次の3つの値があります。サーバー側のみ、オンデバイス専用、ハイブリッド。 `decisioningMethod`が`targetGlobalSettings()`に設定されている場合、[!DNL Target]のすべての決定のデフォルトの決定方法として機能します。

   **[!UICONTROL サーバー側のみ]**:

   [!UICONTROL サーバー側の] みが、at.js 2.5以降が実装されWebプロパティにデプロイされた場合に初期設定で設定されるデフォルトの判定方法です。

   [!UICONTROL サーバー側のみ]をデフォルト設定として使用すると、[!DNL Target]エッジネットワーク上ですべての決定がおこなわれ、ブロックサーバー呼び出しが必要になります。 このアプローチは、徐々に遅延を引き起こす可能性がありますが、[Recommendations](/help/c-recommendations/recommendations.md)、[Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)(AP)、[自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md)アクティビティなど、Targetの機械学習機能を適用する機能を提供するなど、大きなメリットもあります。

   さらに、セッションやチャネルをまたいで保持されるTargetのユーザープロファイルを使用して、パーソナライズされたエクスペリエンスを強化することで、ビジネスに強力な成果をもたらすことができます。

   最後に、[!UICONTROL サーバー側のみ]を使用すると、Audience ManagerやAdobe Analyticsセグメントを介してターゲットに設定できるオーディエンスをAdobe Experience Cloudで微調整できます。

   **[!UICONTROL デバイス上のみ]**:

   [!UICONTROL オンデバイス判定] は、Webページ全体でのみ使用する場合にat.js 2.5以降で設定する必要がある判定方法に限られます。

   オンデバイス判定では、オンデバイス判定の対象となるすべてのアクティビティを含むキャッシュされたルールアーティファクトから判定がおこなわれるので、エクスペリエンスとパーソナライゼーションアクティビティを超高速で配信できます。

   オンデバイス判定の対象となるアクティビティについて詳しくは、サポートされる機能の節を参照してください。

   この判定方法は、[!DNL Target]からの判断を必要とするすべてのページでパフォーマンスが非常に重要な場合にのみ使用してください。 さらに、この判定方法を選択した場合、On-Device Decisioningの対象とならない[!DNL Target]アクティビティは配信も実行もされないことに注意してください。 at.jsライブラリ2.5以降は、キャッシュされたルールアーティファクトのみを検索して決定するように設定されています。

   **ハイブリッド**:

    Hybridisは、Adobe Target Edgeネットワークへのネットワーク呼び出しを必要とするオンデバイス判定とアクティビティの両方を実行する必要がある場合にat.js 2.5以降に設定する必要がある判定方法です。

   デバイス上判定アクティビティとサーバー側アクティビティの両方を管理する場合、ページに[!DNL Target]をデプロイしてプロビジョニングする方法を考える際には、少し複雑で面倒な場合があります。 ハイブリッドを判定方法として使用する場合、[!DNL Target]は、サーバー側での実行が必要なアクティビティに対して、いつAdobe Target Edgeネットワークへのサーバー呼び出しをおこなうか、また、デバイス上での判定のみを実行するかを把握します。

   JSONルールアーティファクトには、mboxがサーバー側のアクティビティを実行しているか、オンデバイス判定アクティビティを実行しているかをat.jsに通知するメタデータが含まれます。 この判定方法では、迅速に配信するアクティビティを、オンデバイス判定を通じておこない、より強力なML駆動型パーソナライゼーションを必要とするアクティビティでは、Adobe Target Edgeネットワークを介しておこないます。

### defaultContentHiddenStyle

* **型**：String
* **デフォルト値**:表示：非表示
* **説明**:クラス名が「mboxDefault」であるDIVを使用し、、 、またはから実行されるmboxのラッピングにのみ使 `mboxCreate()`用さ `mboxUpdate()`れ、デフォルトのコン `mboxDefine()` テンツを非表示にします。

### defaultContentVisibleStyle

* **型**：String
* **デフォルト値**:表示：visible
* **説明**:クラス名が「mboxDefault」であるDIVを使用し、、 、またはから実行されるmboxのラッピングにのみ使用され、適用されたオファー（存在する場合）またはデフォルトのコンテンツを表示しま `mboxCreate()` `mboxUpdate()` `mboxDefine()` す。

### deviceIdLifetime

* **型**:数値
* **デフォルト値**:63244800000 ms = 2年
* **説明**:Cookieに保持さ `deviceId` れる時間。

>[!NOTE]
>
>deviceIdLifetime設定は、at.jsバージョン2.3.1以降で上書きできます。

### 有効

* **型**:Boolean
* **デフォルト値**:true
* **説明**:有効にすると、エクスペリエ [!DNL Target] ンスをレンダリングするためのエクスペリエンスの取得リクエストとDOM操作が自動的に実行されます。さらに、[!DNL Target]呼び出しは、`getOffer(s)` / `applyOffer(s)`を介して手動で実行できます。

   無効にした場合、[!DNL Target]リクエストは自動的にも手動でも実行されません。

### globalMboxAutoCreate

* **型**:数値
* **デフォルト値**:UIを使用して設定された値。
* **説明**:グローバルmboxリクエストを実行するかどうかを示します。

### imsOrgId

* **型**:文字列
* **デフォルト値**:true
* **説明**:IMS ORG IDを表します。

### optinEnabled

* **型**:Boolean
* **デフォルト値**:false
* **説明**: [!DNL Target] では、お客様の同意管理戦略を支援できるよ [!DNL Adobe Experience Platform] うに、を介してオプトイン機能がサポートされています。オプトイン機能を使用すると、[!DNL Target] タグを実行する方法とタイミングを制御できます。また、[!DNL Adobe Experience Platform] を介して [!DNL Target] タグを事前に承認するオプションも提供されています。[!DNL Target] at.jsライブラリでオプトインを使用する機能を有効にするには、`optinEnabled=true`設定を追加します。 [!DNL Adobe Experience Platform]で、拡張機能のインストール表示の[!UICONTROL GDPRオプトイン]ドロップダウンリストから「有効」を選択する必要があります。 詳しくは、[Adobe Experience Platformのドキュメント](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)を参照してください。 この設定は、欧州連合の一般データ保護規則(GDPR)やカリフォルニア州消費者プライバシー法(CCPA)などのプライバシーおよびデータ保護規則に関連するので、詳しくは、[プライバシーとデータ保護規則](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)を参照してください。

### optoutEnabled

* **型**:Boolean
* **デフォルト値**:false
* **説明**:Targetが訪問者API関数を呼び出す必要があるかどうかを示 `isOptedOut()` します。これは、デバイスグラフ有効化の一部です。

### overrideMboxEdgeServer

* **型**:Boolean
* **デフォルト値**:true（at.jsバージョン1.6.2以降）
* **説明**:ドメインまたはドメインを使用する必 `<clientCode>.tt.omtrdc.net` 要があるかど `mboxedge<clusterNumber>.tt.omtrdc.net` うかを示します。

   この値がtrueの場合、`mboxedge<clusterNumber>.tt.omtrdc.net`ドメインはcookieに保存されます。 現在、at.js 1.8.2およびat.js 2.3.1より前のバージョンのat.jsを使用する場合、[CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md)では動作しません。この問題が発生する場合は、[at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を新しいサポート対象バージョンに更新することを検討してください。

### overrideMboxEdgeServerTimeout

* **型**:数値
* **デフォルト値**:1860000 => 31分
* **説明**:値を含むcookieの有効期間を示し `mboxedge<clusterNumber>.tt.omtrdc.net` ます。

### pageLoadEnabled

* **型**:Boolean
* **デフォルト値**:true
* **説明**:有効にすると、ページの読み込み時に返す必要があるエクスペリエンスが自動的に取得されます。

### secureOnly

* **型**:Boolean
* **デフォルト値**:false
* **説明**:at.jsでHTTPSのみを使用するか、ページのプロトコルに基づいてHTTPとHTTPSとの切り替えを許可するかを示します。trueに設定した場合、secureOnlyはSecure属性とSameSite属性もmbox Cookieに設定します。

### selectorsPollingTimeout

* **型**:数値
* **デフォルト値**:5000 ms = 5 s
* **説明**:at.js 0.9.6では、で上書きでき [!DNL Target] るこの新しい設定が導入されまし `targetGlobalSettings`た。

   `selectorsPollingTimeout`設定は、セレクターによって識別されたすべての要素がページに表示されるまで、クライアントが待機する時間を表します。

   Visual Experience Composer（VEC）によって作成されたアクティビティには、セレクターが含まれたオファーがあります。

### serverDomain

* **型**：String
* **デフォルト値**:UIを使用して設定された値。
* **説明**:Targetエッジサーバーを表します。

### serverState

* **型**:後述のハイブリ [ッドのパーソナ](#server-state) ライゼーションを参照。
* **デフォルト値**:後述のハイブリ [ッドのパーソナ](#server-state) ライゼーションを参照。
* **説明**:後述のハイブリ [ッドのパーソナ](#server-state) ライゼーションを参照。

### timeout

* **型**:数値
* **デフォルト値**:UIを使用して設定された値。
* **説明**:エッジリクエスト [!DNL Target] のタイムアウトを表します。

### viewsEnabled

* **型**:Boolean
* **デフォルト値**:true
* **説明**:有効な場合、ページ読み込み時に返す必要があるビューを自動的に取得します。ビューはat.js 2.*x* のみで使用できます。

### visitorApiTimeout

* **型**:数値
* **デフォルト値**:2000ミリ秒= 2秒
* **説明**:訪問者APIリクエストの [!UICONTROL タイム] アウトを表します。

## 使用方法 {#section_9AD6FA3690364F7480C872CB55567FB0}

この関数は、at.jsが読み込まれる前、または&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 実装]** > **[!UICONTROL at.js設定の編集]** > **[!UICONTROL コード設定]** > **[!UICONTROL ライブラリヘッダー]**&#x200B;で定義できます。

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

at.js 2.3.0以降では、配信されたTargetオファーを適用する際に、ページDOMに追加されたSCRIPTタグとSTYLEタグに対するコンテンツセキュリティポリシーのナンスの設定がサポートされます。

at.js 2.3.0以降の読み込みの前に、SCRIPTとSTYLEのnonceを`targetGlobalSettings.cspScriptNonce`と`targetGlobalSettings.cspStyleNonce`に対応して設定する必要があります。 以下の例を参照してください。

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

`cspScriptNonce`と`cspStyleNonce`の設定を指定した後、at.js 2.3.0以降では、Targetオファーの適用時にDOMに追加するすべてのSCRIPTタグとSTYLEタグに対して、これらをnonce属性に設定します。

## ハイブリッドパーソナライゼーション {#server-state}

`serverState` は、at.js v2.2以降で利用可能な設定で、Targetのハイブリッド統合が実装された場合にページパフォーマンスを最適化するために使用できます。ハイブリッド統合とは、at.js v2.2 以降（クライアントサイド）と、配信 API または Target SDK（サーバーサイド）の両方を使用してエクスペリエンスを提供することを意味します。`serverState` には、at.js v2.2 以降で、サーバーサイドで取得したコンテンツからエクスペリエンスを直接適用し、提供されるページの一部としてクライアントに返す機能が備わっています。

### 前提条件

[!DNL Target]のハイブリッド統合が必要です。

* **サーバー側**:新しい配信APIまたは [Target SDK](https://developers.adobetarget.com/api/delivery-api/) を使用 [する必要があります](https://developers.adobetarget.com/api/delivery-api/#section/SDKs)。
* **クライアント側**: [at.jsバージョン2.2以降を使用する必要があります](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

### コードサンプル

この仕組みをより深く理解するには、以下のコード例をサーバー上で参照してください。 このコードは、[Target Node.js SDK](https://github.com/adobe/target-nodejs-sdk)を使用していることを前提としています。

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

ビュープリフェッチ用の`serverState`オブジェクトJSONの例を次に示します。

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

ページがブラウザーに読み込まれた後、at.jsは、[!DNL Target]エッジに対するネットワーク呼び出しを実行せずに、`serverState`からのすべての[!DNL Target]オファーを即座に適用します。 さらに、at.jsは、サーバー側で取得されたコンテンツで[!DNL Target]オファーが使用可能なDOM要素のみを事前に非表示にするので、ページ読み込みのパフォーマンスとエンドユーザーエクスペリエンスにプラスの影響を与えます。

### 重要な注意事項

`serverState`を使用する際は、次の点を考慮してください。

* 現時点で、at.js v2.2は、以下の場合にのみ、serverStateを介したエクスペリエンスの配信をサポートしています。

   * ページの読み込み時に実行されるVECで作成されたアクティビティ。
   * 事前取得済みのビュー

      at.js APIで[!DNL Target]ビューと`triggerView()`を使用するSPAの場合、at.js v2.2は、サーバー側でプリフェッチされたすべてのビューのコンテンツをキャッシュし、`triggerView()`を介して各ビューがトリガーされるとすぐに、Targetに対して追加のコンテンツ取得呼び出しを実行せずに適用します。

   * **注意**:現在、サーバー側で取得されたmboxは、ではサポートされていませ `serverState`ん。

* `serverState `オファーを適用する場合、at.jsでは`pageLoadEnabled`と`viewsEnabled`の設定が考慮されます（例：`pageLoadEnabled`設定がfalseの場合、ページ読み込みオファーは適用されません）。

   これらの設定をオンにするには、**[!UICONTROL 管理] > [!UICONTROL 実装] > [!UICONTROL 編集] > [!UICONTROL ページ読み込みが有効]**&#x200B;の切り替えを有効にします。

   ![ページ読み込み有効設定](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* `serverState`を使用し、返されるコンテンツで`<script>`タグを使用する場合は、HTMLコンテンツで`</script>`ではなく`<\/script>`を使用するようにします。 `</script>`を使用すると、ブラウザーは`</script>`をインラインスクリプトでの終わりと解釈し、HTMLページを壊す可能性があります。

### その他のリソース

`serverState`の仕組みについて詳しくは、次のリソースを参照してください。

* [サンプルコード](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [を使用したシングルページアプリケーション(SPA)サンプルアプリケーシ `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo)ョン。
