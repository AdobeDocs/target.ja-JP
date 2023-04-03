---
keywords: spa vec; react; angular; react.js; spa visual experience composer; spa experience composer オプション; シングルページアプリケーション; シングルページアプリ; spa; モバイルエクスペリエンスオプション; target ビュー
description: SPA VEC を Adobe  [!DNL Target]  で使用して、開発部門に継続的に依存することなく、マーケティング担当者が自ら SPA でテストを作成したりコンテンツをパーソナライズしたりする方法を説明します。
title: シングルページアプリケーション Visual Experience Composer（SPA VEC）の使用方法
feature: Visual Experience Composer (VEC)
exl-id: fd3dcfaa-e5c6-45a1-8229-9c206562e5b0
source-git-commit: f7a9c08567669160684bff8ae5098d57c6237463
workflow-type: tm+mt
source-wordcount: '3748'
ht-degree: 90%

---

# シングルページアプリケーション（SPA）Visual Experience Composer

[!DNL Adobe Target] では、[!UICONTROL Visual Experience Composer]（VEC）により、マーケティング担当者が自らアクティビティを作成して、エクスペリエンスをパーソナライズすることができます。その際、Adobe Target のグローバル mbox を介して、従来のマルチページアプリケーションで動的に配信することが可能です。ただし、以下の図に示すように、オファーを取得する際のページの読み込みや後続のサーバー呼び出しによっては、遅延が生じます。シングルページアプリケーション（SPA）の場合は、ユーザーエクスペリエンスとアプリケーションのパフォーマンスが低下することから、適切な手法とは言えません。

![従来のライフサイクルと SPA のライフサイクルの比較](/help/main/c-experiences/assets/trad-vs-spa.png)

最新リリースでは、SPA 用の VEC が導入されました。SPA VEC を使用すると、開発部門に継続的に依存することなく、マーケティング担当者が自ら SPA でテストを作成したりコンテンツをパーソナライズしたりすることができます。VEC では、React や Angular などの人気あるフレームワークで [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md)や[エクスペリエンスターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md)（XT）アクティビティを作成することが可能です。

## Adobe [!DNL Target] ビューとシングルページアプリケーション

SPA の Adobe Target VEC は、ビューと呼ばれる新しい概念を活用します。ビューとはビジュアル要素の論理的集合体で、全体として SPA のエクスペリエンスを形作ります。このため SPA は、URL ではなくユーザーのインタラクションによりビュー間を移行するものと考えられます。通常、ビューはサイト全体またはサイト内のグループ化されたビジュアル要素を表せます。

ビューとは何かをさらに説明するために、React で実装された架空のオンライン eコマースサイトを操作して、いくつかビューの例を見てみましょう。下のリンクをクリックして、このサイトを新しいブラウザータブで開きます。

**リンク： [ホームサイト](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/)**

![ホームサイト](/help/main/c-experiences/assets/home.png)

ホームサイトに移動すると、イースターセールで使われるヒーローの画像と、サイトで販売されている最新製品を確認できます。この場合、ビューはホームサイト全体として定義できます。この点については、後述の「Adobe Target ビューの実装」セクションで詳しく説明します。

**リンク： [製品サイト](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products)**

![製品サイト](/help/main/c-experiences/assets/product-site.png)

製品への関心が増してきたところで、製品のリンクをクリックします。ホームサイトと同様、製品サイト全体をビューとして定義できます。このビューには `https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products` のパス名と同様に「products」という名前を付けられます。

![製品サイト 2](/help/main/c-experiences/assets/product-site-2.png)

このセクションの冒頭は、ビューをサイト全体またはサイト上の視覚要素のグループとして定義しました。上記のように、サイトに表示されている 4 つの製品をグループ化して、ビューとしても考えられます。このビューに名前を付ける場合は、「products」という名前を使用できます。

![製品サイト 3](/help/main/c-experiences/assets/product-site-3.png)

「Load More」ボタンをクリックすると、サイトに掲載されている他の製品を見ることができます。この場合、web サイトの URL は変化しません。ただし、ここにあるビューは、上に示されている製品の 2 列目のみを表示できます。例えば、表示名を「PRODUCT-PAGE-2」にします。

**リンク： [チェックアウト](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/checkout)**

![チェックアウトページ](/help/main/c-experiences/assets/checkout.png)

