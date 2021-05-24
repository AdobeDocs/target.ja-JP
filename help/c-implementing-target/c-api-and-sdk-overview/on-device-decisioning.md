---
keywords: サーバー側；サーバー側；sdk;sdk；オンデバイス；判定；デバイス上；ondevice;ondevice；ゼロ遅延；待ち時間；near-zero;node.js
description: オンデバイス判定を使用して、サーバー上で [!DNL Target] A/BおよびMVTアクティビティをキャッシュし、ゼロに近い待ち時間でメモリ内判定を実行する方法を説明します。
title: On-Device Decisioningとは
feature: サーバー側の実装
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: ed4e6715c120fe692c7f3f84f6b869b5ad9bd1b7
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 20%

---

# オンデバイス判定

On-device decisioningを使用すると、[!DNL Adobe Target] [!UICONTROL A/B Test]と[!UICONTROL Experience Targeting](XT)アクティビティをサーバー上にキャッシュし、[!DNL Adobe Target] Edgeネットワークへのネットワークリクエストをブロックせずに、ゼロに近い待ち時間でメモリ内判定を実行できます。

詳しくは、*[Adobe Target SDKドキュメント](https://adobetarget-sdks.gitbook.io/docs/)*&#x200B;の「[On-device decisioning](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning)の概要」を参照してください。

## ウェビナー：Adobe Target のオンデバンス判定により、遅延なしのパーソナライズとテストを実現

これまで以上に、マーケターや、製品所有者、開発者は、サイトやアプリなど、顧客とつながるあらゆる場所での顧客エクスペリエンス全体を最適化しようと取り組んでいます。データが分断された複数のサイロと、複雑な実装では、これを実現することはできません。

この記録されたウェビナーでは、[!DNL Adobe Target]製品の専門家が、デバイスに関する重要なエクスペリエンス最適化の決定をローカルで実行する方法について話し合い、ほぼゼロの待ち時間で新しい使用例に扉を開き、顧客のサイトパフォーマンスを向上させます。

>[!VIDEO](https://video.tv.adobe.com/v/328148)

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

## Adobeテクニカルブログ — パート2:エッジプラットフォームで実験とパーソナライゼーションを行うために[!DNL Adobe Target] NodeJS SDKを実行する(AWS Lambda@Edge)

[ブログ投稿にアクセスするには、ここをクリックします](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563)。