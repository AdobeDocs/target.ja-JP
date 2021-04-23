---
keywords: 実装；実装；設定；設定；データプロバイダ
description: データプロバイダーを使用して [!DNL Target] にデータを取得します。
title: データプロバイダー [!DNL Target] にデータを取り込む方法を教えてください。
feature: 実装
role: Developer
exl-id: 05fe9190-4d36-43e2-9fc7-c354a6821bfb
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 67%

---

# データプロバイダー

データプロバイダーは、サードパーティから[!DNL Adobe Target]にデータを簡単に渡すことができる機能です。

注意：データプロバイダーはat.js 1.3以降が必要です。

## 形式

`window.targetGlobalSettings.dataProviders` 設定は、データプロバイダーの配列です。

各データプロバイダーの構造について詳しくは、[データプロバイダー](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)を参照してください。

## 使用例の例

サードパーティから、気象予報サービス、DMP、自社の Web サービスなどのデータを収集します。このデータを利用して、オーディエンスやターゲットコンテンツを構築したり、訪問者プロファイルを充実させることができます。

## 方法の利点

この設定では、Demandbase、BlueKai、カスタムサービスなどのサードパーティのデータプロバイダーからデータを収集し、そのデータをグローバル mbox リクエストで mbox パラメーターとして渡すことができます。

非同期および同期リクエストを介した複数のプロバイダーからのデータ収集もサポートしています。

この手法では、デフォルトのページコンテンツのちらつきを制御しながら、プロバイダーごとに個別のタイムアウトを指定し、ページのパフォーマンスへの影響を抑制することが簡単にできます。

## 注意事項

`window.targetGlobalSettings.dataProviders`に追加されたデータプロバイダが非同期の場合、それらは並行して実行されます。 訪問者APIリクエストは、`window.targetGlobalSettings.dataProviders`に追加された関数と並行して実行され、最小の待ち時間が許可されます。

at.jsはデータをキャッシュしません。 データプロバイダーが 1 回だけデータを取得する場合は、データをキャッシュし、そのプロバイダーの関数が呼び出されたら、2 回目の呼び出しでキャッシュデータを配信できるようにする必要があります。

## コードの例

[データプロバイダー](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)にはいくつかの例が記載されています。

## 関連情報へのリンク

ドキュメント：[データプロバイダー](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

## トレーニングビデオ：

* [Adobe Target でのデータプロバイダーの使用](https://helpx.adobe.com/jp/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Adobe Target でのデータプロバイダーの実装](https://helpx.adobe.com/jp/target/kt/using/dataProviders-atjs-technical-video-implement.html)