サイトに表示されている製品が気に入ったので、いくつかを購入することにしました。現在、チェックアウトサイトでは、通常配送または速達配送を選択できるようになっています。サイト上のどのような視覚要素グループもビューにすることができるので、このビューに「Delivery Preferences」と名前を付けることが可能です。

さらに、ビューの概念を大きく拡張することもできます。マーケティング担当者が、選択された配送設定に合わせてサイト上のコンテンツをパーソナライズする場合は、その配送設定ごとにビューを作成できます。例えば、通常配送を選択した場合、ビューに「Normal Delivery」と名前を付けることができます。速達配送を選択した場合には、ビューを「Express Delivery」という名前にすることができます。

これで、マーケティング担当者は A/B テストを実行し、速達配送が選択されたときにボタンの色を青から赤に変更することで、どちらの配送オプションでも青のままにする場合と比較してコンバージョンが促進されるかどうかを確認できます。

## Adobe [!DNL Target] ビューの実装

Adobe Target ビューとは何かを説明したので、Target でこの概念を活用して、マーケティング担当者が VEC を介して SPA で A/B テストや XT テストを実行できるようにできます。これには開発者による 1 回限りの設定が必要です。以下では、これを設定する手順を説明します。

1. at.js 2.x をインストールします。

   まず、at.js 2.x をインストールする必要があります。このバージョンの at.js は、SPA を考慮して開発されました。at.js の以前のバージョンでは、Adobe Target ビューと SPA VEC はサポートされていません。

   ![実装の詳細ダイアログボックス](/help/main/c-experiences/assets/imp-200.png)

   Adobe Target UI で[!UICONTROL 管理／実装]を選択し、at.js 2.x をダウンロードします。at.js 2.x は、 [Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank}. ただし、Adobe Target の拡張機能は現在最新ではなく、サポートされていません。

