---
keywords: google;samesite;cookie;chrome 80;ietf
description: Adobe [!DNL Target] がGoogle Chromeバージョン80で導入されたSameSite IETF標準をどのように処理するか、およびこれらのポリシーに準拠するために何をする必要があるかを説明します。
title: ' [!DNL Target] はGoogleのSamesite Cookieポリシーをどのように処理しますか。'
feature: プライバシーとセキュリティ
role: Developer
exl-id: 5abd2065-3692-4a6d-9ac9-6d416604c2d2
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '1950'
ht-degree: 7%

---

# Google Chrome SameSite cookie ポリシー

Googleは、2020年初頭にリリース予定のChrome 80以降のユーザーに対し、デフォルトで新しいcookieポリシーの適用を開始します。 この記事では、新しいSameSite cookieポリシー、[!DNL Adobe Target]によるこれらのポリシーのサポート、および[!DNL Target]を使用してGoogle Chromeの新しいSameSite cookieポリシーに準拠する方法について、必要なすべての情報を説明します。

Chrome 80以降、Web開発者は、Webサイト全体で機能するCookieを明示的に指定する必要があります。 これは、GoogleがWeb上のプライバシーとセキュリティを改善するために計画している多くのお知らせの中で最初のものです。

facebookがプライバシーとセキュリティに関して注目を集めていることを考えると、AppleやGoogleなどの他の主要プレーヤーは、プライバシーとセキュリティのチャンピオンとしての新しいアイデンティティを生み出す機会をすぐに利用できます。 Appleは、今年初めにITP 2.1および最近のITP 2.2を通じてCookieポリシーの変更を発表し、Appleを導入しました。ITP 2.1では、サードパーティCookieを完全にブロックし、Cookieをブラウザーに7日間のみ保持します。 ITP 2.2では、Cookieは1日のみ保持されます。 Googleの発表は、Appleの発表と同じように積極的なものではありませんが、同じ目標を達成するための第一歩です。 Appleのポリシーについて詳しくは、 [Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)を参照してください。

## Cookieとは何ですか？また、Cookieの使用方法も教えてください。

Googleのcookieポリシーに対する変更点に取り組む前に、Cookieの概要とその使い方を見てみましょう。 簡単に言うと、cookieは、ユーザー属性を記憶するために使用される、Webブラウザーに格納される小さなテキストファイルです。

Cookieは、Webを閲覧するユーザーのエクスペリエンスを強化するので、重要です。 例えば、eコマースWebサイトで買い物をしていて、買い物かごに何かを追加しても、その訪問でサインインや購入が行われない場合、Cookieは品目を記憶し、次回の訪問用に買い物かごに入れておく必要があります。 また、好きなソーシャルメディアのWebサイトを訪問するたびに、ユーザー名とパスワードを再入力する必要が生じたとします。 Cookieは、サイトが自分が何者であるかを識別するのに役立つ情報を保存するので、この問題も解決します。 この種のCookieは、訪問したWebサイトで作成および使用されるので、ファーストパーティCookieと呼ばれます。

サードパーティCookieも存在します。 詳しく理解するために、次の例を考えてみましょう。

例えば、「友達」と呼ばれる仮のソーシャルメディア会社が、他のサイトに「共有」ボタンを実装して、友達ユーザーが友達フィードでサイトのコンテンツを共有できるようにするとします。 ユーザーが「共有」ボタンを使用しているニュースWebサイトのニュース記事を読み、それをクリックして自動的に友達アカウントに投稿するようになりました。

これを実現するために、ブラウザーはニュース記事が読み込まれたときに`platform.friends.com`から「フレンド共有」ボタンを取得します。 このプロセスでは、ブラウザーは、ユーザーのログイン資格情報を含むFriends CookieをFriendsサーバーにリクエストに添付します。 これにより、Friendsは、ユーザーにログインを求めることなく、ニュース記事をユーザーに代わってフィードに投稿できます。

これはすべて、サードパーティCookieを使用することで可能です。 この場合、サードパーティCookieは`platform.friends.com`のブラウザーに保存され、`platform.friends.com`がユーザーに代わってFriendsアプリで投稿できるようになります。

サードパーティCookieを使用せずにこの使用例を実現する方法を考えてみると、ユーザーは多くの手動手順に従う必要があります。 まず、ユーザーはニュース記事へのリンクをコピーする必要があります。 次に、ユーザーはFriendsアプリに個別にログインする必要があります。 次に、「投稿を作成」ボタンをクリックします。 次に、ユーザーがテキストフィールドにリンクをコピーして貼り付け、最後に「投稿」をクリックします。 ご覧のように、サードパーティCookieは手動の手順を大幅に減らすことができるので、ユーザーエクスペリエンスを非常に助けます。

