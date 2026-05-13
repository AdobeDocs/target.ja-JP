---
keywords: spa vec; react; angular; react.js; spa visual experience composer; spa experience composer オプション; シングルページアプリケーション; シングルページアプリ; spa; モバイルエクスペリエンスオプション; target ビュー
description: SPA VEC を Adobe  [!DNL Target]  で使用して、開発部門に継続的に依存することなく、マーケティング担当者が自ら SPA でテストを作成したりコンテンツをパーソナライズしたりする方法を説明します。
title: シングルページアプリケーション Visual Experience Composer（SPA VEC）の使用方法
feature: Visual Experience Composer (VEC)
exl-id: fd3dcfaa-e5c6-45a1-8229-9c206562e5b0
TQID: https://experienceleague.adobe.com/SilMhoqEp7o5GvyO2vzBt83e8EmiULUvo14Y-E-PcJA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2:
  - id: df62f171-ac37-440f-8f0f-f41a72ebdd34
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c18d9e03-ac7d-4811-9c92-3e92ddc70ade
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 3904
ht-degree: 61%

---

# シングルページアプリケーション（SPA）Visual Experience Composer

[!DNL Adobe Target]では、[!UICONTROL Visual Experience Composer] （VEC）は、Adobe Targetのグローバル mboxを介して、従来のマルチページアプリケーションで動的に配信できるアクティビティを作成し、エクスペリエンスをパーソナライズするための実行機能をマーケターに提供します。 ただし、以下の図に示すように、オファーを取得する際のページの読み込みや後続のサーバー呼び出しによっては、遅延が生じます。 シングルページアプリケーション（SPA）の場合は、ユーザーエクスペリエンスとアプリケーションのパフォーマンスが低下することから、適切な手法とは言えません。

![従来のライフサイクルと SPA のライフサイクルの比較](/help/main/c-experiences/assets/trad-vs-spa.png)

最新リリースでは、SPA 用の VEC が導入されました。 SPA VEC を使用すると、開発部門に継続的に依存することなく、マーケターが自ら SPA でテストを作成したりコンテンツをパーソナライズしたりできます。 VEC では、React や Angular などの人気あるフレームワークで [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md)や[エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md)（XT）アクティビティを作成することが可能です。

## Adobe [!DNL Target] ビューとシングルページアプリケーション

SPA の Adobe Target VEC は、ビューと呼ばれる新しい概念を活用します。ビューとはビジュアル要素の論理的集合体で、全体として SPA のエクスペリエンスを形作ります。 このため SPA は、URL ではなくユーザーのインタラクションによりビュー間を移行するものと考えられます。 通常、ビューはサイト全体またはサイト内のグループ化されたビジュアル要素を表せます。

ビューについて詳しく説明するには、Reactに実装されたこの仮想的なオンライン e コマースサイトを操作し、ビューの例をいくつか見てみましょう。 下のリンクをクリックして、このサイトを新しいブラウザータブで開きます。

**リンク： [ホームサイト](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/)**

![ホームサイト](/help/main/c-experiences/assets/home.png)

ホームサイトに移動すると、イースターセールで使われるヒーロー画像と、サイトで販売されている最新製品を確認できます。 この場合、ビューはホームサイト全体として定義できます。 この点については、後述の「Adobe Target ビューの実装」セクションで詳しく説明します。

**リンク： [製品サイト](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products)**

![製品サイト](/help/main/c-experiences/assets/product-site.png)

製品への関心が増してきたところで、製品のリンクをクリックします。 ホームサイトと同様、製品サイト全体をビューとして定義できます。 このビューには `https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products` のパス名と同様に「products」という名前を付けられます。

![製品サイト 2](/help/main/c-experiences/assets/product-site-2.png)

このセクションの冒頭は、ビューをサイト全体またはサイト上の視覚要素のグループとして定義しました。 上記のように、サイトに表示されている 4 つの製品をグループ化して、ビューとしても考えられます。 このビューに名前を付ける場合は、「products」という名前を使用できます。

![製品サイト 3](/help/main/c-experiences/assets/product-site-3.png)

「Load More」ボタンをクリックすると、サイトに掲載されている他の製品を見ることができます。 この場合、web サイトの URL は変化しません。 ただし、ここにあるビューは、上に示されている製品の 2 列目のみを表示できます。 例えば、表示名を「PRODUCT-PAGE-2」にします。

**リンク： [チェックアウト](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/checkout)**

