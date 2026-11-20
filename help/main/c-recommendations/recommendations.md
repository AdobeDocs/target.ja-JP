---
keywords: レコメンデーション;レコメンデーションの条件;レコメンデーション アルゴリズム;レコメンデーションアクティビティ;条件;レコメンデーションのターゲティング:recs
description: 以前のユーザーアクティビティやその他のアルゴリズムに基づいて、顧客が関心を持つ可能性のあるコンテンツを自動的に表示する、Adobe [!DNL Target]のRecommendations アクティビティについて説明します。
title: '[!DNL Target]のおすすめとは？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 0d986e17-bc99-4c08-a963-7f9a6619609a
TQID: 'https://experienceleague.adobe.com/gR3x6ABhdZNZ4lKvBHpJ-edRj7ZdCKBklMITXaLUhTA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: b31c0a47b82e0b96fa061075f1b8d388b6c0b567
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 68%
---
# レコメンデーションを始める {#recommendations}

>[!BEGINSHADEBOX]

**このページ：** [!DNL Adobe Target Recommendations]の機能、レコメンデーションの仕組み、このセクションで使用される用語について説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target Recommendations] のアクティビティは、以前のユーザーアクティビティ、環境設定、またはその他のアルゴリズムを基にして、顧客が興味を持つ可能性のある製品やコンテンツを自動的に表示します。 [!DNL Recommendations]は、訪問者に他の方法では知られていない可能性のある関連項目を提供し、適切なタイミングと場所で関連コンテンツを提供します。