1. サイトに at.js 2.x の最新の関数 [triggerView()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-triggerview-atjs-2/) を実装します。{target=_blank}

   A/B テストまたは XT テストを実行する SPA のビューを定義したら、ビューをパラメーターとして at.js 2.x の `triggerView()` 関数を実装します。これにより、マーケティング担当者は VEC を使用し、定義されたビューに対して A/B テストと XT テストを設計して実行できます。これらのビューに対して `triggerView()` 関数が定義されていない場合、VEC はビューを検出しません。そのため、マーケティング担当者は VEC を使用して A/B テストや XT テストを設計して実行できません。

   **`adobe.target.triggerView(viewName, options)`**

   | パラメーター | タイプ | 必須？ | 検証 | 説明 |
   | --- | --- | --- | --- | --- |
   | viewName | 文字列 | ○ | 1. 末尾にスペースは入れられません。<br>2.空にはできません。<br>3.ビュー名はすべてのページに対して一意である必要があります。<br>4.**警告**： ビュー名の先頭または末尾を「`/`」にしないでください。これは、顧客は URL パスから表示名を一般的に抽出するためです。「home」と「`/home`」は区別されます。<br>5.**警告**： `{page: true}` オプションを使用して同じビューを連続してトリガーしないでください。 | ビューを表す文字列型として任意の名前を渡します。このビュー名は、VEC の「[!UICONTROL 変更]」パネルに表示されます。マーケティング担当者はこれを使用してアクションを作成し、A/B および XT アクティビティを実行します。 |
   | options | オブジェクト | × |  |  |
   | options > page | ブール値 | × |  | **TRUE**： ページのデフォルト値は true です。`page=true` の場合、インプレッション数を増分するために Edge サーバーに通知が送信されます。<br>**FALSE**: `page=false` の場合、インプレッション数を増分するための通知は送信されません。オファーを含むページ上のコンポーネントを再レンダリングする場合にのみ使用します。 |

   次に、模擬 eコマース SPA 用に React で `triggerView()` 関数を呼び出す方法について、いくつかの例を見てみましょう。

   **リンク： [ホームサイト](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/)**

   ![home-react-1](/help/main/c-experiences/assets/react1.png)

   マーケティング担当者がホームサイト全体で A/B テストを実行したい場合、URL から取り出せるビューに「home」と名前を付けることができます。

   ```javascript
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

   **リンク： [製品サイト](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products)**

   それでは、もう少し複雑な例を見てみましょう。例えば、ユーザーが「Load More」ボタンをクリックした場合に価格ラベルの色を赤に変更して、2 行目にある製品をパーソナライズすることをマーケティング担当者が希望しているとしましょう。

   ![React 製品](/help/main/c-experiences/assets/react4.png)

   ```javascript
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

   **リンク： [チェックアウト](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/checkout)**

   ![React チェックアウト](/help/main/c-experiences/assets/react6.png)

   マーケティング担当者が、選択された配送設定に合わせてサイト上のコンテンツをパーソナライズする場合は、その配送設定ごとにビューを作成できます。例えば、通常配送を選択した場合、ビューに「Normal Delivery」と名前を付けることができます。速達配送を選択した場合には、ビューを「Express Delivery」という名前にすることができます。

   これで、マーケティング担当者は A/B テストを実行し、速達配送が選択されたときにボタンの色を青から赤に変更することで、どちらの配送オプションでも青のままにする場合と比較してコンバージョンが促進されるかどうかを確認できます。

   ```javascript
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
   >SPA VEC は、通常の web ページで使用する VEC と同じものですが、`triggerView()` の実装されたシングルページアプリケーションを開く際に利用できる機能がいくつか追加されています。

VEC が SPA で適切に動作できるように、VEC の[変更](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)パネルとアクションで、大きな改善が 2 点行われました。

**変更パネル**

以下に示すように、[!UICONTROL 変更]パネルでは、特定のビュー用に作成されたアクションが取り込まれます。ビューのすべてのアクションが、ビューの下にグループ化されています。

**アクション**

アクションをクリックすると、このアクションが適用されるサイトの要素がハイライトされます。ビューに作成された各 VEC アクションには、以下のように、情報、編集、複製、移動および削除のアイコンがあります。

![変更](/help/main/c-experiences/assets/modifications.png)

次の表で、各アクションについて説明します。

| ページ | 説明 |
| --- | --- |
| 情報 | アクションの詳細を表示します。 |
| 編集 | アクションのプロパティを直接編集できます。 |
| 複製 | [!UICONTROL 変更]パネルに存在する 1 つ以上のビューまたは VEC で参照および移動した 1 つ以上のビューにアクションを複製します。アクションは、必ずしも[!UICONTROL 変更]パネルに存在する必要はありません。<br>**注意**：複製操作を行ったら、[!UICONTROL 参照]を使用して VEC のビューに移動し、複製されたアクションが有効な操作かどうかを確認します。アクションがビューに適用できない場合、エラーが表示されます。 |
| 移動 | 変更パネルに既に存在するページの読み込みイベントまたはその他のビューにアクションを移動します。<br>[!UICONTROL ページの読み込みイベント] – ページの読み込みイベントに対応するアクションが web アプリケーションの最初のページ読み込みに適用されます。<br>**注意**：移動操作を行ったら、参照を使用して VEC のビューに移動し、移動が有効な操作かどうかを確認します。アクションがビューに適用できない場合、エラーが表示されます。 |
| 削除 | アクションを削除します。 |

>[!NOTE]
>
>VEC でページが読み込まれる前や、ページを読み込めなかった場合には、様々なアクションを実行できます。サイト読み込み前に編集できないアクションは、UI では無効化されます。

**例 1**

ここでは、ホームビューを作成した上記の例を参照します。このビューに対して 2 つの目標があります。

1. 「買い物かごに追加」ボタンと「いいね」ボタンを薄い青色に変更します。ヘッダーのコンポーネントを変更しているので、これは「ページ読み込み」に含まれる必要があります。
1. テキストの色が紫に変更された状態で、「2019 年の最新製品」ラベルを「2019 年の人気製品」に変更します。

これらの変更を反映させるには、VEC で「[!UICONTROL 構成]」をクリックし、変更をホームビューに適用します。

![例 1](/help/main/c-experiences/assets/example1.png)

**例 2**

ここでは、PRODUCTS-PAGE-2 ビューを作成した上記の例を参照します。「価格」のラベルを赤い色の「セール価格」に変更することが目標です。

1. 「[!UICONTROL 参照]」をクリックし、ヘッダーの「[!UICONTROL 製品]」リンクをクリックします。
1. 2 行目の製品を表示するには、「[!UICONTROL Load More]」を 1 回クリックします。
1. 「[!UICONTROL 構成]」をクリックします。
1. アクションを適用して、テキストラベルを「セール価格」に変更し、色を赤に変更します。

![例 2](/help/main/c-experiences/assets/example2.png)

**例 3**

前述のように、ビューはより細かいレベルで定義できます。ラジオボタンの選択などの状態もビューとして定義することができます。ここまでで、「チェックアウト時に速達配送を選択」と「チェックアウト時に通常配送を選択」をビューとして作成しました。ここでは、「チェックアウト時に速達配送を選択」のボタンの色を赤に変更します。

1. 「[!UICONTROL 参照]」をクリックします。
1. 買い物かごに製品を数点追加します。
1. 右上隅のカートアイコンをクリックします。
1. 注文のチェックアウトをクリックします。
1. 「速達配送」のラジオボタンをクリックします。
1. 「[!UICONTROL 構成]」をクリックします。
1. 「支払い」ボタンを「注文の完了」ボタンに変更し、色を赤に変えます。

![例 3](/help/main/c-experiences/assets/example3.png)

>[!NOTE]
>
>「チェックアウト時に速達配送を選択」ビューは、「速達配送」のラジオボタンをクリックするまで、変更パネルには表示されません。これは、`triggerView()` 関数がトリガーされるのは、「速達配送」のラジオボタンが選択され、変更パネルに表示されるビューがあることを VEC が認識したときのみであるためです。

## at.js および SPA の詳細

**SPA で、最初のページ読み込みの後に、アクションによって生じた最新のオーディエンスデータのビューを取得する方法を教えてください。**

at.js 2.x の通常のワークフローでは、サイトの読み込みの際にすべてのビューとアクションがキャッシュに保存されます。そのため、その後のサイト上でのユーザーアクションにより、サーバー呼び出しがトリガーされオファーが取得されることはありません。後続のユーザーアクションによって更新された可能性のある最新のプロファイルデータに合わせてビューを取得するには、最新のオーディエンスユーザーまたは渡されたプロファイルデータで `getOffers()` および `applyOffers()` を呼び出します。

例えば、通信会社の SPA で at.js 2.x を使用しているとします。ビジネスとしての達成目標は、次のとおりです。

* `http://www.telecom.com/home` で、ログアウトするユーザーや匿名のユーザーに対して、「初月無料」のヒーローオファーなどの最新のプロモーションを表示する。
* ログインユーザーで契約期限が近づいている場合に、「無料で電話が手に入ります」などの更新プロモーションを表示する（`http://www.telecom.com/loggedIn/home`）。

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
1. at.js 2.x が使用されているので、ページの読み込み時にパラメーター「`loggedIn = false`」が渡され、ビューが取得されます。この際、オーディエンスにパラメーター「`loggedIn = false`」がある場合に有効となるアクティビティに対応するビューがすべて取得されます。
1. 次に at.js 2.x では、ログアウトホームのビューが取得され、「初月無料」のオファーを表示するアクションが実行され、それがキャッシュに保存されます。
1. `triggerView(“Logged Out Home”)` が呼び出された際には、「初月無料」のオファーがキャッシュから取得されますが、その際にはサーバー呼び出しは生じません。
1. ユーザーが「ログイン」をクリックし、資格情報を入力します。
1. Web サイトは SPA なので、すべてのページは読み込まず、代わりにユーザーを `http://www.telecom.com/loggedIn/home` にルーティングします。

