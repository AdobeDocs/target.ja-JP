---
keywords: google;samesite;cookies;chrome 80;ietf
description: Adobe Target と、Google Chrome バージョン 80 で導入された SameSite IETF 標準に関する情報です。
title: Adobe TargetとGoogleのSameSite cookieポリシー
feature: null
subtopic: Getting Started
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '2033'
ht-degree: 8%

---


# Google Chrome SameSite cookie ポリシー

Googleは、2020年初頭にリリース予定のChrome 80以降のユーザーに対して、デフォルトで新しいCookieポリシーの課金を開始します。 この記事では、新しいSameSite cookieポリシー、これらのポリシーの [!DNL Adobe Target] サポート方法、およびを使用してGoogle Chromeの新しいSameSite Cookieポリシーを遵守する方法について、知っ [!DNL Target] ておく必要があるすべてについて説明します。

Chrome 80以降、Web開発者は、Webサイト間で機能するCookieを明示的に指定する必要があります。 これは、GoogleがWeb上のプライバシーとセキュリティを改善するために計画している多くのお知らせの中で初めてです。

プライバシーとセキュリティに関してFacebookが注目を浴びているという事実を考えると、AppleやGoogleなど他の主要プレーヤーは、プライバシーとセキュリティのチャンピオンとして新しいIDを作成する機会をすぐに利用できます。 Appleは、今年初めにITP 2.1を通じてCookieポリシーに変更を発表し、最近はITP 2.2を採用しました。ITP 2.1では、AppleはサードパーティCookieを完全にブロックし、ブラウザーで作成されたCookieを7日間のみ保持します。 ITP 2.2では、cookieは1日のみ保持されます。 Googleの発表は、Appleの発表ほど積極的ではありませんが、同じ最終目標を達成するための第一歩です。 Appleのポリシーについて詳しくは、 [Apple Intelligent Tracking Prevention(ITP)2.xを参照してください](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

## cookieとは何ですか。cookieの使用方法は何ですか。

Googleのcookieポリシーに対する変更点を調べる前に、cookieの種類と使用方法について見ていきましょう。 簡単に言うと、cookieは、Webブラウザーに保存される、ユーザー属性の記憶に使用される小さなテキストファイルです。

Cookieは、Webを閲覧する際のユーザーの操作性を高めるので、重要です。 例えば、eコマースWebサイトで買い物をしていて、買い物かごに何かを追加しても、サインインしたりその訪問で購入しない場合、cookieには品目が記憶され、次回の訪問のために買い物かごに保存されます。 また、お気に入りのソーシャルメディアWebサイトを訪問するたびに、ユーザー名とパスワードの再入力を強制された場合を考えてみましょう。 Cookieはこの問題を解決するものです。Cookieは、サイトが自分を特定するのに役立つ情報を保存するからです。 この種のcookieは、訪問したWebサイトで作成され使用されるので、ファーストパーティcookieと呼ばれます。

サードパーティCookieも存在します。 この例を理解したうえで、次の例を考えてみましょう。

「友達」と呼ばれる仮のソーシャルメディア会社が「共有」ボタンを提供するとします。このボタンを他のサイトで実装し、友達ユーザーが友達フィードでサイトのコンテンツを共有できるようにします。 現在は、ユーザーがニュースWebサイトのニュース記事を読み、「共有」ボタンをクリックして、自動的に友達アカウントに投稿します。

これを行うには、ブラウザーは、ニュース記事が読み込まれた時点から「友達の共有」ボタン `platform.friends.com` を取得します。 このプロセスで、ブラウザーはユーザーのログイン情報を含むフレンドcookieをフレンドサーバーに送信します。 これにより、友達は、ユーザーのログインを必要とせずに、ユーザーの代わりにニュース記事をフィードに投稿できます。

これは、サードパーティcookieを使用することで可能です。 この場合、のサードパーティCookieがブラウザーに保存され `platform.friends.com`るので、ユーザーに代わってFriendsアプリで投稿 `platform.friends.com` できます。

サードパーティcookieを使用しないでこの使用事例を実現する方法を考えてみると、ユーザーは多くの手動手順に従う必要があります。 まず、ユーザーはニュース記事へのリンクをコピーする必要があります。 2つ目は、ユーザーは別々にFriendsアプリにログインする必要があることです。 次に、「投稿を作成」ボタンをクリックします。 次に、ユーザーがテキストフィールドにリンクをコピーして貼り付け、最後に「投稿」をクリックします。 ご覧のように、サードパーティcookieは、手動の手順を大幅に削減できるので、ユーザーにとって非常に役立ちます。

より一般的に、サードパーティcookieを使用すると、ユーザーがWebサイトを明示的に訪問する必要なく、データをユーザーのブラウザーに保存できます。

## セキュリティ上の懸念

cookieはユーザーの操作性と電力広告を強化しますが、クロスサイト要求偽造(CSRF)攻撃のようなセキュリティの脆弱性を導入する可能性もあります。 例えば、ユーザーがクレジットカードの請求書を支払うために銀行サイトにログインし、ログアウトせずにサイトを離れ、同じセッションで悪質なサイトを閲覧した場合、CSRF攻撃が発生する可能性があります。 悪質なサイトには、ページが読み込まれたときに実行される、銀行サイトへのリクエストを行うコードが含まれている場合があります。 このユーザーは依然としてバンキングサイトで認証されるので、セッションcookieを使用してCSRF攻撃を開始し、ユーザーの銀行口座から資金移動イベントを開始できます。 これは、サイトを訪問するたびに、すべてのcookieがHTTPリクエストに添付されるからです。 セキュリティ上の懸念があるためGoogleは現在、セキュリティを軽減しようとしています。

## ターゲットでcookieを使用する方法

ただし、cookieの [!DNL Target] 使用方法を見てみましょう。 まず、JavaScriptライブラリ [!DNL Target] をサイトにインストールする必要があり [!DNL Target] ます。 これにより、サイトの訪問者のブラウザーにファーストパーティCookieを配置できます。 ユーザーがWebサイトを操作する際に、ユーザーの行動および関心データをJavaScriptライブラリ [!DNL Target] に渡すことができます。 JavaScriptライブラリは、ファーストパーティ [!DNL Target] cookieを使用して、ユーザーに関する識別情報を抽出し、ユーザーの行動と関心データにマッピングします。 このデータは、によってパーソナライゼーションアクティビティ [!DNL Target] を引き出すために使用されます。

ターゲットでも（場合によっては）サードパーティCookieが使用されます。 異なるドメインに存在する複数のWebサイトを所有し、それらのWebサイト間でのユーザーの遍歴を追跡する場合、クロスドメイン追跡を利用してサードパーティCookieを使用できます。 JavaScriptライブラリでクロスドメイントラッキングを有効にすると、 [!DNL Target] サードパーティcookieを使用してアカウントが開始します。 ユーザーがドメイン間をホップすると、ブラウザーはのバックエンドサーバーと通信し [!DNL Target]、このプロセスでサードパーティCookieが作成され、ユーザーのブラウザーに配置されます。 ユーザーのブラウザー上に存在するサードパーティCookieを使用して、1人のユーザーに対して異なるドメイン間で一貫したエクスペリエンス [!DNL Target] を提供できます。

## Googleの新しいcookieレシピ

Googleは、ユーザーを保護するためにCookieがサイト間で送信される際の保護を提供するため、SameSiteと呼ばれるIETF標準のサポートを追加する予定です。このサポートを追加するには、Set-CookieヘッダーにSameSite属性コンポーネントを使用してCookieを管理する必要があります。

Strict、Lax または None の 3 つの異なる値を SameSite 属性に渡すことができます。

| 値 | 説明 |
| --- | --- |
| Strict | この設定を含む cookie には、最初に設定されたドメインへの訪問時にのみアクセスできます。つまり、Strict は、サイト全体で cookie の使用を完全にブロックします。このオプションは、銀行など、高いセキュリティを必要とするアプリケーションに最適です。 |
| Lax | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, like `HTTP GET`. したがって、cookieがサードパーティで使用できる場合にこのオプションを使用できますが、セキュリティ上の利点が強化され、CSRF攻撃による被害を防ぐことができます。 |
| None | この設定を使用するCookieは、現在のCookieと同じように機能します。 |

上記の点を考慮して、Chrome 80ではユーザーに対して次の2つの独立した設定が用意されています。&quot;SameSite by default cookies&quot;と&quot;SameSiteを使用しないcookieは、セキュリティで保護する必要があります。&quot; これらの設定は、Chrome 80ではデフォルトで有効になります。

![SameSiteダイアログボックス](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **SameSite by default cookie**:設定した場合、SameSite属性を指定しないすべてのCookieが自動的に使用されま `SameSite = Lax`す。
* **SameSiteを使用しないcookieは、セキュリティで保護する必要があります**:設定する場合、SameSite属性を持たないCookie、またはセキュリティで保護されている必要 `SameSite = None` があります。 セキュアとは、このコンテキストでは、すべてのブラウザーリクエストが HTTPS プロトコルに従う必要があることを意味します。この要件に準拠しない cookie は拒否されます。この要件を満たすには、すべてのWebサイトでHTTPSを使用する必要があります。

## Google のセキュリティのベストプラクティスに従う Target

Adobe時には、セキュリティとプライバシーに関する業界の最新のベストプラクティスを常にサポートしたいと考えています。 We are happy to announce that [!DNL Target] supports the new security and privacy settings introduced by Google.

「デフォルトのSameSite Cookie」設定では、ユーザーが影響を与えたり介入したりすることなく、 [!DNL Target] 引き続きパーソナライゼーションを提供します。 [!DNL Target]Google Chrome によってフラグ `SameSite = Lax` が適用されるので、 はファーストパーティ cookie を使用し、引き続き適切に機能します。

「Cookie without SameSite must be secure（同じサイトのCookieを保護する必要があります）」オプションで、のクロスドメイントラッキング機能をオプトインしない場合 [!DNL Target]、に含まれるファーストパーティCookieは引き続き機能し [!DNL Target] ます。

However, when you opt-in to use cross-domain tracking to leverage [!DNL Target] across multiple domains, Chrome requires `SameSite = None` and Secure flags to be used for third-party cookies. つまり、サイトでHTTPSプロトコルを使用している必要があります。 のクライアント側ライブラリ [!DNL Target] は、HTTPSプロトコルを自動的に使用し、すべてのアクティビティが引き続き配信されるように、のサードパーティcookieに `SameSite = None` フラグとセキュアフラグ [!DNL Target] を付加します。

## 必要なアクション

Google Chrome 80以降のユーザーが引き続き使用できるようにする必要がある作業を理解するに [!DNL Target] は、次の表を参照してください。次の列が表示されます。

* **ターゲットJavaScriptライブラリ**:mbox.jsを使用している場合は、at.js 1。*x* または at.js 2.*x* （サイト上）
* **SameSite by default cookies = Enabled**:ユーザーが「デフォルトで同じサイトのCookie」を有効にしている場合、その影響と、作業を続けるために必要な操作は何か [!DNL Target] を確認してください。
* **SameSiteを使用しないcookieはセキュア=有効**:ユーザーが「SameSiteを使用しないCookieはセキュリティで保護する必要がある」を有効にしている場合、その影響と [!DNL Target] 継続して動作するために必要な作業は何か。

| ターゲットJavaScriptライブラリ | SameSite by default cookies = 有効 | Cookies without SameSite must be secure = 有効 |
| --- | --- | --- |
| mbox.jsのファーストパーティcookieのみを使用する場合。 | 影響なし。 | クロスドメイントラッキングを使用していない場合は影響しません。 |
| mbox.jsでクロスドメイントラッキングが有効になっている。 | 影響なし。 | サイトでHTTPSプロトコルを有効にする必要があります。<br>[!DNL Target] はユーザーを追跡するためにサードパーティcookieを使用し、Googleはサードパーティcookieに対して保護フラグを設定する `SameSite = None` 必要があります。 セキュアフラグを使用するには、サイトでHTTPSプロトコルを使用する必要があります。 |
| at.js 1.*x* ファーストパーティcookieを使用する場合。 | 影響なし。 | クロスドメイントラッキングを使用していない場合は影響しません。 |
| at.js 1.*x* （クロスドメイントラッキングが有効になっている場合） | 影響なし。 | サイトでHTTPSプロトコルを有効にする必要があります。<br>[!DNL Target] はユーザーを追跡するためにサードパーティcookieを使用し、Googleはサードパーティcookieに対して保護フラグを設定する `SameSite = None` 必要があります。 セキュアフラグを使用するには、サイトでHTTPSプロトコルを使用する必要があります。 |
| at.js 2.*x* | 影響なし。 | 影響なし。 |

## ターゲットは何をする必要がありますか。

新しいGoogle Chrome 80+ SameSite cookieポリシーに準拠するために、アドビのプラットフォームで必要なことは何ですか？

| ターゲットJavaScriptライブラリ | SameSite by default cookies = 有効 | Cookies without SameSite must be secure = 有効 |
| --- | --- | --- |
| mbox.jsのファーストパーティcookieのみを使用する場合。 | 影響なし。 | クロスドメイントラッキングを使用していない場合は影響しません。 |
| mbox.jsでクロスドメイントラッキングが有効になっている。 | 影響なし。 | [!DNL Target] サ `SameSite = None` ー [!DNL Target] バー呼び出し時に、サードパーティcookieに安全なフラグを追加します。 |
| at.js 1.*x* ファーストパーティcookieを使用する場合。 | 影響なし。 | クロスドメイントラッキングを使用していない場合は影響しません。 |
| at.js 1.*x* （クロスドメイントラッキングが有効になっている場合） | 影響なし。 | at.js 1.*x* （クロスドメイントラッキングが有効になっている場合） |
| at.js 2.*x* | 影響なし。 | 影響なし。 |

## HTTPSプロトコルを使用する場合に先に進まないと、どのような影響がありますか。

影響を受ける唯一の使用例は、mbox.jsまたはat.js 1でクロスドメイントラッキング機能を使用し [!DNL Target] ている場合です。*x* では、標準設定ではサポートされていません。Googleが必要とするHTTPSに移動しないと、Googleが使用するサードパーティCookieがGoogleによって破棄されるので、ドメイン間の実訪問者にスパイクが発生します。 また、サードパーティCookieが破棄されるので、ユーザー [!DNL Target] がドメイン間を移動する際に、そのユーザーに対して一貫性のあるパーソナライズされたエクスペリエンスを提供することはできません。 サードパーティCookieは、主に、所有するドメイン間を移動する単一のユーザーを識別するために使用されます。

## まとめ

業界は、より安全な消費者向けWebを構築するために努力しており、エンドユーザーのセキュリティとプライバシーを確保する方法で、お客様がパーソナライズされたエクスペリエンスを提供できるよう、全面的に取り組んでいます。 [!DNL Adobe] 必要な作業は、前述のベストプラクティスに従って、Google Chromeの新しいSameSite Cookieポリシーに準拠す [!DNL Target] るための利点を活用することだけです。
