---
keywords: google;samesite;cookie;chrome 80;ietf
description: Adobe [!DNL Target] は、Google Chrome バージョン 80 で導入された SameSite IETF 標準を処理し、これらのポリシーに準拠するために必要な操作を示します。
title: 方法 [!DNL Target] Googleの SameSite Cookie ポリシーを処理しますか？
feature: Privacy & Security
role: Developer
exl-id: 5abd2065-3692-4a6d-9ac9-6d416604c2d2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1948'
ht-degree: 7%

---

# Google Chrome SameSite cookie ポリシー

Googleは、2020 年初頭にリリースされる予定の Chrome 80 以降のユーザーに対し、デフォルトで新しい cookie ポリシーの適用を開始します。 この記事では、新しい SameSite cookie ポリシーに関して知っておく必要のあるすべてと、その方法について説明します [!DNL Adobe Target] は、これらのポリシーをサポートし、使用する方法を示しています。 [!DNL Target] Google Chrome の新しい SameSite cookie ポリシーに準拠するため。

Chrome 80 以降、Web 開発者は、Web サイト全体で機能する cookie を明示的に指定する必要があります。 これは、Googleが Web 上のプライバシーとセキュリティを改善するために計画している多くのお知らせの最初のものです。

facebookがプライバシーとセキュリティに関して注目を集めていることを踏まえると、AppleやGoogleなど他の主要プレーヤーは、プライバシーとセキュリティのチャンピオンとして新しい ID を作成する機会をすぐに利用できます。 Appleは、今年初めに ITP 2.1 および最近の ITP 2.2 を通じて Cookie ポリシーの変更を発表し、Cookie を最初に Cookie を主導しました。ITP 2.1 では、Appleはサードパーティ Cookie を完全にブロックし、ブラウザーで作成された Cookie を 7 日間に保持します。 ITP 2.2 では、Cookie は 1 日のみ保持されます。 Googleの発表は、Appleの発表ほど積極的ではありませんが、同じ目標を達成するための第一歩です。 Appleポリシーについて詳しくは、 [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

## Cookie とは何ですか？また、Cookie の使用方法も教えてください。

Googleの cookie ポリシーに対する変更点に取り組む前に、cookie の概要と使用方法について説明します。 簡単に言えば、cookie とは、ユーザー属性を記憶するために使用される、Web ブラウザーに保存される小さなテキストファイルです。

Cookie は、Web 閲覧時のユーザーエクスペリエンスを向上させるので、重要です。 例えば、e コマース Web サイトで買い物をしていて、買い物かごに何かを追加しても、その訪問でログインしたり購入しない場合、Cookie は品目を記憶し、次回の訪問用に買い物かごに入れておきます。 あるいは、お気に入りのソーシャルメディア Web サイトを訪問するたびに、ユーザ名とパスワードを再入力しなければならなかった場合を考えてみましょう。 cookie は、サイトが自分を識別するのに役立つ情報を保存するので、この問題も解決します。 この種の cookie は、訪問した Web サイトで作成および使用されるので、ファーストパーティ cookie と呼ばれます。

サードパーティ Cookie も存在します。 これらをよりよく理解するために、次の例を考えてみましょう。

例えば、「友人」と呼ばれる仮のソーシャルメディア会社が「共有」ボタンを提供し、他のサイトが実装して、友人ユーザーが友人フィードでサイトのコンテンツを共有できるようにするとします。 これで、ユーザーは「共有」ボタンを使用しているニュース Web サイトのニュース記事を読み、それをクリックして、自分の友達アカウントに自動的に投稿するようになりました。

これを実現するために、ブラウザーは次の場所から「友達と共有」ボタンを取得します： `platform.friends.com` ニュース記事が読み込まれたとき このプロセスでは、ブラウザーは、ユーザーのログイン資格情報を含む Friends Cookie を Friends サーバーにリクエストに添付します。 これにより、Friends は、ユーザーがログインしなくても、そのユーザーに代わってフィードにニュース記事を投稿できます。

これはすべて、サードパーティ Cookie を使用することで可能になります。 この場合、サードパーティ Cookie は次の用にブラウザーに保存されます。 `platform.friends.com`で、 `platform.friends.com` は、ユーザーに代わって Friends アプリで投稿を作成できます。

サードパーティ Cookie を使用せずにこの使用例を実現する方法を考えている場合、ユーザーは手動で多くの手順を実行する必要があります。 まず、ユーザーはニュース記事へのリンクをコピーする必要があります。 次に、ユーザーは別々に Friends アプリにログインする必要があります。 次に、「投稿を作成」ボタンをクリックします。 次に、ユーザーがテキストフィールドにリンクをコピーして貼り付け、最後に「投稿」をクリックします。 ご覧のように、サードパーティ cookie は手動の手順を大幅に減らすことができるので、ユーザーエクスペリエンスを非常に助けます。

より一般的に、サードパーティ Cookie を使用すると、ユーザーが Web サイトに明示的にアクセスしなくても、ユーザーのブラウザーにデータを保存できます。

## セキュリティ上の問題

cookie はユーザーエクスペリエンスとパワー広告を強化しますが、クロスサイトリクエストフォージェリ (CSRF) 攻撃などのセキュリティの脆弱性を導入する場合もあります。 例えば、ユーザーが銀行サイトにログインしてクレジットカードの請求を支払い、ログアウトせずにサイトを離れ、同じセッションで悪意のあるサイトを閲覧すると、CSRF 攻撃が発生する可能性があります。 悪意のあるサイトには、ページの読み込み時に実行されるバンキングサイトに対して要求を行うコードが含まれている場合があります。 ユーザーは依然としてバンキングサイトに対して認証されているので、セッション cookie を使用して CSRF 攻撃を開始し、ユーザーの銀行口座から資金移動イベントを開始することができます。 これは、サイトを訪問するたびに、すべての Cookie が HTTP リクエストに添付されるからです。 これらのセキュリティ上の問題のため、Googleは現在、セキュリティを軽減しようとしています。

## 方法 [!DNL Target] cookie を使用しますか？

とはいえ、どうやって [!DNL Target] は cookie を使用します。 お客様が [!DNL Target] まず、 [!DNL Target] サイト上の JavaScript ライブラリ。 これにより、ファーストパーティ Cookie をサイトの訪問者のブラウザーに配置できます。 ユーザーが Web サイトを操作する際に、ユーザーの行動と興味のデータをに渡すことができます。 [!DNL Target] JavaScript ライブラリを使用する。 この [!DNL Target] JavaScript ライブラリは、ファーストパーティ cookie を使用して、ユーザーに関する識別情報を抽出し、ユーザーの行動と興味データにマッピングします。 このデータは、 [!DNL Target] パーソナライゼーションアクティビティを強化します。

Target も（場合によって）サードパーティ Cookie を使用します。 異なるドメインに存在する複数の Web サイトを所有し、それらの Web サイトをまたいでユーザージャーニーを追跡する場合、クロスドメイントラッキングを活用してサードパーティ Cookie を使用できます。 でクロスドメイントラッキングを有効にする [!DNL Target] JavaScript ライブラリに保存する場合、お使いのアカウントはサードパーティ Cookie を使用し始めます。 ユーザーがドメイン間をホップすると、ブラウザーは、 [!DNL Target]を作成し、その結果、サードパーティ Cookie がユーザーのブラウザーに配置されます。 ユーザーのブラウザーに存在するサードパーティ Cookie を通じて、 [!DNL Target] は、1 人のユーザーに対して、異なるドメイン間で一貫したエクスペリエンスを提供できます。

## Googleの新しい cookie レシピ

Googleでは、ユーザーを保護するために、サイト間で cookie が送信される際の保護を提供するために、Set-Cookie ヘッダーの SameSite 属性コンポーネントで cookie を管理する必要がある、SameSite と呼ばれる IETF 標準のサポートを追加する予定です。

Strict、Lax または None の 3 つの異なる値を SameSite 属性に渡すことができます。

| 値 | 説明 |
| --- | --- |
| Strict | この設定を含む cookie には、最初に設定されたドメインへの訪問時にのみアクセスできます。つまり、Strict は、サイト全体で cookie の使用を完全にブロックします。このオプションは、銀行など、高いセキュリティを必要とするアプリケーションに最適です。 |
| Lax | この設定を含む cookie は、次のような非べき等 HTTP リクエストを含む同じサイトのリクエストまたはトップレベルナビゲーションに対してのみ送信されます。 `HTTP GET`. したがって、このオプションは、Cookie がサードパーティによって使用できる場合に使用されますが、セキュリティ上のメリットが強化され、CSRF 攻撃による被害からユーザーを保護します。 |
| None | この設定を含む cookie は、現在機能する cookie と同じように機能します。 |

上記を念頭に置いて、Chrome 80 では、ユーザーに対して次の 2 つの独立した設定が導入されています。&quot;SameSite by default cookies&quot;と&quot;Cookies without SameSite must be secure&quot; これらの設定は、Chrome 80 でデフォルトで有効になります。

![SameSite ダイアログボックス](/help/main/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **SameSite by default cookies**:設定すると、SameSite 属性を指定していないすべての cookie が自動的に `SameSite = Lax`.
* **Cookies without SameSite must be secure**:設定すると、SameSite 属性のない cookie、または `SameSite = None` セキュアである必要があります。 セキュアとは、このコンテキストでは、すべてのブラウザーリクエストが HTTPS プロトコルに従う必要があることを意味します。この要件に準拠しない cookie は拒否されます。この要件を満たすには、すべての Web サイトで HTTPS を使用する必要があります。

## Google のセキュリティのベストプラクティスに従う Target

Adobe時には、常に業界の最新のセキュリティおよびプライバシーベストプラクティスをサポートしたいと考えています。 我々は喜んで発表する [!DNL Target] は、Googleが導入した新しいセキュリティおよびプライバシー設定をサポートしています。

「SameSite by default cookies」設定の場合、 [!DNL Target] は引き続きパーソナライゼーションを配信し、ユーザーの影響や介入は不要です。 [!DNL Target]Google Chrome によってフラグ `SameSite = Lax` が適用されるので、 はファーストパーティ cookie を使用し、引き続き適切に機能します。

のクロスドメイントラッキング機能をオプトインしない場合は、「Cookies without SameSite must be secure」オプションで [!DNL Target]、でファーストパーティ Cookie を使用する [!DNL Target] が引き続き機能します。

ただし、 [!DNL Target] 複数のドメインをまたいで、Chrome では `SameSite = None` および Secure フラグをサードパーティ cookie に使用するために使用します。 つまり、サイトで HTTPS プロトコルを使用する必要があります。 のクライアントサイドライブラリ [!DNL Target] が自動的に HTTPS プロトコルを使用し、 `SameSite = None` およびでのセキュアフラグをサードパーティ Cookie に設定 [!DNL Target] すべてのアクティビティが引き続き配信されるようにします。

## 必要なアクション

必要な作業を理解するには [!DNL Target] Google Chrome 80 以降のユーザーに対しても引き続き動作します。以下の表を参照してください。そのうち、次の列が表示されます。

* **Target JavaScript ライブラリ**:at.js 1.*x* または at.js 2.*x* 」を選択します。
* **SameSite by default cookies =有効**:ユーザーが「SameSite by default cookies」を有効にしている場合、どれくらい影響を及ぼすか、および次の点で何らかの作業が必要です： [!DNL Target] 動き続けるために
* **Cookies without SameSite must be secure =有効**:ユーザーが「Cookies without SameSite must be secure」を有効にしている場合、どれくらい影響を及ぼすか、および必要な作業は何か [!DNL Target] 引き続き機能します。

| Target JavaScript ライブラリ | SameSite by default cookies = 有効 | Cookies without SameSite must be secure = 有効 |
| --- | --- | --- |
| at.js 1.*x* をファーストパーティ cookie に設定します。 | 影響なし | クロスドメイントラッキングを使用していない場合は影響しません。 |
| at.js 1.*x* クロスドメイントラッキングを有効にした状態。 | 影響なし | サイトで HTTPS プロトコルを有効にする必要があります。<br>[!DNL Target] はサードパーティ cookie を使用してユーザーを追跡し、Googleはサードパーティ cookie に `SameSite = None` セキュアフラグ。 Secure フラグを使用するには、サイトで HTTPS プロトコルを使用する必要があります。 |
| at.js 2.*x* | 影響なし | 影響なし |

## 機能 [!DNL Target] 必要な操作

新しいGoogle Chrome 80 以降の SameSite cookie ポリシーに準拠するには、プラットフォームで何をおこなう必要がありましたか？

| Target JavaScript ライブラリ | SameSite by default cookies = 有効 | Cookies without SameSite must be secure = 有効 |
| --- | --- | --- |
| at.js 1.*x* をファーストパーティ cookie に設定します。 | 影響なし | クロスドメイントラッキングを使用していない場合は影響しません。 |
| at.js 1.*x* クロスドメイントラッキングを有効にした状態。 | 影響なし | at.js 1.*x* クロスドメイントラッキングを有効にした状態。 |
| at.js 2.*x* | 影響なし | 影響なし |

## HTTPS プロトコルを使用してに移行しない場合、どのような影響がありますか？

影響を受ける唯一の使用例は、 [!DNL Target] at.js 1.*x* では、標準設定ではサポートされていません。Googleで必要な HTTPS に移行しないと、使用するサードパーティ Cookie はGoogleによって破棄されるので、ドメインをまたいだ個別訪問者数が急増します。 また、サードパーティ Cookie は破棄されるので、 [!DNL Target] は、ユーザーがドメイン間を移動する際に、そのユーザーに対して一貫性のあるパーソナライズされたエクスペリエンスを提供できなくなります。 サードパーティ Cookie は、主に、所有するドメイン間を移動する単一のユーザーを識別するために使用されます。

## まとめ

業界は、消費者向けにより安全な Web を作成する方向に進んでいます。 [!DNL Adobe] は、エンドユーザーに対してセキュリティとプライバシーを確保する方法で、顧客がパーソナライズされたエクスペリエンスを提供するのを支援することに全力で取り組んでいます。 必要な操作は、前述のベストプラクティスに従って、 [!DNL Target] Google Chrome の新しい SameSite cookie ポリシーに準拠するため。