ここで問題が発生します。このコードをルート変更時に配置しているため、ユーザーがログインすると、`triggerView(“Logged In Home”)` が発生します。その結果、at.js 2.x ではキャッシュからビューとアクションが取得されますが、キャッシュに存在するビューはログアウトホームのみです。

ではここで、ログイン時のビューを取得し、「無料で電話が手に入ります」のオファーを表示させるにはどうすればいいでしょうか。offer? サイト上でのすべての後続のアクションは、ログインユーザーの視点で行われます。つまり、すべてのアクションが最終的にログインユーザー用にパーソナライズされたオファーとなるようにするには、どうすればいいでしょうか。

at.js 2.x でサポートされている新しい `getOffers()` 関数と `applyOffers()` 関数を使用できます。

```javascript
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

つまり、at.js 2.x では、最新のオーディエンスデータを使用したビュー、アクション、オファーをオンデマンドで取得する方法がサポートされているわけです。

**at.js 2.x はシングルページアプリケーション用に A4T をサポートしていますか。**

はい。Adobe Analytics および Experience Cloud 訪問者 ID サービスを実装した場合、at.js 2.x では、`triggerView()` 関数を通じて SPA 用の A4T をサポートします。詳細については、以下の図を参照してください。

![Target フロー](/help/main/c-experiences/assets/atjs-spa-flow.png)

| 手順 | 説明 |
| --- | --- |
| 1 | `triggerView()` が SPA で呼び出され、ビューがレンダリングされます。また、ビューに関連付けられたビジュアル要素を変更するためのアクションが適用されます。 |
| 2 | ビューのターゲットコンテンツがキャッシュから読み取られます。 |
| 3 | デフォルトコンテンツがちらつくことなく、可能な限り迅速にターゲットコンテンツが表示されます。 |
| 4 | 通知リクエストが Target プロファイルストアに送信され、アクティビティの訪問者がカウントされて、指標が増分されます。 |
| 5 | Analytics データがデータ収集サーバーに送信されます。 |
| 6 | Target データは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。A4T レポートを使用して、Analytics データが Analytics と Target の両方に表示できるようになります。 |

>[!NOTE]
>ビューがトリガーされるたびに、インプレッションのカウントについて Adobe Analytics に通知を送信しない場合は `{page: false}` を `triggerView()` 関数に渡し、恒常的に再レンダリングされるコンポーネントに対してビューが複数回トリガーされた場合でも、インプレッションカウントが急増しないようにします。次に例を示します。
>
>`adobe.target.triggerView(“PRODUCTS-PAGE-2”, {page:false})`

## サポートされているアクティビティ

| アクティビティのタイプ | 対応? |
| --- | --- |
| [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md) | ○ |
| A/B テストおよびエクスペリエンスのターゲット設定（XT）アクティビティにおける[ オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)<br> | ○ |
| [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | ○ |
| [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md) | ○ |
| [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | × |
| [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | × |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | × |
| [レコメンデーション](/help/main/c-recommendations/recommendations.md) | × |

**at.js 2.x をインストールして `triggerView()` をサイトに実装した場合、SPA VEC は自動ターゲットをサポートしませんが、自動ターゲット A/B アクティビティはどのように実行すればよいですか。**

自動ターゲット A/B アクティビティを使用する場合は、ページの読み込みイベントで実行されるすべてのアクションを VEC で移動できます。各アクションにマウスポインターを置いて、「[!UICONTROL ページの読み込みイベントに移動]」ボタンをクリックします。その後、次の手順で、トラフィック配分方法に対応する自動ターゲットを選択できます。

## サポートされる統合

| 統合 | 対応? |
| --- | --- |
| [Analytics for Target（A4T）](/help/main/c-integrating-target-with-mac/a4t/a4t.md) | ○ |
| [Experience Cloud Audiences](/help/main/c-integrating-target-with-mac/mmp.md) | ○ |
| [顧客属性](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/customer-attributes/){target=_blank} | ○ |
| [AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | ○ |

## サポートされる機能 {#supported-features}

| 機能 | 対応? |
| --- | --- |
| [ワークスペースとプロパティ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) | ○ |
| [QA リンク](/help/main/c-activities/c-activity-qa/activity-qa.md) | ○ |
| [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) | × |
| [カスタムコード](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | ○ |
| [VEC オプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) | すべて |
| [クリックの追跡](/help/main/c-activities/r-success-metrics/click-tracking.md) | ○ |
| [複数アクティビティ配信](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md) | ○ |

## SPA VEC のページ配信設定 {#page-delivery-settings}

[!UICONTROL ページ配信]設定を使用すると、オーディエンスに対していつ Target アクティビティが適合および実行されるかを決定するルールを設定できます。

VEC の 3 ステップのガイドによるアクティビティ作成ワークフローから「[!UICONTROL ページ配信]」オプションにアクセスするには、**[!UICONTROL エクスペリエンス]**&#x200B;ステップで、**[!UICONTROL 設定]**（歯車アイコン）／**[!UICONTROL ページ配信]**&#x200B;をクリックします。

![ページ配信オプションダイアログボックス](/help/main/c-experiences/assets/page-delivery.png)

例えば、上に示す[!UICONTROL ページ配信]設定で定義したように、訪問者が直接 `https://www.adobe.com` に到達するか、*または*&#x200B;訪問者が `https://www.adobe.com/products` を含む任意の URL に到達する場合に、Target アクティビティが適合および実行します。これは、ページとのすべてのやり取りでページを再読み込みする複数ページアプリケーションに対して完全に機能します。at.js が、ユーザーが移動する URL に対して適合するアクティビティを取得します。

