---
keywords: シングルページアプリケーションの実装；シングルページアプリケーションの実装；spa;at.js 2.x;at.js；シングルページアプリケーション；シングルページアプリケーション；spa;SPA
description: Adobe [!DNL Target] at.js 2.x の実装 [!DNL Target] ( シングルページアプリケーション (SPA) 用 )
title: 実装可能か [!DNL Target] シングルページアプリケーション (SPA) の場合
feature: Implement Server-side
role: Developer
exl-id: 624f8e62-b443-4093-8e05-9320a365ea07
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '2788'
ht-degree: 73%

---

# シングルページアプリケーションの実装

従来の Web サイトは、「ページ間」ナビゲーションモデル（別名マルチページアプリケーション）を使用していました。このモデルでは、Web サイトデザインは URL と密接に結合され、ある Web ページから別のページへのトランジションにはページ読み込みが必要になります。シングルページアプリケーション（SPA）などの最新型 Web アプリケーションは、代わりにブラウザの UI レンダリングの迅速な使用を推進するモデルを採用しています。多くの場合、ブラウザの UI レンダリングは、ページの再読み込みとは独立しています。これらのエクスペリエンスは、スクロール、クリック、カーソル移動などの顧客のインタラクションによってトリガーされることがよくあります。最新の Web の枠組みが進化するにつれて、パーソナライゼーションと実験をデプロイするためのページ読み込みなどの従来の汎用イベントは機能しなくなりました。

![従来のページのライフサイクルと SPA のライフサイクル](/help/main/c-experiences/assets/trad-vs-spa.png)

at.js 2.x は、次世代のクライアントサイドテクノロジーでパーソナライゼーションを実行するための機能を提供します。このバージョンは、SPA と調和したインタラクションを実現するための at.js の改善に焦点を当てています。

以前のバージョンでは利用できない at.js 2.x を使用するメリットを紹介します。

* ページ読み込み時にすべてのオファーをキャッシュし、複数のサーバー呼び出しを単一のサーバー呼び出しに減らす機能。
* 従来のサーバー呼び出しで発生する遅延時間なしで、キャッシュ経由でオファーが即座に表示されるため、サイトでのエンドユーザーのエクスペリエンスが著しく向上します。
* 1 行のシンプルなコードと開発者による 1 回限りのセットアップで、マーケティング担当者は SPA 上で VEC を使用して A/B およびエクスペリエンスターゲティング（XT）アクティビティを作成し、実行できます。

## Adobe [!DNL Target] ビューとシングルページアプリケーション

SPA の Adobe Target VEC は、ビューと呼ばれる新しい概念を活用します。ビューとはビジュアル要素の論理的集合体で、全体として SPA のエクスペリエンスを形作ります。このため SPA は、URL ではなくユーザーのインタラクションによりビュー間を移行するものと考えられます。通常、ビューはサイト全体またはサイト内のグループ化されたビジュアル要素を表せます。

ビューとは何かをさらに説明するために、React で実装された架空のオンライン eコマースサイトを操作して、いくつかビューの例を見てみましょう。下のリンクをクリックして、このサイトを新しいブラウザータブで開きます。