>[!NOTE]
>
>[!DNL Recommendations] アクティビティは、[Target Premium](/help/main/c-intro/intro.md#premium) ソリューションの一部です。 [!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。
>
>現在 [!DNL Recommendations Classic] がある場合、2 つのソリューションについて詳しくは、[レコメンデーション Classic と Target Premium のレコメンデーションアクティビティ](/help/main/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md)を参照してください。

[!DNL Recommendations]は、チャネル、アプリ、ページ、メールメッセージ、その他の配信オプションをまたいでリアルタイムの提案を最適化およびカスタマイズし、管理の労力を削減しながらエンゲージメントとコンバージョンを高めます。 [!DNL Recommendations]を使用すると、次のことが可能になります。

* レコメンデーションを自動化するための高度な基準（ルール）を作成。
* JavaScriptのスニペットをいくつか使用することで、レコメンデーションを自動的に表示できます。
* レコメンデーションを表示する基準とデザインをテストして最適化します。
* レコメンデーション活動の結果をレポートします。

次の図に、Webページ上のレコメンデーションを示します。

![velocity_example image](assets/velocity_example.png)

Recommendations では、サイト上の顧客のアクティビティに応じ、その顧客に製品を提案する方法を決定します。 次に例を示します。

| 望ましい行動 | レコメンデーション |
|--- |--- |
| リュックサックを購入した顧客に、ハイキングシューズやトレッキングポールの購入を勧めます。 | 「これを購入した人が他に購入したもの」という条件を使用して、よく一緒に購入される品目を表示するレコメンデーションを作成します。 |
| 訪問者が視聴しているメディア内容に類似した内容を勧めることで、訪問者がより長い時間メディアサイトに滞在するようにします。 | 「これを閲覧した人が他に閲覧したもの」という条件を使用して、他のビデオを提案するレコメンデーションを作成します。 |
| 銀行の預金プランに関する情報を閲覧した顧客に、IRA アカウントに関する情報も読むことを提案します。 | 「これを閲覧した人が購入したもの」という条件を使用して、レコメンデーションの最初の製品を表示する代わりに、多くの顧客がある製品の閲覧後に購入した他の商品を表示します。 |

上記の条件や他の [!DNL Recommendations] 条件について詳しくは、[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を参照してください。

## キーワード

[!DNL Recommendations]を使用する前に、この節で使用する用語に慣れてください。 [!DNL Recommendations] アクティビティを設定すると、これらの条件がより明確になります。

| 用語 | 定義 |
| --- | --- |
| アクティビティ | [!DNL Target] のアクティビティを使用すると、特定のオーディエンス対してコンテンツをパーソナライズし、ページのデザインをテストできます。 [!DNL Recommendations]は、[!DNL Target]で利用できるアクティビティの種類の1つです。 詳しくは、[Target のアクティビティタイプ](/help/main/c-activities/target-activities-guide.md)を参照してください。 |
| エンティティ | エンティティとは、レコメンデーションする項目を指します。 製品、コンテンツ（記事、スライドショー、画像、ムービー、テレビ番組など）、求人情報、レストランなど、すべてのものがエンティティに該当します。 詳しくは、[エンティティ](/help/main/c-recommendations/c-products/products.md)を参照してください。 |
| フィード | フィードは、[!DNL Recommendations] にエンティティを読み込むために使用されます。 エンティティは、CSV ファイル、Google Product Search フィード形式および Adobe Analytics の製品分類を使用して送信できます。 詳しくは、[フィード](/help/main/c-recommendations/c-products/feeds.md)を参照してください。 |
| カタログ | カタログは、製品セット（エンティティ）全体を表します。 カタログには多数のコレクションを含めることができます。これにより、商品を論理的なバケットにまとめて整理できます。 |
| コレクション | コレクションは、1 つの製品カテゴリなど、類似した項目や関連項目のセットを指します。 しかし、どのような品目でも、ビジネス上で適切なカテゴリグループ分けすることができます。例えば、ある価格帯や色の製品、ある地域で特に興味がもたれそうな品目などです。 詳しくは、[コレクション](/help/main/c-recommendations/c-products/collections.md) を参照してください。 |
| 条件 | 条件は、事前に決められた訪問者の行動に基づいて、どの製品を推奨するかを決定するルールです。<br>条件の例としては、次のようなものがあります。 <ul><li>これを購入した人が他に購入したもの</li><li>これを閲覧した人が他に閲覧したもの</li><li>類似の属性を持つ品目</li><li>最後に購入された品目</li><li>お気に入りのカテゴリ</li></ul>  詳しくは、[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を参照してください。 |
| デザイン | デザインは、[!DNL Recommendations] アクティビティでのレコメンデーションの外観（行、列、テーブル、グリッドなど）を定義します。 この記事の上部の図は、4 x 1 のデザインを示しています。 詳しくは、[デザインの作成](/help/main/c-recommendations/c-design-overview/create-design.md)を参照してください。 |
| 場所 | 場所とは、パーソナライゼーションと最適化の目的でアクティビティを実行する Web ページ、モバイルアプリ、電子メール上の特定のコンテンツ領域を指します。 |
| オーディエンス | オーディエンスは、ターゲットを絞ったアクティビティを表示する、類似のアクティビティ参加者のグループです。 オーディエンスとは、新規訪問者、再訪問者、中西部からの再訪問者など、同じ特徴を持つ人々のグループのことです。 オーディエンス機能を利用すれば、適切なオーディエンスにタイミングよく適切なメッセージを表示し、特定のオーディエンスに向けてさまざまなコンテンツやエクスペリエンスを提供して、デジタルマーケティングを最適化できます。 詳しくは、[オーディエンス](/help/main/c-target/target.md)を参照してください。 |
| オファーとしてのレコメンデーション | A/B テスト（自動配分と自動ターゲットを含む）およびエクスペリエンスのターゲット設定（XT）アクティビティにレコメンデーションを含めることができる機能。 詳しくは、[オファーとしてのレコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md)をご覧ください。 |

## トレーニングビデオ：アクティビティタイプ ![概要バッジ](/help/main/assets/overview.png)

このビデオでは、[!DNL Target Standard/Premium] で利用できるアクティビティタイプについて説明しています。 [!DNL Recommendations]は7:20から議論されます。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)

<!--
## Adobe Target Basics Webinar: Introduction to Recommendations ![Tutorial badge](/help/main/assets/tutorial.png) {#intro-to-recs}

The *Introduction to Recommendations* webinar includes an in-depth exploration of how to leverage the value of [!DNL Adobe Target Recommendations]. Find out how this [!DNL Target] activity automatically displays products or content that might interest your customers by optimizing real-time suggestions based on previous visits. Further, dive into the [!DNL Target] UI for a step-by-step overview of how to build a [!DNL Recommendations] activity.

[Introduction to Recommendations](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
-->
