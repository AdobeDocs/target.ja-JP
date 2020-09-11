---
keywords: recommendations;recommendations activity;criteria;algorithm;recommendation key;custom key;industry vertical;retail;eccommerce;lead generation;b2b;financial services;media;publishing
description: Adobe TargetRecommendationsの基準とは、あらかじめ決められた訪問者行動に基づいて、どの商品をレコメンデーションするかを決定する規則です。
title: Adobe TargetRecommendationsの基準
feature: criteria
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
translation-type: tm+mt
source-git-commit: 55f0791bb68fc98e319fa70a647e5168ac72ae1e
workflow-type: tm+mt
source-wordcount: '1135'
ht-degree: 68%

---


# ![PREMIUM](/help/assets/premium.png) 条件

条件とは、事前に定義されている訪問者の行動に基づいて、どの商品をレコメンデーションするかを決定するルールです。

条件によって、どのアクションの結果どのレコメンデーションが引き起こされるかが決定されます。複数の条件を追加することで、複数のレコメンデーションタイプを相互にテストすることができます。

## 業種 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

レコメンデーションアクティビティの目標に基づいて業種を選択します。 選択した業種に応じて、

| 業種 | 目標 |
|--- |--- |
| 小売／e コマース | 購入をもたらすコンバージョン |
| リードジェネレーション／B2B／金融サービス | 購入を伴わないコンバージョン |
| メディア／投稿 | エンゲージメント |

## Recommendation key {#section_885B3BB1B43048A88A8926F6B76FC482}

選択するレコメンデーションキーが条件の種類を決定します。いくつかの条件の種類があり、[!DNL Recommendations] アクティビティを設定する際に条件カードとして表示されます。

