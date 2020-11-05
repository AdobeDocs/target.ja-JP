---
keywords: Recommendations;Recommendations criteria;recommendations algorithms;recommendations activity;criteria;recommendations targeting;recs
description: Adobe TargetのRecommendationsアクティビティは、以前のユーザーアクティビティや他のアルゴリズムを基にして、顧客が興味を持つ可能性のある商品やコンテンツを自動的に表示します。 Recommendations により、顧客が関心を持ちそうな商品を積極的に紹介することが可能になります。
title: Adobe TargetRecommendations
feature: recommendations general
uuid: 2aefd118-8fec-493d-ae4e-c1139c877a3f
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 59%

---


# ![PREMIUM](/help/assets/premium.png) Recommendations{#recommendations}

[!DNL Adobe Target Recommendations] アクティビティは、以前のユーザーアクティビティ、環境設定またはその他の条件に基づいて、訪問者が興味を持つ可能性のある製品、サービスまたはコンテンツを自動的に表示します。 [!DNL Target Recommendations] 関連性の高い項目に訪問者を向けるのに役立ちます。 [!DNL Recommendations] 適切なタイミングで適切な場所に関連コンテンツを訪問者に提供できます。

>[!NOTE]
>
>[!DNL Recommendations] アクティビティは、[Target Premium](/help/c-intro/intro.md#premium) ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。
>
>現在 [!DNL Recommendations Classic] がある場合、2 つのソリューションについて詳しくは、[Recommendations Classic と Target Premium の Recommendations アクティビティ](/help/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md#concept_A80223EF66634EA380580C2823A581C5)を参照してください。

[!DNL Recommendations] は、チャネル、アプリ、ページ、電子メールメッセージおよびその他の配信オプションにわたるリアルタイムの提案を最適化、カスタマイズするのに役立ち、管理努力を縮小しながら、エンゲージメントとコンバージョンを上昇させます。

[!DNL Recommendations] によって以下をおこなうことができます。

* レコメンデーションを自動化する高度な条件（ルール）を作成します。
* 少数の JavaScript スニペットを使用して、自動的にレコメンデーションを表示します。
* レコメンデーションを表示するレコメンデーション条件やデザインのテストや最適化をおこないます。
* レコメンデーションアクティビティの結果をレポートします。

次の図に、Webページ上のレコメンデーションを示します。

![](assets/velocity_example.png)

レコメンデーションは、サイトでの訪問者のアクティビティに応じて、訪問者に商品を提案する方法を決定します。 次に例を示します。

| 目的のアクション | 推奨 |
|--- |--- |
| リュックサックを購入した顧客に、ハイキングシューズやトレッキングポールの購入を勧めます。 | 「これを購入した人が他に購入したもの」という条件を使用して、よく一緒に購入される品目を表示するレコメンデーションを作成します。 |
| 訪問者が視聴しているメディア内容に類似した内容を勧めることで、訪問者がより長い時間メディアサイトに滞在するようにします。 | 「これを閲覧した人が他に閲覧したもの」という条件を使用して、他のビデオを提案するレコメンデーションを作成します。 |
| 銀行の預金プランに関する情報を閲覧した顧客に、IRA アカウントに関する情報も読むことを提案します。 | 「これを閲覧した人が購入したもの」という条件を使用して、レコメンデーションの最初の製品を表示する代わりに、多くの顧客がある製品の閲覧後に購入した他の商品を表示します。 |

上記の条件や他の [!DNL Recommendations] 条件について詳しくは、[条件](/help/c-recommendations/c-algorithms/algorithms.md)を参照してください。

## キーワード

を使い始める前に [!DNL Recommendations]、この節で使用する用語の一部を理解しておくと役に立ちます。 これらの用語がまだ完全に理解されていない場合は、 [!DNL Recommendations] アクティビティのセットアップ時に用語の使い方を習得できるようになります。

| 用語 | 定義 |
| --- | --- |
| アクティビティ | のアクティビティ [!DNL Target] を使用すると、特定のオーディエンスにコンテンツをパーソナライズして、ページデザインをテストできます。 [!DNL Recommendations] は、で利用できる多数のアクティビティタイプの1つにすぎま [!DNL Target]せん。 詳しくは、「 [ターゲットアクティビティタイプ](/help/c-activities/target-activities-guide.md)」を参照してください。 |
| エンティティ | エンティティとは、レコメンデーションする項目を指します。エンティティには、製品、コンテンツ（記事、スライドショー、画像、動画、テレビ番組）、ジョブリスト、レストランなどがあります。 For more information, see [Entities](/help/c-recommendations/c-products/products.md). |
| フィード | フィードは、エンティティをに読み込むために使用され [!DNL Recommendations]ます。 エンティティは、CSV ファイル、Google Product Search フィード形式および Adobe Analytics の製品分類を使用して送信できます。詳しくは、[フィード](/help/c-recommendations/c-products/feeds.md)を参照してください。 |
| カタログ | カタログは、製品セット（エンティティ）全体を参照します。 カタログには多数のコレクションを含めることができます。これにより、商品を論理的なグループにまとめて整理できます。 |
| コレクション | コレクションとは、1つの製品カテゴリなど、類似したアイテムや関連アイテムのセットを指します。 しかし、どのような品目でも、ビジネス上で適切なカテゴリグループ分けすることができます。例えば、ある価格帯や色の製品、ある地域で特に興味がもたれそうな品目などです。For more information, see [Collections](/help/c-recommendations/c-products/collections.md). |
| 条件 | 条件とは、事前に定義されている訪問者の行動に基づいて、どの商品をレコメンデーションするかを決定するルールです。<br>条件の例をいくつか挙げます。 <ul><li>これを購入した人が他に購入したもの</li><li>これを閲覧した人が他に閲覧したもの</li><li>類似の属性を持つ品目</li><li>最後に購入された品目</li><li>お気に入りのカテゴリ</li></ul>  詳しくは、[条件](/help/c-recommendations/c-algorithms/algorithms.md)を参照してください。 |
| デザイン | デザインは、行、列、テーブル、グリッドなど、 [!DNL Recommendations] アクティビティ内のレコメンデーションの外観を定義します。 この記事の上部の図は、4 x 1のデザインを示しています。 For more information, see [Create a design](/help/c-recommendations/c-design-overview/create-design.md). |
| 場所 | 場所とは、パーソナライズと最適化の目的でアクティビティを実行するWebページ、モバイルアプリ、電子メール上の特定のコンテンツ領域を指します。 |
| オーディエンス | オーディエンスは、ターゲットアクティビティを表示する、類似したアクティビティ参加者のグループです。 オーディエンスは、新規訪問者、再訪問者、中西部からの再訪問者など、同じ特性を持つ人々のグループです。オーディエンス機能を使用すると、様々なコンテンツやエクスペリエンスを特定のオーディエンスにターゲット設定することで、的確なメッセージを最適な対象者にタイミングよく表示し、デジタルマーケティングを最適化できます。詳しくは、「[オーディエンス](/help/c-target/target.md)」を参照してください。 |
| オファーとしての Recommendations  | A/Bテスト(自動配分と自動ターゲットを含む)およびエクスペリエンスのターゲット設定(XT)アクティビティ内にレコメンデーションを含めることのできる機能。 詳細については、「[オファーとしての Recommendations](/help/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。 |

## トレーニングビデオ：アクティビティタイプ ![の概要バッジ](/help/assets/overview.png)

このビデオでは、[!DNL Target Standard/Premium] で利用できるアクティビティのタイプについて説明しています。[!DNL Recommendations] の説明は 7:20 から始まります。

* [!DNL Adobe Target] に含まれるアクティビティのタイプの説明
* 目標達成に適したアクティビティのタイプの選択
* すべてのアクティビティのタイプに適用される 3 ステップのガイドによるワークフローについての説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)

## Adobe Target Basics ウェビナー：Recommendations の概要 ![チュートリアルバッジ](/help/assets/tutorial.png) {#intro-to-recs}

*Recommendations の概要*&#x200B;ウェビナーには、[!DNL Adobe Target Recommendations] の値をどのように活用するかについての詳細な調査が含まれています。この[!DNL Target]アクティビティが商品やコンテンツを自動的に表示する方法を見ていきます。これは、以前の訪問に基づきリアルタイムに提案を最適化することで、顧客の興味を引く可能性があります。さらに、段階を追って[!DNL Recommendations]アクティビティを構築するための [!DNL Target]UI についても詳しく見ていきます。

[Recommendations の概要](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)