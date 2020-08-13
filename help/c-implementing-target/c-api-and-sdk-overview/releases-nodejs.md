---
keywords: at.js;sdk;node.js;release;updates;sdks;server side;serverside;server-side;nodejs
description: Adobe Targetのサーバー側APIに関するリリースノートです。
title: Adobe TargetのNode.js SDKに関するリリースノートです。
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 0%

---


# リリースノート —ターゲットNode.js SDK

[Adobe TargetのNode.js SDK](https://github.com/adobe/target-nodejs-sdk).

ターゲットNode.js SDKを使用すると、サー [!DNL Target] バー側をデプロイできます。

このNode.js SDKは、、などの他の [!DNL Target] ソリューションとの統合を容易にする [!DNL Adobe Experience Cloud] もの [!DNL Adobe Experience Cloud Identity Service]です [!DNL Adobe Analytics][!DNL Adobe Audience Manager]。

Node.js SDKは、ベストプラクティスを導入し、アドビの配信APIを使用して統合する際の複雑さを排除して、エンジニアリングチームがビジネスロジックに焦点を当てられるようにします。 [!DNL Target]

ターゲットNode.js SDKの詳細については、Adobeテクニカルブログ — [Open Sourcing the NewAdobe Target Node.js SDK](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc)。

## バージョン1.0.0（2019年10月9日）

以下の節では、ターゲットNode.js SDKのバージョン1.0.0について詳しく説明します。

### Admin Console ヘルプに

* ターゲット表示配信v1 APIのサポート(ページ読み込みと表示のプリフェッチを含む)。
* Visual Experience Composer(VEC)でオーサリングされたすべてのタイプのオファーの配信の完全なサポート。
* プリフェッチされたコンテンツのキャッシュによるパフォーマンス最適化のためのプリフェッチおよび通知のサポート。
* サーバー側とクライアント側の両方にデプロイする場合を介し [!DNL Target] たハイブリッド `serverState`[!DNL Target] 統合でのパフォーマンスの最適化をサポートします。

   サーバー側で取得したエクスペリエンス `serverState` を含むという設定が導入され、at.js v2.2以降では、エクスペリエンスを取得するための追加のサーバー呼び出しが行われなくなります。 このアプローチは、ページ読み込みのパフォーマンスを最適化します。

* GitHubをソースとして [ターゲットNode.js SDKとして開きます](https://github.com/adobe/target-nodejs-sdk)。
* getOffers()を介してプリフェッチされたコンテンツ [に対して、表示/クリック通知を送信する新しいsendNotifications() APIメソッド](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientsendnotifications) を追加しました [!DNL Target][](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers)。
* 表示配信APIリクエストの作成がシンプルになりました。内部フィールドのオートコンプリート機能がデフォルト(例： `request.id`、 `request.context`など)で使用されます。
* SDK APIメソッド引数の検証。
* README、サンプル、および単体テストを更新。
* GitHubアクションを使用して設定された新しいCIフロー。
* CoC、貢献度のガイドライン、PR、および雑誌号のテンプレートを追加しました。

### Google+ ページの 

* プロジェクトの名前がに変更され `target-nodejs-sdk`ました。
* メジャーリファクタリング。ターゲットBatchMbox v2 APIをターゲット表示配信v1 APIに置き換えます。
* [create() APIメソッドの引数が変更され](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientcreate) 、重複するネストが削除されました(古いメソッド宣言を参照し [てください](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate))。
* [getOffers() APIメソッドの引数が変更されました](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) (古いメソッド宣言を参照し [てください](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers))。
* この `getTargetCookieName()` APIメソッドは、アクセサーに置き換えられ `TargetCookieName` ました。 TargetClientユーティリティ [アクセサを参照してください](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)。
* この `getTargetLocationHintCookieName()` APIメソッドは、アクセサーに置き換えられ `TargetLocationHintCookieName` ました。  TargetClientユーティリティ [アクセサを参照してください](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)。

### 削除済み

* ターゲットBatchMbox v2 APIのサポート。
* getOffer() APIメソッド [は削除されました](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) 。代わりに、 [getOffers() APIメソッドを使用し](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) ます。

