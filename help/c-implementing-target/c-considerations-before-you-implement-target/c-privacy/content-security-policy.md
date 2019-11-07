---
keywords: コンテンツセキュリティポリシー；csp;at.js;whitelist;flicker;pre-hide;pre-hiding;pre-hiding;pre-hiding;pre-hiding
description: Adobe Target at.js 2.1以降を使用する場合に追加する必要があるコンテンツセキュリティポリシー(CSP)ディレクティブに関する情報です。
title: コンテンツセキュリティポリシー(CSP)
subtopic: 導入
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# コンテンツセキュリティポリシー(CSP)ディレクティブ

Target実装に [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP)を使用している場合は、 [at.js 2.1以降を使用する際に、次のCSPディレクティブを追加する必要があります](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

* `connect-src` ホワイトリス `*.tt.omtrdc.net` トに登録済み ネットワーク要求をエッジに許可するために必 [!DNL Target] 要です。
* `style-src unsafe-inline`をインストールします。事前非表示およびちらつき制御に必要です。
* `script-src unsafe-inline`.  HTMLオファーの一部となる可能性のあるJavaScriptの実行を許可するために必要です。
