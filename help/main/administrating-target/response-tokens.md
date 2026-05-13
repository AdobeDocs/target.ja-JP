---
keywords: 応答トークン；トークン；プラグイン；プラグイン；at.js；応答；platform web sdk;google analytics
description: ' [!DNL Adobe Target] の応答トークンを使用して、デバッグおよびサードパーティ製ツールとの統合に使用する出力固有の情報を取得する方法を説明します。'
title: 応答トークンとは何か、どのように使用すればよいか？
feature: Administration & Configuration
role: Admin
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
TQID: https://experienceleague.adobe.com/Fm2VW0HmAPjf0ZCDawI-s1nPl3c-wjU-evhq-tSAKqA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2:
  - id: c011fe9c-b94b-4a88-93d8-f2acece55112
  - id: c5abb976-5170-45d6-bcac-66d15d10a4d4
  - id: faed1c89-faf7-4df1-910d-a88263e03b15
  - id: fc9c2184-9102-403f-bd6c-0055021e4bea
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1749
ht-degree: 23%

---

# レスポンストークン

応答トークンを使用すると、[!DNL Adobe Target]に固有の情報をブランドのweb ページに自動的に出力できます。 この情報には、アクティビティ、オファー、エクスペリエンス、ユーザープロファイル、位置情報などの詳細が含まれます。 これらの詳細は、内部またはサードパーティのツールと共有したり、デバッグに使用したりするための追加の応答データを提供します。

応答トークンを使用すると、（キー値のペアで）使用する変数を選択し、[!DNL Target]応答の一部として送信できるようにできます。 スイッチを使用して変数を有効にすると、変数は[!DNL Target]応答で送信され、ネットワーク呼び出しで検証できます。 応答トークンは[!UICONTROL Preview] モードでも機能します。

プラグインと応答トークンの重要な違いは、プラグインがJavaScriptを配信時に実行されるページに配信することです。 ただし、応答トークンは、イベントリスナーを使用して読み取りおよびアクションを実行できるオブジェクトを配信します。 応答トークンのアプローチはより安全で、サードパーティ統合の開発とメンテナンスが簡単になります。

{{permissions-update}}

>[!NOTE]
>
>応答トークンは、at.js バージョン 1.1以降で使用できます。