ただし、SPA の動作は異なるので、[!UICONTROL ページ配信]設定は、SPA VEC アクティビティで定義されたとおりに、すべてのアクションがビューに適用できるように設定する必要があります。

### 使用例

以下の使用例を検討します。

![SPA VEC 変更パネル](/help/main/c-experiences/assets/page-delivery-example.png)

以下の変更が加えられました。

* 次の URL の下にあるホームビューの背景色が変更されました。 [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/).
* URL の下にある製品ビューのボタンの色が変更されました。 [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products).

上記の例を念頭に置いて、を設定すると、どうなりますか？ [!UICONTROL ページ配信] 次のみを含める設定： [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/) を at.js 2.*x* を使用）

![ページ配信ダイアログボックス](/help/main/c-experiences/assets/spa-page-delivery.png)

以下の図に、Target フロー -  ページ読み込みリクエスト（at.js 2.*x*）を示します。

![Target フロー - at.js 2.0 ページ読み込みリクエスト](/help/main/c-experiences/assets/page-load-request.png)

**ユーザージャーニー #1**

* ユーザーが [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/).
* at.js 2.*x* は、Edge に対してクエリをおこない、その URL に対してアクティビティを実行する必要があるかどうかを確認します。 [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/).
* 手順 6 で、Target Edge は、ブラウザーでキャッシュできるように、ホームおよび製品ビューに対するアクションを返します。

