---
description: 以前のユーザーアクティビティまたは他のアルゴリズムに基づいて、顧客が興味を持つ可能性のある製品またはコンテンツを自動的に表示するTarget Recommendationsアクティビティの概要です。Recommendations により、顧客が関心を持ちそうな商品を積極的に紹介することが可能になります。
keywords: Recommendations;
seo-description: 以前のユーザーアクティビティまたは他のアルゴリズムに基づいて、顧客が興味を持つ可能性のある製品またはコンテンツを自動的に表示するAdobe Target Recommendationsアクティビティの概要です。Recommendations により、顧客が関心を持ちそうな商品を積極的に紹介することが可能になります。
seo-title: Adobe TargetのRecommendationsアクティビティの概要
solution: 'Target '
title: Recommendationsの概要
title-outputclass: premium
topic: Premium
badge: Premium
translation-type: tm+mt
source-git-commit: 04a4585e1d56f1754b65a248715fa5bdd4f8986f

---


# ![Premium](/help/assets/premium.png) Recommendationsの概要

The text in this article comes from the *Introduction to Recommendations* webinar, which you can view in its entirety below.

*Recommendationsの* ウェビナーの概要には、価値を活用するための詳細な調査が含ま [!DNL Adobe Target Recommendations]れています。この[!DNL Target]アクティビティが商品やコンテンツを自動的に表示する方法を見ていきます。これは、以前の訪問に基づきリアルタイムに提案を最適化することで、顧客の興味を引く可能性があります。さらに、段階を追って[!DNL Recommendations]アクティビティを構築するための [!DNL Target]UI についても詳しく見ていきます。

## はじめに

市販で表示されるレコメンデーションの種類についてはすべてわかります。多くのお客様は、このようなレコメンデーションを期待し、それらのレコメンデーションを出発点として使用して、他の利用可能なオプションを調べることができます。独自の買い物行動について考えてみると、このようなレコメンデーションはとても効果的です。ほとんどのユーザーは、レコメンデーションで最初に表示した製品（ストアにあるか、デジタルプロパティにあったか）を購入したことがあります。

次の図に、充電局、事例、ヘッドホンなど、新しい電話でよく購入されるアクセサリを示します。

![他のユーザーが購入したアクセサリを新しい電話で表示するレコメンデーション。](/help/c-recommendations/assets/intro-1.png)

しかし、デジタルファーストブランドのブランドが顧客の期待をどのように上げているかは、必ずしも考慮していません。より多くの場合、メディアとコンテンツの消費方法は、パーソナライズされたレコメンデーションによって推進されます。Netfix、SspifyまたはYouTubeを開いたときに表示される最初の内容について考えてみましょう。これらのブランドは、レコメンデーションで顧客体験を開始します。より代替可能な世界では、インタラクション時点で顧客にとって最も関連性の高いコンテンツを特定できることが非常に重要です。

![デジタルファーストブランドのレコメンデーション](/help/c-recommendations/assets/intro-2.png)

Marketers use [!DNL Adobe Target] to drive personalized experiences across a wide variety of industries, customer types, and channels.

[!DNL Adobe Target] パーソナライズされたコンテンツをどこでも配信できます。

![Targetが様々な場所でレコメンデーションをどのように配信するかを示す図](/help/c-recommendations/assets/intro-3.png)

* **投稿**:Web発行者は、記事をサイト訪問者にレコメンデーションし、エンゲージメントの増加を推進する [!DNL Target Recommendations] ために使用します。
* **ビデオチュートリアル**: [!DNL Adobe Creative Cloud] を [!DNL Target] 使用して、PhotoshopアプリケーションでPhotoshopユーザーにビデオチュートリアルを推奨します。
* **ゲーム**:ゲーム会社は、ゲームやコンテンツをコンソール上のユーザーに勧める [!DNL Target] ために使用します。
* **B2B販売**:企業間の企業は、ビデオ、ホワイトペーパー、ブログの投稿をB2Bの見込み客に勧める [!DNL Target] ために使用します。ダウンロード、ダウンロード、既存の顧客（https://theblog.adobe.com/testing-shifts-high-gear-intel)）にヘルプを提供します。
* **旅行**:ドイツ語の旅行ブックホルダーはホテルなどを旅行業者に勧める [!DNL Target] ために使用します（https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608)）。
* **小売**:主要なB2B小売業者は、トップ [!DNL Target] カテゴリと製品を推奨して、ブラウザーおよびモバイルアプリ（https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/)）で訪問者を再訪問することを推奨します。