![チェックアウトページ](/help/main/c-experiences/assets/checkout.png)

サイトに表示されている製品が気に入ったので、いくつかを購入することにしました。 現在、チェックアウトサイトでは、通常配送または速達配送を選択できるようになっています。 サイト上のどのような視覚要素グループもビューにすることができるので、このビューに「Delivery Preferences」と名前を付けることが可能です。

さらに、ビューの概念を大きく拡張することもできます。 マーケターが選択された配送設定に応じてサイト上のコンテンツをパーソナライズする場合、配送設定ごとにビューを作成できます。 例えば、通常配送を選択した場合、ビューに「Normal Delivery」と名前を付けることができます。 速達配送を選択した場合には、ビューを「Express Delivery」という名前にすることができます。

これで、マーケターは A/B テストを実行し、速達配送が選択されたときにボタンの色を青から赤に変更することで、どちらの配送オプションでも青のままにする場合と比較してコンバージョンが促進されるかどうかを確認できます。

## Adobe [!DNL Target] ビューの実装

ここまで Adobe Target ビューの内容について説明しました。Target ではこのビューの概念を活用することで、マーケターが SPA での A/B テストや XT テストを VEC を通じて実行できるようにしています。 これには開発者による 1 回限りの設定が必要です。 設定する手順を見てみましょう。

1. at.js 2.x をインストールします。

   まず、at.js 2.xをインストールします。 このバージョンのat.jsは、SPAを念頭に置いて開発されました。 at.js の以前のバージョンでは、Adobe Target ビューと SPA VEC はサポートされていません。

   ![実装の詳細ダイアログボックス](/help/main/c-experiences/assets/imp-200.png)

   [!UICONTROL Administration > Implementation]にあるAdobe Target UIを使用して、at.js 2.xをダウンロードします。 at.js 2.x は、[Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch.html?lang=ja){target=_blank} のタグを使用してデプロイすることもできます。 ただし、Adobe Target の拡張機能は現在最新ではなく、サポートされていません。

