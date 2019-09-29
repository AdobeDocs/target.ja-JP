---
description: 以前のユーザーアクティビティや他のアルゴリズムに基づいて、顧客が興味を持つ可能性のある製品やコンテンツを自動的に表示するTarget Recommendationsアクティビティの概要です。 Recommendations により、顧客が関心を持ちそうな商品を積極的に紹介することが可能になります。
keywords: Recommendations；導入；導入；ウェビナー；デモ
seo-description: 以前のユーザーアクティビティや他のアルゴリズムに基づいて、顧客が興味を持つ可能性のある製品やコンテンツを自動的に表示するAdobe Target Recommendationsアクティビティの概要です。 Recommendations により、顧客が関心を持ちそうな商品を積極的に紹介することが可能になります。
seo-title: Adobe targetのRecommendationsアクティビティの概要
solution: Target
title: Recommendationsの概要
title-outputclass: premium
topic: Premium
badge: Premium
translation-type: tm+mt
source-git-commit: 516433edd366fad5950c99d748aa7f6f718dd5fd

---


# ![RecommendationsのPREMIUM](/help/assets/premium.png) 概要

この記事のテキストは、「Recommendationsの概要」ウ *ェビナーに記載されています* 。このウェビナーは下に完全に表示できます。

*Recommendations の概要*&#x200B;ウェビナーには、[!DNL Adobe Target Recommendations] の値をどのように活用するかについての詳細な調査が含まれています。この[!DNL Target]アクティビティが商品やコンテンツを自動的に表示する方法を見ていきます。これは、以前の訪問に基づきリアルタイムに提案を最適化することで、顧客の興味を引く可能性があります。さらに、段階を追って[!DNL Recommendations]アクティビティを構築するための [!DNL Target]UI についても詳しく見ていきます。

## はじめに

小売業で見られるレコメンデーションの種類は誰もが知っています。 ますます多くのお客様が、このようなレコメンデーションを期待し、利用可能な他のオプションを調べるための出発点として使用するようになっています。 自分の買い物行動を考えてみれば、このようなレコメンデーションは本当にうまくいきます。 私たちのほとんどの人が、店やデジタルの物件に関わらず、私たちが最初に見た商品をどこかでレコメンデーションして買った。

次の図に、充電ステーション、ケース、ヘッドフォンなど、新しい電話で一般的に購入されるアクセサリーを表示する推奨事項を示します。

![他のユーザーが新しい電話で購入したアクセサリーを示す推奨事項。](/help/c-recommendations/assets/intro-1.png)

しかし、デジタルファーストブランドが顧客の期待をどのように高めているか、私たちが常に考えているとは限りません。 メディアやコンテンツの消費方法は、パーソナライズされたレコメンデーションによってますます推進されていきます。 Netflix、Spotify、YouTubeを開いたときに最初に見られるものを考えてみてください。 これらのブランドは、レコメンデーションを使用して顧客体験を開始します。 これまで以上に多くの代替オプションを利用できる世界では、顧客のインタラクションの時点で最も関連性の高いコンテンツを特定できることが重要です。

![デジタルファーストブランドの推奨事項](/help/c-recommendations/assets/intro-2.png)

マーケターは、様 [!DNL Adobe Target] 々な業界、顧客タイプおよびチャネルにわたって、パーソナライズされたエクスペリエンスを推進するのに使用します。

[!DNL Adobe Target] パーソナライズされたコンテンツをあらゆる場所に配信

![Targetが様々な場所でレコメンデーションを提供する方法を示す図](/help/c-recommendations/assets/intro-3.png)