より一般的に、サードパーティCookieを使用すると、ユーザーがWebサイトに明示的にアクセスしなくても、ユーザーのブラウザーにデータを保存できます。

## セキュリティ上の懸念

cookieはユーザーエクスペリエンスとパワー広告を強化しますが、クロスサイトリクエストフォージェリ(CSRF)攻撃などのセキュリティの脆弱性を導入する場合もあります。 例えば、ユーザーが銀行サイトにログインしてクレジットカードの請求書を支払い、ログアウトせずにサイトを離れ、同じセッションで悪意のあるサイトを閲覧すると、CSRF攻撃が発生する可能性があります。 悪意のあるサイトには、ページの読み込み時に実行されるバンキングサイトに対して要求を行うコードが含まれている場合があります。 ユーザーは依然としてバンキングサイトで認証されているので、セッションcookieを使用してCSRF攻撃を開始し、ユーザーの銀行口座から資金移動イベントを開始できます。 これは、サイトを訪問するたびに、すべてのCookieがHTTPリクエストに添付されるからです。 こうしたセキュリティ上の問題から、Googleは現在、セキュリティを軽減しようとしています。

## [!DNL Target]はCookieをどのように使用しますか？

とはいえ、[!DNL Target]がcookieをどのように使うかを見てみましょう。 まず[!DNL Target]を使用するには、サイトに[!DNL Target] JavaScriptライブラリをインストールする必要があります。 これにより、ファーストパーティCookieをサイトを訪問するユーザーのブラウザーに配置できます。 ユーザーがWebサイトとやり取りする際に、JavaScriptライブラリを通じてユーザーの行動と関心のデータを[!DNL Target]に渡すことができます。 [!DNL Target] JavaScriptライブラリは、ファーストパーティcookieを使用して、ユーザーに関する識別情報を抽出し、ユーザーの行動と関心データにマッピングします。 このデータは、 [!DNL Target]によってパーソナライゼーションアクティビティを強化するために使用されます。

また、TargetではサードパーティCookieが使用されることもあります。 異なるドメインに存在する複数のWebサイトを所有し、それらのWebサイトをまたいでユーザージャーニーを追跡する場合、クロスドメイントラッキングを活用してサードパーティCookieを使用できます。 [!DNL Target] JavaScriptライブラリでクロスドメイントラッキングを有効にすると、アカウントでサードパーティCookieの使用が開始されます。 ユーザーがドメイン間をホップすると、ブラウザーは[!DNL Target]のバックエンドサーバーと通信し、このプロセスでサードパーティCookieが作成され、ユーザーのブラウザーに配置されます。 ユーザーのブラウザー上に存在するサードパーティCookieを使用すると、[!DNL Target]は、1人のユーザーに対して、異なるドメイン間で一貫したエクスペリエンスを提供できます。

## Googleの新しいcookieレシピ

Googleは、ユーザーが保護されるように、サイト間でcookieが送信されるタイミングを保護するために、SameSiteと呼ばれるIETF標準のサポートを追加する予定です。Set-CookieヘッダーのSameSite属性コンポーネントを使用してCookieを管理する必要があります。

Strict、Lax または None の 3 つの異なる値を SameSite 属性に渡すことができます。

| 値 | 説明 |
| --- | --- |
| Strict | この設定を含む cookie には、最初に設定されたドメインへの訪問時にのみアクセスできます。つまり、Strict は、サイト全体で cookie の使用を完全にブロックします。このオプションは、銀行など、高いセキュリティを必要とするアプリケーションに最適です。 |
| Lax | この設定を含むcookieは、`HTTP GET`のような、同じサイトのリクエストまたは非べき等HTTPリクエストを含むトップレベルナビゲーションに対してのみ送信されます。 したがって、このオプションは、サードパーティによってCookieが使用できる場合に使用されますが、CSRF攻撃による被害からユーザーを保護する追加のセキュリティ上のメリットがあります。 |
| None | この設定を含むcookieは、現在のcookieと同じように機能します。 |

上記を念頭に置いて、Chrome 80では、ユーザー向けに2つの独立した設定が導入されています。「SameSite by default cookies」と「Cookies without SameSite must be secure」 これらの設定は、Chrome 80ではデフォルトで有効になります。

