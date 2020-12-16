---
keywords: content security policy;csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hiding;prehiding
description: Adobe Targetat.js 2.1以降を使用する場合に追加する必要があるコンテンツセキュリティポリシー(CSP)ディレクティブに関する情報です。
title: コンテンツセキュリティポリシー(CSP)
feature: privacy and security
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---


# コンテンツセキュリティポリシー(CSP)ディレクティブ

ターゲットの実装に[コンテンツセキュリティポリシー](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP)を使用している場合、[at.js 2.1以降](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を使用する際に、次のCSPディレクティブを追加する必要があります。

* `connect-src` を `*.tt.omtrdc.net` 許可リストに含める。[!DNL Target]エッジにネットワーク要求を許可するために必要です。
* `style-src unsafe-inline`をインストールします。事前の非表示とちらつきの制御に必要です。
* `script-src unsafe-inline`.  HTMLオファーの一部である可能性のあるJavaScriptの実行を許可するために必要です。
