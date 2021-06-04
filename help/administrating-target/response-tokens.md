---
keywords: レスポンストークン；トークン；プラグイン；at.js；レスポンス
description: Adobe [!DNL Target] 出力固有の情報でレスポンストークンを使用し、デバッグやサードパーティツールとの統合を行う方法について説明します。
title: レスポンストークンとは何ですか？それらの使用方法を教えてください。
feature: 管理と設定
role: Administrator
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: e5d1aaa3a182bf15466aa29d6632d9009dbcd698
workflow-type: tm+mt
source-wordcount: '1651'
ht-degree: 27%

---

# レスポンストークン

レスポンストークンを使用すると、[!DNL Adobe Target]に固有の情報をブランドのWebページに自動的に出力できます。 この情報には、アクティビティ、オファー、エクスペリエンス、ユーザープロファイル、地域情報などの詳細が含まれます。 これらの詳細は、内部やサードパーティのツールと共有したり、デバッグに使用したりするための追加の応答データを提供します。

レスポンストークンを使用すると、使用する変数（キーと値のペア）を選択し、[!DNL Target]の応答の一部として送信できるようになります。 スイッチを使用して変数を有効にすると、変数が[!DNL Target]応答で送信され、ネットワーク呼び出しで検証できます。 レスポンストークンは[!UICONTROL プレビュー]モードでも機能します。

プラグインとレスポンストークンの主な違いは、プラグインが配信時に実行されるページにJavaScriptを配信することです。 ただし、レスポンストークンは、イベントリスナーを使用して読み取り、処理できるオブジェクトを配信します。 レスポンストークンのアプローチはより安全で、サードパーティ統合の開発とメンテナンスを容易にします。

>[!NOTE]
>
>レスポンストークンはat.jsバージョン1.1以降で利用できます。

>[!IMPORTANT]
>
>[!DNL Adobe Experience Platform Web SDK]を使用したレスポンストークン機能は、今後のリリース（決定予定日）で利用できる予定です。 以下のレスポンストークンとPlatform Web SDKに関するドキュメントは、スニークピークとして含まれています。