1. at.js 2.xの最新の関数[triggerView （） &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-triggerview-atjs-2.html){target=_blank}をサイトに実装します。

   A/BまたはXT テストを実行するSPAのビューを定義したら、パラメーターとして渡されたビューでat.js 2.xの`triggerView()`関数を実装します。 これにより、マーケターは VEC を使用し、定義されたビューに対して A/B テストと XT テストを設計して実行できます。 これらのビューに対して `triggerView()` 関数が定義されていない場合、VEC はビューを検出しません。そのため、マーケターは VEC を使用して A/B テストや XT テストを設計して実行できません。

   **`adobe.target.triggerView(viewName, options)`**

   | パラメーター | タイプ | 必須？ | 検証 | 説明 |
   | --- | --- | --- | --- | --- |
   | viewName | 文字列 | ○ | &#x200B;1. 末尾にスペースがありません。<br>2。 空にすることはできません。<br>3。 ビュー名は、すべてのページに対して一意である必要があります。<br>4。 **警告**： ビュー名の先頭または末尾を「`/`」にしないでください。 これは、顧客は URL パスから表示名を一般的に抽出するためです。 私たちにとって、「ホーム」と「`/home`」は異なります。<br>5。 **警告**： `{page: true}` オプションを使用して同じビューを連続してトリガーしないでください。 | ビューを表す文字列型として任意の名前を渡します。 このビュー名は、VECの[!UICONTROL Modifications] パネルに表示され、マーケターがアクションを作成し、A/BおよびXT アクティビティを実行できるようにします。 |
   | options | オブジェクト | × |  |  |
   | options > page | ブール値 | × |  | **TRUE**： ページのデフォルト値は true です。 `page=true`の場合、インプレッション数を増やすための通知がEdge サーバーに送信されます。<br>**FALSE**: `page=false`の場合、インプレッション数を増やすための通知は送信されません。 オファーを含むページ上のコンポーネントを再レンダリングする場合にのみ使用します。 |

   次に、架空のe コマース SPAに対してReactで`triggerView()`関数を呼び出す方法について、いくつかのユースケースを紹介します。

   **リンク： [ホームサイト](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/)**

   ![home-react-1](/help/main/c-experiences/assets/react1.png)

   マーケターがホームサイト全体で A/B テストを実行したい場合、URL から取り出せるビューに「home」と名前を付けることができます。

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

   **リンク： [製品サイト](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products)**

   では、もう少し複雑な例を見てみましょう。 マーケターが「さらに読み込む」ボタンをクリックした後、価格ラベルの色を赤に変更して、2行目の商品をパーソナライズしたいとします。

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
       var page = this.state.page + 1; // assuming page number is derived from component's state
       this.setState({page: page});
       targetView('PRODUCTS-PAGE-' + page);
     }
   }
   ```

   **リンク： [チェックアウト](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/checkout)**

   ![React チェックアウト](/help/main/c-experiences/assets/react6.png)

   マーケターが選択された配送設定に応じてサイト上のコンテンツをパーソナライズする場合、配送設定ごとにビューを作成できます。 例えば、通常配送を選択した場合、ビューに「Normal Delivery」と名前を付けることができます。 速達配送を選択した場合には、ビューを「Express Delivery」という名前にすることができます。

   マーケターは、A/B テストを実行して、どちらの配送オプションでもボタンの色を青のままにするのに対して、速達が選択されたときに色を青から赤に変更することでコンバージョンを上昇させることができるかどうかを確認したいと思うようになるかもしれません。

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

次に示すように、[!UICONTROL Modifications] パネルは、特定のビューに対して作成されたアクションをキャプチャします。 ビューのすべてのアクションが、ビューの下にグループ化されています。

**アクション**

アクションをクリックすると、このアクションが適用されるサイトの要素がハイライトされます。 ビューに作成された各 VEC アクションには、以下のように、情報、編集、複製、移動および削除のアイコンがあります。

![変更](/help/main/c-experiences/assets/modifications.png)

次の表で、各アクションについて説明します。

| ページ | 説明 |
| --- | --- |
| 情報 | アクションの詳細を表示します。 |
| 編集 | アクションのプロパティを直接編集できます。 |
| 複製 | アクションを、[!UICONTROL Modifications] パネルに存在する1つ以上のビュー、またはVECで参照して移動した1つ以上のビューに複製します。 アクションは、[!UICONTROL Modifications] パネルに必ずしも存在する必要はありません。<br>**注意**: クローン操作が行われた後、[!UICONTROL Browse]経由でVECのビューに移動して、クローン操作が有効な操作であったかどうかを確認する必要があります。 アクションがビューに適用できない場合、エラーが表示されます。 |
| 移動 | アクションをページ読み込みイベントまたは修正パネルに既に存在するその他のビューに移動します。<br>[!UICONTROL Page Load Event] - ページ読み込みイベントに対応するアクションは、web アプリケーションの最初のページ読み込み時に適用されます。<br>**注意**：移動操作を行ったら、参照を使用して VEC のビューに移動し、移動が有効な操作かどうかを確認します。 アクションがビューに適用できない場合、エラーが表示されます。 |
| 削除 | アクションを削除します。 |

>[!NOTE]
>
>VEC でページが読み込まれる前や、ページを読み込めなかった場合には、様々なアクションを実行できます。 サイト読み込み前に編集できないアクションは、UI では無効化されます。

**例 1**

上記のホームビューを作成した例を参照しましょう。 このビューに対して 2 つの目標があります。

1. 「買い物かごに追加」ボタンと「いいね」ボタンを薄い青色に変更します。 ヘッダーのコンポーネントを変更するので、これは「ページ読み込み」にする必要があります。
1. テキストの色が紫に変更された状態で、「2019 年の最新製品」ラベルを「2019 年の人気製品」に変更します。

これらの目標を実行するには、VECで「[!UICONTROL Compose]」をクリックし、変更をホームビューに適用します。

![例 1](/help/main/c-experiences/assets/example1.png)

**例 2**

PRODUCTS-PAGE-2 ビューを作成した上記の例を参照しましょう。 「価格」のラベルを赤い色の「セール価格」に変更することが目標です。

1. [!UICONTROL Browse]をクリックし、ヘッダーの[!UICONTROL Products] リンクをクリックします。
1. 「[!UICONTROL Load More]」を1回クリックすると、2行目の商品に移動します。
1. [!UICONTROL Compose] をクリックします。
1. アクションを適用して、テキストラベルを「セール価格」に変更し、色を赤に変更します。

![例 2](/help/main/c-experiences/assets/example2.png)

**例 3**

前述のように、ビューはより細かいレベルで定義できます。 ラジオボタンの選択などの状態もビューとして定義することができます。 ここまでで、「チェックアウト時に速達配送を選択」と「チェックアウト時に通常配送を選択」をビューとして作成しました。 ここでは、「チェックアウト時に速達配送を選択」のボタンの色を赤に変更します。

1. [!UICONTROL Browse] をクリックします。
1. 買い物かごに製品を数点追加します。
1. 右上隅の買い物かごアイコンをクリックします。
1. 注文のチェックアウトをクリックします。
1. 「速達配送」のラジオボタンをクリックします。
1. [!UICONTROL Compose] をクリックします。
1. 「支払い」ボタンを「注文の完了」ボタンに変更し、色を赤に変えます。

![例 3](/help/main/c-experiences/assets/example3.png)

>[!NOTE]
>
>「チェックアウト時に速達配送を選択」ビューは、「速達配送」のラジオボタンをクリックするまで、変更パネルには表示されません。 これは、`triggerView()` 関数がトリガーされるのは、「速達配送」のラジオボタンが選択され、変更パネルに表示されるビューがあることを VEC が認識したときのみであるためです。

## at.js および SPA の詳細

**SPA で、最初のページ読み込みの後に、アクションによって生じた最新のオーディエンスデータのビューを取得する方法を教えてください。**

at.js 2.xの一般的なワークフローは、サイトの読み込み時にすべてのビューとアクションがキャッシュされ、サイト上のその後のユーザーアクションがサーバー呼び出しをトリガーしてオファーを取得しないようにすることです。 後続のユーザーアクションによって更新された可能性のある最新のプロファイルデータに合わせてビューを取得するには、最新のオーディエンスユーザーまたは渡されたプロファイルデータで `getOffers()` および `applyOffers()` を呼び出します。

例えば、通信会社で、at.js 2.xを使用するSPAがあるとします。 企業は、次のような目標を達成できます。

* ログアウトしたユーザーまたは匿名ユーザーの場合は、`http://www.telecom.com/home`に「初月無料」ヒーローオファーを表示するなど、最新の会社プロモーションを表示します。
* ログインしているユーザーの場合は、「無料電話の対象となります」など、契約が発生するユーザーに対してアップグレードプロモーションオファーを表示します。 （`http://www.telecom.com/loggedIn/home`）。

