---
keywords: コンテンツセキュリティポリシー；csp;at.js；ホワイトリスト；許可リスト；ちらつき；事前非表示；事前非表示；事前非表示
description: Adobe Targetを使用する際に追加する必要があるコンテンツセキュリティポリシー (CSP) ディレクティブについて説明します。
title: 方法 [!DNL Target] コンテンツセキュリティポリシー (CSP) を処理しますか？
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 5%

---

# コンテンツセキュリティポリシー（CSP）指令

次を使用する場合： [コンテンツセキュリティポリシー](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) を [!DNL Adobe Target] 実装する場合、を使用する際に次の CSP ディレクティブを追加する必要があります [at.js 2.1 以降](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` と `*.tt.omtrdc.net` 許可リストに加える。 ネットワークリクエストを [!DNL Target] エッジです。
* `style-src unsafe-inline`をインストールします。事前非表示およびちらつき制御に必要です。
* `script-src unsafe-inline`.  HTMLオファーの一部となる JavaScript の実行を許可するために必要です。
