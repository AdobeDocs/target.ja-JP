---
description: シングルページアプリケーション（SPA）の Visual Experience Composer（VEC）を使用すると継続的な開発の依存性を持たず、マーケティング担当者が自ら SPA でテストを作成したりコンテンツをパーソナライズすることができます。VEC は、React や Angular などの人気あるフレームワークの多くでアクティビティを作成するのに利用できます。
keywords: spa vec; react; angular; react.js; spa visual experience composer; spa experience composer オプション; シングルページアプリケーション; シングルページアプリ; spa; モバイルエクスペリエンスオプション; target ビュー
seo-description: Adobe Target のシングルページアプリケーション（SPA）の Visual Experience Composer（VEC）を使用すると、継続的な開発に依存せずに、マーケティング担当者が自ら SPA でテストを作成したりコンテンツをパーソナライズしたりすることができます。VEC は、React や Angular などの人気あるフレームワークの多くでアクティビティを作成するのに利用できます。
seo-title: シングルページアプリケーション（SPA）Visual Experience Composer
solution: 'Target '
title: シングルページアプリケーション（SPA）Visual Experience Composer
topic: Standard
uuid: 4dcd6d9c-b2e3-4759-a2e0-3696c572faba
translation-type: tm+mt
source-git-commit: dda07f19bddb870b20dabc484a1b97d55bcc5775

---


# シングルページアプリケーション（SPA）Visual Experience Composer{#single-page-app-spa-visual-experience-composer}

[!DNL Adobe Target] では、[!UICONTROL Visual Experience Composer]（VEC）により、マーケティング担当者が自らアクティビティを作成して、エクスペリエンスをパーソナライズすることができます。その際、Adobe Target のグローバル mbox を介して、従来のマルチページアプリケーションで動的に配信することが可能です。ただし、以下の図に示すように、オファーを取得する際のページの読み込みや後続のサーバー呼び出しによっては、遅延が生じます。シングルページアプリケーション（SPA）の場合は、ユーザーエクスペリエンスとアプリケーションのパフォーマンスが低下することから、適切な手法とは言えません。

![従来のライフサイクルと SPA のライフサイクルの比較](/help/c-experiences/assets/trad-vs-spa.png)

最新リリースでは、SPA 用の VEC が導入されました。SPA 用 VEC を使用すると、継続的な開発に依存せずに、マーケティング担当者が自ら SPA でテストを作成したりコンテンツをパーソナライズしたりすることができます。VEC では、React や Angular などの人気あるフレームワークで [A/B テスト](/help/c-activities/t-test-ab/test-ab.md)や[エクスペリエンスターゲット設定](/help/c-activities/t-experience-target/experience-target.md)（XT）アクティビティを作成することが可能です。

## Adobe Target ビューとシングルページアプリケーション

SPA の Adobe Target VEC は、ビューと呼ばれる新しい概念を活用します。ビューとはビジュアル要素の論理的集合体で、全体として SPA のエクスペリエンスを形作ります。このため SPA は、URL ではなくユーザーのインタラクションによりビュー間を移行するものと考えられます。通常、ビューはサイト全体またはサイト内のグループ化されたビジュアル要素を表せます。

ビューとは何かをさらに説明するために、React で実装された架空のオンライン e コマースサイトを操作して、いくつかビューの例を見てみましょう。下のリンクをクリックして、このサイトを新しいブラウザタブで開きます。