これらは、顧客がパーソナライズされたレコメンデーションを配信するためにTargetを使用する方法のほんの一部です。

優れたレコメンデーションの原因

![優れたレコメンデーションを行う3つの要素を示す図](/help/c-recommendations/assets/intro-4.png)

優れたレコメンデーションは、関連性がありパーソナライズされている必要があります。つまり、関連性とパーソナライゼーションを3つの要因で推進する必要があります。

* **マーケティング担当者コントロール** を使用して、レコメンデーションされる品目の関連性を高めることができます。マーケティング担当者は、貴重なコンテキストを表に追加し、商品やコンテンツの属性がレコメンデーションモデルにとってどのような属性であるかを把握することができます。ビデオサイトを実行している場合、ユーザは同じ監督から映画を見たいと思っていることがありますが、同じスタジオによって生成された映画を見てはいけません。[!DNL Target] コントロールを使用すると、このドメイン情報を使用してアルゴリズムを強化できます。
* **カタログやインタラクションイベントで数百万もの項目を意味する高度なモデル** 。[!DNL Target] には、10年にわたって作成された高度な機械学習機能があり、数十億件のレコメンデーションを毎年処理しています。
* **レコメンデーションがタイムリーで、ユーザーに対して適切であることを確認するためのユーザーコンテキスト** 。単に誰かが買い物かごに追加したビデオやシャツをレコメンデーションしたくない。Targetのリッチユーザープロファイルは、パーソナライゼーションのためにレコメンデーションで使用できます。

## Target Recommendationsの実装

戦略から始めます。

![レコメンデーション戦略を示す図](/help/c-recommendations/assets/intro-5.png)

* **レコメンデーションする品目は何ですか。** まず、レコメンデーションする品目について考えてみましょう。これは製品、ビデオ、またはコンテンツです。
* **レコメンデーションを表示する場所を教えてください。** 次に、レコメンデーションを作成する場所について考えてみましょう。大まかなチャネル（Web、モバイル、店頭、キオスクなど）。顧客の遍歴のどの部分にレコメンデーションが含まれているか。サイト上のどのページにレコメンデーションが含まれているか。
* **レコメンデーションが成功したかどうかを判断するにはどうしますか。** レコメンデーションのないエクスペリエンスやレコメンデーションのエクスペリエンスを持っていない場合、または2種類のレコメンデーションがあるとします。どのエクスペリエンスが顧客にとってより優れたエクスペリエンスだったかを判断するにはどうしますか。指標の中には、他の指標よりも難しいものもあります。例えば、顧客ライフタイム値に対するレコメンデーションの影響は、多くの場合、直接到達するのが困難です。したがって、少ない抽象指標や、より具体的な指標（訪問あたりの売上高、平均注文額、クリック数など）をより簡単に把握できます。場合によっては、サポートコール数など、指標を最小限に抑えることが考えられます。

After you come up with your strategy, you are ready to start the implementation of [!DNL Target Recommendations].

recommendations実装の作成には、次の3つの手順があります。

![レコメンデーション実装を作成する手順を示す図](/help/c-recommendations/assets/intro-6.png)

1. Teach [!DNL Target] about your context or products.
1. ユーザーの行動をキャプチャします。
1. 適切なコンテキストでレコメンデーションを取得します。

### Teach [!DNL Target] about your context or products

When you start with [!DNL Recommendations], you pass information about every item you want to recommend. [!DNL Target] に、カタログを作成するための複数の統合オプションを用意します。

![コンテキストまたは製品についてTargetを学習する方法を示す図](/help/c-recommendations/assets/intro-7.png)

