---
description: Adobe Target アプリケーションとコンテンツ配信は様々なブラウザーとデバイスでテストされています。
keywords: ブラウザー;前提条件;要件;Internet Explorer;Chrome;Firefox;Safari;Android;Surface
seo-description: Adobe Target アプリケーションとコンテンツ配信は様々なブラウザーとデバイスでテストされています。
seo-title: サポートされているブラウザー
solution: 'Target '
subtopic: 導入
title: サポートされているブラウザー
topic: Standard
uuid: 614088da-412c-45e3-9f2d-6985391973be
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# サポートされているブラウザー{#supported-browsers}

[!DNL Adobe Target] アプリケーションとコンテンツ配信は様々なブラウザーとデバイスでテストされています。

TLS に関する追加の重要情報については、「[TLS（トランスポート層セキュリティ）暗号化の変更](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)」を参照してください。

## [!DNL Target] Standard/Premiumのインターフェイス {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

[!DNL[!DNL Target]] Standard/Premium] インターフェイスは、次のブラウザーおよびデバイスをサポートしています。

| デバイスタイプ | ブラウザーのバージョン |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome（最新、最新の 1 つ前）</li><li>Mozilla Firefox（最新、最新の 1 つ前）</li></ul> |
| Mac | <ul><li>Firefox（最新、最新の 1 つ前）</li><li>Chrome（最新、最新の 1 つ前）</li></ul> |

## Content delivery {#section_1045A946056441268D40025529918D3D}

コンテンツ配信は、次のブラウザーおよびデバイスでテストされています。

| デバイスタイプ | ブラウザーのバージョン |
|--- |--- |
| Windows | <ul><li>Internet Explorer 9 および 10。エミュレーションモードでテスト済み。<br>**注意**： at.js 1.3.0 以降では、Microsoft Internet Explorer 9 でのコンテンツ配信がサポート対象外になりました。</li><li>Internet Explorer 11</li><li>Microsoft Edge</li><li>Chrome（最新、最新の 1 つ前）</li><li>Firefox（最新、最新の 1 つ前）</li></ul> |
| Mac | <ul><li>Apple Safari（最新）<br>**注意**： Safari でファーストパーティ Cookie とサードパーティ Cookie がどのように処理されるかについて詳しくは、「[Target の Cookie](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md)」を参照してください。</li><li>Firefox（最新、最新の 1 つ前）</li><li>Chrome（最新、最新の 1 つ前）</li></ul> |
| モバイル／タブレット | <ul><li>Apple iOS（最新）</li><li>Android デバイスおよびタブレット（Android 4 以降）</li><li>Microsoft Surface（Windows 8.1）</li></ul> |

[!DNL at.js] 実装の場合、[!DNL Target] は、Internet Explorer の旧バージョンおよび上述のブラウザーの旧バージョンでは、デフォルトコンテンツを表示します。[!DNL mbox.js] 実装の場合、[!DNL Target] はコンテンツのレンダリングを試みますが、エラーが発生する場合があります。

[!DNL Target] は、上述のリストに記載されていないブラウザーおよび[互換モード](https://en.wikipedia.org/wiki/Quirks_mode)を使用するブラウザーで、デフォルトコンテンツを表示します。at.js には、`<!DOCTYPE html>` など、標準モードでレンダリングを行う doctype が必要です。

>[!NOTE]
>
>Adobe Delivery インフラストラクチャの安全確保のために、2018 年 9 月 13 日以降、TLS 1.0 のデバイスおよびブラウザーはサポートされなくなっています。「[TLS（トランスポート層セキュリティ）暗号化の変更](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)」を参照して、この変更による全体への影響について理解してください。
