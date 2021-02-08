---
keywords: サーバー側：サーバー側；api;sdk;node.js;nodejs;node js;recommendations api;api:api
description: Adobe Targetのサーバー側配信API、SDK、ターゲットRecommendationsAPIについて説明します。
title: ターゲットサーバー側配信APIおよびSDKについて学習できる情報
feature: Implement Server-side
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 20%

---


# サーバー側：Target の実装

[!DNL Adobe Target]サーバー側配信API、SDK、および[!DNL Target Recommendations] APIに関する情報です。

以下の処理は、[!DNL Target] のサーバー側実装で発生します。

1. クライアントデバイスがサーバーを通じてエクスペリエンスのリクエストをおこないます。
1. サーバーは、そのリクエストを [!DNL Target] に送信します。
1. [!DNL Target] は、サーバーに応答を送り返します。
1. サーバーは、どのエクスペリエンスをクライアントデバイスに配信してレンダリングするかを決定します。

エクスペリエンスをブラウザーで表示する必要はありません。 エクスペリエンスは、電子メールやキオスク、音声アシスタント、視覚に訴えない他のデバイス、またはブラウザーベースでないデバイスを通して表示できます。 サーバーはクライアントと [!DNL Target] の間に位置するので、より優れたコントロールおよびセキュリティが必要であったり、サーバーで実行したい複雑なバックエンド処理がある場合、このタイプの実装も理想的です。

>[!NOTE]
>
>初回訪問者は、クライアント側でのみ初期化できます。 初回訪問者&#x200B;*は、サーバ側で初期化できません。*

以下の節では、様々なAPIとNodeJS SDKについて詳しく説明します。

## Server Side Delivery API

リンク：[サーバ側配信API](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

[!DNL Target]配信APIを使用すると、次のことができます。

* SPAやモバイルチャネル、および接続されたTV、キオスク、店頭のデジタル画面など、ブラウザーベース以外のIoTデバイスを含むWeb上でエクスペリエンスを配信できます。
* HTTP/s呼び出しを行うことのできる任意のサーバー側プラットフォームまたはアプリケーションからエクスペリエンスを提供します。
* 訪問者がどのチャネルやデバイスを使用してビジネスに関与したかに関係なく、一貫したパーソナライズされたエクスペリエンスを訪問者に提供します。
* サーバー上のセッション内の訪問者に対するエクスペリエンスをキャッシュすることで、複数のAPI呼び出しを回避でき、パフォーマンスが向上します。
* [!DNL Adobe Analytics]、[!DNL Adobe Audience Manager](AAM)、[!DNL Experience Cloud ID Service]などの[!DNL Adobe Experience Cloud]製品と、サーバ側からシームレスに統合できます。

## サーバー側SDK

リンク：[Adobe TargetSDK](https://adobetarget-sdks.gitbook.io/docs/)

[!DNL Adobe Target]サーバー側SDKドキュメントポータルは、お使いのサーバーに対して好みの言語で[!DNL Target]を実装するのに役立ちます。

## Target Recommendations API

リンク：[ターゲットRecommendationsAPI](https://developers.adobetarget.com/api/recommendations)と[Adobe RecommendationsAPIの概要](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html)。

RecommendationsAPIを使用すると、[!DNL Target] recommendationsサーバーとプログラム的にやり取りできます。 これらのAPIは、様々なアプリケーションスタックと統合して、[!DNL Target]ユーザーインターフェイスを通じて通常行う機能を実行できます。
