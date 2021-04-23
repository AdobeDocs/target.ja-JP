---
keywords: コンテンツセキュリティポリシー；csp;at.js;whitelist;許可リスト；ちらつき；事前非表示；事前非表示；事前非表示
description: Adobe Targetを使用する場合に追加する必要があるコンテンツセキュリティポリシー(CSP)ディレクティブについて説明します。
title: ' [!DNL Target] コンテンツセキュリティポリシー(CSP)の処理方法'
feature: プライバシーとセキュリティ
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# コンテンツセキュリティポリシー(CSP)ディレクティブ

[コンテンツセキュリティポリシー](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP)を[!DNL Adobe Target]実装に使用している場合、[at.js 2.1以降](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を使用する際に、次のCSPディレクティブを追加する必要があります。

* `connect-src`  `*.tt.omtrdc.net` 許可リストに加える[!DNL Target]エッジにネットワーク要求を許可するために必要です。
* `style-src unsafe-inline`をインストールします。事前の非表示とちらつきの制御に必要です。
* `script-src unsafe-inline`.  HTMLオファーの一部である可能性のあるJavaScriptの実行を許可するために必要です。
