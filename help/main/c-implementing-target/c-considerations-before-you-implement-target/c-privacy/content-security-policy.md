---
keywords: コンテンツセキュリティポリシー;csp;at.js;ホワイトリスト;許可リスト;ちらつき;事前非表示;事前非表示;事前非表示
description: Adobe Target の使用時に追加する必要があるコンテンツセキュリティポリシー（CSP）指令について説明します。
title: ' [!DNL Target]  では、コンテンツセキュリティポリシー（CSP）にどのように対応しますか？'
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 97%

---

# コンテンツセキュリティポリシー（CSP）指令

[コンテンツセキュリティポリシー](https://en.wikipedia.org/wiki/Content_Security_Policy)（CSP）を [!DNL Adobe Target] の実装に使用する場合、[at.js 2.1 以降](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)を使用する際は以下の CSP 指令を追加する必要があります。

* `connect-src` と `*.tt.omtrdc.net` 許可リスト。[!DNL Target] エッジへのネットワークリクエストを許可するために必要です。
* `style-src unsafe-inline`をインストールします。事前非表示およびちらつき制御に必要です。
* `script-src unsafe-inline`。HTML オファーの一部となる JavaScript の実行を許可するために必要です。

## よくある質問（FAQ）

セキュリティポリシーに関する以下の FAQ を参照してください。

### クロスオリジンリソース共有（CORS）と Flash クロスドメインポリシーには、セキュリティの問題がありますか？

CORS ポリシーを実装する推奨方法は、信頼済みのドメインの許可リストを介して、アクセスを必要とする信頼されたオリジンだけにアクセスを許可することです。Flash クロスドメインポリシーについても同じことがいえます。一部の [!DNL Adobe Target] のお客様は、[!DNL Target] でのドメインに対するワイルドカード文字の使用を心配しています。ユーザーがアプリケーションにログインし、ポリシーで許可されたドメインを訪問した場合に、そのドメインで実行されている悪意のあるコンテンツがアプリケーションから機密コンテンツを取得し、ログインしているユーザーのセキュリティコンテキスト内でアクションを実行する可能性があるという心配です。これは、一般に、クロスサイトリクエストフォージェリ（CSRF）と呼ばれます。

ただし、[!DNL Adobe Target] 実装では、これらのポリシーは、セキュリティの問題にはならないはずです。

「adobe.tt.omtrdc.net」は、アドビが所有するドメインです。[!DNL Adobe Target] は、テストとパーソナライゼーションのツールです。[!DNL Target] は、認証を必要とせずに、どこからでもリクエストを受け取り、処理できることが期待されます。これらのリクエストには、A/B テスト、レコメンデーション、コンテンツのパーソナライゼーションに使用されるキーと値のペアが含まれています。

[!DNL Adobe] は、個人を特定できる情報（PII）やその他の機密情報を、「adobe.tt.omtrdc.net」で指定される [!DNL Adobe Target] エッジサーバー上に格納しません。

これにより、JavaScript 呼び出しを使用してどのドメインからでも [!DNL Target] にアクセスできることが期待されます。このアクセスを許可する唯一の方法は、ワイルドカードと共に「Access-Control-Allow-Origin」を活用することです。