最も簡単で最も頻繁に使用される方法は、製品情報管理システムまたはコンテンツ管理システムから毎日または毎週CSVファイルを送信することです。[!DNL Adobe Target] しかし、JavaScriptライブラリを使用してページ上のデータレイヤーに情報を渡すことも、アドビのAPIを利用して情報をソースシステムから直接渡すことも、既にカタログデータを渡している場合 [!DNL Adobe Analytics] は統合を使用 [!DNL Analytics]することもできます。

場合によっては、複数のオプションを同時に使用することもできます。例えば、ほとんどのデータを毎日CSVファイル経由で渡し、API経由で在庫更新をより頻繁に渡すことができます。

通常、IT部門はこの手順の設定を支援します。

選択する方法のいずれにも、3つのカテゴリの各項目に関するメタデータを含める必要があります。

![カタログのメタデータ情報を表示する図](/help/c-recommendations/assets/intro-8.png)

* レコメンデーションを受け取るユーザーに表示するデータ。例えば、ムービー名とサムネール画像URLなどです。
* マーケティングおよびマーチャンダイジングコントロールの適用に役立つデータです。例えば、NC-17ムービーをレコメンデーションしないようにムービーのレーティングを設定するとします。
* 他の項目との類似性を決定するのに役立つデータ。例えば、映画のジャンル、映画内の俳優などです。

### ユーザ行動の捕捉

Next, you should add tags or leverage you existing [!DNL Analytics] implementation to track the conversion events (such as views and purchases) that drive [!DNL Target] algorithms.

![ユーザーの行動をキャプチャする方法を示す図](/help/c-recommendations/assets/intro-9.png)

You need to ensure that [!DNL Target] is aware of the items that your users are viewing and purchasing. 購入がお客様のコンテキストに関連しない場合、例えば、PDFのダウンロード、調査の完了、ニュースレターの購読、ビデオの視聴など、様々なタイプのコンバージョンイベントを追跡できます。

If you are already using [!DNL Target] to run A/B Tests activities on your site, you might have already completed this step. Or if you are already using [!DNL Adobe Analytics] to report on site visits and conversion behavior, you can use [!DNL Analytics] as your behavioral datasource. If not, it’s easiest to set this up using a tag manager such as [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). It’s also possible to send offline or in-app interactions to [!DNL Target] via real-time API.

### 適切なコンテキストによるレコメンデーションの取得

Pass information about the user and context at the point of interaction to [!DNL Target] to return relevant and personalized recommendations.

![適切なコンテキストでレコメンデーションを取得する方法を示す図](/help/c-recommendations/assets/intro-10.png)

Besides user behavior in aggregate, you need to pass [!DNL Target] the specific context where recommendations are being shown. これには、ページに関する情報と、ユーザープロファイルからの情報が含まれます。[!DNL Target] この情報を使用して、パーソナライズされたレコメンデーションを作成します。例えば、小売Webサイトでは、訪問者が現在閲覧している製品および製品カテゴリを把握する必要があります。また、そのユーザー（お気に入りのブランド、お気に入りの製品カテゴリ、忠誠層など）に関する情報も知りたいものです。This information is important so that [!DNL Target] can filter items and improve the personalization of recommendations.

## Recommendationsアクティビティの作成

[!DNL Recommendations] アクティビティとは何ですか。

![適切なレコメンデーションアクティビティを行うパーツを示す図](/help/c-recommendations/assets/intro-11.png)

[!DNL Recommendations] アクティビティは、次のコンポーネントで構成されます。

* **オーディエンス**:これらのレコメンデーションは誰に表示されますか。
* **条件**:レコメンデーションする品目
* **デザイン**:レコメンデーション品目の表示方法

![以下に、レコメンデーションアクティビティの構成要素を示します。オーディエンス、条件およびデザイン](/help/c-recommendations/assets/intro-12.png)

Out of the box, [!DNL Target] includes 14 built-in audiences, 42 built-in criteria, and 10 built-in design templates. これらの各項目をカスタマイズしたり、独自のアイテムを追加したりできます。We’ve had previous [webinars about building audiences](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) in [!DNL Target]. ここでは、魔女項目を定義する条件の定義について説明します。