ここでは、デベロッパー名が表示された状態で、次のように `triggerView()` を呼び出します。

* `http://www.telecom.com/home` の場合のビュー名は、「ログアウトホーム」です。
   * `triggerView("Logged Out Home")` が呼び出されます。
* `http://www.telecom.com/loggedIn/home` の場合のビュー名は、「ログインホーム」です。
   * `triggerView("Logged In Home")` がルートの変更時に呼び出されます。

マーケターが VEC を通じて次の A/B アクティビティを実行します。

* `http://www.telecom.com/home`に表示されるパラメーター「`loggedIn= false`」を持つオーディエンスに対する「初月無料」オファーを含むA/B アクティビティ。ビュー名はログアウトホームです。
* 「無料電話の対象となります。」を使用したA/B アクティビティ `http://www.telecom.com/loggedIn/home`に表示されるパラメーター「`loggedIn=true`」を持つオーディエンスのオファー。ビュー名は「ヒーローオファーにログイン」です。

次に、このときのユーザーフローについて考えてみましょう。

1. 匿名のログアウトユーザーがページにアクセスします。
1. at.js 2.xを使用しているので、ページロード時にパラメーター「`loggedIn = false`」を渡して、オーディエンスがパラメーター「`loggedIn = false`」を持つ場合に適格となる、アクティブなアクティビティに存在するすべてのビューを取得します。
1. at.js 2.xは、ログアウトホームビューと「初月無料」オファーを表示するアクションを取得し、キャッシュに保存します。
1. `triggerView("Logged Out Home")`が呼び出されると、「初月無料」オファーがキャッシュから取得され、サーバーコールなしでオファーが表示されます。
1. ユーザーは「ログイン」をクリックし、資格情報を提供します。
1. Web サイトは SPA なので、すべてのページは読み込まず、代わりにユーザーを `http://www.telecom.com/loggedIn/home` にルーティングします。

ここで問題が発生します。 このコードをルート変更時に配置しているため、ユーザーがログインすると、`triggerView("Logged In Home")` が発生します。 その結果、at.js 2.x ではキャッシュからビューとアクションが取得されますが、キャッシュに存在するビューはログアウトホームのみです。

