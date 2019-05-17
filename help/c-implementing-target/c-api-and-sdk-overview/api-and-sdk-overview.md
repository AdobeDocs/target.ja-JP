---
description: Target Server Side Delivery API、Recommendations API および NodeJS SDK について説明します。
keywords: server side; サーバー側; api, sdk; nodejs; node js; recommendations api
seo-description: Target Server Side Delivery API、Recommendations API および NodeJS SDK について説明します。
seo-title: サーバー側 Target の実装
solution: 'Target '
title: サーバー側 Target の実装
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# サーバー側：Target の実装{#server-side-implement-target}

Target Server Side delivery API、Server Side Batch Delivery API、NodeJS SDK、Target Recommendations API、Target Classic API（廃止）に関する情報。

以下のセクションに、様々な API および NodeJS SDK の一覧と詳細情報を示します。

## Server Side Delivery API

リンク: [Server Side Delivery API](https://developers.adobetarget.com/api/#server-side-delivery)

`/rest/v1/mbox`

Adobe Target を使用すると、アプリケーションはブラウザー、モバイルデバイス、または別のサーバーから mbox を呼び出します。Server Side Delivery API は、HTTP／HTTPS 呼び出しをおこなうサーバー側プラットフォームと Adobe Target を統合するように設計されています。

API を使用して、カスタムアプリケーションを Target と統合できます。これは、接続されている TV、キオスク、店内のデジタルスクリーンをはじめとした、ブラウザーベースでない IoT デバイスをターゲットに配信する場合に特に役立ちます。

このエンドポイントでは、通常の mbox のみにオファーを返すことができます。また、単一の mbox のみに対してコンテンツを取得することもできます。

この API は、RESTful 形式で既存の mbox 機能を実装します。

この API は、Cookie またはリダイレクトの呼び出しを処理しません。

## Server Side Batch Delivery API

リンク: [Server Side Batch Delivery API](https://developers.adobetarget.com/api/#server-side-batch-delivery)

`/rest/v2/batchmbox`

Batch Delivery API を使用すると、アプリケーションは 1 回の呼び出しで複数の mbox のコンテンツを要求します。また、モバイルアプリケーション、サーバーなどのクライアントが 1 回の要求で複数の mbox のコンテンツを取得してローカルにキャッシュし、後でユーザーがそれらの mbox を訪問したときに Target に通知できるようにするプリフェッチモードもあります。

このエンドポイントでは、通常の mbox のみにオファーを返すことができます。複数の mbox のコンテンツを取得できるので、パフォーマンスの点から一括 mbox API を使用することをお勧めします。これにより、高い負荷がかかる可能性がある複数の HTTP リクエストの実行を回避できます。

## NodeJS SDK

リンク: [NodeJS SDK](https://www.npmjs.com/package/@adobe/target-node-client)

現在アドビでは、1 種類の SDK（NodeJS SDK）のみを提供しています。

NodeJS SDK は、NodeJS の HTTP／HTTPS コアモジュールを囲む thin ラッパーです。NodeJS SDK API は、バックグラウンドで同じ Server Side Delivery API を使用します。

マッピングを次に示します。

* `MarketingCloudClient.getOffer() \*- invokes \*/res/v1/mbox endpoint`
* `MarketingCloudClient.getOffers() \*- invokes \*/res/v2/batchmbox endpoint`

## Target Recommendations API

リンク: [Target Recommendations API](https://developers.adobetarget.com/api/recommendations)

Recommendations API を使用すると、プログラムによって Target の Recommendations サーバーとのインタラクションをおこなうことができます。これらの API は様々なアプリケーションスタックと統合して、通常ユーザーインターフェイスから実行する関数を実行できます。

## Target Classic API

Target Classic UI と API は廃止されました。Target の最新の API への切り替えについて詳しくは、[従来の Target API から Adobe I/O への移行](../../c-implementing-target/c-api-and-sdk-overview/target-api-documentation.md#concept_3A31E26C8FAF49598152ACFE088BD4D2)を参照してください。

>[!NOTE]
>（アクティビティ、オファー、オーディエンスなどを作成する）オーサリング API は、クロスオリジンリソース共有（CORS）をサポートしていません。

## Server Side Delivery API と NodeJS SDK の違い {#section_10336B7934F54CE98E35907A4748A4A4}

Server Side Delivery API と NodeJS SDK の違いがわからないという方も多くいらっしゃることでしょう。特に、パフォーマンスについては相違がほとんどありません。

次の FAQ は、どちらを使用するべきかを決定するのに役立ちます。

**「生の」Server Side API と NodeJS SDK は、それぞれどのような場合に使用するべきですか？**

NodeJS をバックエンドテクノロジーとして使用している場合は、必然的に NodeJS SDK を選択することになります。SDK は、Cookie、ヘッダー、データソースなどの多くの詳細情報を処理します。これにより、アプリケーションのコア機能に注力できます。

**NodeJS SDK を使用すると、パフォーマンスが向上しますか？**

残念ながら、パフォーマンスに関するデータは提供しておりません。しかし、一般的に、NodeJS SDK を使用すると、NodeJS のイベントドリブン型のアーキテクチャによりパフォーマンスが向上します。処理のほとんどが Target のバックエンドでおこなわれます。NodeJS SDK による処理はごくわずかです。SDK は、基本的に Target のリクエストをパッケージ化し、Target の応答を解析する役割を担います。