Targetは、条件カードの概念を使用します。条件カードは、パーソナライゼーションのレシピと似ています。

![条件カードの図](/help/c-recommendations/assets/intro-13.png)

好みのパーソナライゼーション結果を達成するために、適切な条件を選択または作成することが重要です。条件は、カタログ全体から最終セットのレコメンデーションに至るファネルのようなものです。

![ファンネル図](/help/c-recommendations/assets/intro-14.png)

The following sections describe the various parts of this funnel and how they work in [!DNL Target]:

### 静的フィルター（コレクションと除外）

静的フィルターは、頻繁に変更することが予想されないカタログ属性に関連する大まかなルールです。

![コレクションと除外の図](/help/c-recommendations/assets/intro-16.png)

例えば、コンテンツコンテキストでは、レコメンデーションにすべてのムービーを含めることができますが、NC-17を評価したムービーは除外することができます。小売コンテキストでは、世界各地の複数のブランドを持つことができますが、米国で利用できる製品のみをレコメンデーションすることをお勧めします。また、地域のプライベートラベルから製品を除外することもできます。

これらは、複数のレコメンデーションで使用したいと思われる、すべてのカタログ属性であり、頻繁に変更する必要はありません。

### アルゴリズム（レコメンデーションキーとロジック）

次の手順は、レコメンデーションキーとロジックを選択することです。ここで、レコメンデーションの基本を決定します。

![アルゴリズムの図](/help/c-recommendations/assets/intro-17.png)

最初に選択する必要があるのは、レコメンデーションキーです。レコメンデーションキーは、レコメンデーションを選択するための「検索」のキーです。これは、推奨の基準となります。

推奨の基になるか。

* 訪問者が現在閲覧している品目
* 訪問者が現在閲覧しているカテゴリ
* 最後に購入または買い物かごに追加した品目
* 訪問者または項目に関連するカスタム属性

これらのキーに基づいて、次のように推奨ロジックを選択します。

* 類似の属性を持つ品目
* 特定のカテゴリで最も閲覧された品目
* この品目を購入した顧客もこれらの品目を購入した
* カスタム属性

Out of the box, [!DNL Target] includes a portfolio of algorithms.

![アルゴリズムの図のポートフォリオ](/help/c-recommendations/assets/intro-15.png)

* **人気度ベースのアルゴリズム** には、最も多く閲覧されたものとトップセラーが含まれています。
* **コンテンツベースのアルゴリズム** には、コンテンツの類似性が含まれています。
* **項目ベースのコラボレーションアルゴリズムには、表示/閲覧、閲覧/購入済み、購入/購入済みのもの** があります。「購入済み」は任意のコンバージョンです。
* **パーソナライズされたアルゴリズム** には、最近表示した、サイトの親和性、プロファイルによって拡張されたコラボレーションフィルターが含まれています。
* **独自のアルゴリズム** を使用すると、独自のカスタムアルゴリズムを使用できます。

### オンラインビジネスルール

最後のステップは、オンラインビジネスルールを適用しています。ここでは、デジタルプロパティで訪問者が実行していることに基づいて、ドメインの知識と現在のコンテキストを使用してアルゴリズムを強化します。

![オンラインビジネスルールの図](/help/c-recommendations/assets/intro-18.png)

例えば、コンテンツコンテキストで、訪問者が以前に視聴した映画を除外したり、同じディレクターによって映画をレコメンデーションしたり、同じジャンルで映画をブーストしたりすることができます。小売コンテキストでは、在庫切れ製品を除外したり、価格帯の品目を$5~$500の範囲で表示したり、同じブランドから品目をブーストしたりできます。

## Demo

レコメンデーションファネルに示されているタスクを完了すると、最終的なレコメンデーションで終了します。To watch an in-product demonstration inside [!DNL Target], the demo begins at 21:00 in the *Adobe Target Basics Webinar*, linked to below.

## Adobe Target Basics ウェビナー：Recommendations の概要 {#intro-to-recs}

[Recommendationsの概要](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)