| Target SDK | 推奨アクション |
|--- |--- |
| [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) | Platform Web SDKバージョン2.6.0以降を使用していることを確認します。 Platform Web SDKの最新バージョンのダウンロードについて詳しくは、『*Platform Web SDKの概要*』ガイドの「[SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html)のインストール」を参照してください。 Platform Web SDKの各バージョンの新機能について詳しくは、『*Platform Web SDKの概要*』ガイドの[リリースノート](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html)を参照してください。 |
| [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) | 必ず at.js バージョン 1.1 以降を使用します。at.js の最新バージョンのダウンロードについて詳しくは、[at.js のダウンロード](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md) を参照してください。at.js の各バージョンでの新機能について詳しくは、[at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を参照してください。<br>at.js を使用する場合は、プラグインを廃止しレスポンストークンを使用することをお勧めします。mbox.jsには存在するがat.jsには存在しない内部メソッドを使用するプラグインの中には、配信されても失敗するものもあります。 詳しくは、[at.js の制限](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md)を参照してください。 |

## レスポンストークンの使用 {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. Platform Web SDKバージョン2.6.0（以降）またはat.jsバージョン1.1（以降）を使用していることを確認します。

   詳しくは、以下を参照してください。

   * **Platform Web SDK**:『  [Platform Web SDK Overview](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) ガイド』の「 SDKのイ *ンスト* ール」を参照してください。
   * **at.js**:at.jsのダ [ウンロードを参照してください](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_1E1F958F9CCC4E35AD97581EFAF659E2)。

1. [!DNL Target]で、**[!UICONTROL 管理]** /**[!UICONTROL レスポンストークン]**&#x200B;をクリックします。

   ![](assets/response_tokens-new.png)

1. `activity.id`や`option.id`など、目的のレスポンストークンを有効にします。

   デフォルトでは次のパラメーターを使用できます。

   | タイプ | パラメーター | メモ |
   |--- |--- |--- |
   | ビルトインプロファイル | `profile.activeActivities` | 訪問者が該当する `activityIds` の配列を返します。ユーザーが該当するたびに増分されます。例えば、2つの異なるアクティビティを配信する2つの[!DNL Target]リクエストを含むページの場合、2番目のリクエストには両方のアクティビティが含まれます。 |
   |  | `profile.isFirstSession` | 「true」または「false」を返します。 |
   |  | `profile.isNewSession` | 「true」または「false」を返します。 |
   |  | `profile.daysSinceLastVisit` | 訪問者の最後の訪問からの経過日数を返します。 |
   |  | `profile.tntId` | 訪問者の tntID を返します。 |
   |  | `profile.marketingCloudVisitorId` | 訪問者の Experience Cloud 訪問者 ID を返します。 |
   |  | `profile.thirdPartyId` | 訪問者のサードパーティ ID を返します。 |
   |  | `profile.categoryAffinity` | 訪問者のお気に入りのカテゴリを返します。 |
   |  | `profile.categoryAffinities` | 訪問者の上位 5 カテゴリの配列を文字列として返します。 |
   | アクティビティ | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`option.name`<br>`option.id` | 現在のアクティビティの詳細です。「option」は「offer」と同義です。 |
   | 地域 | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | アクティビティでの地域ターゲット設定について詳しくは、[地域](/help/c-target/c-audiences/c-target-rules/geo.md)を参照してください。 |
   | トラフィック配分方法<br>([!UICONTROL 自動ターゲット]および[!UICONTROL Automated Personalization]アクティビティにのみ適用) | `experience.trafficAllocationId` | 訪問者が「コントロール」トラフィックからエクスペリエンスを受け取った場合は0を、「ターゲット」トラフィック配分からエクスペリエンスを受け取った場合は1を返します。 |
   |  | `experience.trafficAllocationType` | 「control」または「targeted」を返します。 |

   ユーザープロファイル属性と顧客属性もリストに表示されます。

   >[!NOTE]
   >
   >特殊文字を含むパラメーターはリストに表示されません。英数字とアンダースコアのみサポートされます。

1. （条件付き）プロファイルパラメーターを応答トークンとして使用する場合でも、パラメーターが[!DNL Target]リクエストを経由せず、[!DNL Target] UIに読み込まれていない場合は、「[!UICONTROL 応答トークンを追加]」ボタンを使用して、プロファイルをUIに追加できます。

   「**[!UICONTROL レスポンストークンを追加]**」をクリックし、トークン名を入力して、「****&#x200B;をアクティブ化」をクリックします。

   ![](assets/response_token_create.png)

1. アクティビティを作成します。

## 応答のリッスンとレスポンストークンの読み取り

[!DNL Target]応答をリッスンしレスポンストークンを読み取るプロセスは、[!DNL Platform Web SDK]実装かat.js実装かによって異なります。

### ![Handleオブジェクトク](/help/assets/platform.png) [!DNL Platform Web SDK] ラスを使用したAdobe Experience Platform Web SDKバッジ

メタデータオブジェクトとデータオブジェクトを持つHandleオブジェクトクラスを使用して、[!DNL Target]応答をリッスンし、レスポンストークンを読み取ります。

次の応答の例では、[!DNL Platform Web SDK]カスタムイベントハンドラーをHTMLページに直接追加します（この表では、コードで使用されるオブジェクトについて説明しています）。

| オブジェクト | 情報 |
| --- | --- |
| タイプ — Personalization.decision | [!DNL Target]またはOffer decisioningプロバイダーが決定したか。 |
| DecisionProvider - TGT | TGT-[!DNL Target]。 [!DNL Target] は、レスポンストークンのメタデータと値をページに提供します。 |
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

### ![カスタムイベ](/help/assets/atjs.png) ントを使用したat.js badgeat.js

[at.js カスタムイベント](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md)を使用して の応答をリッスンし、レスポンストークンを読み取ります。[!DNL Target]

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

## レスポンストークンのFAQ {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**レスポンストークンを有効または無効にするには、どの役割が必要ですか？**

レスポンストークンは、[!DNL Target] [!UICONTROL 管理者]の役割を持つユーザーのみが有効化または無効化できます。

**[!DNL Platform Web SDK] 2.6.0（またはそれ以前）を実行している場合はどうなりますか？

レスポンストークンへのアクセス権がありません。

**at.js 1.0（またはそれ以前）を実行している場合はどうなりますか。**

レスポンストークンは表示されますが、at.jsでは使用できません。

**[!DNL Target Classic] プラグインとレスポンストークンの両方を同時に有効にすることはできますか？**

プラグインとレスポンストークンは同時に使用できます。ただし、プラグインは今後非推奨となります。

**レスポンストークンは、すべての応答を通じ [!DNL Target] て配信されますか。それとも、アクティビティを [!DNL Target] 配信する応答を通じてのみ配信されますか。**

レスポンストークンは、アクティビティを配信する[!DNL Target]応答を介してのみ配信されます。

**プラグイン [!DNL Target Classic] にJavaScriptが含まれていました。レスポンストークンを使用してこの機能を複製するにはどうすればよいですか？**

レスポンストークンに移行する際には、このタイプのJavaScriptをコードベースまたはタグ管理ソリューションに保持する必要があります。 [!DNL Platform Web SDK]または[!DNL at.js]カスタムイベントを使用してこのコードをトリガーし、レスポンストークンの値をJavaScript関数に渡すことができます。

**プロファイル／顧客属性パラメーターがレスポンストークンのリストに表示されないのはなぜですか？**

[!DNL Target] 通常、パラメーターは15分ごとに更新されます。この更新は、ユーザーのアクションによって異なり、レスポンストークンページを表示した場合にのみデータが更新されます。 パラメーターがレスポンストークンのリストに表示されない場合、[!DNL Target]はデータを更新していません。

また、パラメーターに英数字以外の文字やアンダースコア以外の記号が含まれている場合は、そのパラメーターはリストに表示されません。 現時点では、サポートされるのは英数字とアンダースコアのみです。

**削除されたプロファイルスクリプトまたはプロファイルパラメーターを使用している場合、応答トークンは引き続きコンテンツを配信しますか？**

レスポンストークンはユーザープロファイルから情報を抽出し、その情報を配信します。プロファイルスクリプトまたはプロファイルパラメーターを削除しても、ユーザープロファイルから情報が削除されるわけではありません。ユーザープロファイルには、プロファイルスクリプトに対応するデータが引き続き含まれます。 応答トークンはコンテンツの配信を続けます。 その情報をプロファイルに保存していないユーザーや新規訪問者の場合、そのデータがプロファイルに存在しないので、トークンは配信されません。

[!DNL Target] では、トークンの自動的なオフは切り替えられません。プロファイルスクリプトを削除し、このトークンの配信が不要になった場合は、手動でトークンを無効にする必要があります。

**プロファイルスクリプトの名前を変更しましたが、そのスクリプトを使用しているトークンが変更前の名前のままで引き続き有効なのはなぜですか？**

前述したように、レスポンストークンはユーザーの保存済みのプロファイル情報を基に機能します。プロファイルスクリプトの名前を変更した場合でも、Webサイトにアクセスしたユーザーのプロファイルには、古いプロファイルスクリプトの値が保存されます。 トークンは、ユーザープロファイルに既に保存されている古い値を引き続き取得します。 新しい名前でコンテンツを配信したい場合は、以前のトークンを無効にし、新しいトークンを有効にする必要があります。

**属性が変更された場合、いつリストから削除されますか。**

[!DNL Target] では、一定間隔で属性が更新されます。オンに切り替えられていない属性は、次回の更新時に削除されます。 ただし、オンに切り替えられて削除された属性がある場合、そのスクリプトは、オフに切り替えるまで属性リストから削除されません。 例えば、トークンとして使用されたプロファイルスクリプトを削除しました。 [!DNL Target] では、削除または名前変更しても、無効にされている属性しかリストから削除されません。

## Google Analyticsへのデータ送信

次の節では、[!DNL Target]データをGoogle Analyticsに送信する方法について説明します。 レスポンストークンから送信されたデータは、他のサードパーティ統合に送信することもできます。

### ![AEPバッ](/help/assets/platform.png) ジPlatform Web SDKを介してGoogle Analyticsにデータを送信

Google Analyticsは、HTMLページに次のコードを追加することで、Platform Web SDKバージョン2.6.0（またはそれ以降）を使用してデータを送信できます。

>[!NOTE]
>
>レスポンストークンのキーと値のペアが`alloy(“sendEvent”`オブジェクトの下にあることを確認します。

```
<script type="text/javascript"> 
   (function(i, s, o, g, r, a, m) { 
   i['GoogleAnalyticsObject'] = r; 
   i[r] = i[r] || function() { 
   (i[r].q = i[r].q || []).push(arguments) 
   }, i[r].l = 1 * new Date(); 
   
   
   a = s.createElement(o), 
   m = s.getElementsByTagName(o)[0]; 
   a.async = 1; 
   a.src = g; 
   m.parentNode.insertBefore(a, m) 
   })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
   ga('create', 'Google Client Id', 'auto'); 
</script> 
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
   
   
   ga('send', 'event', { 
   eventCategory: "target", 
   eventAction: experienceNames, 
   eventLabel: activityNames 
   }); 
   
   
   });
</script>
```

### ![at.jsバッ](/help/assets/atjs.png) ジat.jsを使用したGoogle Analyticsへのデータの送信 {#section_04AA830826D94D4EBEC741B7C4F86156}

次のコードを HTML ページに追加することで、Google Analytics に at.js を介してデータを送信できます。

```javascript
<script type="text/javascript"> 
  (function(i, s, o, g, r, a, m) { 
    i['GoogleAnalyticsObject'] = r; 
    i[r] = i[r] || function() { 
      (i[r].q = i[r].q || []).push(arguments) 
    }, i[r].l = 1 * new Date(); 
    a = s.createElement(o), 
      m = s.getElementsByTagName(o)[0]; 
    a.async = 1; 
    a.src = g; 
    m.parentNode.insertBefore(a, m) 
  })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
  ga('create', 'Google Client Id', 'auto'); 
</script> 
 
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
 
    ga('send', 'event', { 
      eventCategory: "target", 
      eventAction: experienceNames, 
      eventLabel: activityNames 
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

以下の節では、レスポンストークンのデバッグに関する情報を示します。

### ![at.jsバッ](/help/assets/atjs.png) ジGoogle Analyticsとデバッグ

次のコードを使用すると、デバッグにGoogle Analyticsを使用できます。

```javascript
<script type="text/javascript"> 
  (function(i, s, o, g, r, a, m) { 
    i['GoogleAnalyticsObject'] = r; 
    i[r] = i[r] || function() { 
      (i[r].q = i[r].q || []).push(arguments) 
    }, i[r].l = 1 * new Date(); 
    a = s.createElement(o), 
      m = s.getElementsByTagName(o)[0]; 
    a.async = 1; 
    a.src = g; 
    m.parentNode.insertBefore(a, m) 
  })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
  ga('create', 'Google Client Id', 'auto'); 
</script> 
 
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
 
    ga('send', 'event', { 
      eventCategory: "target", 
      eventAction: experienceNames, 
      eventLabel: activityNames 
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
```

### ttMetaプラグインと同等のを使用したデバッグ

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
        'OfferId': token["option.id"], 
        'OfferName': token["option.name"], 
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

## ![at.jsト](/help/assets/atjs.png) レーニングビデオ：レスポンストークンとat.jsカスタムイベント {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

次のビデオでは、レスポンストークンとat.jsカスタムイベントを使用して[!DNL Target]からサードパーティシステムにプロファイル情報を共有する方法を説明します。

>[!NOTE]
>
>[!DNL Target] [!UICONTROL 管理]メニューUI（旧称[!UICONTROL セットアップ]）が再設計され、パフォーマンスの向上、新機能のリリースに要するメンテナンス時間の短縮、製品全体でのユーザーエクスペリエンスの向上が実現しました。 次のビデオの情報は正しい。ただし、オプションの位置は若干異なります。

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