では、ログインしたビューを取得し、「無料の電話の対象です」を表示するにはどうすればよいですか？ offer? サイト上でのすべての後続のアクションは、ログインユーザーの視点で行われます。つまり、すべてのアクションが最終的にログインユーザー用にパーソナライズされたオファーとなるようにするには、どうすればいいでしょうか。

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

`getOffers()`の応答を`applyOffers()`に渡すと、「loggedIn = true」に関連付けられたすべてのビューとアクションがat.js キャッシュを更新します。

つまり、at.js 2.x では、最新のオーディエンスデータを使用したビュー、アクション、オファーをオンデマンドで取得する方法がサポートされているわけです。

**at.js 2.x はシングルページアプリケーション用に A4T をサポートしていますか。**

はい。Adobe Analytics および Experience Cloud 訪問者 ID サービスを実装した場合、at.js 2.x では、`triggerView()` 関数を通じて SPA 用の A4T をサポートします。 詳細については、以下の図を参照してください。

![Target フロー](/help/main/c-experiences/assets/atjs-spa-flow.png)

| 手順 | 説明 |
| --- | --- |
| 1 | `triggerView()` が SPA で呼び出され、ビューがレンダリングされます。また、ビューに関連付けられたビジュアル要素を変更するためのアクションが適用されます。 |
| 2 | ビューのターゲットコンテンツがキャッシュから読み取られます。 |
| 3 | デフォルトコンテンツがちらつくことなく、可能な限り迅速にターゲットコンテンツが表示されます。 |
| 4 | 通知リクエストが Target プロファイルストアに送信され、アクティビティの訪問者がカウントされて、指標が増分されます。 |
| 5 | Analytics データがデータ収集サーバーに送信されます。 |
| 6 | Target データは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。 A4T レポートを使用して、Analytics データが Analytics for Target の両方に表示できるようになります。 |

>[!NOTE]
>ビューがトリガーされるたびにインプレッション数をカウントする通知をAdobe Analyticsに送信しない場合は、`{page: false}`を`triggerView()`関数に渡して、常に再レンダリングされるコンポーネントのビューが複数回トリガーされたときにインプレッション数が膨らまないようにします。 次に例を示します。
>
>`adobe.target.triggerView("PRODUCTS-PAGE-2", {page:false})`

## サポートされているアクティビティ

