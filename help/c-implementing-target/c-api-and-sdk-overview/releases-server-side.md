---
keywords: at.js;api;release;updates;apis;sdks;server side;serverside;server-side;api;delivery api
description: Adobe targetのサーバー側APIに関するリリースノートです。
title: Adobe targetのサーバー側APIに関するリリースノートです。
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# リリースノート — Targetサーバー側API

[Adobe targetのサーバー側APIに関するリリースノートです](https://developers.adobetarget.com/api/delivery-api/)。

## V1/配信（2019年10月9日）

まったく新しい配信APIエンドポイントがリリースされました。

* New [documentation](https://developers.adobetarget.com/api/delivery-api/) is available.
* 1つ以上のmboxのエクスペリエンスを取得するための1つのエンドポイント。
* APIを使用してVECで作成されたアクティビティを取得します。

   VECで作成されたアクティビティを含む応答にはセレクターが含まれ、このセレクターは、パーソナライズする必要があるページの一部のみを事前に非表示にするために使用できます。 これは、ページの [First Contentful Paint指標を最適化するのに役立ちます](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)。これは、 [Google pageRank](https://en.wikipedia.org/wiki/PageRank) システムで高スコアを達成するためのビジネスにとって重要なKPIです。

* シングルページアプリ(SPA)およびモバイルアプリケーションで使用されるビューと呼ば [れる新しいオブジェクトのサポ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) ートです [](/help/c-target-mobile-app/target-mobile-app.md)。
* キャッシュを使用したパフォーマンスを最適化するための、ビューおよびmboxのプリフェッチのサポート。
* 事前に取得されたビューおよびmboxに対する通知の送信をサポート。

>[!IMPORTANT]
>
>従来の/v1 [/mboxおよび/v2/batchmbox APIドキュメントには](https://developers.adobetarget.com/api/legacy-api/index.html) 、引き続きアクセスできます。 ただし、新しい機能は新しい配信APIで開発され、レガシーAPIにはバックポートされません。
