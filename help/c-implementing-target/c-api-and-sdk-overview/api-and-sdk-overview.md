---
keywords: server side;server-side;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
description: Adobe Targetのサーバ側配信API、SDK、ターゲットRecommendationsAPIに関する情報です。
title: Adobe Targetのサーバ側配信API、Node.js SDK、ターゲットRecommendationsAPIに関する情報です。
feature: server-side
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 42ecb1d2eee4b12e4eff3a646e6d596286e01e00
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 20%

---


# サーバー側：Target の実装{#server-side-implement-target}

サーバー側 [!DNL Adobe Target] の配信API、SDK、 [!DNL Target Recommendations] APIに関する情報です。

以下の処理は、[!DNL Target] のサーバー側実装で発生します。

1. クライアントデバイスがサーバーを通じてエクスペリエンスのリクエストをおこないます。
1. サーバーは、そのリクエストを [!DNL Target] に送信します。
1. [!DNL Target] は、サーバーに応答を送り返します。
1. サーバーは、どのエクスペリエンスをクライアントデバイスに配信してレンダリングするかを決定します。

エクスペリエンスをブラウザーで表示する必要はありません。 エクスペリエンスは、電子メールやキオスク、音声アシスタント、視覚に訴えない他のデバイス、またはブラウザーベースでないデバイスを通して表示できます。 サーバーはクライアントと [!DNL Target] の間に位置するので、より優れたコントロールおよびセキュリティが必要であったり、サーバーで実行したい複雑なバックエンド処理がある場合、このタイプの実装も理想的です。

>[!NOTE]
>
>初回訪問者は、クライアント側でのみ初期化できます。 サーバー側で初回訪問者 *を初期化できません* 。

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

## サーバー側SDK

リンク： [Adobe TargetSDK](https://adobetarget-sdks.gitbook.io/docs/)

サーバー側SDKドキュメ [!DNL Adobe Target] ントポータルは、選択した言語でサーバー [!DNL Target] に実装する際に役立ちます。

## Target Recommendations API

リンク： [ターゲットRecommendationsAPI](https://developers.adobetarget.com/api/recommendations) 、 [Adobe RecommendationsAPIの概要](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html)。

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