**結果**：ユーザーのホームビューに緑の背景色が表示されます。ユーザーが [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products)に設定すると、製品ビューの下でアクションがブラウザーにキャッシュされるので、ボタンの青い背景色が表示されます。

注意：移動先のユーザー [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products) ページの読み込みをトリガーしませんでした。

**ユーザージャーニー #2**

* ユーザーが [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products).
* at.js 2.*x* は、Edge に対してクエリをおこない、その URL に対してアクティビティを実行する必要があるかどうかを確認します。 [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products).
* 適合するアクティビティがありません [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products).
* 適合するアクティビティがないので、トリガーする at.js 2.*x* 用にキャッシュされるアクションおよびビューはありません。

**結果**:定義済みの `triggerView()` 製品ビューの場合、およびSPA VEC を使用して製品ビューに対してアクションを実行した場合、を含むルールを作成していないので、期待されたアクションは表示されません [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/#/products) 」と入力します。

### ベストプラクティス

ユーザーは SPA の任意の URL に到達したり他のページに移動したりする可能性があるので、管理するユーザージャーニーは非常に難しくなる可能性があります。このため、SPA 全体を含むことができるように、ベース URL を含むページ配信ルールを指定することが最適です。この方法では、A/B テストまたはエクスペリエンスターゲット設定（XT）アクティビティを表示したいページにユーザーが到達するために取る可能性のあるすべての異なるジャーニーおよびパスについて検討する必要がありません。

例えば、上記で直面した問題を解決するために、以下のようにページ配信設定にベース URL を指定できます。

![ページ配信ダイアログボックス](/help/main/c-experiences/assets/conclusion.png)

これにより、訪問者が SPA のどこに到達し、ホームまたはページビューのどちらに移動しても、適用されたアクションが表示されます。

これで、SPA VEC のビューにいつアクションを追加しても、以下のポップアップメッセージが表示され、[!UICONTROL ページ配信]ルールについて検討するように促します。

![ページ配信設定メッセージ](/help/main/c-experiences/assets/pop-up-message.png)

このメッセージは、作成する新しい各アクティビティ用のビューに最初のアクションを追加すると表示されます。このメッセージは、お客様の組織の全員がこれらの[!UICONTROL ページ配信]ルールを正しく適用する方法を学習するのに役立ちます。

## トレーニングビデオ：Adobe Target での SPA VEC の使用

>[!VIDEO](https://video.tv.adobe.com/v/26249)

詳しくは、[Adobe Target でのシングルページアプリケーション Visual Experience Composer（SPA VEC）の使用](https://helpx.adobe.com/jp/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html)を参照してください。
