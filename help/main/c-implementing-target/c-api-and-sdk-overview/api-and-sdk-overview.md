---
keywords: server side；サーバー側；api;sdk;node.js;nodejs;node js;recommendations api;api:api
description: Adobe [!DNL Target] サーバー側配信 API、SDK、 [!DNL Target] Recommendations API
title: 詳細はこちら [!DNL Target] サーバー側配信 API および SDK
feature: Implement Server-side
role: Developer
exl-id: cdee007f-f54d-4cf3-9575-6319da3434a5
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 21%

---

# サーバー側：Target の実装

次に関する情報： [!DNL Adobe Target] サーバー側配信 API、SDK、 [!DNL Target Recommendations] API

以下の処理は、[!DNL Target] のサーバー側実装で発生します。

1. クライアントデバイスがサーバーを通じてエクスペリエンスのリクエストをおこないます。
1. サーバーは、そのリクエストを [!DNL Target] に送信します。
1. [!DNL Target] は、サーバーに応答を送り返します。
1. サーバーは、エクスペリエンスをレンダリングするクライアントデバイスに対して、どのエクスペリエンスを配信するかを決定します。

エクスペリエンスをブラウザーに表示する必要はありません。 エクスペリエンスは、E メールやキオスク、音声アシスタント、または他の視覚的でないエクスペリエンスやブラウザーベース以外のデバイスを通じて表示できます。 サーバーはクライアントと [!DNL Target] の間に位置するので、より優れたコントロールおよびセキュリティが必要であったり、サーバーで実行したい複雑なバックエンド処理がある場合、このタイプの実装も理想的です。

>[!NOTE]
>
>初回訪問者は、クライアント側でのみ初期化できます。 初回訪問者 *できません* をサーバー側で初期化する。

以下の節では、様々な API と NodeJS SDK に関する詳細を説明します。

## Server Side Delivery API

リンク： [Server Side Delivery API](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

の使用 [!DNL Target] Delivery API では、次の操作を実行できます。

* SPAやモバイルチャネルを含む Web をまたいでエクスペリエンスを提供します。また、接続された TV、キオスク、店内のデジタル画面など、ブラウザーベース以外の IoT デバイスも提供します。
* HTTP/s 呼び出しをおこなうことのできる任意のサーバー側プラットフォームまたはアプリケーションからエクスペリエンスを提供します。
* 訪問者がビジネスに関与するために使用したチャネルやデバイスに関係なく、一貫性のあるパーソナライズされたエクスペリエンスを訪問者に提供します。
* サーバー上のセッション内で訪問者のエクスペリエンスをキャッシュして、複数の API 呼び出しを回避できるようにします。これにより、パフォーマンスが向上します。
* とシームレスに統合 [!DNL Adobe Experience Cloud] 製品： [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) および [!DNL Experience Cloud ID Service] をサーバー側から削除します。

## Server Side SDK

リンク： [Adobe Target SDK](https://developer.adobe.com/target/)

この [!DNL Adobe Target] サーバー側 SDK ドキュメントポータルは、 [!DNL Target] を選択した言語のサーバーで使用します。

## Target Recommendations API

リンク： [Target Recommendations API](https://developer.adobe.com/target/){target=_blank}。

Recommendations API を使用すると、プログラムによる操作が可能です [!DNL Target] recommendations サーバー。 これらの API を様々なアプリケーションスタックと統合して、通常は [!DNL Target] ユーザーインターフェイス。
