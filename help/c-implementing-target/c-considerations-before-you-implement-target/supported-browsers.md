---
keywords: ブラウザー;前提条件;要件;Internet Explorer;Chrome;Firefox;Safari;Android;Surface
description: インターフェイスとコンテンツ配信に対して、Adobe [!DNL Target] がサポートするインターネットブラウザーについて説明します。
title: ' [!DNL Target] はどのブラウザーをサポートしていますか？'
feature: 実装
role: Developer
exl-id: 8a366c79-d944-4d44-be5a-7c4f65385beb
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 48%

---

# サポートされているブラウザー

[!DNL Adobe Target] アプリケーションとコンテンツ配信は様々なブラウザーとデバイスでテストされています。

TLSの詳細については、「 [TLS (Transport Layer Security) Encryption Changes](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) 」を参照してください。

## [!DNL Target]Standard／Premium インターフェイス {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

[!DNL Target]インターフェイスは、次のブラウザーとデバイスをサポートしています。

| デバイスタイプ | ブラウザーのバージョン |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome（最新、最新の1つ前）</li><li>Mozilla Firefox（最新、最新の1つ前）</li></ul> |
| Mac | <ul><li>Firefox（最新、最新の1つ前）</li><li>Chrome（最新、最新の1つ前）</li></ul> |

## コンテンツ配信 {#section_1045A946056441268D40025529918D3D}

コンテンツ配信は、次のブラウザーおよびデバイスでテストされています。

| デバイスタイプ | ブラウザーのバージョン |
|--- |--- |
| Windows | <ul><li>Microsoft Internet Explorer 9 および 10. エミュレーションモードでテスト済み。<br>**注意**:IE 9でのコンテンツ配信は、at.js 1.3.0以降ではサポートされなくなりました。IE 10、11、およびすべての古いバージョンでのコンテンツ配信は、at.js 2.5.0（以降）ではサポートされなくなりました。</li><li>Internet Explorer 11 <br>**注意**:IE 10、11、およびすべての古いバージョンでのコンテンツ配信は、at.js 2.5.0（以降）ではサポートされなくなりました。</li><li>Microsoft Edge</li><li>Chrome（最新、最新の1つ前）</li><li>Firefox（最新、最新の1つ前）</li></ul> |
| Mac | <ul><li>Apple Safari（最新）<br>**注意**:SafariでファーストパーティCookieとサードパーティCookieがどのように処理されるかについて詳しくは、「[Target Cookie](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md)」を参照してください。</li><li>Firefox（最新、最新の1つ前）</li><li>Chrome（最新、最新の1つ前）</li></ul> |
| モバイル／タブレット | <ul><li>Apple iOS（最新）</li><li>Android デバイスおよびタブレット（Android 4 以降）</li><li>Microsoft Surface（Windows 8.1）</li></ul> |

以下のことに注意してください。

* [!DNL at.js] 実装の場合、[!DNL Target] は、Internet Explorer の旧バージョンおよび上述のブラウザーの旧バージョンでは、デフォルトコンテンツを表示します。
* Internet Explorerは、不明な要素（カスタム要素など）をすべて同じ要素の種類として扱います。 その結果、配信はカスタム要素では機能しません。
* [!DNL Target] は、上述のリストに記載されていないブラウザーおよび[互換モード](https://en.wikipedia.org/wiki/Quirks_mode)を使用するブラウザーで、デフォルトコンテンツを表示します。at.js には、`<!DOCTYPE html>` など、標準モードでレンダリングを行う doctype が必要です。
* Adobe Delivery インフラストラクチャの安全確保のために、2018 年 9 月 13 日以降、TLS 1.0 のデバイスおよびブラウザーはサポートされなくなっています。「[TLS（トランスポート層セキュリティ）暗号化の変更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)」を参照して、この変更による全体への影響について理解してください。
