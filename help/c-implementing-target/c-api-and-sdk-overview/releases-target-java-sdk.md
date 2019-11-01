---
description: Adobe targetのJava SDKに関するリリースノート
keywords: at.js;sdk;release;updates;sdks;server side;serverside;server-side;java;java sdk
seo-description: Adobe targetのJava SDKに関するリリースノートです。
seo-title: Adobe targetのJava SDKに関するリリースノートです。
solution: Target
title: リリースノート — Target Java SDK
topic: Standard
translation-type: tm+mt
source-git-commit: 5f05f218e5fdea26827b86cb7fbea05ac6349014

---


# リリースノート — Target Java SDK

[Target Java SDKに関するリリースノートです](https://github.com/adobe/target-java-sdk)。

Java SDKを使 [!DNL Target] 用すると、サーバー側 [!DNL Target] をデプロイできます。 このJava SDKを使用すると、、、などの他のソ [!DNL Target] リューシ [!DNL Adobe Experience Cloud] ョンとの統合を簡単に [!DNL Adobe Experience Cloud Identity Service]行うこ [!DNL Adobe Analytics]とができま [!DNL Adobe Audience Manager]す。

Java SDKは、アドビの配信APIを使用して統合する際に、ベストプラクティスを導入し、複雑 [!DNL Target] さを排除して、エンジニアリングチームがビジネスロジックに焦点を当てられるようにします。

新しいTarget Java SDKを使用したサーバ側の最適化に関するアドビ [のテクニカルブログ（英語）で詳しく説明します](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)。

## バージョン1.0.0（2019年10月31日）

以下の節で、Target Java SDKのバージョン1.0.0について詳しく説明します。

### Admin Console ヘルプに

* [Target View Delivery v1 APIのサポート(ページ読み込み](https://developers.adobetarget.com/api/delivery-api/) 、表示プリフェッチなど)。
   * Visual Experience Composer(VEC)で作成されたすべてのタイプのオファーの配信を完全にサポートします。
* プリフェッチと通知のサポートを追加しました。これにより、プリフェッチされたコンテンツをキャッシュしてパフォーマンスを最適化できます。
* サーバー側とクライアント側の両方にデプ [!DNL Target] ロイする場合に、 `serverState`を介し [!DNL Target] たハイブリッド統合でパフォーマンスを最適化するためのサポートを追加しました。
   * サーバー側で取得したエクスペリエンスを含むという設定が導入され、at.js v2.2以降では、エクスペリエンスを取得するための追加のサーバー呼び出しが行われなくなります。 `serverState` このアプローチは、ページ読み込みのパフォーマンスを最適化します。
* GitHubをソースとして [Target Java SDKとして開きます](https://github.com/adobe/target-java-sdk)。
* SDK APIメソッド引数の検証。
* README、サンプル、ユニットテストを追加しました。
* CoC、貢献度のガイドライン、PRおよび雑誌号のテンプレートを追加しました。

