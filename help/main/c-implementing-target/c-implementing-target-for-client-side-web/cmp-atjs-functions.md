---
keywords: at.js;関数;JavaScript ライブラリ
description: Adobe Targetの at.js JavaScript ライブラリの 1.x および 2.x バージョンで使用できる関数のリストを表示します。
title: at.js で使用できる関数
feature: at.js
role: Developer
exl-id: a386e478-16f4-4bf6-9771-6b1e75f2e362
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 94%

---

# at.js 関数

Adobe Target の at.js JavaScript ライブラリで使用できる関数のリストです。詳細および例については、「関数」列のリンクをクリックしてください。

| 関数 | 詳細 |
| --- | --- | 
| [adobe.target.getOffer(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) | この関数は、Target オファーを取得するリクエストを実行します。`adobe.target.applyOffer()` と併用して、応答を処理するか、独自の成功処理を使用します。 |
| [adobe.target.getOffers(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)<br>(at.js 2.x) | この関数を使用すると、複数の mbox を渡すことで複数のオファーを取得できます。さらに、アクティブなアクティビティのすべてのビュー向けに複数のオファーを取得できます。<br>**注：**&#x200B;この関数は at.js. 2.x で導入されました。この関数は at.js バージョン 1.x では使用できません。*x*. |
| [adobe.target.applyOffer(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) | この関数は、応答内容を適用するために使用します。 |
| [adobe.target.applyOffers(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffers-atjs-2.md)<br>(at.js 2.x) | この関数を使用すると、adobe.target.getOffers(). で取得した複数のオファーを適用できます。<br>**注：**&#x200B;この関数は at.js. 2.x で導入されました。この関数は at.js バージョン 1.x では使用できません。*x*。 |
| [adobe.target.triggerView (viewName, options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md)<br>(at.js 2.x) | この関数は、新しいページが読み込まれるときや、ページ上のコンポーネントが再レンダリングされるときに呼び出すことができます。<br> Visual Experience Composer（VEC）を使用して A/Bテストおよびエクスペリエンスターゲット設定（XT）のアクティビティを作成するには、この関数をシングルページアプリケーション（SPA）に実装する必要があります。 |
| [adobe.target.trackEvent(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) | この関数は、クリックやコンバージョンなどのユーザーアクションを報告するリクエストを実行します。応答でアクティビティを配信することはありません。 |
| [mboxCreate(mbox,params)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)<br>(at.js 1.x) | リクエストを実行し、mboxDefault クラス名を持つ最も近い DIV にオファーを適用します。<br>**注：**&#x200B;この関数は at.js バージョン 1.*x* のみで使用できます。この関数は at.js 2.x のリリースで廃止されました。at.js 2.x で使用する場合、この関数はデフォルトコンテンツを返します。 |
| [mboxDefine(options) および mboxUpdate(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/mboxdefine-mboxupdate-atjs-1x.md)<br>(at.js 1.x) | mbox を定義および更新します。<br>**注：**&#x200B;この関数は at.js バージョン 1.*x* のみで使用できます。この関数は at.js 2.x のリリースで廃止されました。at.js 2.x で使用する場合、この関数はデフォルトコンテンツを返します。 |
| [targetGlobalSettings(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Target Standard／Premium UI や REST API を使用して設定を構成する代わりに、`targetGlobalSettings()` を使用して at.js ライブラリで設定を上書きすることができます。<ul><li>データプロバイダー：この設定では、Demandbase、BlueKai、カスタムサービスなどのサードパーティのデータプロバイダーからデータを収集し、そのデータをグローバル mbox リクエストで mbox パラメーターとして Target に渡すことができます。</li></ul> |
| [targetPageParams(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) | このメソッドにより、リクエストコードの外部からグローバル mbox にパラメーターを付加できます。 |
| [targetPageParamsAll(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) | このメソッドにより、リクエストコードの外部からすべての mbox にパラメーターを付加できます。 |
| [registerExtension(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/registerextension-atjs-1x.md)<br>(at.js 1.x) | 特定の拡張を登録するための標準的な方法を提供します。<br>**注：**&#x200B;この関数は at.js バージョン 1.*x* のみで使用できます。この関数は at.js 2.x のリリースで廃止されました。at.js 2.x で使用する場合、この関数はデフォルトコンテンツを返します。 |
| [at.js カスタムイベント](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | at.js カスタムイベントを使用すると、mbox リクエストまたはオファーが失敗または成功した場合に通知できます。 |
| [adobe.target.sendNotifications(options)](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)<br>（at.js 2.1.0） | この関数は、`adobe.target.applyOffer()` や `adobe.target.applyOffers()` を使用せずにエクスペリエンスがレンダリングされる場合、Target Edge に通知を送信します。<br>**注意**：この関数は、at.js 2.1.0 で導入され、2.1.0 以上の任意のバージョンで使用できます。 |
