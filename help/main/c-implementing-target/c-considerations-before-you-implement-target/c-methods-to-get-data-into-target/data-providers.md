---
keywords: 実装；実装する；設定；設定；データプロバイダー
description: データをに取り込む [!DNL Target] データプロバイダーを使用する。
title: データをに取り込む方法 [!DNL Target] データプロバイダーを使用する場合
feature: Implementation
role: Developer
exl-id: 05fe9190-4d36-43e2-9fc7-c354a6821bfb
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 55%

---

# データプロバイダー

データプロバイダーは、サードパーティからにデータを簡単に渡すことができる機能です。 [!DNL Adobe Target].

注意：データプロバイダーには at.js 1.3 以降が必要です。

## 形式

`window.targetGlobalSettings.dataProviders` 設定は、データプロバイダーの配列です。

各データプロバイダーの構造について詳しくは、 [データプロバイダー](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}。

## 使用例

サードパーティから、気象予報サービス、DMP、自社の Web サービスなどのデータを収集します。このデータを利用して、オーディエンスやターゲットコンテンツを構築したり、訪問者プロファイルを充実させることができます。

## 方法の利点

この設定では、Demandbase、BlueKai、カスタムサービスなどのサードパーティのデータプロバイダーからデータを収集し、そのデータをグローバル mbox リクエストで mbox パラメーターとして渡すことができます。

非同期および同期リクエストを介した複数のプロバイダーからのデータ収集もサポートしています。

この手法では、デフォルトのページコンテンツのちらつきを制御しながら、プロバイダーごとに個別のタイムアウトを指定し、ページのパフォーマンスへの影響を抑制することが簡単にできます。

## 注意事項

データプロバイダーが `window.targetGlobalSettings.dataProviders` が非同期の場合は、同時に実行されます。 訪問者 API リクエストは、に追加された関数と同時に実行されます。 `window.targetGlobalSettings.dataProviders` 待ち時間を最小限に抑える。

at.js はデータをキャッシュしません。 データプロバイダーが 1 回だけデータを取得する場合は、データをキャッシュし、そのプロバイダーの関数が呼び出されたら、2 回目の呼び出しでキャッシュデータを配信できるようにする必要があります。

## コード例

以下にいくつかの例を示します。 [データプロバイダー](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}。

## 関連情報へのリンク

ドキュメント：[データプロバイダー](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)

## トレーニングビデオ：

* [Adobe Target でのデータプロバイダーの使用](https://helpx.adobe.com/jp/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Adobe Target でのデータプロバイダーの実装](https://helpx.adobe.com/jp/target/kt/using/dataProviders-atjs-technical-video-implement.html)