**リンク:[ホームサイト](https://target.enablementadobe.com/react/demo/#/)**

![ホームサイト](/help/c-experiences/assets/home.png)

ホームサイトに移動すると、イースターセールで使われるヒーローの画像と、サイトで販売されている最新製品を確認できます。この場合、ビューはホームサイト全体として定義できます。この点については、後述の「Adobe Target ビューの実装」セクションで詳しく説明します。

**リンク:[製品サイト](https://target.enablementadobe.com/react/demo/#/products)**

![製品サイト](/help/c-experiences/assets/product-site.png)

製品への関心が増してきたところで、製品のリンクをクリックします。ホームサイトの場合と同様に、製品サイト全体をビューとして定義できます。このビューには`https://target.enablementadobe.com/react/demo/#/products` のパス名と同様に「products」という名前を付けられます。

![製品サイト 2](/help/c-experiences/assets/product-site-2.png)

このセクションの冒頭は、ビューをサイト全体またはサイト上の視覚要素のグループとして定義しました。上のように、サイトに表示されている 4 つの製品をグループ化して、ビューとみなすこともできます。このビューに名前を付ける場合は、「products」という名前を使用できます。

![製品サイト 3](/help/c-experiences/assets/product-site-3.png)

「Load More」ボタンをクリックすると、サイトに掲載されている他の製品をみることができます。この場合、Web サイトの URL は変更されません。ただし、表示される製品のうち、2 行目のものだけをビューで表示させることができます。たとえば、表示名を「PRODUCT-PAGE-2」にします。

**リンク:[チェックアウト](https://target.enablementadobe.com/react/demo/#/checkout)**

![チェックアウトページ](/help/c-experiences/assets/checkout.png)

サイトに表示されている製品が気に入ったので、いくつかを購入することにしました。現在、チェックアウトサイトでは、通常配送または速達配送を選択できるようになっています。サイト上のどのような視覚要素グループもビューにすることができるので、このビューに「Delivery Preferences」と名前を付けることが可能です。

さらに、ビューの概念を大きく拡張することもできます。マーケティング担当者が、選択された配送設定に合わせてサイト上のコンテンツをパーソナライズする場合は、その配送設定ごとにビューを作成できます。たとえば、通常配送を選択した場合、ビューに「Normal Delivery」と名前を付けることができます。速達配送を選択した場合には、ビューを「Express Delivery」という名前にすることができます。

これで、マーケティング担当者は A/B テストを実行し、速達配送が選択されたときにボタンの色を青から赤に変更することで、どちらの配送オプションでも青のままにする場合と比較してコンバージョンが促進されるかどうかを確認できます。

## Adobe Target ビューの実装

Adobe Target ビューとは何かを説明したので、Target でこの概念を活用して、マーケティング担当者が VEC を介して SPA で A/B テストや XT テストを実行できるようにできます。これには開発者による 1 回限りの設定が必要です。以下では、これを設定する手順を説明します。

1. at. js2. xをインストールします。

   まず、at. js2. xをインストールする必要があります。このバージョンのat. jsは、SPOで開発されました。at.js および mbox.ｊs の以前のバージョンでは、Adobe Target ビューと SPA 用 VEC はサポートされていません。

   ![実装の詳細ダイアログボックス](/help/c-experiences/assets/imp-200.png)

   セットアップ/実装に [!UICONTROL あるAdobe Target UIを使用してat. js2. xをダウンロード]します。at. js2. xは、 [Adobe Launchでもデプロイ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)できます。ただし、Adobe Target エクステンションは現在最新ではなく、サポートされていません。

1. at. js2. xの最新の機能を実装します。 [triggerView（）](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md) 。

   A/BまたはXTテストを実行するSPAのビューを定義したら、パラメーターとして渡されたビューを使用してat. js2. xの `triggerView()` 関数を実装します。これにより、マーケティング担当者は VEC を使用し、定義されたビューに対して A/B テストと XT テストを設計して実行できます。これらのビューに対して `triggerView()` 関数が定義されていない場合、VEC はビューを検出しません。そのため、マーケティング担当者は VEC を使用して A/B テストや XT テストを設計して実行できません。

   **`adobe.target.triggerView(viewName, options)`**

   | パラメーター | タイプ | 必須？ | 検証 | 説明 |
   | --- | --- | --- | --- | --- |
   | viewName | 文字列 | ○ | 1. 末尾にスペースは入れられません。<br>2.空にはできません。<br>3.ビュー名はすべてのページに対して一意である必要があります。<br>4.**警告**： ビュー名の先頭または末尾を「`/`」にしないでください。これは、顧客は URL パスから表示名を一般的に抽出するためです。「home」と「`/home`」は区別されます。<br>5.**警告**： `{page: true}` オプションを使用して同じビューを連続してトリガーしないでください。 | ビューを表す文字列型として任意の名前を渡します。このビュー名は、VEC の「[!UICONTROL 変更]」パネルに表示されます。マーケティング担当者はこれを使用してアクションを作成し、A/B および XT アクティビティを実行します。 |
   | options | オブジェクト | × |
   | options &gt; page | ブール値 | × | **TRUE**： ページのデフォルト値は true です。`page=true` の場合、インプレッション数を増分するために Edge サーバーに通知が送信されます。<br>**FALSE**: `page=false` の場合、インプレッション数を増分するための通知は送信されません。ページのコンポーネントをオファーの際にだけ再レンダリングする場合に使用します。 |

   次に、模擬 e コマース SPA 用に React で `triggerView()` 関数を呼び出す方法について、いくつかの例を見てみましょう。

   **リンク:[ホームサイト](https://target.enablementadobe.com/react/demo/#/)**

   ![home-react-1](/help/c-experiences/assets/react1.png)

   マーケティング担当者がホームサイト全体で A/B テストを実行したい場合、URL から取り出せるビューに「home」と名前を付けることができます。

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

   **リンク:[製品サイト](https://target.enablementadobe.com/react/demo/#/products)**

   ここでは、少し複雑な例を見てみましょう。たとえば、ユーザーが「Load More」ボタンをクリックした場合に価格ラベルの色を赤に変更して、2 行目にある製品をパーソナライズすることをマーケティング担当者が希望しているとしましょう。

   ![製品欄の反応](/help/c-experiences/assets/react4.png)

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

   **リンク:[チェックアウト](https://target.enablementadobe.com/react/demo/#/checkout)**

   ![React チェックアウト](/help/c-experiences/assets/react6.png)

   マーケティング担当者が、選択された配送設定に合わせてサイト上のコンテンツをパーソナライズする場合は、その配送設定ごとにビューを作成できます。たとえば、通常配送を選択した場合、ビューに「Normal Delivery」と名前を付けることができます。速達配送を選択した場合には、ビューを「Express Delivery」という名前にすることができます。

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

1. VEC 経由で A/B アクティビティまたは XT アクティビティを起動します。

   SPA で、`adobe.target.triggerView()` にビュー名をパラメーターとして指定して実装した場合、VEC でそれらのビューを検出でき、ユーザーがアクションを作成して A/B アクティビティや XT アクティビティを修正できるようになります。

   >[!NOTE]
   >
   >SPA 用 VEC は、通常の Web ページで使用する VEC と同じものですが、`triggerView()` の実装されたシングルページアプリケーションを開く際に利用できる機能がいくつか追加されています。

VEC が SPA で適切に動作できるように、VEC の[変更](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)パネルとアクションで、大きな改善が 2 点行われました。

**変更パネル**

以下に示すように、[!UICONTROL 変更]パネルでは、特定のビュー用に作成されたアクションが取り込まれます。ビューのすべてのアクションが、ビューの下にグループ化されています。

**アクション**

アクションをクリックすると、このアクションが適用されるサイトの要素がハイライトされます。ビューで作成される各VECアクションには、次のように4つのアイコンがあります。情報、編集、移動および削除。

![変更](/help/c-experiences/assets/modifications-new.png)

次の表で、各アクションについて説明します。

| ページ | 説明 |
| --- | --- |
| 情報 | アクションの詳細を表示します。 |
| 編集 | アクションのプロパティを直接編集できます。 |
| 移動 | アクションをページ読み込みイベントまたは既に変更パネルに存在する他のビューに移動します。<br>[!UICONTROL ページ読み込みイベント] -ページ読み込みイベントに対応するアクションが、Webアプリケーションの最初のページ読み込み時に適用されます。<br>**注意** 移動操作の実行後、移動が有効な操作であるかどうかを確認するには、VECの「参照」に移動する必要があります。アクションを表示できない場合は、エラーが表示されます |
| 削除 | アクションを削除します。 |

>[!NOTE]
>
>VECでページが読み込まれる前に、またはページの読み込みに失敗した場合でも、多くのアクションを実行できます。サイト読み込み前に編集できないアクションは、 UI では無効化されます。

**例 1**

ここでは、ホームビューを作成した上記の例を参照します。このビューに対して 2 つの目標があります。

1. 「買い物かごに追加」ボタンと「いいね」ボタンを薄い青色に変更します。ヘッダーのコンポーネントを変更しているので、これは「ページ読み込み」に含まれる必要があります。
1. テキストの色が紫に変更された状態で、「2019 年の最新製品」ラベルを「2019 年の人気製品」に変更します。

これらの変更を反映させるには、VEC で「[!UICONTROL 構成]」をクリックし、変更をホームビューに適用します。

![例 1](/help/c-experiences/assets/example1.png)

**例 2**

ここでは、PRODUCTS-PAGE-2 ビューを作成した上記の例を参照します。「価格」のラベルを赤い色の「セール価格」に変更することが目標です。

1. 「[!UICONTROL 参照]」をクリックし、ヘッダーの「[!UICONTROL 製品]」リンクをクリックします。
1. 2 行目の製品を表示するには、「[!UICONTROL Load More]」を 1 回クリックします。
1. 「[!UICONTROL 構成]」をクリックします。
1. アクションを適用して、テキストラベルを「セール価格」に変更し、色を赤に変更します。

![例 2](/help/c-experiences/assets/example2.png)

**例 3**

前述のように、ビューはより細かいレベルで定義できます。ラジオボタンの選択などの状態もビューとして定義することができます。ここまでで、「チェックアウト時に速達配送を選択」と「チェックアウト時に通常配送を選択」をビューとして作成しました。ここでは、「チェックアウト時に速達配送を選択」のボタンの色を赤に変更します。

1. 「[!UICONTROL 参照]」をクリックします。
1. 買い物かごに製品を数点追加します。
1. 右上隅のカートアイコンをクリックします。
1. 注文のチェックアウトをクリックします。
1. 「速達配送」のラジオボタンをクリックします。
1. 「[!UICONTROL 構成]」をクリックします。
1. 「支払い」ボタンを「注文の完了」ボタンに変更し、色を赤に変えます。

![例 3](/help/c-experiences/assets/example3.png)

>[!NOTE]
>
>「チェックアウト時に速達配送を選択」ビューは、「速達配送」のラジオボタンをクリックするまで、変更パネルには表示されません。これは、`triggerView()` 関数がトリガーされるのは、「速達配送」のラジオボタンが選択され、変更パネルに表示されるビューがあることを VEC が認識したときのみであるためです。

## at.js および SPA の詳細

**SPA で、最初のページ読み込みの後に、アクションによって生じた最新のオーディエンスデータのビューを取得する方法を教えてください。**

at. js2. xの一般的なワークフローは、サイトが読み込まれるときに、サイトの後続のユーザーアクションがオファーを取得するサーバー呼び出しをトリガしないようにキャッシュされます。後続のユーザーアクションによって更新された可能性のある最新のプロファイルデータに合わせてビューを取得するには、最新のオーディエンスユーザーまたは渡されたプロファイルデータで `getOffers()` および `applyOffers()` を呼び出します。

例えば、通信会社で、at. js2. xを使用するSPAがあるとします。ビジネスとして、以下の目標を達成します。

* `http://www.telecom.com/home` で、ログアウトするユーザーや匿名のユーザーに対して、「初月無料」のヒーローオファーなどの最新のプロモーションを表示する。
* ログインユーザーで契約期限が近づいている場合に、「無料で電話が手に入ります」などの更新プロモーションを表示する。on `http://www.telecom.com/loggedIn/home`.

ここでは、デベロッパー名が表示された状態で、次のように `triggerView()` を呼び出します。

* `http://www.telecom.com/home` の場合のビュー名は、「ログアウトホーム」です。
   * `triggerView(“Logged Out Home”)` が呼び出されます。
* `http://www.telecom.com/loggedIn/home` の場合のビュー名は、「ログインホーム」です。
   * `triggerView(“Logged In Home”)` がルートの変更時に呼び出されます。

マーケティング担当者が VEC を通じて次の A/B アクティビティを実行します。

* 「初月無料」を表示する A/B アクティビティ。パラメーター「`loggedIn= false`」でオーディエンスにオファーされ、`http://www.telecom.com/home` に表示される。ビュー名はログアウトホーム。
* 「無料で電話が手に入ります」と表示する A/B アクティビティ。パラメーター「`loggedIn=true`」でオーディエンスにオファーされ、`http://www.telecom.com/loggedIn/home` に表示される。ビュー名はログインヒーローオファー。

次に、このときのユーザーフローについて考えてみましょう。

1. 匿名のログアウトユーザーがページにアクセスします。
1. at. js2. xを使用しているので、「」ページ読み込み時にパラメーター「`loggedIn = false`」を渡して、オーディエンスにパラメーター「`loggedIn = false`」があるときに資格のあるアクティブなアクティビティに存在するすべてのビューを取得します。
1. at. js2. xは、&quot;First Month Free&quot;オファーを表示してキャッシュに保存するために、ログアウトされたホームビューとアクションを取得します。
1. `triggerView(“Logged Out Home”)` が呼び出された際には、「初月無料」のオファーがキャッシュから取得されますが、その際にはサーバー呼び出しは生じません。
1. ユーザーが「ログイン」をクリックし、資格情報を入力します。
1. Web サイトは SPA なので、すべてのページは読み込まず、代わりにユーザーを `http://www.telecom.com/loggedIn/home` にルーティングします。

ここで問題が発生します。このコードをルート変更時に配置しているため、ユーザーがログインすると、`triggerView(“Logged In Home”)` が発生します。これにより、. js2. xには、キャッシュからビューおよびアクションを取得しますが、キャッシュに存在する唯一のビューはログアウトホームです。

ではここで、ログイン時のビューを取得し、「無料で電話が手に入ります」のオファーを表示させるにはどうすればいいでしょうか。offer? サイト上でのすべての後続のアクションは、ログインユーザーの視点で行われます。つまり、すべてのアクションが最終的にログインユーザー用にパーソナライズされたオファーとなるようにするには、どうすればいいでしょうか。

at. js2. xでサポートされている新しい `getOffers()` 関数と `applyOffers()` 関数を使用できます。

```
adobe.target.getOffers({
  request: {
  prefetch: {
    "views": [
      {
        "parameters": {
          "loggedIn": true
        },
      }
    ]
  },
});
```

`getOffers()` の応答を `applyOffers()` に渡し、「loggedIn = true」に関連付けられているすべてのビューとアクションを at.js キャッシュで更新します。

つまり、at. js2. xでは、最新のオーディエンスデータを使用して、ビュー、アクションおよびオファーをオンデマンド方式で取得できます。

**シングルページアプリケーションでは、at. js2. xはA4Tをサポートしていますか?**

はい。at. js2. xは、Adobe AnalyticsおよびExperience Cloud訪問者IDサービスを実装していることを示す `triggerView()` 、SPAのA4Tをサポートしています。詳細については、以下の図を参照してください。

![Target フロー](/help/c-experiences/assets/atjs-spa-flow.png)

| 手順 | 説明 |
| --- | --- |
| 1 | `triggerView()` が SPA で呼び出され、ビューがレンダリングされます。また、ビューに関連付けられたビジュアル要素を変更するためのアクションが適用されます。 |
| 2 | ビューのターゲットコンテンツがキャッシュから読み取られます。 |
| 3 | デフォルトコンテンツがちらつくことなく、可能な限り迅速にターゲットコンテンツが表示されます。 |
| 4 | 通知リクエストが Target プロファイルストアに送信され、アクティビティの訪問者がカウントされて、指標が増分されます。 |
| 5 | Analytics データがデータ収集サーバーに送信されます。 |
| 6 | Target データは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。A4T レポートを使用して、Analytics データが Analytics および Target に表示できるようになります。 |

>[!NOTE]
>ビューがトリガーされるたびに、インプレッションのカウントについて Adobe Analytics に通知を送信しない場合は `{page: false}` を `triggerView()` 関数に渡し、恒常的に再レンダリングされるコンポーネントに対してビューが複数回トリガーされた場合でも、インプレッションカウントが急増しないようにします。次に例を示します。
>
>`adobe.target.triggerView(“PRODUCTS-PAGE-2”, {page:false})`

## サポートされているアクティビティ

| アクティビティのタイプ | 対応? |
| --- | --- |
| [A/B テスト](/help/c-activities/t-test-ab/test-ab.md) | ○ |
| A/B テストおよびエクスペリエンスのターゲット設定（XT）アクティビティにおける[オファーとしての Recommendations](/help/c-recommendations/recommendations-as-an-offer.md)<br> | ○ |
| [自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | ○ |
| [SPA 向けのエクスペリエンスのターゲット設定](/help/c-activities/t-experience-target/experience-target.md) | ○ |
| [多変量分析テスト](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | × |
| [自動ターゲット](/help/c-activities/auto-target-to-optimize.md) | × |
| [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) | × |
| [推奨事項](/help/c-recommendations/recommendations.md) | × |

**at. js2. xをインストールしてサイトに実装`triggerView()`した場合、SPA VECは自動ターゲットをサポートしていないので、自動ターゲットA/Bアクティビティをどのように実行するのですか。**

自動ターゲット A/B アクティビティを使用する場合は、ページ読み込みイベントで実行されるすべてのアクションを VEC で移動できます。各アクションにカーソルを合わせて、「[!UICONTROL ページ読み込みイベントに移動]」ボタンをクリックします。その後、次の手順で、トラフィック配分方法に対応する自動ターゲットを選択できます。

## サポートされる統合

| 統合 | 対応? |
| --- | --- |
| [Analytics for Target（A4T）](/help/c-integrating-target-with-mac/a4t/a4t.md) | ○ |
| [Experience Cloud オーディエンス](/help/c-integrating-target-with-mac/mmp.md) | ○ |
| [顧客属性](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | ○ |
| [AEM エクスペリエンスフラグメント](/help/c-experiences/c-manage-content/aem-experience-fragments.md) | ○ |

## サポートされる機能 {#supported-features}

| 機能 | 対応? |
| --- | --- |
| [ワークスペースとプロパティ](/help/administrating-target/c-user-management/property-channel/property-channel.md) | ○ |
| [QA リンク](/help/c-activities/c-activity-qa/activity-qa.md) | ○ |
| [フォームベースの Experience Composer](/help/c-experiences/form-experience-composer.md) | × |
| [カスタムコード](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | ○ |
| [VEC オプション](/help/c-experiences/c-visual-experience-composer/viztarget-options.md) | すべて |
| [クリックの追跡](/help/c-activities/r-success-metrics/click-tracking.md) | ○ |
| [複数アクティビティ配信](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) | ○ |

## トレーニングビデオ：Adobe Target での SPA 用 VEC の使用

>[!VIDEO](https://video.tv.adobe.com/v/26249)

詳しくは、Adobe [Targetのシングルページアプリケーション用のVisual Experience Composer（SPA](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) VEC）の使用を参照してください。
