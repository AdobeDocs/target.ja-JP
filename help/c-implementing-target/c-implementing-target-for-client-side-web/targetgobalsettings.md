---
description: 'at. jsのtargetGlobalSettings（）関数について取り上げます。 '
keywords: adobe.target.notification;要素;セレクター;通知;拡張子
seo-description: Adobe Target at. js JavaScriptライブラリのtargetGlobalSettings（）関数に関する情報です。
seo-title: Adobe Target at. js JavaScriptライブラリのtargetGlobalSettings（）関数に関する情報です。
solution: 'Target '
subtopic: 導入
title: targetGlobalSettings()
topic: Standard
translation-type: tm+mt
source-git-commit: ffa6585834b271838629d65ceb00d1770b37e80c

---


# targetGlobalSettings()

[!DNL Target] Standard/Premium UI や REST API を使用して設定を構成する代わりに、`targetGlobalSettings()` を使用して at.js ライブラリで設定を上書きできます。

これは特に、設定の一部を上書きする場合に、at.js が [!DNL Dynamic Tag Management]（DTM）から配信されている場合におこなわれます。

## 設定 {#section_42C759AE9B524A43B8659018677224B8}

次の設定を上書きできます。

| 設定 | タイプ | デフォルト値 | 説明 |
|--- |--- |--- |--- |
| clientCode | 文字列 | UI から設定された値 | クライアントコードを表します。 |
| serverDomain | 文字列 | UI から設定された値 | Target エッジサーバーを表します。 |
| cookieDomain | 文字列 | 可能であればトップレベルドメインに設定 | Cookie の保存時に使用するドメインを表します。 |
| crossDomain | 文字列 | UI から設定された値 | クロスドメイントラッキングが有効になっているかどうかを表します。<br>使用できる値は次のとおりです。<ul><li>無効</li><li>有効</li><li>x のみ</li></ul> |
| timeout | 数値 | UI から設定された値 | Target エッジリクエストのタイムアウト |
| globalMboxAutoCreate | ブール値 | UI から設定された値 | グローバル mbox リクエストを実行するかどうかを示します。 |
| visitorApiTimeout | 数値 | 2000 ミリ秒 = 2 秒 | 訪問者 API リクエストのタイムアウトを示します。 |
| 有効 | ブール値 | true |  at.js がライブラリとして有効になっているか、つまりこのライブラリが何らかの処理を実行するかどうかを示します。この設定は主に、cookie のオプトアウトや、その他 at.js の機能をカスタムに無効にする場合に使用します。 |
| defaultContentHiddenStyle | 文字列 | visibility: hidden | クラス名が「mboxDefault」である DIV を使用し、`mboxUpdate()`、`mboxCreate()`、または `mboxDefine()` から実行される mbox のラッピングにのみ使用され、デフォルトのコンテンツを非表示にします。 |
| defaultContentVisibleStyle | 文字列 | visibility: visible | クラス名が「mboxDefault」である DIV を使用し、`mboxUpdate()`、`mboxCreate()`、または `mboxDefine()` から実行される mbox のラッピングにのみ使用され、適用されたオファー（存在する場合）またはデフォルトのコンテンツを表示します。 |
| bodyHiddenStyle | 文字列 | body { opacity: 0 } | `globalMboxAutocreate === true` の場合にのみ使用され、ちらつきの発生を最小限に抑えます。<br>詳細については、「[at.js によるちらつきの制御方法](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md)」を参照してください。 |
| bodyHidingEnabled | ブール値 | true | Visual Experience Composer で作成されたオファー（ビジュアルオファー）の配信に `target-global-mbox` が使用されている場合に、ちらつきの制御に使用します。 |
| imsOrgId | 文字列 | IMS ORG ID | IMS ORG ID を表します。 |
| secureOnly | ブール値 | false | at.js で HTTPS のみを使用するか、ページのプロトコルに基づいて HTTP と HTTPS との切り替えを許可するかを示します。 |
| overrideMboxEdgeServer | ブール値 | true（at.js バージョン 1.6.2 以降） | `<clientCode>.tt.omtrdc.net` ドメインまたは `mboxedge<clusterNumber>.tt.omtrdc.net` ドメインを使用する必要があるかどうかを示します。<br>この値が true の場合、`mboxedge<clusterNumber>.tt.omtrdc.net` ドメインは cookie に保存されます。 |
| overrideMboxEdgeServerTimeout | 数値 | 1860000 =&gt; 31 分 | `mboxedge<clusterNumber>.tt.omtrdc.net` 値を含む cookie の有効期間を示します。 |
| optoutEnabled | ブール値 | false | Target が訪問者 API `isOptedOut()` 関数を呼び出す必要があるかどうかを示します。これは、デバイスグラフ有効化の一部です。 |
| selectorsPollingTimeout | 数値 | 5000 ミリ秒 = 5 秒 | at.js 0.9.6 では、`targetGlobalSettings` で上書きできるこの新しい設定が Target に導入されました。<br>`selectorsPollingTimeout` は、セレクターによって識別されたすべての要素がページに表示されるまでの待機時間が、クライアントによってどれくらい許容されるかを表します。<br>Visual Experience Composer（VEC）によって作成されたアクティビティには、セレクターが含まれたオファーがあります。 |
| dataProviders | 以下の「データプロバイダー」を参照してください。 | 以下の「データプロバイダー」を参照してください。 | 以下の「データプロバイダー」を参照してください。 |