**リンク： [ホームサイト](https://target.enablementadobe.com/react/demo/#/)**

![ホームサイト](/help/main/c-experiences/assets/home.png)

ホームサイトに移動すると、イースターセールを宣伝するヒーロー画像やこのサイトで販売されている最新の製品がすぐに表示されます。この場合、ビューはホームサイト全体として定義できます。この点については、後述の「Adobe Target ビューの実装」セクションで詳しく説明します。

**リンク： [製品サイト](https://target.enablementadobe.com/react/demo/#/products)**

![製品サイト](/help/main/c-experiences/assets/product-site.png)

販売されている製品に興味を引かれたため、「Products」リンクをクリックすることにします。ホームサイトと同様、製品サイト全体をビューとして定義できます。このビューには `https://target.enablementadobe.com/react/demo/#/products)` のパス名と同様に「products」という名前を付けられます。

![製品サイト 2](/help/main/c-experiences/assets/product-site-2.png)

このセクションの冒頭は、ビューをサイト全体またはサイト上の視覚要素のグループとして定義しました。上記のように、サイトに表示されている 4 つの製品をグループ化して、ビューとしても考えられます。このビューに名前を付ける場合、「Products」という名前を使用できます。

![製品サイト 3](/help/main/c-experiences/assets/product-site-3.png)

「Load More」ボタンをクリックして、サイト上のより多くの製品を見てみることにします。この場合、Web サイトの URL は変化しません。ただし、ここにあるビューは、上に示されている製品の 2 列目のみを表示できます。このビューは「PRODUCTS-PAGE-2」と呼べます。

**リンク： [チェックアウト](https://target.enablementadobe.com/react/demo/#/checkout)**

![チェックアウトページ](/help/main/c-experiences/assets/checkout.png)

サイトに表示されている製品が気に入ったので、いくつかを購入することにしました。現在、チェックアウトサイトでは、通常配送または速達配送を選択できるようになっています。ビューはサイト上のビジュアル要素のグループにできるため、これに「View Delivery Preferences」という名前を付けられます。

さらに、ビューの概念を大きく拡張することもできます。マーケティング担当者が、選択された配送設定に合わせてサイト上のコンテンツをパーソナライズする場合は、その配送設定ごとにビューを作成できます。この例では、「Normal Delivery」を選択する場合、ビューに「Normal Delivery」という名前を付けられます。「Express Delivery」を選択する場合、ビューに「Express Delivery」という名前を付けることができます。

これで、マーケティング担当者は A/B テストを実行し、速達配送が選択されたときにボタンの色を青から赤に変更することで、どちらの配送オプションでも青のままにする場合と比較してコンバージョンが促進されるかどうかを確認できます。

## Adobe [!DNL Target] ビューの実装

Adobe Target ビューとは何かを説明したので、Target でこの概念を活用して、マーケティング担当者が VEC を介して SPA で A/B テストや XT テストを実行できるようにできます。これには開発者による 1 回限りの設定が必要です。以下では、これを設定する手順を説明します。

1. at.js 2.x をインストールします。

   まず、at.js 2.x をインストールする必要があります。このバージョンの at.js は、SPA を考慮して開発されました。at.js および mbox.js（現在は非推奨）の以前のバージョンでは、Adobe Target Views およびSPA用 VEC はサポートされていません。

   次の場所にあるAdobe Target UI を使用して、at.js 2.x をダウンロードします。 [!UICONTROL 管理/実装]. at.js 2.x は、 [!DNL Adobe Experience Platform].

1. サイトに at.js 2.x の最新の関数 `triggerView()` を実装します。

   A/B テストまたは XT テストを実行する SPA のビューを定義したら、ビューをパラメーターとして at.js 2.x の `triggerView()` 関数を実装します。これにより、マーケティング担当者は VEC を使用し、定義されたビューに対して A/B テストと XT テストを設計して実行できます。これらのビューに対して `triggerView()` 関数が定義されていない場合、VEC はビューを検出しません。そのため、マーケティング担当者は VEC を使用して A/B テストや XT テストを設計して実行できません。

   **`adobe.target.triggerView(viewName, options)`**

   | パラメーター | タイプ | 必須？ | 検証 | 説明 |
   | --- | --- | --- | --- | --- |
   | viewName | 文字列 | ○ | 1. 末尾にスペースは入れられません。<br>2.空にはできません。<br>3.ビュー名はすべてのページに対して一意である必要があります。<br>4.**警告**： ビュー名の先頭または末尾を「`/`」にしないでください。これは、顧客は URL パスから表示名を一般的に抽出するためです。「home」と「`/home`」は区別されます。<br>5.**警告**： `{page: true}` オプションを使用して同じビューを連続してトリガーしないでください。 | ビューを表す文字列型として任意の名前を渡します。このビュー名は、VEC の「[!UICONTROL 変更]」パネルに表示されます。マーケティング担当者はこれを使用してアクションを作成し、A/B および XT アクティビティを実行します。 |
   | options | オブジェクト | × |  |  |
   | options > page | ブール値 | × |  | **TRUE**： ページのデフォルト値は true です。`page=true` の場合、インプレッション数を増分するために Edge サーバーに通知が送信されます。<br>**FALSE**: `page=false` の場合、インプレッション数を増分するための通知は送信されません。オファーを含むページ上のコンポーネントを再レンダリングする場合にのみ使用します。 |

   次に、仮想的な e コマース SPA 向けに React で `triggerView()` 関数を呼び出す方法の使用例を見てみましょう。

   **リンク： [ホームサイト](https://target.enablementadobe.com/react/demo/#/)**

   ![home-react-1](/help/main/c-experiences/assets/react1.png)

   マーケティング担当者の立場からホームサイト全体で A/B テストを実行する場合、ビューに「home」という名前を付けられます。

```
 function targetView() {
   var viewName = window.location.hash; // or use window.location.pathName if router works on path and not hash

   viewName = viewName || 'home'; // view name cannot be empty

   // Sanitize viewName to get rid of any trailing symbols derived from URL
   if (viewName.startsWith('#') || viewName.startsWith('/')) {
     viewName = viewName.substr(1);
   }

   // Validate if the Target Libraries are available on your website
   if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
     adobe.target.triggerView(viewName);
   }
 }

 // react router v4
 const history = syncHistoryWithStore(createBrowserHistory(), store);
 history.listen(targetView);

 // react router v3
 <Router history={hashHistory} onUpdate={targetView} >
```

**リンク： [製品サイト](https://target.enablementadobe.com/react/demo/#/products)**

それでは、もう少し複雑な例を見てみましょう。マーケティング担当者の立場から、ユーザーが「Load More」ボタンをクリックした後に「Price」ラベルの色を赤にして、2 列目の製品をパーソナライズするとしましょう。

![React 製品](/help/main/c-experiences/assets/react4.png)

```
 function targetView(viewName) {
   // Validate if the Target Libraries are available on your website
   if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
     adobe.target.triggerView(viewName);
   }
 }

 class Products extends Component {
   render() {
     return (
       <button type="button" onClick={this.handleLoadMoreClicked}>Load more</button>
     );
   }

   handleLoadMoreClicked() {
     var page = this.state.page + 1; // assuming page number is derived from component’s state
     this.setState({page: page});
     targetView('PRODUCTS-PAGE-' + page);
   }
 }
```

**リンク： [チェックアウト](https://target.enablementadobe.com/react/demo/#/checkout)**

![React チェックアウト](/help/main/c-experiences/assets/react6.png)

マーケティング担当者が、選択された配送設定に合わせてサイト上のコンテンツをパーソナライズする場合は、その配送設定ごとにビューを作成できます。この例では、「Normal Delivery」を選択する場合、ビューに「Normal Delivery」という名前を付けられます。「Express Delivery」を選択する場合、ビューに「Express Delivery」という名前を付けることができます。

これで、マーケティング担当者は A/B テストを実行し、速達配送が選択されたときにボタンの色を青から赤に変更することで、どちらの配送オプションでも青のままにする場合と比較してコンバージョンが促進されるかどうかを確認できます。

```
 function targetView(viewName) {
   // Validate if the Target Libraries are available on your website
   if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
     adobe.target.triggerView(viewName);
   }
 }

 class Checkout extends Component {
   render() {
     return (
       <div onChange={this.onDeliveryPreferenceChanged}>
         <label>
           <input type="radio" id="normal" name="deliveryPreference" value={"Normal Delivery"} defaultChecked={true}/>
           <span> Normal Delivery (7-10 business days)</span>
         </label>

         <label>
           <input type="radio" id="express" name="deliveryPreference" value={"Express Delivery"}/>
           <span> Express Delivery* (2-3 business days)</span>
         </label>
       </div>
     );
   }
   onDeliveryPreferenceChanged(evt) {
     var selectedPreferenceValue = evt.target.value;
     targetView(selectedPreferenceValue);
   }
 }
```

## at.js 2.x のシステム図

次の図は、ビューを使用した at.js 2 ワークフローと、これが SPA 統合をどのように強化するかについて説明しています。at.js 2.x で使用されている概念に関するより詳しい概要については、「[シングルページアプリケーションの実装](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/)」を参照してください。

![at.js 2.x での Target のフロー](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| 手順 | 詳細 |
| --- | --- |
| 1 | 呼び出しユーザーが認証されると、呼び出しが [!DNL Experience Cloud ID]を返し、別の呼び出しが顧客 ID を同期します。 |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.js は、ページに実装されているスニペットを非表示にするオプションを使用して非同期で読み込むこともできます。 |
| 3 | すべての設定済みパラメーター（MCID、SDID および顧客 ID）を含む、ページ読み込みリクエストがおこなわれます。 |
| 4 | プロファイルスクリプトが実行されてから、プロファイルストアにフィードされます。ストアは、オーディエンスライブラリから正規のオーディエンスをリクエストします（例えば、Adobe Analytics、Audience Management などから共有されたオーディエンス）。<br>顧客属性がバッチ処理でプロファイルストアに送信されます。 |
| 5 | URL リクエストパラメーターとプロファイルデータに基づいて、[!DNL Target] が現在のページおよび将来のビューでどのアクティビティおよびエクスペリエンスを訪問者に返すかを決定します。 |
| 6 | ターゲットコンテンツが（オプションで、追加のパーソナライゼーションに関するプロファイル値を含めて）ページに送り返されます。<br>デフォルトコンテンツがちらつくことなく、可能な限り迅速に現在のページ上のターゲットコンテンツが表示されます。<br>SPA でのユーザーアクションの結果として表示されるビューのターゲットコンテンツは、ブラウザーにキャッシュされます。そのため、`triggerView()` を介してビューがトリガーされたときに追加のサーバー呼び出しをおこなわずに即座にターゲットコンテンツを適用できます。 |
| 7 | Analytics データがデータ収集サーバーに送信されます。 |
| 8 | ターゲットデータは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。<br>A4T レポートを使用して、Analytics データが Analytics for Target の両方に表示できるようになります。 |

これで、`triggerView()` が SPA のどこに 実装されているかに関わらず、ビューとアクションはキャッシュから取得され、サーバー呼び出しなしでユーザーに表示されるようになります。`triggerView()` は、インプレッション数を増分して記録するために、[!DNL Target] バックエンド に通知リクエストもおこないます。

![Target フローの at.js 2.x triggerView](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 手順 | 詳細 |
| --- | --- |
| 1 | `triggerView()` は SPA で呼び出され、ビューをレンダリングし、ビジュアル要素を変更ためのアクションを適用します。 |
| 2 | ビューのターゲットコンテンツがキャッシュから読み取られます。 |
| 3 | デフォルトコンテンツがちらつくことなく、可能な限り迅速にターゲットコンテンツが表示されます。 |
| 4 | 通知リクエストが [!DNL Target] プロファイルストア に送信され、アクティビティで訪問者がカウントされ、指標が増分されます。 |
| 5 | Analytics データがデータ収集サーバーに送信されます。 |
| 6 | Target データは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。A4T レポートを使用して、Analytics データが Analytics と Target の両方に表示できるようになります。 |

## シングルページアプリケーションの Visual Experience Composer

at.js 2.x のインストールを完了し、サイトに `triggerView()` を追加した後、VEC を使用して A/B および XT アクティビティを実行します。詳細については、「[シングルページアプリケーション（SPA）の Visual Experience Composer](/help/main/c-experiences/spa-visual-experience-composer.md)」を参照してください。

>[!NOTE]
>
>SPA 用 VEC は、通常の Web ページで使用する VEC と同じものですが、`triggerView()` の実装されたシングルページアプリケーションを開く際に利用できる機能がいくつか追加されています。

## トリガービューによる A4T と at.js 2.x および SPA との正常な連携 {#triggerview}

[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md)（A4T）が at.js 2.x で正しく動作するように、Target リクエストと Analytics リクエストで同じ SDID を送信してください。

SPA に関するベストプラクティスは次のとおりです。

* カスタムイベントを使用して、アプリケーションへの注目を喚起する通知をおこなう
* ビューのレンダリングが開始する前にカスタムイベントを発生させる
* ビューのレンダリングが終了したらカスタムイベントを発生させる

at.js 2.x には、新しい API 関数 [triggerView()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-triggerview-atjs-2/) が追加されました。`triggerView()` を使用して、ビューのレンダリングが開始したことを at.js に通知する必要があります。

カスタムイベント、at.js 2.x、Analytics を組み合わせる方法については、次の例を参照してください。この例では、HTML ページに訪問者 API、at.js 2.x、AppMeasurement がこの順に含まれていると仮定します。

次のカスタムイベントがあるとしましょう。

* `at-view-start` - ビューのレンダリングが開始したときに発生
* `at-view-end` - ビューのレンダリングが終了したときに発生

A4T と at.js 2.x を確実に連携させるには、

ビュー開始ハンドラーは次のようになります。

```
document.addEventListener("at-view-start", function(e) {
  var visitor = Visitor.getInstance("<your Adobe Org ID>");
  
  visitor.resetState();
  adobe.target.triggerView("<view name>");
});
```

ビュー終了ハンドラーは次のようになります。

```
document.addEventListener("at-view-end", function(e) {
  // s - is the AppMeasurement tracker object
  s.t();
});
```

>[!NOTE]
>
>`at-view-start` および `at-view-end` イベントを発生させる必要があります。これらのイベントは、at.js カスタムイベントには含まれていません。

この例では JavaScript コードを使用していますが、タグマネージャーを使用する場合は、これらすべてを簡略化できます。例えば、 [Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/).

上記の手順に従う場合は、SPA 用の堅牢な A4T ソリューションが必要です。

## 実装のベストプラクティス {#bp}

at.js 2.x API を使用すると、 [!DNL Target] 様々な方法での実装ですが、このプロセス中に、正しい操作順に従うことが重要です。

次の情報は、ブラウザーで初めてシングルページアプリケーションを読み込む際、および後で発生するビューの変更について従う必要がある操作の順序を示します。

### 最初のページ読み込みの操作の順序

| 手順 | アクション | 詳細 |
| --- | --- | --- |
| 1 | VisitorAPI JS を読み込む | このライブラリは、訪問者に ECID を割り当てる役割を担います。 この ID は後で他のユーザーによって使用されます [!DNL Adobe] ソリューションを参照してください。 |
| 2 | at.js 2.x を読み込む | at.js 2.x は、の実装に使用する必要な API をすべて読み込みます。 [!DNL Target] リクエストと表示。 |
| 3 | 実行 [!DNL Target] リクエスト | データレイヤーがある場合、に送信するために必要な重要なデータを読み込むことをお勧めします [!DNL Target] 実行する前に [!DNL Target] リクエスト。 これにより、 `targetPageParams` を使用して、ターゲティングに使用する任意のデータを送信します。 この API 呼び出しで、execute > pageLoad および prefetch > ビューを必ずリクエストする必要があります。 もし `pageLoadEnabled` および `viewsEnabled`その後、手順 2 で execute > pageLoad と prefetch > ビューの両方が自動的に実行されます。それ以外の場合は、 `getOffers()` このリクエストをおこなう API。 |
| 4 | 呼び出し `triggerView()` | これは、 [!DNL Target] 手順 3 で開始したリクエストで、ページ読み込みの実行とビューの両方のエクスペリエンスが返される場合は、次の点を確認してください。 `triggerView()` が [!DNL Target] リクエストが返され、オファーのキャッシュへの適用が完了します。 この手順は、ビューごとに 1 回だけ実行する必要があります。 |
| 5 | を [!DNL Analytics] ページビュービーコン | このビーコンは、手順 3 と 4 に関連付けられた SDID をに送信します。 [!DNL Analytics] データステッチ用。 |
| 6 | 追加呼び出し `triggerView({"page": false})` | これは、ビューの変更がおこなわれずに、ページ上の特定のコンポーネントが再レンダリングされる可能性があるSPAフレームワークのオプションの手順です。 このような場合、この API を呼び出して、 [!DNL Target] SPAフレームワークがコンポーネントを再レンダリングした後で、エクスペリエンスが再適用されます。 この手順は、必要な回数だけ実行できます。 [!DNL Target] エクスペリエンスはSPAビューに保持されます。 |

### SPAビューの変更に対する操作の順序（完全なページの再読み込みなし）

| 手順 | アクション | 詳細 |
| --- | --- | --- |
| 1 | 呼び出し `visitor.resetState()` | この API は、読み込み時に、新しいビュー用に SDID が再生成されるようにします。 |
| 2 | を呼び出してキャッシュを更新 `getOffers()` API | これは、このビューの変更が、現在の訪問者をさらに絞り込むための可能性がある場合に実行するオプションの手順です [!DNL Target] アクティビティをアクティビティから除外するか、アクティビティから除外します。 この時点で、追加データをに送信することもできます。 [!DNL Target] 追加のターゲティング機能を有効にする場合。 |
| 3 | 呼び出し `triggerView()` | 手順 2 を実行した場合は、 [!DNL Target] この手順を実行する前に、オファーをリクエストしてキャッシュに適用します。 この手順は、ビューごとに 1 回だけ実行する必要があります。 |
| 4 | 呼び出し `triggerView()` | 手順 2 を実行していない場合は、手順 1 を完了したらすぐにこの手順を実行できます。 手順 2 と手順 3 を実行した場合は、この手順をスキップする必要があります。 この手順は、ビューごとに 1 回だけ実行する必要があります。 |
| 5 | を [!DNL Analytics] ページビュービーコン | このビーコンは、手順 2、3、4 に関連付けられた SDID をに送信します。 [!DNL Analytics] データステッチ用。 |
| 6 | 追加呼び出し `triggerView({"page": false})` | これは、ビューの変更がおこなわれずに、ページ上の特定のコンポーネントが再レンダリングされる可能性があるSPAフレームワークのオプションの手順です。 このような場合、この API を呼び出して、 [!DNL Target] SPAフレームワークがコンポーネントを再レンダリングした後で、エクスペリエンスが再適用されます。 この手順は、必要な回数だけ実行できます。 [!DNL Target] エクスペリエンスはSPAビューに保持されます。 |

## トレーニングビデオ

詳細は次のビデオで説明されています。

### at.js 2.x の仕組みについて![概要バッジ](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/26250)

詳しくは、[at.js 2.x の仕組みについて](https://experienceleague.adobe.com/docs/target-learn/tutorials/implementation/understanding-how-atjs-20-works.html?lang=ja)を参照してください。

### SPAでの at.js 2.x の実装 ![チュートリアルバッジ](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/26248)

詳しくは、 [シングルページアプリケーション (SPA) での at.js 2.x を使用したAdobe Targetの実装](https://helpx.adobe.com/target/kt/using/atjs2-single-page-application-technical-video-implement.html) を参照してください。

### Adobe TargetでのSPA用 VEC の使用 ![チュートリアルバッジ](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/26249)

詳しくは、[Adobe Target でのシングルページアプリケーション Visual Experience Composer（SPA VEC）の使用](https://helpx.adobe.com/jp/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html)を参照してください。
