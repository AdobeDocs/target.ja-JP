---
description: Target と、Google Chrome バージョン 76 以降で使用される SameSite IETF 標準に関する情報です。
keywords: google;samesite;cookie;chrome 80;ietf
seo-description: Adobe Target と、Google Chrome バージョン 80 で導入された SameSite IETF 標準に関する情報です。
seo-title: Adobe targetとGoogleのSameSite cookieポリシー
solution: 'Target '
subtopic: 導入
title: Google Chrome SameSite cookie ポリシー
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# Google Chrome SameSite cookie ポリシー

Googleは、Chrome 80以降のユーザーに対して、デフォルトで新しいcookieポリシーを課し始めます。これは2020年初めにリリースされる予定です。 この記事では、新しいSameSite cookieポリシー、これらのポリシーのサポート方法、およびを使用してGoogle Chromeの新しいSameSite [!DNL Adobe Target] Cookieポリシーに準拠する方法につい [!DNL Target] て、知る必要のあるすべてを説明します。

Chrome 80以降では、Web開発者はWebサイト間で機能するCookieを明示的に指定する必要があります。 これは、GoogleがWeb上のプライバシーとセキュリティの向上を計画している多くのお知らせの中で、初めてです。

Facebookがプライバシーとセキュリティに関して注目を集めているという事実を考えると、AppleやGoogleなど他の主要プレーヤーは、プライバシーとセキュリティの擁護者として新しいIDを作る機会を利用して、すぐに利用できます。 Appleは、今年初めにITP 2.1を通じてcookieポリシーの変更を発表し、最近はITP 2.2を採用し、Cookieポリシーの変更を発表しました。ITP 2.1では、Appleはサードパーティcookieを完全にブロックし、作成されたcookieをブラウザー上で保持するのは7日間のみです。 ITP 2.2では、cookieは1日のみ保持されます。 Googleの発表はAppleの発表ほど積極的ではありませんが、同じ最終目標を達成するための第一歩です。 Appleのポリシーについて詳しくは、 [Apple Intelligent Tracking Prevention(ITP)2.xを参照してください](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

## cookieとは何ですか。また、cookieの使用方法について教えてください。

Googleのcookieポリシーに対する変更点について詳しくは、cookieの内容とその使用方法について説明します。 簡単に言うと、cookieとは、Webブラウザーに保存される小さなテキストファイルで、ユーザー属性を記憶するために使用されます。

cookieは、Webを閲覧する際のユーザーの操作性を高めるので、重要です。 例えば、eコマースWebサイトで買い物をしていて、買い物かごに何かを追加しても、その訪問でサインインまたは購入しない場合、cookieには品目が記憶され、次回の訪問時には買い物かごに保存されます。 また、お気に入りのソーシャルメディアWebサイトを訪問するたびに、ユーザー名とパスワードの再入力を強制されたとします。 cookieは、サイトが自分を識別するのに役立つ情報を保存するので、この問題を解決することもできます。 この種のcookieは、訪問したWebサイトで作成および使用されるので、ファーストパーティcookieと呼ばれます。

サードパーティcookieも存在します。 これらをより深く理解するために、次の例を考えてみましょう。

例えば、「友達」と呼ばれる仮のソーシャルメディア会社が、他のサイトに実装された「共有」ボタンを提供し、友達ユーザーが友達フィードでサイトのコンテンツを共有できるようにします。 ユーザーが「共有」ボタンを使用しているニュースWebサイトのニュース記事を読み、クリックして自動的に友達アカウントに投稿するようになりました。

これを行うには、ニュース記事が読み込まれた時点から「友達の共有」ボ `platform.friends.com` タンをブラウザーが取得します。 このプロセス内で、ブラウザーはユーザーのログイン情報を含む友達cookieを友達サーバーに添付します。 これにより、ユーザーがログインする必要なく、友達がユーザーの代わりにニュース記事をフィードに投稿できます。

これは、サードパーティcookieを使用することで可能です。 この場合、サードパーティCookieがのブラウザーに保存され、ユ `platform.friends.com`ーザーに代わ `platform.friends.com` って友達アプリで投稿できるようになります。

サードパーティcookieを使用しないでこの使用事例を実現する方法を少し考えると、ユーザーは多くの手動手順に従う必要があります。 まず、ユーザーはニュース記事へのリンクをコピーする必要があります。 2つ目は、ユーザーは別々にFriendsアプリにログインする必要がある場合です。 次に、「投稿を作成」ボタンをクリックします。 その後、ユーザーはテキストフィールドにリンクをコピーして貼り付け、最後に「投稿」をクリックします。 ご覧の通り、サードパーティcookieは、手動の手順を大幅に減らすことができるので、ユーザーにとって非常に役立ちます。

一般に、サードパーティcookieを使用すると、ユーザーがWebサイトを明示的に訪問する必要なく、ユーザーのブラウザーにデータを保存できます。

## セキュリティ上の懸念

cookieはユーザーエクスペリエンスと電力広告を強化しますが、クロスサイト要求偽造(CSRF)攻撃などのセキュリティの脆弱性が発生する可能性もあります。 例えば、ユーザーがクレジットカードの請求書を支払うために銀行サイトにログインし、ログアウトせずにサイトを離れ、同じセッションで悪意のあるサイトを閲覧した場合、CSRF攻撃が発生する可能性があります。 悪質なサイトには、ページの読み込み時に実行される、銀行サイトにリクエストを行うコードが含まれる場合があります。 ユーザーは依然としてバンキングサイトに対して認証されるので、セッションcookieを使用してCSRF攻撃を開始し、ユーザーの銀行口座から資金移動イベントを開始できます。 これは、サイトを訪問するたびに、すべてのcookieがHTTPリクエストに添付されるからです。 セキュリティ上の懸念から、Googleは現在、セキュリティを軽減しようとしています。

## Targetでcookieを使用する方法

以上の点で、cookieの使用方法を見てみま [!DNL Target] しょう。 まず、JavaScriptライブラリをサ [!DNL Target] イトにインストールする必要が [!DNL Target] あります。 これにより、サイトを訪問するユーザのブラウザにファーストパーティCookieを配置できます。 ユーザーがWebサイトを操作するときに、ユーザーの行動と関心のデータをJavaScriptライブラリ [!DNL Target] に渡すことができます。 JavaScriptラ [!DNL Target] イブラリは、ファーストパーティcookieを使用して、ユーザーに関する識別情報を抽出し、ユーザーの行動と関心データにマッピングします。 このデータは、パーソナライゼーションアクティビティ [!DNL Target] を実行するためにに使用されます。

Targetでも（場合によっては）サードパーティcookieを使用します。 異なるドメインに存在する複数のWebサイトを所有し、それらのWebサイト間のユーザーの移動を追跡する場合は、クロスドメイン追跡を利用してサードパーティcookieを使用できます。 JavaScriptライブラリでクロスドメイン追跡を有効にす [!DNL Target] ると、アカウントでサードパーティcookieの使用が開始されます。 ユーザーがドメイン間をホップすると、ブラウザーはのバックエンドサーバーと通信し、このプロセスでは、サードパーティcookieが作成され、ユーザーのブラウザーに配置されます。 [!DNL Target]ユーザーのブラウザー上に存在するサードパーティCookieを通じて、1人のユーザーに対し [!DNL Target] て異なるドメイン間で一貫したエクスペリエンスを提供できます。

## Googleの新しいcookieレシピ

Googleは、SameSiteと呼ばれるIETF標準のサポートを追加し、Set-CookieヘッダーにSameSite属性コンポーネントを使用してCookieを管理する必要があるので、Cookieがサイト間で送信される際の保護を提供します。

Strict、Lax または None の 3 つの異なる値を SameSite 属性に渡すことができます。

| 値 | 説明 |
| --- | --- |
| Strict | この設定を含む cookie には、最初に設定されたドメインへの訪問時にのみアクセスできます。つまり、Strict は、サイト全体で cookie の使用を完全にブロックします。このオプションは、銀行など、高いセキュリティを必要とするアプリケーションに最適です。 |
| Lax | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, like `HTTP GET`. したがって、このオプションは、cookieがサードパーティで使用できる場合に使用されますが、CSRF攻撃による被害を防ぐセキュリティ上の利点が追加されている場合に使用されます。 |
| None | この設定のCookieは、今日のCookieと同じように機能します。 |

上記の点に留意して、Chrome 80ではユーザーに対して2つの独立した設定が導入されています。"SameSite by default cookies"と"SameSiteを使用しないcookieはセキュリティで保護する必要があります。" これらの設定は、Chrome 80ではデフォルトで有効になります。

![SameSiteダイアログボックス](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **SameSite by default cookie**:設定すると、SameSite属性を指定しないすべてのCookieが自動的に使用されます `SameSite = Lax`。
* **SameSiteを使用しないCookieはセキュリティで保護する必要があります**。設定する場合、SameSite属性を持たないCookieまたはセキュリティで保護され `SameSite = None` ているCookieが必要です。 セキュアとは、このコンテキストでは、すべてのブラウザーリクエストが HTTPS プロトコルに従う必要があることを意味します。この要件に準拠しない cookie は拒否されます。この要件を満たすには、すべてのWebサイトでHTTPSを使用する必要があります。

## Google のセキュリティのベストプラクティスに従う Target

アドビでは、セキュリティとプライバシーに関する業界の最新のベストプラクティスを常にサポートしたいと考えています。 We are happy to announce that [!DNL Target] supports the new security and privacy settings introduced by Google.

「SameSite by default cookies」設定では、ユーザーが影響を与え [!DNL Target] たり介入したりすることなく、引き続きパーソナライゼーションを提供します。 [!DNL Target]Google Chrome によってフラグ `SameSite = Lax` が適用されるので、 はファーストパーティ cookie を使用し、引き続き適切に機能します。

「同じサイトのないcookieはセキュリティで保護する必要があります」オプションで、のクロスドメイン追跡機能をオプトインしない場合、でのファーストパーティcookieは引き続き [!DNL Target][!DNL Target] 機能します。

However, when you opt-in to use cross-domain tracking to leverage [!DNL Target] across multiple domains, Chrome requires `SameSite = None` and Secure flags to be used for third-party cookies. つまり、サイトでHTTPSプロトコルを使用していることを確認する必要があります。 のクライアント側ライブラ [!DNL Target] リは、自動的にHTTPSプロトコルを使用し、すべてのアクティビティが引き続き配信されるように、 `SameSite = None` およびセキュアフラグをサードパーティcookieに [!DNL Target] 付加します。

## 必要なアクション

Google Chrome 80以降のユーザーが引き続き使 [!DNL Target] 用する必要がある作業を理解するには、次の表を参照してください。次の列が表示されます。

* **Target javaScript Library**:mbox.jsを使用している場合は、at.js 1。*x* または at.js 2.*xを設定します* 。
* **SameSite by default cookies = Enabled**:ユーザーが「デフォルトで同じサイトのCookie」を有効にしている場合、その影響と、作業を続けるために必要な操作が [!DNL Target] あります。
* **SameSiteを使用しないcookieはセキュア=有効にする**:ユーザーが「同じサイトのないcookieはセキュリティで保護する必要があります」を有効にしている場合、その影響と、作業を続けるために必要な作業が何かあ [!DNL Target] りますか。

| Target javaScriptライブラリ | SameSite by default cookies = 有効 | Cookies without SameSite must be secure = 有効 |
| --- | --- | --- |
| mbox.jsをファーストパーティcookieのみで使用する。 | 影響なし。 | クロスドメイントラッキングを使用しない場合は、影響はありません。 |
| mbox.jsでクロスドメイントラッキングが有効になっている。 | 影響なし。 | サイトでHTTPSプロトコルを有効にする必要があります。<br>[!DNL Target] はサードパーティcookieを使用してユーザーを追跡し、Googleはサードパーティcookieに「保護」フラグを設定する `SameSite = None` 必要があります。 セキュアフラグを使用するには、サイトでHTTPSプロトコルを使用する必要があります。 |
| at.js 1.*x* ファーストパーティcookieを使用する場合。 | 影響なし。 | クロスドメイントラッキングを使用しない場合は、影響はありません。 |
| at.js 1.*x* クロスドメイントラッキングを有効にした場合。 | 影響なし。 | サイトでHTTPSプロトコルを有効にする必要があります。<br>[!DNL Target] はサードパーティcookieを使用してユーザーを追跡し、Googleはサードパーティcookieに「保護」フラグを設定する `SameSite = None` 必要があります。 セキュアフラグを使用するには、サイトでHTTPSプロトコルを使用する必要があります。 |
| at.js 2.*x* | 影響なし。 | 影響なし。 |

## Targetで必要な操作

新しいGoogle Chrome 80+ sameSite cookieポリシーに準拠するために、アドビのプラットフォームで必要な操作は何ですか。

| Target javaScriptライブラリ | SameSite by default cookies = 有効 | Cookies without SameSite must be secure = 有効 |
| --- | --- | --- |
| mbox.jsをファーストパーティcookieのみで使用する。 | 影響なし。 | クロスドメイントラッキングを使用しない場合は、影響はありません。 |
| mbox.jsでクロスドメイントラッキングが有効になっている。 | 影響なし。 | [!DNL Target] サーバ `SameSite = None` ーが呼び出されるときに、サードパーティcookieに保護フラグ [!DNL Target] が追加されます。 |
| at.js 1.*x* ファーストパーティcookieを使用する場合。 | 影響なし。 | クロスドメイントラッキングを使用しない場合は、影響はありません。 |
| at.js 1.*x* クロスドメイントラッキングを有効にした場合。 | 影響なし。 | at.js 1.*x* クロスドメイントラッキングを有効にした場合。 |
| at.js 2.*x* | 影響なし。 | 影響なし。 |

## HTTPSプロトコルを使用しない場合の影響は何ですか。

影響を与える唯一の使用例は、mbox.jsまたはat.js 1でクロスドメイントラッキング機能 [!DNL Target] を使用している場合です。*x* ではサポートされていませんでした。Googleが必要とするHTTPSに移動しないと、Googleが使用するサードパーティcookieがGoogleによって破棄されるので、ドメイン間での実訪問者数が急増します。 また、サードパーティCookieが破棄されるので、ユーザーがドメイン間を移動する際に、そのユーザーに対して一貫性のあるパーソナライズされたエクスペリエンスを提供することはできません。 [!DNL Target] サードパーティCookieは、主に、所有するドメイン間を移動する単一のユーザーを識別するために使用されます。

## まとめ

業界は、より安全な消費者向けWebを作成するために努力しており、エンドユーザーのセキュリティとプライバシーを確保する方法で、お客様がパーソナライズされたエクスペリエンスを提供できるように努めています。 [!DNL Adobe] 必要なのは、前述のベストプラクティスに従って、Google Chromeの新しいSameSite cookieポリシーに準拠す [!DNL Target] るための利点を活用することだけです。