| Target SDK | 推奨アクション |
|--- |--- |
| [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} | Platform Web SDK バージョン 2.6.0以降を使用していることを確認します。 最新バージョンのPlatform Web SDKのダウンロードについて詳しくは、*Platform Web SDKの概要* ガイドの[SDKのインストール &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html){target=_blank}を参照してください。 Platform Web SDKの各バージョンの新機能について詳しくは、*Platform Web SDKの概要* ガイドの[&#x200B; リリースノート &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja)を参照してください。 |
| [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank} | 必ず at.js バージョン 1.1 以降を使用します。 at.js の最新バージョンのダウンロードについて詳しくは、[at.js のダウンロード](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html?lang=en){target=_blank} を参照してください。 at.jsの各バージョンの新機能について詳しくは、[at.js バージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank}を参照してください。<br>at.jsを使用しているお客様は、応答トークンを使用し、プラグインから移動することをお勧めします。 mbox.js （現在は非推奨）に存在していたものの、at.jsには存在しない内部メソッドに依存する一部のプラグインは、配信されますが、失敗します。 |

## 応答トークンの使用 {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. Platform Web SDK バージョン 2.6.0 （またはそれ以降）またはat.js バージョン 1.1 （またはそれ以降）を使用していることを確認します。

   詳細：

   * **Platform Web SDK**: *Platform Web SDKの概要* ガイドの[SDKのインストール &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html)を参照してください。
   * **at.js**: [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html?lang=ja){target=_blank}のダウンロードを参照してください。

1. [!DNL Target]で、**[!UICONTROL Administration]** > **[!UICONTROL Response Tokens]**&#x200B;をクリックします。

1. `activity.id`や`offer.id`など、必要な応答トークンをアクティブ化します。

   デフォルトでは次のパラメーターを使用できます。

   | タイプ | パラメーター | メモ |
   |--- |--- |--- |
   | ビルトインプロファイル | `profile.activeActivities` | 訪問者が該当する `activityIds` の配列を返します。 ユーザーが該当するたびに増分されます。 例えば、2つの異なるアクティビティを配信する2つの[!DNL Target] リクエストを含むページでは、2番目のリクエストには両方のアクティビティが含まれます。 |
   |  | `profile.isFirstSession` | 「true」または「false」を返します。 |
   |  | `profile.isNewSession` | 「true」または「false」を返します。 |
   |  | `profile.daysSinceLastVisit` | 訪問者の最後の訪問からの経過日数を返します。 |
   |  | `profile.tntId` | 訪問者の tntID を返します。 |
   |  | `profile.marketingCloudVisitorId` | 訪問者の Experience Cloud 訪問者 ID を返します。 |
   |  | `profile.thirdPartyId` | 訪問者のサードパーティ ID を返します。 |
   |  | `profile.categoryAffinity` | 訪問者のお気に入りのカテゴリを返します。 |
   |  | `profile.categoryAffinities` | 訪問者の上位 5 カテゴリの配列を文字列として返します。 |
   | アクティビティ | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`offer.name`<br>`offer.id` | 現在のアクティビティの詳細。<br> オファーパラメーターの値は、エクスペリエンスレベルで評価されます。 |
   | 地域 | `geo.country`<br>`geo.countryCode`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | アクティビティでの地域ターゲティングについて詳しくは、[地域](/help/main/c-target/c-audiences/c-target-rules/geo.md)を参照してください。 |
   | トラフィック配分メソッド <br> （[!UICONTROL Auto-Target]および[!UICONTROL Automated Personalization]のアクティビティにのみ適用されます） | `experience.trafficAllocationId` | 訪問者が「対象」トラフィックからエクスペリエンスを受け取った場合は0を返し、訪問者が「対象」トラフィック分布からエクスペリエンスを受け取った場合は1を返します。 |
   |  | `experience.trafficAllocationType` | 「control」または「targeted」を返します。 |

   ユーザープロファイル属性と顧客属性もリストに表示されます。

   >[!NOTE]
   >
   >特殊文字を含むパラメーターはリストに表示されません。 英数字とアンダースコアのみサポートされます。

1. （条件付き）プロファイルパラメーターを応答トークンとして使用する場合、パラメーターが[!DNL Target] リクエストを通じて渡されていないため、[!DNL Target] UIに読み込まれていない場合は、[!UICONTROL Add Response Token] ボタンを使用してプロファイルをUIに追加できます。

   「**[!UICONTROL Add Response Token]**」をクリックし、トークン名を入力してから「**[!UICONTROL Activate]**」をクリックします。

1. アクティビティを作成します。

## 応答をリッスンし、応答トークンを読み取る

[!DNL Target]応答をリッスンし、応答トークンを読み取るために使用するプロセスは、[!DNL Platform Web SDK]実装とat.js実装のどちらを使用しているかによって異なります。

### Handle オブジェクトクラスを使用する![Adobe Experience Platform Web SDK バッジ &#x200B;](/help/main/assets/platform.png) [!DNL Platform Web SDK] {#platform-web-sdk}

[!DNL Target]件の応答をリッスンして応答トークンを読み取るには、メタデータオブジェクトとデータオブジェクトを持つHandle オブジェクトクラスを使用します。

次のレスポンスの例では、[!DNL Platform Web SDK] カスタムイベントハンドラーをHTML ページに直接追加しています（このテーブルでは、コードで使用されるオブジェクトについて説明しています）。

| オブジェクト | 情報 |
| --- | --- |
| 種類 – Personalization.decision | [!DNL Target]またはOffer Decisioning プロバイダーによって決定されたかどうか。 |
| DecisionProvider - TGT | TGT-[!DNL Target]。 [!DNL Target]は、応答トークンのメタデータと値をページに提供します。 |
| Meta | ページに渡されるメタデータ。 |
| データ | ページに渡されるメタデータの値。 |

```html
<html>

<head>
 ...
 <script src="alloy.js"></script>
 <script>
  {
   "requestId": "4d0a7cfd-952c-408c-b3b8-438edc38250a",
   "handle": [{
    "type": "personalization:decisions",
    "payload": [{
     "id": "....",
     "scope": "__view__",
     "scopeDetails": {
      "decisionProvider": "TGT",
      "activity": {
       "id": "..."
      },
      "experience": {
       "id": "...."
      }
     },
     "items": [{
      "id": "123",
      "schema": "https://ns.adobe.com/personalization/dom-action",
      "meta": {
       "activity.id": "...",
       "activity.name": "...",
       "profile.foo": "...",
       "profile.bar": "..."
      },
      "data": {
       "id": "123",
       "type": "setHtml",
       "selector": "#foo",
       "prehidingSelector": "#foo",
       "content": "<div>Hello world</div>"
      }
     }]
    }]
   }]
  }
  });
 </script>
</head>

<body>
 ...
</body>

</html>
```

### カスタムイベントを使用した![at.js バッジ &#x200B;](/help/main/assets/atjs.png) at.js

[at.js カスタムイベント &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/atjs-custom-events.html?lang=en){target=_blank}を使用して[!DNL Target]応答をリッスンし、応答トークンを読み取ります。

以下のコードサンプルは、[!DNL at.js] カスタムイベントハンドラーを HTML ページに直接追加します。

```html
<html> 
  <head> 
    .... 
    <script src="at.js"></script> 
    <script> 
      document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
        console.log("Request succeeded", e.detail); 
      }); 
    </script> 
  <head> 
  <body> 
  ... 
  </body> 
</html>
```

## 応答トークンに関するFAQ {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**レスポンストークンを有効または無効にするには、どの役割が必要ですか？**

応答トークンは、[!DNL Target] [!UICONTROL Administrator]の役割を持つユーザーのみがアクティブ化または非アクティブ化できます。

**2.6.0 （またはそれ以前）を実行している場合はどうなりますか？**&#x200B;[!DNL Platform Web SDK]

応答トークンへのアクセス権がありません。

**at.js 1.0 （またはそれ以前）を実行しているとどうなりますか？**

応答トークンが表示されますが、at.jsでは使用できません。

**[!DNL Target Classic]個のプラグインと応答トークンの両方を同時にアクティブにできますか？**

プラグインと応答トークンは並行して利用できますが、プラグインは今後サポート終了となります。

**応答トークンは、すべての[!DNL Target]回の応答または[!DNL Target]回の応答を通じてのみ配信されますか？**

応答トークンは、アクティビティを配信する[!DNL Target]件の応答を通じてのみ配信されます。

**私の[!DNL Target Classic] プラグインにはJavaScriptが含まれています。 レスポンストークンを使用してこの機能を複製するにはどうすればよいですか？**

応答トークンに移行する場合、この種類のJavaScriptはコードベースまたはタグ管理ソリューションに保持する必要があります。 このコードは、[!DNL Platform Web SDK]または[!DNL at.js]個のカスタムイベントを使用してトリガーし、応答トークンの値をJavaScript関数に渡すことができます。

**プロファイル／顧客属性パラメーターがレスポンストークンのリストに表示されないのはなぜですか？**

[!DNL Target]は通常、15分ごとにパラメーターを更新します。 この更新はユーザーのアクションに依存し、応答トークンページを表示した場合にのみデータが更新されます。 パラメーターが応答トークン リストに表示されない場合、[!DNL Target]はまだデータを更新していません。

また、パラメーターに英数字以外の文字やアンダースコア以外の記号が含まれている場合、パラメーターはリストに表示されません。 現時点では、サポートされるのは英数字とアンダースコアのみです。

**削除されたプロファイルスクリプトまたはプロファイルパラメーターを使用する場合、応答トークンは引き続きコンテンツを配信しますか？**

レスポンストークンはユーザープロファイルから情報を抽出し、その情報を配信します。 プロファイルスクリプトまたはプロファイルパラメーターを削除しても、ユーザープロファイルから情報が削除されるわけではありません。 ユーザープロファイルには、プロファイルスクリプトに対応するデータが残っています。 応答トークンは引き続きコンテンツを配信します。 プロファイルにその情報が保存されていないユーザー、または新しい訪問者の場合、データがプロファイルに存在しないため、そのトークンは配信されません。

[!DNL Target]は、トークンを自動的にオフにしません。 プロファイルスクリプトを削除し、このトークンの配信が不要になった場合は、手動でトークンを無効にする必要があります。

**プロファイルスクリプトの名前を変更しましたが、そのスクリプトを使用しているトークンが変更前の名前のままで引き続き有効なのはなぜですか？**

前述したように、レスポンストークンはユーザーの保存済みのプロファイル情報を基に機能します。 プロファイルスクリプトの名前を変更しても、web サイトを訪問したユーザーには、プロファイルに古いプロファイルスクリプトの値が保存されます。 トークンは、ユーザープロファイルにすでに保存されている古い値を引き続き取得します。 新しい名前でコンテンツを配信したい場合は、以前のトークンを無効にし、新しいトークンを有効にする必要があります。

**属性が変更された場合、いつリストから削除されますか？**

[!DNL Target]は、属性の更新を定期的に実行します。 切り替えられていない属性は、次の更新時に削除されます。 ただし、オンに切り替えられ、削除された属性がある場合は、オフに切り替えるまで、そのスクリプトは属性リストから削除されません。 例えば、トークンとして使用されたプロファイルスクリプトを削除しました。 [!DNL Target]は、切り替えられた属性が削除または名前が変更された場合にのみ、リストから削除します。

## Google Analyticsへのデータ送信

以下の節では、[!DNL Target] データをGoogle Analytics 4に送信する方法について説明します。 応答トークンによって送信されたデータは、他の3rd パーティ統合にも送信できます。

### ![AEP バッジ &#x200B;](/help/main/assets/platform.png) Platform Web SDKを介してGoogle Analyticsにデータを送信する

Google Analyticsは、HTML ページに次のコードを追加することで、Platform Web SDK バージョン 2.6.0以降を介してデータを送信できます。

>[!NOTE]
>
>応答トークン キー値のペアが`alloy("sendEvent"` オブジェクトの下にあることを確認してください。

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>
<script type="text/javascript">
    alloy("sendEvent", {
 
 
    })
    .then(({ renderedPropositions, nonRenderedPropositions }) => {
        // concatenate all the propositions
        const propositions = [...renderedPropositions, ...nonRenderedPropositions];
        // extractResponseTokens() extract the meta from item -> meta
        const tokens = extractResponseTokens(propositions);
        const activityNames = [];
        const experienceNames = [];
        const uniqueTokens = distinct(tokens);
    
    
        uniqueTokens.forEach(token => {
            activityNames.push(token["activity.name"]);
            experienceNames.push(token["experience.name"]);
        });
 
        gtag('config', 'TAG_ID');
        gtag('event', 'action_name', {'eventCategory': 'target',
            'eventAction': experienceNames, 'eventLabel': activityNames
        });
    });
</script>
```

### ![at.js バッジ &#x200B;](/help/main/assets/atjs.png) at.js経由でGoogle Analyticsにデータを送信する {#section_04AA830826D94D4EBEC741B7C4F86156}

次のコードを HTML ページに追加することで、Google Analytics に at.js を介してデータを送信できます。

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>

<script type="text/javascript">
    document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) {
        var tokens = e.detail.responseTokens;

        if (isEmpty(tokens)) {
            return;
        }

        var activityNames = [];
        var experienceNames = [];
        var uniqueTokens = distinct(tokens);

        uniqueTokens.forEach(function(token) {
            activityNames.push(token["activity.name"]);
            experienceNames.push(token["experience.name"]);
        });

        gtag('config', 'TAG_ID');
        gtag('event', 'action_name', {'eventCategory': 'target',
            'eventAction': experienceNames, 'eventLabel': activityNames
        });
    });

    function isEmpty(val) {
        return (val === undefined || val == null || val.length <= 0) ? true : false;
    }

    function key(obj) {
        return Object.keys(obj)
        .map(function(k) { return k + "" + obj[k]; })
        .join("");
    }

    function distinct(arr) {
        var result = arr.reduce(function(acc, e) {
            acc[key(e)] = e;
            return acc;
        }, {});

        return Object.keys(result)
        .map(function(k) { return result[k]; });
    }
</script>
```

## デバッグ

以下の節では、応答トークンのデバッグに関する情報を提供します。

### ![at.js バッジ &#x200B;](/help/main/assets/atjs.png) Google Analyticsとデバッグ

次のコードを使用すると、Google Analyticsを使用してデバッグできます。

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>
  
<script type="text/javascript">
    document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) {
      var tokens = e.detail.responseTokens;
  
      if (isEmpty(tokens)) {
        return;
      }
  
      var activityNames = [];
      var experienceNames = [];
      var uniqueTokens = distinct(tokens);
  
      uniqueTokens.forEach(function(token) {
        activityNames.push(token["activity.name"]);
        experienceNames.push(token["experience.name"]);
      });
  
      gtag('config', 'TAG_ID');
      gtag('event', 'action_name', {'eventCategory': 'target',
          'eventAction': experienceNames, 'eventLabel': activityNames
      });
    });
  
    function isEmpty(val) {
      return (val === undefined || val == null || val.length <= 0) ? true : false;
    }
  
    function key(obj) {
       return Object.keys(obj)
      .map(function(k) { return k + "" + obj[k]; })
      .join("");
    }
  
    function distinct(arr) {
      var result = arr.reduce(function(acc, e) {
        acc[key(e)] = e;
        return acc;
      }, {});
  
      return Object.keys(result)
      .map(function(k) { return result[k]; });
    }
