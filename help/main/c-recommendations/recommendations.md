---
keywords: Recommendations;Recommendations の条件;Recommendations アルゴリズム;Recommendations アクティビティ;条件;Recommendations のターゲティング:recs
description: Adobe  [!DNL Target] の Recommendations アクティビティについて説明します。これらのアクティビティでは、以前のユーザーアクティビティやその他のアルゴリズムに基づいて、顧客が興味を持つ可能性のあるコンテンツを自動的に表示します。
title: ' [!DNL Target]  Recommendations とは'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 0d986e17-bc99-4c08-a963-7f9a6619609a
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 98%

---

# レコメンデーション

[!DNL Adobe Target Recommendations] のアクティビティは、以前のユーザーアクティビティ、環境設定、またはその他のアルゴリズムを基にして、顧客が興味を持つ可能性のある製品やコンテンツを自動的に表示します。[!DNL Target Recommendations] は、訪問者が知らなかったであろう関連項目へと訪問者を誘導できます。[!DNL Recommendations] は、適切なタイミング、適切な場所で訪問者に関連コンテンツを提供できます。

>[!NOTE]
>
>[!DNL Recommendations] アクティビティは、[Target Premium](/help/main/c-intro/intro.md#premium) ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。
>
>現在 [!DNL Recommendations Classic] がある場合、2 つのソリューションについて詳しくは、[Recommendations Classic と Target Premium の Recommendations アクティビティ](/help/main/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md#concept_A80223EF66634EA380580C2823A581C5)を参照してください。

[!DNL Recommendations] は、チャネル、アプリ、ページ、電子メールメッセージおよびその他の配信オプションにわたるリアルタイムの提案を最適化、カスタマイズするのに役立ち、管理努力を縮小しながら、エンゲージメントとコンバージョンを上昇させます。

[!DNL Recommendations] によって以下をおこなうことができます。

* レコメンデーションを自動化する高度な条件（ルール）を作成します。
* 少数の JavaScript スニペットを使用して、自動的にレコメンデーションを表示します。
* レコメンデーションを表示するレコメンデーション条件やデザインのテストや最適化をおこないます。
* レコメンデーションアクティビティの結果をレポートします。

次の図に、Webページ上のレコメンデーションを示します。

![velocity_example 画像 ](assets/velocity_example.png)

Recommendations では、サイト上の顧客のアクティビティに応じ、その顧客に製品を提案する方法を決定します。次に例を示します。

| 目的のアクション | レコメンデーション |
|--- |--- |
| リュックサックを購入した顧客に、ハイキングシューズやトレッキングポールの購入を勧めます。 | 「これを購入した人が他に購入したもの」という条件を使用して、よく一緒に購入される品目を表示するレコメンデーションを作成します。 |
| 訪問者が視聴しているメディア内容に類似した内容を勧めることで、訪問者がより長い時間メディアサイトに滞在するようにします。 | 「これを閲覧した人が他に閲覧したもの」という条件を使用して、他のビデオを提案するレコメンデーションを作成します。 |
| 銀行の預金プランに関する情報を閲覧した顧客に、IRA アカウントに関する情報も読むことを提案します。 | 「これを閲覧した人が購入したもの」という条件を使用して、レコメンデーションの最初の製品を表示する代わりに、多くの顧客がある製品の閲覧後に購入した他の商品を表示します。 |

上記の条件や他の [!DNL Recommendations] 条件について詳しくは、[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を参照してください。

## キーワード

[!DNL Recommendations]を使い始める前に、この節で使用する用語の一部を理解しておくと役に立ちます。これらの用語をまだ十分に理解していない方であっても、[!DNL Recommendations] アクティビティを設定しながら慣れることができます。

| 用語 | 定義 |
| --- | --- |
| アクティビティ | [!DNL Target] のアクティビティを使用すると、特定のオーディエンス対してコンテンツをパーソナライズし、ページのデザインをテストできます。[!DNL Recommendations] は、 [!DNL Target] で利用できる多数のアクティビティタイプの 1 つにすぎません。詳しくは、[Target のアクティビティタイプ](/help/main/c-activities/target-activities-guide.md)を参照してください。 |
| エンティティ | エンティティとは、レコメンデーションする項目を指します。製品、コンテンツ（記事、スライドショー、画像、ムービー、テレビ番組など）、求人情報、レストランなど、すべてのものがエンティティに該当します。詳しくは、[エンティティ](/help/main/c-recommendations/c-products/products.md)を参照してください。 |
| フィード | フィードは、[!DNL Recommendations] にエンティティを読み込むために使用されます。エンティティは、CSV ファイル、Google Product Search フィード形式および Adobe Analytics の製品分類を使用して送信できます。詳しくは、[フィード](/help/main/c-recommendations/c-products/feeds.md)を参照してください。 |
| カタログ | カタログは、製品セット（エンティティ）全体を表します。カタログには多数のコレクションを含めることができます。これにより、商品を論理的なグループにまとめて整理できます。 |
| コレクション | コレクションは、1 つの製品カテゴリなど、類似した項目や関連項目のセットを指します。しかし、どのような品目でも、ビジネス上で適切なカテゴリグループ分けすることができます。例えば、ある価格帯や色の製品、ある地域で特に興味がもたれそうな品目などです。詳しくは、[コレクション](/help/main/c-recommendations/c-products/collections.md) を参照してください。 |
| 条件 | 条件とは、事前に定義されている訪問者の行動に基づいて、どの商品をレコメンデーションするかを決定するルールです。<br>条件の例をいくつか挙げます。 <ul><li>これを購入した人が他に購入したもの</li><li>これを閲覧した人が他に閲覧したもの</li><li>類似の属性を持つ品目</li><li>最後に購入された品目</li><li>お気に入りのカテゴリ</li></ul>  詳しくは、[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を参照してください。 |
| デザイン | デザインは、[!DNL Recommendations] アクティビティでの Recommendations の外観（行、列、テーブル、グリッドなど）を定義します。この記事の上部の図は、4 x 1 のデザインを示しています。詳しくは、[デザインの作成](/help/main/c-recommendations/c-design-overview/create-design.md)を参照してください。 |
| 場所 | 場所とは、パーソナライゼーションと最適化の目的でアクティビティを実行する Web ページ、モバイルアプリ、電子メール上の特定のコンテンツ領域を指します。 |
| オーディエンス | オーディエンスは、ターゲット設定されたアクティビティを表示する対象となる、類似アクティビティ参加者のグループです。オーディエンスは、新規訪問者、再訪問者、中西部からの再訪問者など、同じ特性を持つ人々のグループです。オーディエンス機能を使用すると、様々なコンテンツやエクスペリエンスを特定のオーディエンスにターゲット設定することで、的確なメッセージを最適な対象者にタイミングよく表示し、デジタルマーケティングを最適化できます。詳しくは、[オーディエンス](/help/main/c-target/target.md)を参照してください。 |
|  オファーとしての Recommendations  | A/B テスト（自動配分と自動ターゲットを含む）およびエクスペリエンスのターゲット設定（XT）アクティビティに Recommendations を含めることができる機能。詳細については、「[ オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。 |

## トレーニングビデオ：アクティビティタイプ ![概要バッジ](/help/main/assets/overview.png)

このビデオでは、[!DNL Target Standard/Premium] で利用できるアクティビティタイプについて説明しています。[!DNL Recommendations] の説明は 7:20 から始まります。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)

## Adobe Targetの基本ウェビナー：Recommendationsの概要 ![ チュートリアルバッジ ](/help/main/assets/tutorial.png) {#intro-to-recs}

*Recommendations の概要*&#x200B;ウェビナーには、[!DNL Adobe Target Recommendations] の値をどのように活用するかについての詳細に説明しています。この[!DNL Target]アクティビティが商品やコンテンツを自動的に表示する方法を見ていきます。これは、以前の訪問に基づきリアルタイムに提案を最適化することで、顧客の興味を引く可能性があります。さらに、[!DNL Recommendations] アクティビティを作成するための、[!DNL Target] の UI での手順の概要も説明しています。

[Recommendations の概要](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