| アクティビティのタイプ | 対応? |
| --- | --- |
| [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md) | ○ |
| A/B テストおよびエクスペリエンスのターゲット設定（XT）アクティビティにおける[オファーとしてのレコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md)<br> | ○ |
| [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | ○ |
| [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md) | ○ |
| [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | × |
| [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | × |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | × |
| [レコメンデーション](/help/main/c-recommendations/recommendations.md) | × |

**at.js 2.x をインストールして `triggerView()` をサイトに実装した場合、SPA VEC は自動ターゲットをサポートしませんが、自動ターゲット A/B アクティビティはどのように実行すればよいですか。**

自動ターゲット A/B アクティビティを使用する場合は、ページの読み込みイベントで実行されるすべてのアクションを VEC で移動できます。 各アクションにカーソルを合わせて、[!UICONTROL Move to Page Load Event] ボタンをクリックします。 その後、次の手順で、トラフィック配分方法に対応する自動ターゲットを選択できます。

## サポートされる統合

| 統合 | 対応? |
| --- | --- |
| [Analytics for Target（A4T）](/help/main/c-integrating-target-with-mac/a4t/a4t.md) | ○ |
| [Experience Cloud Audiences](/help/main/c-integrating-target-with-mac/mmp.md) | ○ |
| [顧客属性](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/customer-attributes.html?lang=ja){target=_blank} | ○ |
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

[!UICONTROL Page Delivery]設定を使用すると、Target アクティビティがオーディエンスに対して適格で実行されるタイミングを決定するルールを設定できます。

VECの3部構成のガイド付きアクティビティ作成ワークフロー内から[!UICONTROL Page Delivery] オプションにアクセスするには、**[!UICONTROL Experiences]** ステップで、**[!UICONTROL Configure]** （歯車アイコン） > **[!UICONTROL Page Delivery]**&#x200B;をクリックします。

![ページ配信オプションダイアログボックス](/help/main/c-experiences/assets/page-delivery.png)

例えば、上記の[!UICONTROL Page Delivery]設定で定義されているように、訪問者が`https://www.adobe.com/jp/products`を含む任意のURLにアクセスしたときに`https://www.adobe.com` *または*&#x200B;に直接アクセスしたときに、Target アクティビティが修飾され、実行されます。 これは、ページとのすべてのやり取りでページを再読み込みする複数ページアプリケーションに対して完全に機能します。at.js が、ユーザーが移動する URL に対して適合するアクティビティを取得します。

ただし、SPAの動作は異なるため、SPA VEC アクティビティで定義されているすべてのアクションをビューに適用できるように、[!UICONTROL Page Delivery]設定を設定する必要があります。

### 使用例

以下の使用例を検討します。

![SPA VEC 変更パネル](/help/main/c-experiences/assets/page-delivery-example.png)

以下の変更が加えられました。

* URL [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/)の下にあるホームビューの背景色を変更しました。
* URL [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products)の下にある製品ビューのボタンの色を変更しました。

上記の例を念頭に置いて、at.js 2.*x*&#x200B;のSPAに[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/)のみを含めるように[!UICONTROL Page Delivery]設定を設定するとどうなりますか？

![ページ配信ダイアログボックス](/help/main/c-experiences/assets/spa-page-delivery.png)

次の図は、at.js 2.*x*&#x200B;のTarget Flow - Page Load リクエストを示しています。

![Target フロー - at.js 2.0 ページ読み込みリクエスト](/help/main/c-experiences/assets/page-load-request.png)

**ユーザージャーニー #1**

* ユーザーは直接[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/)に移動します。
* at.js 2.*x*&#x200B;は、次のURLに対してアクティビティを実行する必要があるかどうかをEdgeに問い合わせます：[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/)。
* 手順 6 で、Target Edge は、ブラウザーでキャッシュできるように、ホームおよび製品ビューに対するアクションを返します。

**結果**：ユーザーのホームビューに緑の背景色が表示されます。 ユーザーが[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products)に移動すると、アクションが製品ビューの下のブラウザーにキャッシュされるため、ボタンの青い背景色が表示されます。

注意：[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products)に移動するユーザーは、ページ読み込みをトリガーしませんでした。

**ユーザージャーニー #2**

* ユーザーは直接[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products)に移動します。
* at.js 2.*x*&#x200B;は、次のURLに対してアクティビティを実行する必要があるかどうかをEdgeに問い合わせます：[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products)。
* [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products)に適格なアクティビティはありません。
* アクティビティが修飾されていないため、at.js 2.*x*&#x200B;に対してキャッシュするアクションとビューがありません。からトリガーします。

**結果**：製品ビューに`triggerView()`を定義し、SPA VECを介して製品ビューに対してアクションを実行した場合でも、ページ配信設定に[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=ja#/products)を含むルールを作成していないため、期待されるアクションは表示されません。

### ベストプラクティス

ユーザーは SPA の任意の URL に到達したり他のページに移動したりする可能性があるので、管理するユーザージャーニーは非常に難しくなる可能性があります。 このため、SPA 全体を含むことができるように、ベース URL を含むページ配信ルールを指定することが最適です。 これにより、A/B テストやエクスペリエンスターゲティング（XT）アクティビティを表示するページに移動するために、ユーザーが辿る可能性のあるさまざまなジャーニーやパスを考慮する必要がなくなります。

例えば、上記で直面した問題を解決するために、以下のようにページ配信設定にベース URL を指定できます。

![ページ配信ダイアログボックス](/help/main/c-experiences/assets/conclusion.png)

これにより、訪問者が SPA のどこに到達し、ホームまたはページビューのどちらに移動しても、適用されたアクションが表示されます。

これで、SPA VECのビューにアクションを追加するたびに、次のポップアップメッセージが表示され、[!UICONTROL Page Delivery] ルールについて考えるように促されます。

![ページ配信設定メッセージ](/help/main/c-experiences/assets/pop-up-message.png)

このメッセージは、作成する新しい各アクティビティ用のビューに最初のアクションを追加すると表示されます。 このメッセージは、組織内の全員がこれらの[!UICONTROL Page Delivery] ルールを正しく適用する方法を確実に学習するのに役立ちます。

## トレーニングビデオ：Adobe Target での SPA VEC の使用

>[!VIDEO](https://video.tv.adobe.com/v/26249)

詳しくは、[Adobe Target でのシングルページアプリケーション Visual Experience Composer（SPA VEC）の使用](https://helpx.adobe.com/jp/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html)を参照してください。

