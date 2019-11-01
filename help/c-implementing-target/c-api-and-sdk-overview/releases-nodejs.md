---
description: Adobe targetのNode.js SDKに関するリリースノート
keywords: at.js;sdk;node.js;release;updates;sdks;server side;serverside;server-side;nodejs
seo-description: Adobe targetのサーバー側APIに関するリリースノートです。
seo-title: Adobe targetのNode.js SDKに関するリリースノートです。
solution: Target
title: リリースノート — Target Node.js SDK
topic: Standard
translation-type: tm+mt
source-git-commit: 5f05f218e5fdea26827b86cb7fbea05ac6349014

---


# リリースノート — Target Node.js SDK

[Adobe targetのNode.js SDKに関するリリースノートです](https://github.com/adobe/target-nodejs-sdk)。

Target Node.js SDKを使用すると、サーバー側でデプ [!DNL Target] ロイできます。

このNode.js SDKを使用すると、、、などの他のソ [!DNL Target] リューシ [!DNL Adobe Experience Cloud] ョンとの統合を簡 [!DNL Adobe Experience Cloud Identity Service]単に行 [!DNL Adobe Analytics]えま [!DNL Adobe Audience Manager]す。

Node.js SDKは、アドビの配信APIを使用して統合する際に、ベストプラクティスを導入し、複雑さを排除し [!DNL Target] て、エンジニアリングチームがビジネスロジックに焦点を当てられるようにします。

Adobe Tech BlogのOpen Sourcing the New Adobe Target Node.js SDKで、Target Node.js SDKの詳細をご覧くだ [さい](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc)。

## バージョン1.0.0（2019年10月9日）

以下の節では、Target Node.js SDKのバージョン1.0.0について詳しく説明します。

### Admin Console ヘルプに

* Target View Delivery v1 APIのサポート（ページ読み込みと表示プリフェッチを含む）。
* Visual Experience Composer(VEC)で作成されたすべてのタイプのオファーの配信を完全にサポートします。
* プリフェッチされたコンテンツをキャッシュすることによるパフォーマンス最適化のためのプリフェッチと通知のサポートを追加しました。
* サーバー側とクライアント側の両方に展開さ [!DNL Target] れる場合を介し `serverState` たハイブ [!DNL Target] リッド統合でのパフォーマンスの最適化をサポートしました。

   サーバー側で取得したエクスペリエンスを含むという設定が導入され、at.js v2.2以降では、エクスペリエンスを取得するための追加のサーバー呼び出しが行われなくなります。 `serverState` このアプローチは、ページ読み込みのパフォーマンスを最適化します。

* GitHubをソースとして [Target Node.js SDKとして開きます](https://github.com/adobe/target-nodejs-sdk)。
* getOffers()を介し [てプリフェッチされたコンテンツに対して表示](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientsendnotifications) /クリック通知を送 [!DNL Target] 信する新しいsendNotifications() APIメ [ソッドです](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers)。
* ビュー配信APIリクエストの作成がシンプルになり、内部フィールドの自動完了がデフォルト( `request.id`例えば、 `request.context`など)で行われます。
* SDK APIメソッド引数の検証。
* README、サンプル、および単体テストを更新しました。
* GitHubアクションを使用して新しいCIフローが設定されました。
* CoC、貢献度のガイドライン、PRおよび雑誌号のテンプレートを追加しました。

### Google+ ページの 

* プロジェクトの名前がに変更されま `target-nodejs-sdk`した。
* メジャーリファクタリング。Target batchMbox v2 APIをTarget View Delivery v1 APIに置き換えます。
* [create() APIメソッドの引数が変更され](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientcreate) 、重複するネストが削除されました(古いメソッド宣言を参照し [てください](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate))。
* [getOffers() APIメソッドの引数が変更されました](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) (古いメソッド宣言を参照し [てください](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers))。
* APIメソッド `getTargetCookieName()` は、アクセサーに置き換えられ `TargetCookieName` ました。 TargetClientユーテ [ィリティアクセサを参照](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)。
* APIメソッド `getTargetLocationHintCookieName()` は、アクセサーに置き換えられ `TargetLocationHintCookieName` ました。  TargetClientユーテ [ィリティアクセサを参照](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)。

### 削除済み

* Target batchMbox v2 APIのサポート。
* getOffer() APIメ [ソッドが削除されました](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) 。代わりに、 [getOffers() APIメソッドを使用してください](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) 。