</script>
```

### ttMeta プラグインと同等のものを使用したデバッグ

ttMeta プラグインと同様のデバッグ機能は、HTML ページに次のコードを追加することで作成できます。

```javascript
<script type="text/javascript" > 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function (e) { 
    window.ttMETA= typeof(window.ttMETA)!="undefined" ? window.ttMETA : []; 
 
    var tokens=e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
     
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      window.ttMETA.push({ 
        'CampaignName': token["activity.name"], 
        'CampaignId' : token["activity.id"], 
        'RecipeName': token["experience.name"], 
        'RecipeId': token["experience.id"], 
        'OfferId': token["offer.id"], 
        'OfferName': token["offer.name"], 
        'MboxName': e.detail.mbox}); 
      console.log(ttMETA); 
    }); 
  }); 
 
  function isEmpty(val){ 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
</script>
```

## ![at.js](/help/main/assets/atjs.png) トレーニング ビデオ：応答トークンとat.js カスタムイベント {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

次のビデオでは、応答トークンとat.js カスタムイベントを使用して、[!DNL Target]からサードパーティシステムにプロファイル情報を共有する方法を説明します。

>[!NOTE]
>
>[!DNL Target] [!UICONTROL Administration] メニューUI （旧称[!UICONTROL Setup]）は、パフォーマンスの向上、新機能のリリース時に必要なメンテナンス時間の短縮、製品全体でのユーザーエクスペリエンスの向上を目的として再設計されました。 次のビデオの情報は正しいですが、オプションは少し異なる場所にあります。
>
>ビデオは`option.name`と`option.id`について言及しており、それぞれ`offer.name`と`offer.id`に置き換えられています。

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
