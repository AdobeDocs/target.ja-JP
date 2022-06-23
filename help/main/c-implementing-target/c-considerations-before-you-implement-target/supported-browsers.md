---
keywords: ブラウザー;前提条件;要件;Internet Explorer;Chrome;Firefox;Safari;Android;Surface
description: インターネットブラウザーのAdobe [!DNL Target] は、そのインターフェイスとコンテンツ配信をサポートしています。
title: ブラウザーの機能 [!DNL Target] サポート？
feature: Implementation
role: Developer
exl-id: 8a366c79-d944-4d44-be5a-7c4f65385beb
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 41%

---

# サポートされているブラウザー

[!DNL Adobe Target] アプリケーションとコンテンツ配信は様々なブラウザーとデバイスでテストされています。

TLS について詳しくは、 [TLS(Transport Layer Security) 暗号化の変更](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/).

## [!DNL Target]Standard／Premium インターフェイス {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

この [!DNL Target] インターフェイスは、次のブラウザーおよびデバイスをサポートしています。

| デバイスタイプ | ブラウザーのバージョン |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome（最新、最新の 1 つ前）</li><li>Mozilla Firefox（最新、最新の 1 つ前）</li></ul> |
| Mac | <ul><li>Firefox（最新、最新の 1 つ前）</li><li>Chrome（最新、最新の 1 つ前）</li></ul> |

## コンテンツ配信 {#section_1045A946056441268D40025529918D3D}

コンテンツ配信は、次のブラウザーおよびデバイスでテストされています。

| デバイスタイプ | ブラウザーのバージョン |
|--- |--- |
| Windows | <ul><li>Microsoft Internet Explorer 9 および 10. エミュレーションモードでテスト済み。<br>**注意**:IE 9 でのコンテンツ配信は、at.js 1.3.0 以降ではサポートされなくなりました。 IE 10、11、およびすべての古いバージョンでのコンテンツ配信は、at.js 2.5.0（以降）ではサポートされなくなりました。</li><li>Internet Explorer 11 <br>**注意**:IE 10、11、およびすべての古いバージョンでのコンテンツ配信は、at.js 2.5.0（以降）ではサポートされなくなりました。</li><li>Microsoft Edge</li><li>Chrome（最新、最新の 1 つ前）</li><li>Firefox（最新、最新の 1 つ前）</li></ul> |
| Mac | <ul><li>Apple Safari（最新）<br>**注意**:Safari でファーストパーティ Cookie とサードパーティ Cookie がどのように処理されるかについて詳しくは、 [Target の Cookie](https://developer.adobe.com/target/before-implement/privacy/cookie-behavior/).</li><li>Firefox（最新、最新の 1 つ前）</li><li>Chrome（最新、最新の 1 つ前）</li></ul> |
| モバイル／タブレット | <ul><li>Apple iOS（最新）</li><li>Android デバイスおよびタブレット（Android 4 以降）</li><li>Microsoft Surface（Windows 8.1）</li></ul> |

以下のことに注意してください。

* [!DNL at.js] 実装の場合、[!DNL Target] は、Internet Explorer の旧バージョンおよび上述のブラウザーの旧バージョンでは、デフォルトコンテンツを表示します。
* Internet Explorer は、すべての不明な要素（カスタム要素など）を同じ要素タイプとして扱います。 その結果、配信はカスタム要素では機能しません。
* [!DNL Target] は、上述のリストに記載されていないブラウザーおよび[互換モード](https://en.wikipedia.org/wiki/Quirks_mode)を使用するブラウザーで、デフォルトコンテンツを表示します。at.js には、`<!DOCTYPE html>` など、標準モードでレンダリングを行う doctype が必要です。
* Adobe Delivery インフラストラクチャの安全確保のために、2018 年 9 月 13 日以降、TLS 1.0 のデバイスおよびブラウザーはサポートされなくなっています。詳しくは、 [TLS(Transport Layer Security) 暗号化の変更](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/){target=_blank} を参照してください。
