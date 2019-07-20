---
description: at.js で使用できる関数のリストです。
keywords: adobe.target.notification;要素;セレクター;通知;拡張子
seo-description: Adobe Target の at.js JavaScript ライブラリで使用できる関数のリストです。
seo-title: Adobe Target at.js 関数
solution: 'Target '
subtopic: 導入
title: at.js 関数
topic: Standard
uuid: ec5f27a7-b22a-48c9-968c-9eb02830a2a6
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# at.js 関数{#at-js-functions}

Adobe Target の at.js JavaScript ライブラリで使用できる関数のリストです。詳細および例については、「関数」列のリンクをクリックしてください。

| 関数 | 詳細 |
| --- | --- | 
| [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) | この関数は、Target オファーを取得するリクエストを実行します。`adobe.target.applyOffer()` と併用して、応答を処理するか、独自の成功処理を使用します。 |
| [adobe.target.getOffers(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)<br>(at.js 2.x) | この関数を使用すると、複数の mbox を渡すことで複数のオファーを取得できます。さらに、アクティブなアクティビティのすべてのビュー向けに複数のオファーを取得できます。<br>**注：**&#x200B;この関数は at.js. 2.x で導入されました。この関数は at.js バージョン 1 では使用できません。*x*. |
| [adobe.target.applyOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) | この関数は、応答内容を適用するために使用します。 |
| [adobe.target.applyOffers(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffers-atjs-2.md)<br>(at.js 2.x) | この関数を使用すると、adobe.target.getOffers(). で取得した複数のオファーを適用できます。<br>**注：**&#x200B;この関数は at.js. 2.x で導入されました。この関数は at.js バージョン 1 では使用できません。*x*. |
| [adobe.target.triggerView (viewName, options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md)<br>(at.js 2.x) | この関数は、新しいページが読み込まれるときや、ページ上のコンポーネントが再レンダリングされるときに呼び出すことができます。<br> Visual Experience Composer（VEC）を使用して A/Bテストおよびエクスペリエンスターゲット設定（XT）のアクティビティを作成するには、この関数をシングルページアプリケーション（SPA）に実装する必要があります。 |
| [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) | この関数は、クリックやコンバージョンなどのユーザーアクションを報告するリクエストを実行します。応答でアクティビティを配信することはありません。 |
| [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)<br>(at.js 1.x) | リクエストを実行し、mboxDefault クラス名を持つ最も近い DIV にオファーを適用します。<br>**注：**&#x200B;この関数は at.js バージョン 1.*x* のみで使用できます。この関数は at.js 2.x のリリースで廃止されました。at.js 2.x で使用する場合、この関数はデフォルトコンテンツを返します。 |
| [mboxDefine(options) および mboxUpdate(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxdefine-mboxupdate-atjs-1x.md)<br>(at.js 1.x) | mbox を定義および更新します。<br>**注：**&#x200B;この関数は at.js バージョン 1.*x* のみで使用できます。この関数は at.js 2.x のリリースで廃止されました。at.js 2.x で使用する場合、この関数はデフォルトコンテンツを返します。 |
| [targetGlobalSettings(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Target Standard／Premium UI や REST API を使用して設定を構成する代わりに、`targetGlobalSettings()` を使用して at.js ライブラリで設定を上書きすることができます。<ul><li>データプロバイダー：この設定では、Demandbase、BlueKai、カスタムサービスなどのサードパーティのデータプロバイダーからデータを収集し、そのデータをグローバル mbox リクエストで mbox パラメーターとして Target に渡すことができます。</li></ul> |
| [targetPageParams(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) | このメソッドにより、リクエストコードの外部からグローバル mbox にパラメーターを付加できます。 |
| [targetPageParamsAll(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) | このメソッドにより、リクエストコードの外部からすべての mbox にパラメーターを付加できます。 |
| [registerExtension(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/registerextension-atjs-1x.md)<br>(at.js 1.x) | 特定の拡張を登録するための標準的な方法を提供します。<br>**注：**&#x200B;この関数は at.js バージョン 1.*x* のみで使用できます。この関数は at.js 2.x のリリースで廃止されました。at.js 2.x で使用する場合、この関数はデフォルトコンテンツを返します。 |
| [at.js カスタムイベント](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | at. jsカスタムイベントを使用すると、mboxリクエストやオファーが失敗または成功した場合に通知できます。 |
| [adobe. target. sendNotifications（options）](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)<br>（at. js2.1.0） | This function sends a notification to Target edge when an experience is rendered without using `adobe.target.applyOffer()` or `adobe.target.applyOffers()`.<br>**注意**:この関数はat. js2.1.0で導入されており、2.1.0より前のバージョンで使用できます。 |

