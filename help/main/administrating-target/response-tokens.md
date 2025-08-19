---
keywords: レスポンストークン；トークン；プラグイン；プラグイン；at.js；レスポンス；platform web sdk;google analytics
description: で応答トークンを使用して、サードパーティのツール  [!DNL Adobe Target]  デバッグおよび統合するための出力固有の情報を出力する方法について説明します。
title: 応答トークンとその使用方法
feature: Administration & Configuration
role: Admin
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '1622'
ht-degree: 24%

---

# レスポンストークン

応答トークンを使用すると、[!DNL Adobe Target] に固有の情報をブランドの web ページに自動的に出力できます。 この情報には、アクティビティ、オファー、エクスペリエンス、ユーザープロファイル、地域情報などの詳細が含まれます。 これらの詳細により、内部またはサードパーティのツールと共有したり、デバッグに使用したりするための追加の応答データが提供されます。

レスポンストークンを使用すると、使用する変数を（キーと値のペアで）選択し、[!DNL Target] 応答の一部として送信できるようにします。 スイッチを使用して変数を有効にすると、変数は [!DNL Target] 応答で送信され、ネットワーク呼び出しで検証できます。 レスポンストークンは [!UICONTROL Preview] モードでも機能します。

プラグインとレスポンストークンの主な違いは、配信時に実行されるページにJavaScriptを配信する点です。 ただし、応答トークンはオブジェクトを配信し、このオブジェクトはイベントリスナーを使用して読み取り、操作できます。 応答トークンのアプローチは、より安全で、サードパーティ統合の開発とメンテナンスを容易にします。

{{permissions-update}}

>[!NOTE]
>
>応答トークンは、at.js バージョン 1.1 以降で使用できます。

| Target SDK | 提案されたアクション |
|--- |--- |
| [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} | Platform Web SDK バージョン 2.6.0 以降を使用していることを確認します。 Platform Web SDKの最新バージョンのダウンロードについて詳しくは、『 [Platform Web SDKの概要 ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=ja){target=_blank} ガイドの *SDKのインストール* を参照してください。 Platform Web SDKの各バージョンの新機能について詳しくは、『 [Platform Web SDKの概要 ](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) ガイドの *リリースノート* を参照してください。 |
| [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html?lang=ja){target=_blank} | 必ず at.js バージョン 1.1 以降を使用します。at.js の最新バージョンのダウンロードについて詳しくは、[at.js のダウンロード](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html?lang=ja){target=_blank} を参照してください。at.js の各バージョンでの新機能について詳しくは、[at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank}を参照してください。<br>at.js を使用する場合は、プラグインを廃止しレスポンストークンを使用することをお勧めします。mbox.js （現在は非推奨）には存在し、at.js には存在しない内部メソッドに依存する一部のプラグインは、配信されますが失敗します。 |

## レスポンストークンの使用 {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. Platform Web SDK バージョン 2.6.0 （以降）または at.js バージョン 1.1 （以降）を使用していることを確認します。

   詳しくは、以下を参照してください。

   * **Platform Web SDK**:『 [Platform Web SDKの概要 ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=ja) ガイドの *SDKのインストール* を参照してください。
   * **at.js**:[at.js のダウンロード ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html?lang=ja){target=_blank} を参照してください。

