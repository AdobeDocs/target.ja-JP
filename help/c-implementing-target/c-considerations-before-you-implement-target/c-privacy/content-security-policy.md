---
description: Adobe Target at.js 2.1以降を使用する場合に追加する必要があるコンテンツセキュリティポリシー(CSP)ディレクティブに関する情報です。
keywords: コンテンツセキュリティポリシー；csp;at.js;whitelist;flicker;pre-hide;pre-hiding;pre-hiding;pre-hiding;pre-hiding
seo-description: Adobe Target at.js 2.1以降を使用する場合に追加する必要があるコンテンツセキュリティポリシー(CSP)ディレクティブに関する情報です。
seo-title: コンテンツセキュリティポリシー(CSP)
solution: 'Target '
subtopic: 導入
title: コンテンツセキュリティポリシー(CSP)ディレクティブ
topic: Standard
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# コンテンツセキュリティポリシー(CSP)ディレクティブ

Target実装に [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP)を使用している場合は、 [at.js 2.1以降を使用する際に、次のCSPディレクティブを追加する必要があります](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

* `connect-src` ホワイトリス `*.tt.omtrdc.net` トに登録済み ネットワーク要求をエッジに許可するために必 [!DNL Target] 要です。
* `style-src unsafe-inline`をインストールします。事前非表示およびちらつき制御に必要です。
* `script-src unsafe-inline`.  HTMLオファーの一部となる可能性のあるJavaScriptの実行を許可するために必要です。
