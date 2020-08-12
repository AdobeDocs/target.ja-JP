---
keywords: at.js;api;release;updates;apis;sdks;server side;serverside;server-side;api;delivery api
description: Adobe Targetのサーバー側APIに関するリリースノートです。
title: Adobe Targetのサーバー側APIに関するリリースノートです。
feature: null
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# リリースノート —ターゲットサーバー側API

[Adobe Targetのサーバー側APIに関するリリースノート](https://developers.adobetarget.com/api/delivery-api/)。

## V1/配信（2019年10月9日）

まったく新しい配信APIエンドポイントがリリースされました。

* New [documentation](https://developers.adobetarget.com/api/delivery-api/) is available.
* 1つのエンドポイントで、1つ以上のmboxのエクスペリエンスを取得できます。
* APIを使用してVECで作成されたアクティビティを取得します。

   VECで作成されたアクティビティを含む応答にはセレクターがあり、このセレクターを使用して、ページの中でパーソナライズする必要のある部分のみを事前に非表示にできます。 これは、ページの [最初のコンテンツペイント指標を最適化するのに役立ちます。これは、](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)Google PageRank [](https://en.wikipedia.org/wiki/PageRank) システムで高スコアを達成するためのビジネスにとって重要なKPIです。

* シン [グルページアプリ(SPA)および](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) モバイルアプリケーションで使用される表示と呼ばれる、まったく新しいオブジェクトのサポート [](/help/c-target-mobile-app/target-mobile-app.md)。
* 表示およびmboxのプリフェッチをサポートし、キャッシュを使用したパフォーマンスを最適化。
* 事前に取得された表示およびmboxに関する通知の送信をサポートします。

>[!IMPORTANT]
>
>従来の [/v1/mboxおよび/v2/batchmbox APIドキュメント](https://developers.adobetarget.com/api/legacy-api/index.html) は、引き続きアクセスできます。 ただし、新しい機能は新しい配信APIで開発され、レガシーAPIにバックポートされることはありません。
