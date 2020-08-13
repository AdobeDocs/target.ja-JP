---
keywords: at.js;sdk;release;updates;sdks;server side;serverside;server-side;java;java sdk
description: Adobe TargetのJava SDKに関するリリースノートです。
title: Adobe TargetのJava SDKに関するリリースノートです。
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---


# リリースノート —ターゲットJava SDK

[ターゲットJava SDK](https://github.com/adobe/target-java-sdk)。

Java [!DNL Target] SDKを使用すると、サー [!DNL Target] バー側をデプロイできます。 このJava SDKを使用すると、、、など [!DNL Target] の他の [!DNL Adobe Experience Cloud] ソリューションとの統合を簡単に行え [!DNL Adobe Experience Cloud Identity Service][!DNL Adobe Analytics][!DNL Adobe Audience Manager]ます。

Java SDKは、ベストプラクティスを導入し、アドビの配信APIを [!DNL Target] 使用して統合する際の複雑さを排除して、エンジニアリングチームがビジネスロジックに集中できるようにします。

新しいターゲットのJava SDKを使用した [サーバ側のターゲットに関するAdobeテクニカルブログ](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)。

## バージョン1.1.0（2019年12月16日）

次の節では、ターゲットJava SDKのバージョン1.1.0について詳しく説明します。

### Admin Console ヘルプに

* @hisham-hassanが行ったオープンソースの貢献により、プロキシ設定のサポートが追加されました。

## バージョン1.0.1（2019年11月11日）

次の節では、ターゲットJava SDKのバージョン1.0.1について詳しく説明します。

### 固定

* 訪問者API cookieがない場合でも、ターゲットリクエストで補足的なデータIDを送信します。

## バージョン1.0.0（2019年10月31日）

次の節で、ターゲットJava SDKのバージョン1.0.0について詳しく説明します。

### Admin Console ヘルプに

* [ターゲット表示配信v1 APIのサポート(ページ読み込みと表示プリフェッチを含む)。](https://developers.adobetarget.com/api/delivery-api/)
   * Visual Experience Composer(VEC)でオーサリングされたすべてのタイプのオファーの配信の完全なサポート。
* プリフェッチのサポートと、プリフェッチされたコンテンツをキャッシュしてパフォーマンスを最適化できる通知機能を追加しました。
* サーバー側とクライアント側の両方にデプロイする場合に、を介し [!DNL Target] たハイブリッド `serverState`[!DNL Target] 統合でパフォーマンスを最適化するためのサポートを追加しました。
   * サーバー側で取得したエクスペリエンス `serverState` を含むという設定が導入され、at.js v2.2以降では、エクスペリエンスを取得するための追加のサーバー呼び出しが行われなくなります。 このアプローチは、ページ読み込みのパフォーマンスを最適化します。
* GitHubをソースとして [ターゲットJava SDKとして開きます](https://github.com/adobe/target-java-sdk)。
* SDK APIメソッド引数の検証。
* README、サンプル、および単体テストを追加。
* CoC、貢献度のガイドライン、PR、および雑誌号のテンプレートを追加しました。

