---
keywords: コンテンツセキュリティポリシー；csp;at.js;whitelist;許可リスト；ちらつき；事前非表示；事前非表示；事前非表示；事前非表示
description: Adobe Targetを使用する場合に追加する必要があるコンテンツセキュリティポリシー(CSP)ディレクティブについて説明します。
title: ターゲットはコンテンツセキュリティポリシー(CSP)をどのように処理しますか？
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---


# コンテンツセキュリティポリシー(CSP)ディレクティブ

[コンテンツセキュリティポリシー](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP)を[!DNL Adobe Target]実装に使用している場合、[at.js 2.1以降](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を使用する際に、次のCSPディレクティブを追加する必要があります。

* `connect-src` を `*.tt.omtrdc.net` 許可リストに含める。[!DNL Target]エッジにネットワーク要求を許可するために必要です。
* `style-src unsafe-inline`をインストールします。事前の非表示とちらつきの制御に必要です。
* `script-src unsafe-inline`.  HTMLオファーの一部である可能性のあるJavaScriptの実行を許可するために必要です。
