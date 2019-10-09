---
description: Adobe targetのサーバー側配信API、Node.js SDKおよびTarget Recommendations APIに関する情報です。
keywords: サーバー側；サーバー側；api;sdk;node.js;nodejs;node js;recommendations api;api:apis
seo-description: Adobe targetのサーバー側配信API、Node.js SDKおよびTarget Recommendations APIに関する情報です。
seo-title: Adobe targetのサーバー側配信API、Node.js SDKおよびTarget Recommendations APIに関する情報です。
solution: Target
title: Target のサーバー側実装
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 9fa095b910b85f244b626c34cacdf9f4a13a6929

---


# サーバー側：Target の実装{#server-side-implement-target}

サーバー [!DNL Adobe Target] 側配信API、Node.js SDKおよびAPIに関する情報で [!DNL Target Recommendations] す。

以下の処理は、[!DNL Target] のサーバー側実装で発生します。

1. クライアントデバイスがサーバーを通じてエクスペリエンスのリクエストをおこないます。
1. サーバーは、そのリクエストを [!DNL Target] に送信します。
1. [!DNL Target] は、サーバーに応答を送り返します。
1. サーバーは、どのエクスペリエンスをクライアントデバイスに配信してレンダリングするかを決定します。

エクスペリエンスをブラウザーに表示する必要はありません。 エクスペリエンスは、電子メールやキオスク、音声アシスタント、または他のビジュアルでないエクスペリエンスやブラウザーベースでないデバイスを通じて表示できます。 サーバーはクライアントと [!DNL Target] の間に位置するので、より優れたコントロールおよびセキュリティが必要であったり、サーバーで実行したい複雑なバックエンド処理がある場合、このタイプの実装も理想的です。

以下の節では、様々なAPIとNodeJS SDKについて詳しく説明します。

## Server Sice Delivery API

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Delivery APIを使用し [!DNL Target] て、次のことができます。

* SPAやモバイルチャネルを含むWeb上で、また、接続されたTV、キオスク、店頭のデジタル画面など、ブラウザーベース以外のIoTデバイスを使用してエクスペリエンスを提供します。
* HTTP/s呼び出しを行える任意のサーバー側プラットフォームまたはアプリケーションからエクスペリエンスを提供します。
* 訪問者がビジネスに関与するために使用したチャネルやデバイスに関係なく、一貫したパーソナライズされたエクスペリエンスを訪問者に提供します。
* サーバー上のセッション内の訪問者のエクスペリエンスをキャッシュして、複数のAPI呼び出しを回避できるようにします。これにより、パフォーマンスが向上します。
* 製品(AAM) [!DNL Adobe Experience Cloud] や、サーバー側 [!DNL Adobe Analytics]の製品と [!DNL Adobe Audience Manager] シームレスに [!DNL Experience Cloud ID Service] 統合できます。

## Node.js SDK

リンク： [Node.js SDK](https://github.com/adobe/target-nodejs-sdk)

Node.js SDKは、Cookie、セッションの管理、製品（、など）との統合に伴う複雑さを排除した高度なソ [!DNL Experience Cloud] フトウェア開発キ [!DNL Analytics]ット [!DNL Experience Cloud Visitor ID Service]です [!DNL Audience Manager]。 背後で、Node.js SDKは `/rest/v1/delivery` APIを使用します。 Node.js SDKでサポートされる主な機能を以下に示します。

* **** プリフェッチと、キャッシュを使用したパフォーマンスの最適化を可能にする通知のサポート：Node.js SDKを使用して、エクスペリエンスを取得し、Node.jsサーバー上でローカルにキャッシュできます。これにより、アプリケーションのパフォーマンスを最小限に抑え、サーバー呼び出 [!DNL Target] しを最適化できます。
* **** VECで作成されたアクティビティの取得機能：サーバー側でVECが作成したアクティビティを取得します。 VECで作成されたアクティビティを含む応答にはセレクターが含まれ、このセレクターは、パーソナライズする必要があるページの一部のみを事前に非表示にするために使用できます。 これは、ページの [First Contentful Paint指標の最適化に役立ちます](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)。これは、 [Google pageRankシステムで高スコアを達成するためのビジネスにとって重要なKPIです](https://en.wikipedia.org/wiki/PageRank) 。

## Target Recommendations API

Link: [Target Recommendations APIs](https://developers.adobetarget.com/api/recommendations)

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
