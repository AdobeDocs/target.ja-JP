---
description: Target Server Side Delivery API、Recommendations API および NodeJS SDK について説明します。
keywords: server side; サーバー側; api, sdk; nodejs; node js; recommendations api
seo-description: Adobe Target Server Side Delivery API、Recommendations API、およびNodeJS SDKについて取り上げます。
seo-title: サーバー側実装Adobe Target
solution: 'Target '
title: Target のサーバーサイドの実装
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# サーバー側：Target の実装{#server-side-implement-target}

[!DNL Adobe Target] サーバー側配信API、サーバー側配信API、NodeJS SDK、 [!DNL Target Recommendations] API、 [!DNL Target Classic] API（廃止された）に関する情報です。

The following process occurs in a server-side implementation of [!DNL Target]:

1. クライアントデバイスは、サーバーからエクスペリエンスをリクエストします。
1. Your server sends that request to [!DNL Target].
1. [!DNL Target] 応答をサーバーに返します。
1. サーバーは、クライアントデバイスに配信するエクスペリエンスを決定して、レンダリングします。

エクスペリエンスはブラウザーに表示する必要はありません。電子メールまたはキオスク、音声アシスタント経由、または他の非視覚的なエクスペリエンスやブラウザーベースのデバイスを介して表示できます。Because your server sits between the client and [!DNL Target], this type of implementation is also ideal if you need greater control and security or have complex backend processes that you want to run on your server.

以下のセクションに、様々な API および NodeJS SDK の一覧と詳細情報を示します。

## Server Side Delivery API

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/#server-side-delivery)

`/rest/v1/mbox`

[!DNL Target] を使用すると、アプリケーションはブラウザー、モバイルデバイス、または別のサーバーから mbox を呼び出します。The Server Side delivery API is specifically designed to integrate [!DNL Target] with any server-side platform that makes HTTP/HTTPS calls.

You can use the API to integrate your custom application with [!DNL Target]. これは、接続されている TV、キオスク、店内のデジタルスクリーンをはじめとした、ブラウザーベースでない IoT デバイスをターゲットに配信する場合に特に役立ちます。

このエンドポイントでは、通常の mbox のみにオファーを返すことができます。また、単一の mbox のみに対してコンテンツを取得することもできます。

この API は、RESTful 形式で既存の mbox 機能を実装します。

この API は、Cookie またはリダイレクトの呼び出しを処理しません。

## Server Side Batch Delivery API

Link: [Server Side Batch Delivery APIs](https://developers.adobetarget.com/api/#server-side-batch-delivery)

`/rest/v2/batchmbox`

Batch Delivery API を使用すると、アプリケーションは 1 回の呼び出しで複数の mbox のコンテンツを要求します。It also has a prefetch mode that enables clients like mobile apps, servers, and so forth to fetch content for multiple mboxes in one request, cache it locally, and later notify [!DNL Target] when the user visits those mboxes.

このエンドポイントでは、通常の mbox のみにオファーを返すことができます。複数の mbox のコンテンツを取得できるので、パフォーマンスの点から一括 mbox API を使用することをお勧めします。これにより、高い負荷がかかる可能性がある複数の HTTP リクエストの実行を回避できます。

## NodeJS SDK

Link: [NodeJS SDK](https://www.npmjs.com/package/@adobe/target-node-client)

現在アドビでは、1 種類の SDK（NodeJS SDK）のみを提供しています。

NodeJS SDK は、NodeJS の HTTP／HTTPS コアモジュールを囲む thin ラッパーです。NodeJS SDK API は、バックグラウンドで同じ Server Side Delivery API を使用します。

マッピングを次に示します。

* `MarketingCloudClient.getOffer() \*- invokes \*/res/v1/mbox endpoint`
* `MarketingCloudClient.getOffers() \*- invokes \*/res/v2/batchmbox endpoint`

## [!DNL Target Recommendations] API

Link: [Target Recommendations APIs](https://developers.adobetarget.com/api/recommendations)

Recommendations API を使用すると、プログラムによって Target の Recommendations サーバーとのインタラクションをおこなうことができます。これらの API は様々なアプリケーションスタックと統合して、通常ユーザーインターフェイスから実行する関数を実行できます。

## [!DNL Target Classic] API

[!DNL Target Classic] UIおよびAPIは廃止されました。Target の最新の API への切り替えについて詳しくは、[従来の Target API から Adobe I/O への移行](../../c-implementing-target/c-api-and-sdk-overview/target-api-documentation.md#concept_3A31E26C8FAF49598152ACFE088BD4D2)を参照してください。

>[!NOTE]
>（アクティビティ、オファー、オーディエンスなどを作成する）オーサリング API は、クロスオリジンリソース共有（CORS）をサポートしていません。

## Server Side Delivery API と NodeJS SDK の違い {#section_10336B7934F54CE98E35907A4748A4A4}

Server Side Delivery API と NodeJS SDK の違いがわからないという方も多くいらっしゃることでしょう。特に、パフォーマンスについては相違がほとんどありません。

次の FAQ は、どちらを使用するべきかを決定するのに役立ちます。

**「生の」Server Side API と NodeJS SDK は、それぞれどのような場合に使用するべきですか？**

NodeJS をバックエンドテクノロジーとして使用している場合は、必然的に NodeJS SDK を選択することになります。SDK は、Cookie、ヘッダー、データソースなどの多くの詳細情報を処理します。これにより、アプリケーションのコア機能に注力できます。

**NodeJS SDK を使用すると、パフォーマンスが向上しますか？**

残念ながら、パフォーマンスに関するデータは提供しておりません。しかし、一般的に、NodeJS SDK を使用すると、NodeJS のイベントドリブン型のアーキテクチャによりパフォーマンスが向上します。Be aware that most of the time is spent on the [!DNL Target] backend. NodeJS SDK による処理はごくわずかです。The SDK is basically responsible for packaging a [!DNL Target] request and parsing a [!DNL Target] response.
