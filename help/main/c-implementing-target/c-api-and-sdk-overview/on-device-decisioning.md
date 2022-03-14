---
keywords: サーバー側；サーバー側；sdk;sdk；オンデバイス；決定；デバイス上；ondevice；遅延なし；待ち時間；near-zero;node.js
description: オンデバイス判定を使用して [!DNL Target] サーバー上で A/B および MVT アクティビティを使用して、ほぼゼロの遅延でメモリ内判定を実行する。
title: On-Device Decisioning とは
feature: Implement Server-side
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 10%

---

# オンデバイス判定

オンデバイス判定機能を使用すると、 [!DNL Adobe Target] [!UICONTROL A/B テスト] および [!UICONTROL エクスペリエンスのターゲット設定] (XT) サーバー上でのアクティビティと、ほぼゼロの待ち時間でメモリ内判定を実行する。 [!DNL Adobe Target] Edge ネットワーク。

詳しくは、 [オンデバイス判定の概要](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) 内 *[Adobe Target SDK ドキュメント](https://adobetarget-sdks.gitbook.io/docs/)*.

## ウェビナー：[!DNL Adobe Target] からオンデバイスで決定し、待ち時間ゼロでパーソナライズとテストを行います。

これまで以上に、マーケターや、製品所有者、開発者は、サイトやアプリなど、顧客とつながるあらゆる場所での顧客エクスペリエンス全体を最適化しようと取り組んでいます。データのサイロや複雑な実装を備えた複数のツールが不十分です。

この記録済みウェビナーでは、 [!DNL Adobe Target] 製品エキスパートは、ほぼゼロの遅延で、デバイス上での重要なエクスペリエンス最適化の決定をローカルで実行する方法を説明し、新しい使用例に扉を開き、お客様のサイトのパフォーマンスを向上させます。

>[!VIDEO](https://video.tv.adobe.com/v/328148)

## ベストプラクティス

Adobeは、オンデバイス判定を使用する際に、次のベストプラクティスを推奨します。

### 判定方法が「オンデバイス」の場合のベストプラクティス {#best-practices-on-device}

「オンデバイス」を判定方法として使用する場合、訪問者が Web ページを初めて読み込むと、アーティファクトがダウンロードされます。 最初のページ読み込み時（キャッシュなし）に発生する必要があるアクティビティ認定は、アーティファクトが完全にダウンロードされた後でのみ発生します。 新しい匿名訪問者に対してアクティビティの認定が迅速におこなわれるように、いくつかのベストプラクティスに従うことができます。

* アーティファクトに含まれない「オンデバイス」対応アクティビティを非アクティブ化します。
* 次の場合： [!DNL Target Premium]を使用する場合、 [プロパティ/ワークスペース](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) ワークスペースごとに異なるアーティファクトファイルを作成する場合。
* 正当な理由でアーティファクトファイルが非常に大きくなった場合は、「ハイブリッド」判定方法を使用できます。 この方法を使用すると、アーティファクトを並行して、すべての [!DNL Target] API 呼び出しは、アーティファクトがダウンロードされるまで通信を経由します。 最高の情報を読む [「ハイブリッド」判定モードのプラクティスの節](#best-practices-hybrid) この方法の詳細については、以下を参照してください。
* シングルページアプリケーション (SPA) の場合、 [!DNL Adobe] では、最初のページ読み込み時にアプリケーションのメイン JavaScript ファイルを読み込む前に、at.js を読み込んで初期化することをお勧めします。 このアプローチは、アーティファクトのダウンロードをより早く開始し、エクスペリエンスのレンダリングを高速化します。

### 判定方法が「ハイブリッド」の場合のベストプラクティス {#best-practices-hybrid}

「ハイブリッド」を判定方法として使用する場合、アーティファクトは同時にダウンロードされます。 アーティファクトがダウンロードされるまで、 [!DNL Target] API 呼び出しは、「ロケーション」がデバイス上に対応している場合でも、通信を経由します。 この動作は、すべての `getOffers()` を呼び出し、ほとんどの状況で最高のパフォーマンスを提供します。 デフォルトの動作を `getOffers()` 設定 `decisioningMethod` から `on-device`エラーを回避し、最高のパフォーマンスを確保するには、次のベストプラクティスに従います。

* お客様が `getOffers()` と `decisioningMethod` as `on-device` ページを初めて読み込む際は、エラーを避けるために、「ARTIFACT_DOWNLOAD_SUCCEEDED」at.js イベントハンドラー内で読み込む必要があります。 アーティファクトが非常に大きい場合、この方法を使用する「場所」は、アーティファクトが完全にダウンロードされた後にのみレンダリングされ、エクスペリエンスのレンダリングが遅れる可能性があります。 [!DNL Adobe] では、この方法をほとんど使用しないことをお勧めします。 ベストプラクティスに従って、 [「デバイス上」のベストプラクティスの節](#best-practices-on-device) 上記の手順を使用して、

## チュートリアル：オンデバイス判定

[!DNL Adobe Target] オンデバイス判定により、待ち時間がほぼゼロのコンテンツ配信が可能になります。

この 7 分間のビデオ：

* オンデバイス判定を表します。これには、他のの方法との比較方法も含まれます。 [!DNL Target] 実装
* でデバイス上の判定を有効にする方法を示します [!DNL Target]
* JSON コンテンツを使用して設定されたサンプルのフォームベースのコンポーザーアクティビティを調べます。
* オンデバイス判定に必要なキー設定を含む Node.JS SDK コードのサンプルを示します
* ブラウザーでの結果を示します。

>[!VIDEO](https://video.tv.adobe.com/v/329032)

その他のビデオおよびチュートリアルについては、 [Adobe TargetTutorials](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html?lang=ja) ガイド。

## Adobeテクニカルブログ — 第 1 部：実行 [!DNL Adobe Target] エッジプラットフォームでの実験とパーソナライゼーションのための NodeJS SDK(Akamai Edge Workers)

[ブログ投稿にアクセスするには、ここをクリックしてください](https://medium.com/adobetech/part-1-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-4d8660964ed9).

## Adobe Tech Blog - パート 2：Edge Platform で実験とパーソナライゼーションをおこなうために [!DNL Adobe Target] NodeJS SDK を実行する（AWS Lambda@Edge）

[ブログ投稿にアクセスするには、ここをクリックしてください](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563).