1. [!DNL Target] で、**[!UICONTROL Administration]**/**[!UICONTROL Response Tokens]** をクリックします。

1. `activity.id` や `offer.id` など、目的の応答トークンを有効化します。

   デフォルトでは次のパラメーターを使用できます。

   | タイプ | パラメーター | メモ |
   |--- |--- |--- |
   | ビルトインプロファイル | `profile.activeActivities` | 訪問者が該当する `activityIds` の配列を返します。ユーザーが該当するたびに増分されます。例えば、2 つの異なるアクティビティを配信する 2 つの [!DNL Target] リクエストを含むページの場合、2 番目のリクエストには両方のアクティビティが含まれます。 |
   |  | `profile.isFirstSession` | 「true」または「false」を返します。 |
   |  | `profile.isNewSession` | 「true」または「false」を返します。 |
   |  | `profile.daysSinceLastVisit` | 訪問者の最後の訪問からの経過日数を返します。 |
   |  | `profile.tntId` | 訪問者の tntID を返します。 |
   |  | `profile.marketingCloudVisitorId` | 訪問者の Experience Cloud 訪問者 ID を返します。 |
   |  | `profile.thirdPartyId` | 訪問者のサードパーティ ID を返します。 |
   |  | `profile.categoryAffinity` | 訪問者のお気に入りのカテゴリを返します。 |
   |  | `profile.categoryAffinities` | 訪問者の上位 5 カテゴリの配列を文字列として返します。 |
   | アクティビティ | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`offer.name`<br>`offer.id` | 現在のアクティビティの詳細。<br> オファーパラメーターの値はエクスペリエンスレベルで評価されます。 |
   | 地域 | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | アクティビティでの地域ターゲット設定について詳しくは、[地域](/help/main/c-target/c-audiences/c-target-rules/geo.md)を参照してください。 |
   | トラフィック配分方法 <br> （[!UICONTROL Auto-Target] および [!UICONTROL Automated Personalization] アクティビティにのみ適用） | `experience.trafficAllocationId` | 訪問者が「コントロール」トラフィックからエクスペリエンスを受け取った場合は 0 を、訪問者が「ターゲット」トラフィック分配からエクスペリエンスを受け取った場合は 1 を返します。 |
   |  | `experience.trafficAllocationType` | 「control」または「targeted」を返します。 |

   ユーザープロファイル属性と顧客属性もリストに表示されます。

   >[!NOTE]
   >
   >特殊文字を含むパラメーターはリストに表示されません。英数字とアンダースコアのみサポートされます。

1. （条件付き）プロファイルパラメーターを応答トークンとして使用するが、[!DNL Target] リクエストを通じてパラメーターが渡されたことがなく、そのため [!DNL Target] UI に読み込まれていない場合は、「[!UICONTROL Add Response Token]」ボタンを使用して、プロファイルを UI に追加できます。

   「**[!UICONTROL Add Response Token]**」をクリックし、トークン名を入力して「**[!UICONTROL Activate]**」をクリックします。

1. アクティビティを作成します。

## 応答をリッスンし、応答トークンを読み取ります

[!DNL Target] 応答および応答トークンの読み取りをリッスンするために使用するプロセスは、実装が [!DNL Platform Web SDK] と at.js のどちらに含まれているかによって異なります。

### ![Adobe Experience Platform Web SDK バッジ ](/help/main/assets/platform.png) [!DNL Platform Web SDK] Handle オブジェクトクラスを使用 {#platform-web-sdk}

メタデータオブジェクトとデータオブジェクトを持つ Handle オブジェクトクラスを使用して、[!DNL Target] 応答をリッスンし、応答トークンを読み取ります。

次の応答例では、[!DNL Platform Web SDK] のカスタムイベントハンドラーをHTMLページに直接追加します（コードで使用されるオブジェクトについて説明した表）。

| オブジェクト | 情報 |
| --- | --- |
| タイプ - Personalization.decision | [!DNL Target] またはOffer Decisioningのプロバイダーによって決定されたかどうか。 |
| DecisionProvider - TGT | TGT-[!DNL Target]。 [!DNL Target] は、応答トークンのメタデータと値をページに提供します。 |
| メタ | ページに渡されるメタデータ。 |
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

### ![at.js バッジ ](/help/main/assets/atjs.png) カスタムイベントを使用した at.js

[at.js カスタムイベント ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/atjs-custom-events.html?lang=ja){target=_blank} を使用して [!DNL Target] 応答をリッスンし、応答トークンを読み取ります。

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

## 応答トークンの FAQ {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**レスポンストークンを有効または無効にするには、どの役割が必要ですか？**

レスポンストークンは、[!DNL Target] [!UICONTROL Administrator] の役割を持つユーザーのみがアクティブ化または非アクティブ化できます。

**[!DNL Platform Web SDK] 2.6.0 （またはそれ以前）を実行している場合はどうなりますか？**

レスポンストークンへのアクセス権がありません。

**at.js 1.0 （またはそれ以前）を実行しているとどうなりますか？**

応答トークンは表示されますが、at.js では使用できません。

**[!DNL Target Classic] プラグインとレスポンストークンの両方を同時にアクティブにできますか？**

プラグインと応答トークンは並行して使用できますが、プラグインは今後非推奨となる予定です。

**応答トークンは、すべての応答を通じて配信されるか、アクティビティを配信する [!DNL Target] 応答 [!DNL Target] みを通じて配信されますか？**

応答トークンは、アクティビティを配信する [!DNL Target] 応答を通じてのみ配信されます。

**[!DNL Target Classic] プラグインにはJavaScriptが含まれています。 レスポンストークンを使用してこの機能を複製するにはどうすればよいですか？**

レスポンストークンに移行する場合、このタイプのJavaScriptは、コードベースまたはタグ管理ソリューションに保持する必要があります。 [!DNL Platform Web SDK] または [!DNL at.js] カスタムイベントを使用してこのコードをトリガーし、応答トークン値をJavaScript関数に渡すことができます。

**プロファイル／顧客属性パラメーターがレスポンストークンのリストに表示されないのはなぜですか？**

通常、[!DNL Target] はパラメーターを 15 分ごとに更新します。 この更新はユーザー・アクションに依存し、データはレスポンス・トークン・ページを表示した場合にのみ更新されます。 応答トークンリストにパラメーターが表示されない場合は、データ [!DNL Target] まだ更新されていません。

また、パラメーターに英数字以外の文字またはアンダースコア以外の記号が含まれる場合、そのパラメーターはリストに表示されません。 現時点では、サポートされるのは英数字とアンダースコアのみです。

**削除されたプロファイルスクリプトやプロファイルパラメーターを使用している場合、応答トークンは引き続きコンテンツを配信しますか？**

レスポンストークンはユーザープロファイルから情報を抽出し、その情報を配信します。プロファイルスクリプトまたはプロファイルパラメーターを削除しても、ユーザープロファイルから情報が削除されるわけではありません。ユーザープロファイルには、プロファイルスクリプトに対応するデータがまだ残っています。 応答トークンは引き続きコンテンツの配信を行います。 プロファイルにその情報が保存されていないユーザーの場合、または新規訪問者の場合、プロファイルにデータが存在しないので、そのトークンは配信されません。

[!DNL Target] は、トークンを自動的にオフにしません。 プロファイルスクリプトを削除し、このトークンの配信が不要になった場合は、手動でトークンを無効にする必要があります。

**プロファイルスクリプトの名前を変更しましたが、そのスクリプトを使用しているトークンが変更前の名前のままで引き続き有効なのはなぜですか？**

前述したように、レスポンストークンはユーザーの保存済みのプロファイル情報を基に機能します。プロファイルスクリプトの名前を変更しても、web サイトを訪問したユーザーのプロファイルには、古いプロファイルスクリプト値が保存されます。 トークンは、ユーザープロファイルに既に保存されている古い値を引き続き取得します。 新しい名前でコンテンツを配信したい場合は、以前のトークンを無効にし、新しいトークンを有効にする必要があります。

**属性が変更された場合、いつリストから削除されますか？**

[!DNL Target] は、一定の間隔で属性のリフレッシュを実行します。 切り替えられていない属性は、次回の更新時に削除されます。 ただし、切り替えられた属性が既に削除されている場合、そのスクリプトは、切り替えるまで属性リストから削除されません。 例えば、トークンとして使用されたプロファイルスクリプトを削除したとします。 [!DNL Target] は、切り替え済みの属性のみを、削除または名前変更の際にリストから削除します。

## Google Analyticsへのデータの送信

次の節では、Google Analytics 4 にデータ [!DNL Target] 送信する方法について説明します。 応答トークンから送信されたデータは、他のサードパーティ統合環境に送信することもできます。

### ![AEP バッジ ](/help/main/assets/platform.png)Platform Web SDKを介してGoogle Analyticsにデータを送信する

Google Analyticsページに次のコードを追加すると、Platform Web SDK バージョン 2.6.0 （またはそれ以降）を介してHTMLからデータを送信できます。

>[!NOTE]
>
>応答トークンキーと値のペアが `alloy("sendEvent"` オブジェクトの下にあることを確認します。

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

### ![at.js バッジ ](/help/main/assets/atjs.png)at.js を使用したGoogle Analyticsへのデータの送信 {#section_04AA830826D94D4EBEC741B7C4F86156}

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

次の節では、応答トークンのデバッグについて説明します。

### ![at.js バッジ ](/help/main/assets/atjs.png)Google Analyticsとデバッグ

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

## ![at.js](/help/main/assets/atjs.png) トレーニングビデオ：応答トークンと at.js カスタムイベント {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

次のビデオでは、応答トークンと at.js カスタムイベントを使用して、プロファイル情報を [!DNL Target] からサードパーティシステムに共有する方法を説明します。

>[!NOTE]
>
>パフォーマンスを向上、新機能のリリースに要するメンテナンス時間を短縮、製品全体でのユーザーエクスペリエンスが向上するため、[!DNL Target] [!UICONTROL Administration] メニュー（以前の [!UICONTROL Setup]）のデザインが一新されました。 次のビデオの情報は正しいですが、オプションの場所が若干異なります。
>
>このビデオでは `option.name` と `option.id` について説明していますが、それぞれ `offer.name` と `offer.id` に置き換えられています。

>[!VIDEO](https://video.tv.adobe.com/v/34066?captions=jpn)