* **Publishing: Web publishers use  to recommend articles to site visitors and drive increased engagement.**[!DNL Target Recommendations]
* **Video Tutorials:  uses  to recommend video tutorials to Photoshop users in the Photoshop application.**[!DNL Adobe Creative Cloud][!DNL Target]
* **Gaming: Gaming companies use  to recommend games and content to users on their consoles.**[!DNL Target]
* **B2B Sales: Business-to-business companies use Target to recommend videos, whitepapers, and blog posts to B2B prospects; deliver downloads; and provide help to existing customers.**[](https://theblog.adobe.com/testing-shifts-high-gear-intel)

* **Travel: A German travel booker uses Target to recommend hotels and more to travelers.**[](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608)

* **Retail: A leading B2B retailer uses Target to recommend top categories and products to return visitors in the browser and in its mobile app.**[](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/)

These are just a few of the ways customers use Target to deliver personalized recommendations.

What makes for great recommendations?

![Illustration showing the three elements that make great recommendations](/help/c-recommendations/assets/intro-4.png)

Great recommendations should be relevant and personalized. This means you need three things to drive relevance and personalization:

* **Marketer controls to help drive relevance of the items that are recommended.** As a marketer, you bring valuable context to the table and you know what attributes of your products or content are relevant for a recommendations model to consider. ビデオサイトを運営している場合、ユーザは同じ監督の映画を見たいと思うかもしれませんが、同じスタジオで制作された映画を見たいとは思わないでしょう。 [!DNL Target] を使用すると、このドメインの知識によってアルゴリズムを強化できるコントロールを強化できます。
* **カタログ** やインタラクションイベントに含まれる数百万の品目を把握できる高度なモデル。 [!DNL Target] 10年以上の経験を通じて高度な機械学習機能を構築し、年間で数十億件の推奨事項を扱っています。
* **レコメンデーションが** 、タイムリーでユーザーに関連性のあるものであることを確認するユーザーコンテキスト。 誰かが見たビデオや、買い物かごに追加したシャツをレコメンデーションしないでください。 Targetのリッチユーザープロファイルをレコメンデーションで使用して、パーソナライゼーションを実現できます。

## Target Recommendationsの実装

戦略から始めます。

![推奨方法を示す図](/help/c-recommendations/assets/intro-5.png)

* **レコメンデーションする商品を選択してください。** まず、レコメンデーションしたい商品を考えてみましょう。 製品、ビデオ、コンテンツなどがあります。
* **レコメンデーションを表示する場所** 次に、レコメンデーションを作成する場所を考えます。 概ねどのチャネル（Web、モバイル、店頭、キオスクなど）か。 顧客の遍歴のどの部分にレコメンデーションが含まれるか。 サイトのどのページにレコメンデーションが含まれますか。
* **レコメンデーションが成功したかどうかは、どのように判断しますか。** レコメンデーションのないエクスペリエンスとレコメンデーションのあるエクスペリエンスがある場合、または2つの異なるタイプのレコメンデーションがある場合を考えてみます。 どのエクスペリエンスが顧客にとってより良いエクスペリエンスだったかは、どのように判断しますか。 一部の指標は、他の指標よりも測定が困難な場合があります。 例えば、顧客の全期間値に対するレコメンデーションの影響は、多くの場合、直接把握するのが困難です。 したがって、抽象度の低い指標や、訪問あたりの売上高、平均注文額、クリック数など、より具体的な指標を得る方が簡単です。 場合によっては、指標を最小限に抑えたいと考えることがあります。例えば、サポートの呼び出し数などです。

戦略を策定したら、の実装を開始する準備が整いました [!DNL Target Recommendations]。

There are three broad steps involved in creating your recommendations implementation:

![推奨の実装を作成する手順を示す図](/help/c-recommendations/assets/intro-6.png)

1. Teach  about your context or products.[!DNL Target]
1. ユーザーの行動を捕捉します。
1. 適切なコンテキストでレコメンデーションを取得します。

### Teach [!DNL Target] about your context or products

最初に、レコメンデ [!DNL Recommendations]ーションするすべての品目に関する情報を渡します。 [!DNL Target] offers several integration options to create your catalog.

![コンテキストや製品についてTargetに教える方法を示す図](/help/c-recommendations/assets/intro-7.png)

The simplest, and most frequently used method is to send a CSV file on a daily or weekly basis from your product information management system or from your content management system. また、 [!DNL Adobe Target] JavaScriptライブラリを使用してページからデータレイヤー上の情報を渡したり、APIを利用してソースシステムから直接情報を渡したり、既にカタログデータを渡している場合は、統合を使用したりすることも [!DNL Adobe Analytics] できます [!DNL Analytics]。

多くの日別データをCSVファイルで渡したり、APIを使用して在庫の更新をより頻繁に渡したりするなど、複数のオプションを一緒に使用する場合があります。

通常、お客様のIT部門がこのステップの設定に関与します。

どちらの方法を選択する場合でも、3つのカテゴリに各項目に関するメタデータを含める必要があります。

![カタログのメタデータ情報を示す図](/help/c-recommendations/assets/intro-8.png)

* レコメンデーションを受け取るユーザーに表示するデータ。 例えば、ムービーの名前とサムネール画像のURL。
* マーケティングとマーチャンダイジングのコントロールを適用するのに役立つデータです。 例えば、NC-17ムービーをレコメンデーションしないように、ムービーのレーティングを指定します。
* 他の項目との類似性を判断するのに役立つデータです。 例えば、映画のジャンルや、その映画に含まれる俳優。

### ユーザーの行動の捕捉

次に、アルゴリズムを駆動するコンバージョンイベント( [!DNL Analytics] ビューや購入など)を追跡するために、タグを追加するか、既存の実装を活用する必要があ [!DNL Target] ります。

![ユーザーの行動を捕捉する方法を示す図](/help/c-recommendations/assets/intro-9.png)

ユーザーが表示し [!DNL Target] 購入している品目をに知らせる必要があります。 購入がコンテキストに関係ない場合は、例えば、PDFのダウンロード、調査の完了、ニュースレターの購読、ビデオの視聴など、様々なタイプのコンバージョンイベントを追跡できます。

既にサイトでA/Bテ [!DNL Target] ストアクティビティを実行している場合は、この手順が既に完了している可能性があります。 または、既にサイト訪問数とコンバ [!DNL Adobe Analytics] ージョン行動のレポートを使用している場合は、行動データソース [!DNL Analytics] としてを使用できます。 そうでない場合は、 [Adobe Launchなどのタグマネージャーを使用してこの設定を行う方が簡単です](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)。 また、リアルタイムAPIを使用して、オフラインまたはアプリ内のインタラクションをに送 [!DNL Target] 信することもできます。

### 適切なコンテキストでレコメンデーションを取得する

ユーザーとコンテキストに関する情報をインタラクションの時点で渡して、関連性の高いパーソナラ [!DNL Target] イズされたレコメンデーションを返します。

![適切なコンテキストでレコメンデーションを取得する方法を示す図](/help/c-recommendations/assets/intro-10.png)

集計でのユーザーの行動に加えて、レコメンデーションが表示され [!DNL Target] る特定のコンテキストを渡す必要があります。 これには、ページに関する情報や、ユーザープロファイルからの情報が含まれます。 [!DNL Target] この情報を使用して、パーソナライズされたレコメンデーションを作成します。 For example, on a retail website, you want to know the product and product category that the visitor is currently viewing. また、そのユーザーに関する情報（お気に入りのブランド、お気に入りの製品カテゴリ、忠誠度層など）を知りたい場合もあります。 この情報は、品目をフィルターしてレコメンデー [!DNL Target] ションのパーソナライゼーションを向上させるために重要です。

## 初めてのRecommendationsアクティビティの作成

アクティビティと [!DNL Recommendations] は何か

![適切なレコメンデーションアクティビティを作成する部品を示す図](/help/c-recommendations/assets/intro-11.png)

アクティビティ [!DNL Recommendations] は、次のコンポーネントで構成されています。

* **オーディエンス**:この推奨を誰に表示しますか。
* **条件**:レコメンデーションする品目
* **デザイン**:レコメンデーション品目の表示方法

![Recommendationsアクティビティの構成要素を示す図：オーディエンス、条件およびデザイン](/help/c-recommendations/assets/intro-12.png)

初期設定では、14個の組み込み [!DNL Target] オーディエンス、42個の組み込み条件、10個の組み込みのデザインテンプレートが含まれます。 これらの各項目をカスタマイズしたり、独自の項目を追加したりできます。 オーディエンスの構築に関するウェビ [ナーは、以前に開催し](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) まし [!DNL Target]た。 ここでは、レコメンデーションする品目を定義する条件の定義について説明します。

Targetは条件カードの概念を使用します。 条件カードは、パーソナライゼーションのレシピのようなものです。

![条件カードの図](/help/c-recommendations/assets/intro-13.png)

必要なパーソナライゼーションの結果を得るために、適切な条件を選択または作成することが重要です。 条件は、カタログ全体からレコメンデーションの最終セットに至るファネルのようなものです。

![ファネルの図](/help/c-recommendations/assets/intro-14.png)

次の節では、このファネルの様々な部分とその機能について説明しま [!DNL Target]す。

### 静的フィルター（コレクションおよび除外）

静的フィルターは、頻繁に変更されないと予想されるカタログ属性に関連する、幅広く適用されるルールです。

![コレクションと除外の図](/help/c-recommendations/assets/intro-16.png)

例えば、コンテンツのコンテキストでは、NC-17に分類される映画は除外し、すべての映画をrecommendationsに含めることができます。 小売業界では、世界の異なる地域に複数のブランドが存在する場合がありますが、米国で提供される製品のみをレコメンデーションしたい場合があります。 また、地域のプライベートラベルから製品を除外することもできます。

これらは、複数のレコメンデーションで使用する場合に広く適用できるカタログ属性で、頻繁に変更されることはありません。

### アルゴリズム（レコメンデーションキーとロジック）

次の手順は、レコメンデーションキーとロジックを選択することです。 ここで、レコメンデーションの基本を決定します。

![アルゴリズムの図](/help/c-recommendations/assets/intro-17.png)

最初に選択する必要があるのはレコメンデーションキーです。 レコメンデーションキーは、レコメンデーションを選択するための「検索」対象です。 これが、レコメンデーションの基になっている内容です。

次の基に推奨を設定できます。

* 訪問者が現在閲覧中の項目
* 訪問者が現在閲覧中のカテゴリ
* 訪問者が最後に購入または買い物かごに追加した品目
* 訪問者または項目に関連するカスタム属性

これらのキーに基づいて、目的のレコメンデーションロジックを選択します。

* 類似の属性を持つ品目
* 特定のカテゴリで最も多く閲覧された品目
* この商品を購入した顧客がこれらの商品も購入した
* カスタム属性

デフォルトで、アルゴリズムのポ [!DNL Target] ートフォリオが含まれています。

![アルゴリズムのポートフォリオの図](/help/c-recommendations/assets/intro-15.png)

* **人気ベースのアルゴリズムには** 、「最も多く閲覧された」と「トップセラー」が含まれます。
* **コンテンツベースのアルゴリズムには** 、コンテンツの類似性が含まれます。
* **品目ベースのコラボレーションフィルタリングアルゴリズムには** 、「閲覧済み/閲覧済み」、「閲覧済み/購入済み」および「購入済み/購入済み」が含まれます。 「購入済み」は任意のコンバージョンである可能性があります。
* **パーソナライズされたアルゴリズム** には、最近表示されたアルゴリズム、サイトの親和性、プロファイル拡張コラボレーションフィルターなどがあります。
* **独自のアルゴリズムを使用すると** 、独自のカスタムアルゴリズムを使用できます。

### オンラインビジネスルール

最後の手順は、オンラインビジネスルールの適用です。 ここでは、訪問者がデジタルプロパティで何をしているかに基づいて、ドメインの知識と現在の状況を活用してアルゴリズムを強化します。

![オンラインビジネスルールの図](/help/c-recommendations/assets/intro-18.png)

例えば、コンテンツのコンテキストでは、訪問者が以前に視聴した映画を除外したり、同じ監督が映画をレコメンデーションしたり、同じジャンルの映画をブーストしたりすることができます。 小売業界では、在庫切れの製品の除外、$5～$500の価格帯の品目の表示、同じブランドの品目のブーストを行うことができます。

## Demo

上記の推奨ファネルに説明されているタスクを完了すると、最後の推奨が残ります。 内部で製品内のデモを見るには [!DNL Target]、以下にリンクした *Adobe Target Basicsウェビナーの21:00からデモを開始します*。

## Adobe Target Basics ウェビナー：Recommendations の概要 {#intro-to-recs}

[Recommendationsの概要](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)