![SameSiteダイアログボックス](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **SameSite by default cookies**:設定すると、SameSite属性を指定していないすべてのcookieが自動的に使用されま `SameSite = Lax`す。
* **Cookies without SameSite must be secure**（SameSiteを使用しないCookieはセキュリティで保護する必要がある）:設定すると、SameSite属性のないcookieまたはをセキュアにす `SameSite = None` る必要があります。セキュアとは、このコンテキストでは、すべてのブラウザーリクエストが HTTPS プロトコルに従う必要があることを意味します。この要件に準拠しない cookie は拒否されます。この要件を満たすには、すべてのWebサイトでHTTPSを使用する必要があります。

## Google のセキュリティのベストプラクティスに従う Target

Adobeでは、常に、セキュリティとプライバシーに関する業界の最新のベストプラクティスをサポートしたいと考えています。 [!DNL Target]は、Googleが導入した新しいセキュリティとプライバシー設定をサポートしています。

「SameSite by default cookies」設定の場合、[!DNL Target]は引き続きパーソナライゼーションを提供し、ユーザーの影響や介入を受けません。 [!DNL Target]Google Chrome によってフラグ `SameSite = Lax` が適用されるので、 はファーストパーティ cookie を使用し、引き続き適切に機能します。

「Cookies without SameSite must be secure」オプションについて、[!DNL Target]のクロスドメイントラッキング機能をオプトインしない場合、[!DNL Target]のファーストパーティcookieは引き続き機能します。

ただし、クロスドメイントラッキングの使用をオプトインして複数のドメインで[!DNL Target]を活用する場合、Chromeではサードパーティcookieで使用するために`SameSite = None`およびSecureフラグが必要です。 つまり、サイトでHTTPSプロトコルを使用する必要があります。 [!DNL Target]のクライアント側ライブラリは、自動的にHTTPSプロトコルを使用し、[!DNL Target]のサードパーティCookieに`SameSite = None`およびSecureフラグを添付して、すべてのアクティビティが引き続き配信されるようにします。

## 必要なアクション

Google Chrome 80以降のユーザーで引き続き[!DNL Target]を機能させるために必要な操作を理解するには、以下の表を参照してください。次の列が表示されます。

* **Target JavaScriptライブラリ**:at.js 1.** at.js 2.** をサイトに追加します。
* **SameSite by default cookies =有効**:ユーザーが「SameSite by default cookies」を有効にしている場合、その影響と、作業を続行するためにおこなう必要がある [!DNL Target] ことは何か。
* **Cookies without SameSite must be secure =有効**:ユーザーが「Cookies without SameSite must be secure」を有効にしている場合、その影響と、引き続き機能するために必要な事項は何か [!DNL Target] です。

| Target JavaScriptライブラリ | SameSite by default cookies = 有効 | Cookies without SameSite must be secure = 有効 |
| --- | --- | --- |
| at.js 1.*x* をファーストパーティcookieに置き換えます。 | 影響なし | クロスドメイントラッキングを使用しない場合は影響しません。 |
| at.js 1.*x* （クロスドメイントラッキングが有効な場合） | 影響なし | サイトに対してHTTPSプロトコルを有効にする必要があります。<br>[!DNL Target] はサードパーティcookieを使用してユーザーを追跡し、Googleはサードパーティcookieに対してとセキュアフラグを `SameSite = None` 持つよう要求します。Secureフラグを使用するには、サイトでHTTPSプロトコルを使用する必要があります。 |
| at.js 2.*x* | 影響なし | 影響なし |

## [!DNL Target]には何が必要ですか？

新しいGoogle Chrome 80以降のSameSite cookieポリシーを遵守するために、アドビのプラットフォームでは何をする必要がありましたか？

| Target JavaScriptライブラリ | SameSite by default cookies = 有効 | Cookies without SameSite must be secure = 有効 |
| --- | --- | --- |
| at.js 1.*x* をファーストパーティcookieに置き換えます。 | 影響なし | クロスドメイントラッキングを使用しない場合は影響しません。 |
| at.js 1.*x* （クロスドメイントラッキングが有効な場合） | 影響なし | at.js 1.*x* （クロスドメイントラッキングが有効な場合） |
| at.js 2.*x* | 影響なし | 影響なし |

## HTTPSプロトコルを使用しない場合、どのような影響がありますか。

影響を受ける唯一の使用例は、[!DNL Target]からat.js 1.*x* では、標準設定ではサポートされていません。Googleで必要なHTTPSに移行しないと、使用するサードパーティcookieはGoogleによって破棄されるので、ドメイン間の個別訪問者数の急増が発生します。 また、サードパーティCookieは破棄されるので、ユーザーがドメイン間を移動する際に、[!DNL Target]は、そのユーザーに対して一貫性のあるパーソナライズされたエクスペリエンスを提供できません。 サードパーティCookieは、主に、所有するドメイン間を移動する単一のユーザーを識別するために使用されます。

## まとめ

[!DNL Adobe]は、業界が消費者向けにより安全なWebを作成する方向に進んでおり、エンドユーザーのセキュリティとプライバシーを確保する方法でパーソナライズされたエクスペリエンスを提供するのを支援することに全力で取り組んでいます。 必要な操作は、前述のベストプラクティスに従い、[!DNL Target]を活用してGoogle Chromeの新しいSameSite Cookieポリシーに準拠することだけです。
