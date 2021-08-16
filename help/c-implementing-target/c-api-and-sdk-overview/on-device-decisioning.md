---
keywords: サーバー側；サーバー側；sdk;sdk；オンデバイス；判定；デバイス上；ondevice;ondevice；ゼロ遅延；待ち時間；near-zero;node.js
description: オンデバイス判定を使用して、サーバー上で [!DNL Target] A/BおよびMVTアクティビティをキャッシュし、ゼロに近い待ち時間でメモリ内判定を実行する方法を説明します。
title: On-Device Decisioningとは
feature: サーバー側の実装
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: fe70f357e2298f1656d713aae5fae800e6775d64
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 10%

---

# オンデバイス判定

On-device decisioningを使用すると、[!DNL Adobe Target] [!UICONTROL A/B Test]と[!UICONTROL Experience Targeting](XT)アクティビティをサーバー上にキャッシュし、[!DNL Adobe Target] Edgeネットワークへのネットワークリクエストをブロックせずに、ゼロに近い待ち時間でメモリ内判定を実行できます。

詳しくは、*[Adobe Target SDKドキュメント](https://adobetarget-sdks.gitbook.io/docs/)*&#x200B;の「[On-device decisioning](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning)の概要」を参照してください。

## ウェビナー： のオンデバンス判定により、遅延なしのパーソナライズとテストを実現[!DNL Adobe Target]

これまで以上に、マーケターや、製品所有者、開発者は、サイトやアプリなど、顧客とつながるあらゆる場所での顧客エクスペリエンス全体を最適化しようと取り組んでいます。データサイロや複雑な実装を備えた複数のツールは不十分です。

この記録されたウェビナーでは、[!DNL Adobe Target]製品の専門家が、デバイスに関する重要なエクスペリエンス最適化の決定をローカルで実行する方法について話し合い、ほぼゼロの待ち時間で新しい使用例に扉を開き、顧客のサイトパフォーマンスを向上させます。

>[!VIDEO](https://video.tv.adobe.com/v/328148)

## ベストプラクティス

Adobeは、オンデバイス判定を使用する際に、次のベストプラクティスを推奨します。

### 判定方法が「オンデバイス」の場合のベストプラクティス {#best-practices-on-device}

「オンデバイス」を判定方法として使用する場合は、訪問者がWebページを初めて読み込む際に、アーティファクトがダウンロードされます。 最初のページ読み込み（キャッシュなし）で発生する必要があるアクティビティ認定は、アーティファクトが完全にダウンロードされた後でのみ発生します。 新しい匿名訪問者に対してアクティビティの認定が迅速におこなわれるように、いくつかのベストプラクティスに従うことができます。

* アーティファクトに含まれない「オンデバイス」対応アクティビティを非アクティブ化します。
* [!DNL Target Premium]がある場合は、[properties/workspaces](/help/administrating-target/c-user-management/property-channel/property-channel.md)を使用して、異なるワークスペースに異なるアーティファクトファイルを作成できます。
* 正当な理由でアーティファクトファイルが非常に大きくなった場合は、「ハイブリッド」判定方法を使用できます。 この方法を使用すると、アーティファクトを並行してダウンロードでき、すべての[!DNL Target] API呼び出しがアーティファクトがダウンロードされるまでワイヤーを経由します。 このアプローチの詳細については、以下の「ハイブリッド」判定モード](#best-practices-hybrid)に関するベストプラクティスの節を参照してください。[
* シングルページアプリケーション(SPA)の場合、[!DNL Adobe]では、最初のページ読み込み時にアプリケーションのメインのJavaScriptファイルを読み込む前に、at.jsを読み込んで初期化することをお勧めします。 このアプローチにより、アーティファクトのダウンロードがはるかに早く開始され、エクスペリエンスのレンダリングが高速になります。

### 判定方法が「ハイブリッド」の場合のベストプラクティス {#best-practices-hybrid}

「ハイブリッド」を判定方法として使用する場合、アーティファクトは同時にダウンロードされます。 アーティファクトがダウンロードされるまで、「ロケーション」がオンデバイス対応であっても、[!DNL Target] API呼び出しはすべて有線で送信されます。 この動作は、すべての`getOffers()`呼び出しのデフォルトで、ほとんどの状況で最高のパフォーマンスを提供します。 `decisioningMethod`を`on-device`に設定して`getOffers()`のデフォルトの動作を変更する場合は、次のベストプラクティスに従って、エラーを回避し、最高のパフォーマンスを確保します。

* ページの初回読み込み時に`decisioningMethod`を`on-device`として`getOffers()`を呼び出す場合は、エラーを避けるために、「ARTIFACT_DOWNLOAD_SUCCEEDED」at.jsイベントハンドラー内で呼び出す必要があります。 アーティファクトが非常に大きい場合、この方法を使用する「場所」は、アーティファクトが完全にダウンロードされた後にのみレンダリングされ、エクスペリエンスのレンダリングが遅れる可能性があります。 [!DNL Adobe] では、この方法をほとんど使用しないことをお勧めします。このアプローチを使用する場合は、上記の「[「デバイス上」のベストプラクティスの節](#best-practices-on-device)で、アーティファクトのサイズを小さくするためのベストプラクティスに従ってください。

## チュートリアル：オンデバイス判定

[!DNL Adobe Target] on-device decisioningは、ゼロに近い遅延のコンテンツ配信を可能にします。

この7分間のビデオ：

* [!DNL Target]実装の他の方法との比較方法を含む、デバイス上の判定について説明します
* [!DNL Target]でオンデバイス判定を有効にする方法を示します。
* JSONコンテンツを使用して設定されたフォームベースのコンポーザーアクティビティの例を調べます。
* オンデバイス判定に必要なキー設定を含むNode.JS SDKコードのサンプルを示します
* ブラウザーでの結果の表示

>[!VIDEO](https://video.tv.adobe.com/v/329032)

その他のビデオやチュートリアルについては、 [Adobe TargetTutorials](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html?lang=ja)ガイドを参照してください。

## Adobeテクニカルブログ — 第1部：エッジプラットフォーム(Akamai Edge Workers)で実験とパーソナライゼーションを行うために[!DNL Adobe Target] NodeJS SDKを実行します。

[ブログ投稿にアクセスするには、ここをクリックします](https://medium.com/adobetech/part-1-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-4d8660964ed9)。

## Adobe Tech Blog - パート 2：Edge Platform で実験とパーソナライゼーションをおこなうために [!DNL Adobe Target] NodeJS SDK を実行する（AWS Lambda@Edge）

[ブログ投稿にアクセスするには、ここをクリックします](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563)。