## 使用方法 {#section_9AD6FA3690364F7480C872CB55567FB0}

この関数は、at.js が読み込まれる前、または「**[!UICONTROL セットアップ]**」／「**[!UICONTROL 実装]**」／「**[!UICONTROL at.js 設定を編集]**」／「**[!UICONTROL コード設定]**」／「**[!UICONTROL ライブラリヘッダー]**」の順に移動して定義できます。

「ライブラリのヘッダー」フィールドでは、JavaScript を自由形式で入力できます。カスタマイズコードは次の例のようになります。

```
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
| [Adobe Target でのデータプロバイダーの使用](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html) | データプロバイダーは、サードパーティから Target へデータを簡単に渡すことのできる機能です。サードパーティとしては、気象予報サービス、DMP、自社の Web サービスなども利用可能です。このデータを利用して、オーディエンスやターゲットコンテンツを構築したり、訪問者プロファイルを充実させることができます。 |
| [Adobe Target でのデータプロバイダーの実装](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html) | サードパーティデータプロバイダーからデータを回収し Target リクエストで渡す、Adobe Target のデータプロバイダー機能の使用方法の実装詳細と例。 |

`window.targetGlobalSettings.dataProviders` 設定は、データプロバイダーの配列です。

各データプロバイダーの構造は次のとおりです。

| キー | タイプ | 説明 |
|--- |--- |--- |
| name | 文字列 | プロバイダーの名前。 |
| version | 文字列 | プロバイダーのバージョン。このキーはプロバイダーの展開に使用されます。 |
| timeout | 数値 | ネットワークリクエストの場合は、プロバイダーのタイムアウトを表します。このキーはオプションです。 |
| provider | 関数 | プロバイダーデータの取得ロジックを含む関数。<br>この関数の必須パラメーターは `callback` のみです。この callback パラメーターは、データを適切に取得した場合またはエラーが発生した場合にのみ呼び出す必要があります。<br>このコールバックは、次の 2 つのパラメーターを受け取ります。<ul><li>error：エラーの有無を表します。エラーがない場合、このパラメーターは null に設定されます。</li><li>params：Target リクエストで送信されるパラメーターを表す JSON オブジェクト。</li></ul> |

データプロバイダーで同期実行を使用する場合の例は次のとおりです。

```
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

```
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

```
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