| 条件の種類 | キー |
|--- |--- |
| 現在のページアクティビティ | 現在のページでユーザーがおこなったことに基づいてレコメンデーションされる品目です。例えば、特定の記事を表示した訪問者は、同じカテゴリの記事を見る可能性があると考えられます。<ul><li>[現在の品目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-item)</li><li>[現在のカテゴリ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-category)</li></ul> |
| カスタム | カスタム属性に基づいてレコメンデーションされる品目です。<ul><li>[カスタム属性](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#custom)</li></ul>レコメンデーションをカスタム属性に基づいておこなう場合、カスタム属性を選択してからレコメンデーションタイプを選択する必要があります。 |
| 過去の行動 | 過去、訪問者がある品目にどのように反応したかに基づいてレコメンデーションされる品目です。例えば、ある特定のブランドを購入したことがある人は、同じブランドの別の品目を購入する可能性が高いと考えられます。<ul><li>[最後に購入された品目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-purchased)</li><li>[最後に閲覧された品目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-viewed)</li><li>[最も多く閲覧された品目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed-logic)</li><li>[お気に入りのカテゴリ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#favorite-category)</li></ul> |
| 人気度 | 関連するカテゴリで一番人気のあるビデオや、サイトで一番表示されている製品など、一番人気のある品目がレコメンデーションされます。<ul><li>[人気度](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#popularity)</li></ul> |
| 最近表示された項目 | 訪問者が前回サイトに訪問した際に表示した品目や、現在一番好まれている記事など、訪問者が最近表示した品目をレコメンドします。<br>「最近表示された項目」アルゴリズムは、[環境](/help/administrating-target/hosts.md)内の訪問者のアクティビティ固有の結果を返します。2 つのサイトが異なる環境に属している場合、訪問者が 2 つのサイトを切り替えると、アルゴリズムは適切なサイトから最近表示された項目のみを返します。<br>この条件タイプは、コレクションによって制限されません。<ul><li>[最近表示された項目](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#recently-viewed)</li></ul>**注意：**&#x200B;最近表示された項目の条件は、バックアップレコメンデーションには使用できません。<br>最近表示された項目／メディアは、フィルターを適用し、特定の属性を含む項目のみを表示できます。<ul><li>最近表示された項目の条件は、レコメンデーションの他の条件と同じように変更可能です。</li><li>他の条件と同じ方法で、[コレクション](/help/c-recommendations/c-products/collections.md)、[除外](/help/c-recommendations/c-products/exclusions.md)、および[インクルージョン](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)（価格および在庫用の特殊なルールも含む）を使用できます。</li></ul>主な使用例は次のとおりです。<ul><li>複数のビジネスを営む多国籍企業で、複数のデジタルプロパティで項目を閲覧する訪問者がいるとします。その場合は、最近表示した項目をレコメンデーションする場所を、それが表示された各プロパティのみに制限できます。これにより、最近表示された項目が別のデジタルプロパティでレコメンデーションされるのを防ぐことができます。</li></ul> |

## カスタムレコメンデーションキーの使用 {#custom-key}

カスタムプロファイル属性の値に基づいてレコメンデーションを設定することもできます。

>[!NOTE]
>
>カスタムプロファイルパラメーターは、JavaScript、APIまたは統合を介してターゲットに渡すことができます。 カスタムプロファイル属性について詳しくは、 [訪問者プロファイルを参照してください](/help/c-target/c-visitor-profile/visitor-profile.md)。

例えば、ユーザーが最後にキューに追加したムービーに基づいてレコメンデーションされるムービーを表示するとします。

1. Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Last Show Added to Watchlist]).

1. Select your [!UICONTROL Recommendation Logic] (for example, [!UICONTROL People Who Viewed This, Viewed That]).

   ![新しい条件を作成ダイアログボックス](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

If your custom profile attribute does not directly match to a single entity ID, it is necessary to explain to [!DNL Recommendations] how you want the match to an entity to occur.

例えば、ユーザーのお気に入りのブランドからトップセルの商品を表示したいとします。

1. Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Favorite Brand]).

1. Select the [!UICONTROL Recommendation Logic] you want to use with this key (for example, [!UICONTROL Top Sellers]).

   「[!UICONTROL 次の一意の値でグループ化]」オプションが表示されます。

1. 選択したキーに一致するエンティティ属性を選択します。In this case [!UICONTROL Favorite Brand] matches to `entity.brand`.

   [!DNL Recommendations] 現在は、各ブランドに対して「トップセラー」リストを作成し、「お気に入りのブランド  プロファイル」属性に保存された値に基づいて適切な「トップセラー」リストをユーザーに表示します。

   ![トップセラー属性](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

## Criteria/algorithms {#criteria-algorithms}

[!DNL Target Recommendations] は、高度なアルゴリズムを使用して、訪問者のアクションがアクティビティに設定された条件に該当するタイミングを決定します。レコメンデーションキーは、利用可能なレコメンデーションロジックオプションを決定します。

| 条件 | 説明 |
|--- |--- |
| [類似の属性を持つ品目／メディア](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#similar-attributes) | 現在のページアクティビティまたは過去の訪問者の行動に基づいた品目またはメディアに類似した品目またはメディアをレコメンドします。 |
| [これを閲覧した人が他に閲覧したもの](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-viewed) | 指定した品目が閲覧された同じセッションで、閲覧される頻度が最も高い品目をレコメンドします。 |
| [これを閲覧した人が購入したもの](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-bought) | 指定した品目が閲覧された同じセッションで、購入される頻度が最も高い品目をレコメンドします。 |
| [これを購入した人が他に購入したもの](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#bought-bought) | 指定した品目と同時に顧客に購入される頻度が最も高い品目をレコメンドします。 |
| [サイトの親和性](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#site-affinity) | 品目間の関係の確実性に基づいて品目をレコメンドします。 |
| [トップセラー](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#top-sellers) | 完了した注文の最も多くに含まれている品目。1 回の注文で同じ品目が複数含まれていても、1 回の注文としてカウントします。 |
| [最も頻繁に閲覧された](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed) | 最も高い頻度で閲覧される品目またはメディア。 |
| [ユーザーベースのRecommendations](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#user-based) | 各訪問者の閲覧、表示および購入履歴に基づいて品目をレコメンドします。 これらの品目は、一般に「推奨」と呼ばれます。 |

>[!NOTE]
>
>レコメンデーションを実行中にその条件を変更すると、レポートデータが失われます。

訪問者に関する既知の追加情報を使用して、レコメンデーションを強化することもできます。

1 日条件は、すべて 1 日に 2 回実行します。1 週間およびそれ以上の条件は、すべて 1 日に 1 回実行します。サイトの親和性条件は、1 日に 1 回実行します。代替条件は、1 日に 2 回実行します。

## Viewing criteria information {#section_7162DE58E4594FD688A4D7FDB829FD8B}

ポップアップカードにマウスポインターを置いてから、条件カードの情報アイコンをクリックすると、条件を開くことなくポップアップカードの条件の詳細を表示できます。

![条件カードにマウスポインターを置く](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

「**[!UICONTROL アルゴリズム情報]**」タブをクリックして、選択した条件に関する一般的な情報（名前、説明、業種、ページタイプ、レコメンデーションキー、レコメンデーションロジック、アルゴリズム ID など）を表示します。

![「アルゴリズム情報」タブ](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

「**[!UICONTROL アルゴリズム使用状況]**」タブをクリックして、選択した条件を参照するアクティビティのリストを表示します。アクティブ、非アクティブ、ドラフトの各アクティビティのカードリスト。 「ライブアクティビティ」、「非アクティブアクティビティ」、「ドラフトアクティビティ」の各ドロップダウンリストをクリックし、その条件を参照するアクティビティのリスト全体を表示します。 アクティビティリンクをクリックすると、編集するアクティビティを開くことができます。

![「アルゴリズムの使用」タブ](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>アル [!UICONTROL ゴリズムの使用] (Algorithm Usage)機能は、現在、Recommendationsアクティビティに対してのみサポートされています。 この機能は、現在、オファーとして [recommendationsを含むA/Bテスト、自動配分、自動ターゲット、エクスペリエンスターゲット設定(XT)アクティビティではサポートされていません](/help/c-recommendations/recommendations-as-an-offer.md)。
