---
keywords: server side;server-side;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
description: Adobe Targetのサーバ側配信API、Node.js SDK、ターゲットRecommendationsAPIに関する情報です。
title: Adobe Targetのサーバ側配信API、Node.js SDK、ターゲットRecommendationsAPIに関する情報です。
feature: server-side
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 11%

---


# サーバー側：Target の実装{#server-side-implement-target}

サーバー側 [!DNL Adobe Target] の配信API、Node.js SDK、 [!DNL Target Recommendations] APIに関する情報です。

以下の処理は、[!DNL Target] のサーバー側実装で発生します。

1. クライアントデバイスがサーバーを通じてエクスペリエンスのリクエストをおこないます。
1. サーバーは、そのリクエストを [!DNL Target] に送信します。
1. [!DNL Target] は、サーバーに応答を送り返します。
1. サーバーは、どのエクスペリエンスをクライアントデバイスに配信してレンダリングするかを決定します。

エクスペリエンスをブラウザーで表示する必要はありません。 エクスペリエンスは、電子メールやキオスク、音声アシスタント、視覚に訴えない他のデバイス、またはブラウザーベースでないデバイスを通して表示できます。 サーバーはクライアントと [!DNL Target] の間に位置するので、より優れたコントロールおよびセキュリティが必要であったり、サーバーで実行したい複雑なバックエンド処理がある場合、このタイプの実装も理想的です。

以下の節では、様々なAPIとNodeJS SDKについて詳しく説明します。

## Server Side Delivery API

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

配信 [!DNL Target] APIを使用すると、次のことができます。

* SPAやモバイルチャネル、および接続されたTV、キオスク、店頭のデジタル画面など、ブラウザーベース以外のIoTデバイスを含むWeb上でエクスペリエンスを配信できます。
* HTTP/s呼び出しを行うことのできる任意のサーバー側プラットフォームまたはアプリケーションからエクスペリエンスを提供します。
* 訪問者がどのチャネルやデバイスを使用してビジネスに関与したかに関係なく、一貫したパーソナライズされたエクスペリエンスを訪問者に提供します。
* サーバー上のセッション内の訪問者に対するエクスペリエンスをキャッシュすることで、複数のAPI呼び出しを回避でき、パフォーマンスが向上します。
* サーバ側の [!DNL Adobe Experience Cloud] 製品( [!DNL Adobe Analytics]、 [!DNL Adobe Audience Manager][!DNL Experience Cloud ID Service] (AAM)など)とシームレスに統合できます。

## Node.js SDK

リンク： [Node.js SDK](https://github.com/adobe/target-nodejs-sdk)

Node.js SDKは、Cookie、セッションの管理、製品（、など）との統合の複雑さを排除した高度なソフトウェア開発キットで [!DNL Experience Cloud][!DNL Analytics]す [!DNL Experience Cloud Visitor ID Service][!DNL Audience Manager]。 内部では、Node.js SDKが `/rest/v1/delivery` APIを使用します。 Node.js SDKでサポートされる主な機能を以下に示します。

* **プリフェッチのサポートと、キャッシュを使用したパフォーマンスの最適化を可能にする通知：** Node.js SDKを使用すると、エクスペリエンスを取得し、Node.jsサーバー上にローカルにキャッシュできます。これは、アプリケーションのパフォーマンスを最小限に抑え、最適化するためで [!DNL Target] す。
* **VECが作成したアクティビティの取得機能：** サーバー側でVECが作成したアクティビティを取得します。 VECで作成されたアクティビティを含む応答にはセレクターがあり、このセレクターを使用して、ページの中でパーソナライズする必要のある部分のみを事前に非表示にできます。 これは、ページの [最初のコンテンツペイント指標の最適化に役立ちます](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)。これは、 [Google PageRank](https://en.wikipedia.org/wiki/PageRank) システムで高スコアを達成するためのビジネスにとって重要なKPIです。

## ターゲットJava SDK

リンク： [ターゲットJava SDK](https://github.com/adobe/target-java-sdk)

Java SDKは、Cookie、セッションの管理、およびソリューション（、、など）との統合の複雑さを排除した高度なソフトウェア開発キットで [!DNL Adobe Experience Cloud][!DNL Adobe Analytics][!DNL Experience Cloud Visitor ID Service][!DNL Adobe Audience Manager]す。 内部では、Java SDKが `/rest/v1/delivery` APIを使用します。 Java SDKでサポートされる主な機能を以下に示します。

* **プリフェッチのサポートと、キャッシュを使用したパフォーマンスの最適化を可能にする通知**:JavaSDKを使用して、エクスペリエンスを取得し、Javaサーバー上にローカルにキャッシュできます。これにより、アプリケーションのパフォーマンスを最小限に抑え、最適化す [!DNL Target] ることができます。
* **VECが作成したアクティビティの取得**:サーバー側でVECが作成したアクティビティを取得します。 VECで作成されたアクティビティを含む応答にはセレクターがあり、このセレクターを使用して、ページの中でパーソナライズする必要のある部分のみを事前に非表示にできます。 これは、ページの [最初のコンテンツペイント](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html) 指標の最適化に役立ちます。これは、 [Google PageRank](https://en.wikipedia.org/wiki/PageRank) システムで高スコアを達成するためのビジネスにとって重要なKPIです。

## Target Recommendations API

リンク： [ターゲットRecommendationsAPI](https://developers.adobetarget.com/api/recommendations) 、 [Adobe RecommendationsAPIの概要](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html)。

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
