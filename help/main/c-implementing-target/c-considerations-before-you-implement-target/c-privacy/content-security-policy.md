---
keywords: コンテンツセキュリティポリシー；csp;at.js；ホワイトリスト；許可リスト；ちらつき；事前非表示；事前非表示；事前非表示
description: Adobe Targetを使用する際に追加する必要があるコンテンツセキュリティポリシー (CSP) ディレクティブについて説明します。
title: 方法 [!DNL Target] コンテンツセキュリティポリシー (CSP) を処理しますか？
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: db632225d21c2e061e82269bec168341b410575a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 1%

---

# コンテンツセキュリティポリシー（CSP）指令

次を使用する場合： [コンテンツセキュリティポリシー](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) を [!DNL Adobe Target] 実装する場合、を使用する際に次の CSP ディレクティブを追加する必要があります [at.js 2.1 以降](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` と `*.tt.omtrdc.net` 許可リストに加える。 ネットワークリクエストを [!DNL Target] エッジです。
* `style-src unsafe-inline`をインストールします。事前非表示およびちらつき制御に必要です。
* `script-src unsafe-inline`.  HTMLオファーの一部となる JavaScript の実行を許可するために必要です。

## よくある質問 (FAQ)

セキュリティポリシーに関する次の FAQ を参照してください。

### クロスオリジンリソース共有 (CORS) およびFlashクロスドメインポリシーは、セキュリティ上の問題を生じますか？

CORS ポリシーを実装する推奨される方法は、信頼されたドメインのを介して、信頼されたオリジンに対してのみアクセスできるようにする許可リストことです。 クロスドメインポリシーについても同じことがFlashできます。 一部 [!DNL Adobe Target] のお客様は、 [!DNL Target]. ユーザーがアプリケーションにログインし、ポリシーで許可されたドメインを訪問した場合、そのドメインで実行する悪意のあるコンテンツは、潜在的にアプリケーションから機密コンテンツを取得し、ログインユーザーのセキュリティコンテキスト内でアクションを実行します。 これは、一般に、クロスサイトリクエストフォージェリ (CSRF) と呼ばれます。

内 [!DNL Adobe Target] ただし、これらのポリシーはセキュリティ上の問題を表すものではありません。

「adobe.tt.omtrdc.net」は、Adobeが所有するドメインです。 [!DNL Adobe Target] はテストおよびパーソナライゼーションツールで、 [!DNL Target] は、認証を必要とせずに、どこからでも要求を受け取って処理できます。 これらのリクエストには、A/B テスト、レコメンデーションまたはコンテンツのパーソナライゼーションに使用されるキーと値のペアが含まれます。

[!DNL Adobe] 個人を特定できる情報 (PII) やその他の機密情報を [!DNL Adobe Target] エッジサーバー。「adobe.tt.omtrdc.net」が指す。

これは予想されている [!DNL Target] は、JavaScript 呼び出しを使用して、任意のドメインからアクセスできます。 このアクセスを許可する唯一の方法は、ワイルドカードで「Access-Control-Allow-Origin」を利用することです。
