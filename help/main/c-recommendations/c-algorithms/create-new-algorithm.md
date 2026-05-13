---
keywords: 条件；アルゴリズム；業界縦組み；ページタイプ；レコメンデーションキー；レコメンデーションロジック；データ範囲；ルックバックウィンドウ；動作データソース；部分的デザイン；バックアップレコメンデーション；包含ルール；属性の重み付け；現在のカテゴリ；カスタム属性；最後に購入した項目；最後に閲覧した項目；最も閲覧した項目；お気に入りカテゴリ；人気度；最近閲覧した項目；最終閲覧；最も閲覧；お気に入入り；最近閲覧
description: 'アクティビティのコンテンツを制御する条件を作成して、アクティビティに最も適した推奨事項を表示する方法を説明します。 [!DNL Recommendations] '
title: ' [!DNL Recommendations]で[!UICONTROL Criteria]を作成するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 3f4f59b2-6637-4c33-bf17-bff11bef7173
TQID: https://experienceleague.adobe.com/r9FWgHWw6NX1CmhqI-7MLoamNFDepeCq1bpiJ8eyISM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2578
ht-degree: 49%

---

# 条件の作成

[!UICONTROL Adobe Target] [!UICONTROL Recommendations]の条件によって、[!UICONTROL Recommendations] アクティビティのコンテンツが制御されます。 アクティビティに最適なレコメンデーションを表示するために、条件を作成します。 これらの基準では、訪問者のアクションを使用して、表示するコンテンツや商品を決定します。

次の節では、新しい基準の作成方法について説明します。

## 新しい条件の作成画面にアクセス

[!UICONTROL Create New Criteria]画面に到達する方法は複数あります。 一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** ライブラリ画面で、**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**&#x200B;をクリックします。 ここで作成した条件は、自動的にすべての [!DNL Recommendations] アクティビティで利用できるようになります。
* [!UICONTROL Visual Experience Composer] （VEC）を使用して[!DNL Recommendations] アクティビティを作成する場合、ページ上の要素を選択して[!UICONTROL Replace w/ Recommendations]、[!UICONTROL Insert Recommendations Before]、または[!UICONTROL Insert Recommendations After]をクリックすると、すぐに[!UICONTROL Select Criteria]画面に移動します。 次に、使用可能な条件を選択するか、**[!UICONTROL Create Criteria]**&#x200B;をクリックします。 新しい条件を作成する場合は、他の[!DNL Recommendations] アクティビティで使用するために条件を保存するオプションがあります。 詳しくは、[Recommendations アクティビティの作成](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)を参照してください。
* [!DNL Recommendations] アクティビティを編集する場合は、ページの[!UICONTROL Recommendations Location] ボックス内をクリックし、**[!UICONTROL Change Criteria]**&#x200B;を選択します。 [!UICONTROL Select Criteria]画面で、**[!UICONTROL Create Criteria]**&#x200B;をクリックします。 他の [!DNL Recommendations] アクティビティで使用するために新しい条件を保存するオプションがあります。

次の手順では、最初の方法（**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** ライブラリ画面）を使用して、[!UICONTROL Create New Criteria]画面にアクセスすることを前提としています。

1. **[!UICONTROL Recommendations]**／**[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL Create Criteria]**／**[!UICONTROL Create Criteria]**&#x200B;をクリックします。

1. 次のセクションで情報を設定します。

## [!UICONTROL Basic Information] {#info}

1. **[!UICONTROL Criteria Name]**&#x200B;を入力します。

   これは、条件の説明に使用される「内部」名です。 例えば、条件を「利幅の高い商品」と呼びたいが、正式に表示されるタイトルにはそれを使いたくないという場合があります。 公開されるタイトルを設定するには、次の手順を参照してください。

1. この条件を使用するレコメンデーションのページに表示する公開用&#x200B;**[!UICONTROL Display Title]**&#x200B;を入力します。

   例えば、この条件を使用してレコメンデーションを表示する際に、「これを表示したひとはこれも表示しています」または「類似の商品」と表示したい場合があります。

1. 条件の短い&#x200B;**[!UICONTROL Description]**&#x200B;を入力します。

   説明は、基準の特定に役立ち、基準の目的に関する情報が含まれる場合があります。

1. レコメンデーション活動の目標に基づいて、業種を選択します。

   | 業種 | 目標 |
   |--- |--- |
   | [!UICONTROL Retail/Ecommerce] | 購入をもたらすコンバージョン |
   | [!UICONTROL Lead Generation/B2B/Financial Services] | 購入を伴わないコンバージョン |
   | [!UICONTROL Media/Publishing] | エンゲージメント |

   その他の基準オプションは、選択した業界の業種によって異なります。

1. **[!UICONTROL Page Type]**&#x200B;を選択します。

   複数のページタイプを選択できます。

   業界の垂直型とページ型を組み合わせることで、保存された基準を分類し、他の[!DNL Recommendations]活動の基準を簡単に再利用できます。

## [!UICONTROL Recommendations Algorithm] {#rec-algo}

1. **[!UICONTROL Algorithm Type]**&#x200B;と&#x200B;**[!UICONTROL Algorithm]**&#x200B;を選択：

   ![推奨されるアルゴリズムセクション &#x200B;](assets/recommended-algorithm.png)

   | アルゴリズムタイプ | 使用するタイミング/使用可能なアルゴリズム |
   | --- | --- |
   | [!UICONTROL Cart-Based] | ユーザーのカートの内容に基づいてレコメンデーションを行います。 <ul><li>[!UICONTROL People Who Viewed These, Also Viewed] </li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul> |
   | [!UICONTROL Popularity-Based] | サイト全体でのアイテムの人気度や、ユーザーが好むカテゴリーや最も閲覧されたカテゴリー、ブランド、ジャンルなどの中でのアイテムの人気度にもとづいて、レコメンデーションを行うことができます。 <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
   | [!UICONTROL Item-Based] | 利用者が現在閲覧している項目や最近閲覧した項目と類似する項目を見つけることで、レコメンデーションを行うことができます。 <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
   | [!UICONTROL User-Based] | 利用者の行動にもとづいてレコメンデーションする：<ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
   | [!UICONTROL Custom Criteria] | アップロードしたカスタムファイルにもとづいて、レコメンデーションを作成できます。<ul><li>カスタムアルゴリズム</li></ul> |

   >[!NOTE]
   >
   >**[!UICONTROL Items]**/**[!UICONTROL Media with Similar Attributes]**&#x200B;を選択した場合、[&#x200B; コンテンツの類似性ルール &#x200B;](#similarity)を設定するオプションがあります。

1. 必要に応じて、**項目属性**&#x200B;と&#x200B;**プロファイル属性を選択して一致**&#x200B;に設定し、**推奨キー**、**フィルタリングキー**&#x200B;および/または&#x200B;**分析指標**&#x200B;を選択して、アルゴリズムを設定します。

残りのアルゴリズム設定オプションは、選択したアルゴリズムによって異なります。 アルゴリズムの設定を完了するには、[!UICONTROL Recommendation Key]、[!UICONTROL Filtering Key]、[!UICONTROL Co-Occurrence Basis]、[!UICONTROL Analytics Metric]および/または[!UICONTROL Item Attribute]および[!UICONTROL Profile Attribute to Match]を選択します。

[!UICONTROL Recommendation Key]の選択について詳しくは、[&#x200B; レコメンデーションキーに基づくレコメンデーション &#x200B;](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)を参照してください。

## [!UICONTROL Backup Content] {#content}

[!UICONTROL Backup Content] ルールは、推奨されるアイテムの数が[&#x200B; レコメンデーションデザイン &#x200B;](/help/main/c-recommendations/c-design-overview/design-overview.md)に含まれていない場合の処理を決定します。 [!DNL Recommendations]条件で、デザインが要求するレコメンデーション数よりも少ないレコメンデーションを返すこともできます。 例えば、デザインに4つの項目のスロットが含まれているが、基準によって2つの項目だけが推奨される場合、残りのスロットを空のままにするか、バックアップの推奨事項を使用して追加のスロットを埋めるか、推奨事項を表示しないように選択できます。

1. （オプション） **[!UICONTROL Partial Design Rendering]** トグルを「オン」の位置にスライドさせます。

   可能な限り多くのスロットが埋められますが、デザインテンプレートには残りのスロット用の空白スペースが含まれる場合があります。 このオプションが無効になっていて、利用可能なすべてのスロットを埋めるのに十分なコンテンツがない場合は、レコメンデーションは提供されず、代わりにデフォルトコンテンツが表示されます。

   空のスロットでレコメンデーションを提供する場合は、このオプションを有効にします。 次のステップで説明するように、サイトの類似または人気のコンテンツで満たされた空のスロットを基準に、レコメンデーションスロットにコンテンツを入力する場合は、バックアップのレコメンデーションを使用します。

1. （オプション） **[!UICONTROL Show Backup Content]** トグルを「オン」の位置にスライドさせます。

   デザインに残っている空のスロットを、サイト全体から最も閲覧された商品をランダムに選択して埋めます。

   バックアップのレコメンデーションを使用すると、レコメンデーションのデザインが利用可能なすべてのスロットに確実に埋められます。 以下に示すように、4 x 1のデザインを持っているとします。

   ![4 x 1 デザイン &#x200B;](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

   条件によって推奨される項目が2つだけであるとします。 [!UICONTROL Partial Design Rendering] オプションを有効にすると、最初の2つのスロットは一杯になりますが、残りの2つのスロットは空のままです。 ただし、[!UICONTROL Show Backup Recommendations] オプションを有効にすると、指定した条件に基づいて最初の2つのスロットが入力され、残りの2つのスロットはバックアップの推奨事項に基づいて入力されます。

   次のマトリックスは、[!UICONTROL Partial Design Rendering]および[!UICONTROL Backup Content] オプションを使用した場合に表示される結果を示しています。

   | デザインの部分レンダリング | バックアップコンテンツ | 結果 |
   |--- |--- |--- |
   | 無効 | 無効 | 返されたレコメンデーションがデザインで指定されているよりも少ない場合、レコメンデーションデザインはデフォルトコンテンツに置き換えられ、レコメンデーションは表示されません。 |
   | 有効 | 無効 | デザインはレンダリングされますが、返されたレコメンデーションがデザインで指定されているよりも少ない場合、空白スペースが含まれることがあります。 |
   | 有効 | 有効 | 使用可能なデザインの「スロット」に代替レコメンデーションが挿入され、デザインが完全にレンダリングされます。<br>インクルージョンルールを代替レコメンデーションに適用するとデザインに挿入できなくなるほど適格な代替レコメンデーションの数が制限される場合、デザインは部分的にレンダリングされます。<br>この基準がレコメンデーションを返さず、インクルージョンルールが代替レコメンデーションをゼロに制限する場合、デザインはデフォルトコンテンツで置き換えられます。 |
   | 無効 | 有効 | 使用可能なデザインの「スロット」に代替レコメンデーションが挿入され、デザインが完全にレンダリングされます。<br>インクルージョンルールを代替レコメンデーションに適用するとデザインに挿入できなくなるほど適格な代替レコメンデーションの数が制限される場合、デザインはデフォルトコンテンツに置き換えられ、レコメンデーションは表示されません。 |

   詳しくは、[&#x200B; バックアップの推奨事項の使用](/help/main/c-recommendations/c-algorithms/backup-recs.md)を参照してください。

1. （条件付き）前の手順で&#x200B;**[!UICONTROL Show Backup Content]**&#x200B;を選択した場合、**[!UICONTROL Apply inclusion rules to backup recommendations]**&#x200B;を有効にできます。

   包含ルールは、どの項目をレコメンデーションに含めるかを決定します。 使用できるオプションは、業種によって異なります。

   詳細については、以下の「[包含ルールの指定](#inclusion)」を参照してください。

## [!UICONTROL Data Source] {#data-source}

1. 目的の&#x200B;**[!UICONTROL Behavioral Data Source]**&#x200B;を選択：[!UICONTROL Adobe Target]または[!UICONTROL Analytics]。

   >[!NOTE]
   >
   >[!UICONTROL Behavioral Data Source] セクションは、実装で[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用している場合にのみ表示されます。

   ![行動データ Source セクション &#x200B;](assets/data-source.png)

   [!UICONTROL Analytics]を選択した場合は、目的のレポートスイートを選択します。

   条件で[!DNL Adobe Analytics]を行動データソースとして使用する場合、作成された条件の可用性の時間は、選択したレポートスイートとルックバックウィンドウが他の条件に使用されているかどうかに応じて異なります。以下に説明します。

   * **1 回限りのレポートスイート設定**：指定されたデータ範囲のルックバックウィンドウで最初にレポートスイートが使用されると、[!DNL Target Recommendations] は、選択されたレポートスイートの行動データを [!DNL Analytics] から完全にダウンロードするまで 2 ～ 7 日間かかる可能性があります。 この時間枠は、[!DNL Analytics] システムの読み込みによって異なります。
   * **新しい条件または既に使用可能なレポートスイートを使用して編集した条件**：新しい条件を作成したり既存の条件を編集したりする場合、選択されたレポートスイートが選択されたデータ範囲以下のデータ範囲で既に [!DNL Target Recommendations] で使用されていれば、データは即座に使用でき、1 回限りの設定は必要ありません。 この場合、または選択されたレポートスイートまたはデータ範囲が変更されずにアルゴリズムの設定が編集されると、12 時間以内にアルゴリズムが実行または再実行されます。
   * **進行中のアルゴリズム実行**：毎日の [!DNL Analytics] から [!DNL Target Recommendations] へのデータフロー。 例えば、[!UICONTROL Viewed Affinity]のレコメンデーションでは、ユーザーが製品を閲覧すると、リアルタイムに近い[!DNL Analytics]に製品ビューのトラッキング呼び出しが渡されます。 [!DNL Analytics] データが翌日早くに [!DNL Target] にプッシュされ、[!DNL Target] が 12 時間以内にアルゴリズムを実行します。

   詳しくは、[Target RecommendationsでのAdobe Analyticsの使用](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md)を参照してください。

1. 表示するレコメンデーションを決定する際に使用できる過去のユーザー行動データの時間範囲を決定するには、**[!UICONTROL Lookback Window]**&#x200B;を設定します。 このオプションは、[!UICONTROL Items with Similar Attributes]と[!UICONTROL Custom Algorithms]を除くすべてのアルゴリズムで使用できます。

   ![&#x200B; ルックバックウィンドウ スライダー](assets/data-range.png)

   サイトのトラフィックが多く、行動が頻繁に変わる場合は、データの範囲を狭めます。 [!DNL Recommendations] は、範囲を狭くするほどマーケットやビジネスの変化に反応しやすくなります。 例えば、範囲を狭く設定した場合、訪問者が新学期やクリスマスなどの季節の製品の購入を始めると、[!DNL Recommendations] は訪問者の行動の変化を検知して季節に適した品目をレコメンデーションするようになります。

   データ量が多くない場合や、訪問者の行動が頻繁に変化しない場合は、範囲を長くすることもできます。 しかし、多くのサイトでは、ウィンドウが短いほど高品質のレコメンデーションが得られます。

   有効なデータ範囲は、次のとおりです。

   | 「ルックバックウィンドウ」オプション | 更新頻度（ホバーに表示） | サポートされるアルゴリズム |
   | --- | --- | --- |
   | 6時間 | アルゴリズムは3～6時間ごとに実行されます | 選択した[!UICONTROL Behavioral Data Source]が[!DNL Adobe Target]の場合の[!UICONTROL Popularity-Based] アルゴリズム |
   | 1日 | アルゴリズムは12～24時間ごとに実行されます | [!UICONTROL Popularity-Based] アルゴリズム |
   | 2 日 | アルゴリズムは12～24時間ごとに実行されます | <ul><li>[!UICONTROL Popularity-Based] アルゴリズム</li><li>[!UICONTROL Item-Based] アルゴリズム</li><li>[!UICONTROL User-Based] アルゴリズム</li><li>[!UICONTROL Cart-Based] アルゴリズム</li></ul> |
   | 1 週間 | アルゴリズムは24～48時間ごとに実行されます | <ul><li>[!UICONTROL Popularity-Based] アルゴリズム</li><li>[!UICONTROL Item-Based] アルゴリズム</li><li>[!UICONTROL User-Based] アルゴリズム</li><li>[!UICONTROL Cart-Based] アルゴリズム</li></ul> |
   | 2 週間 | アルゴリズムは24～48時間ごとに実行されます | <ul><li>[!UICONTROL Popularity-Based] アルゴリズム</li><li>[!UICONTROL Item-Based] アルゴリズム</li><li>すべての[!UICONTROL User-Based] アルゴリズム</li><li>[!UICONTROL Cart-Based] アルゴリズム</li></ul> |
   | 1か月（30日間） | アルゴリズムは24～48時間ごとに実行されます | <ul><li>[!UICONTROL Popularity-Based] アルゴリズム</li><li>[!UICONTROL Item-Based] アルゴリズム</li><li>[!UICONTROL User-Based] アルゴリズム</li><li>[!UICONTROL Cart-Based] アルゴリズム</li></ul> |
   | 2か月（61日） | アルゴリズムは24～48時間ごとに実行されます | <ul><li>[!UICONTROL Popularity-Based] アルゴリズム</li><li>[!UICONTROL Item-Based] アルゴリズム</li><li>[!UICONTROL User-Based] アルゴリズム</li><li>[!UICONTROL Cart-Based] アルゴリズム</li></ul> |

## コンテンツの類似性 {#similarity}

[!UICONTROL Content Similarity] ルールを使用して、アイテムまたはメディアの属性に基づいてレコメンデーションを行います。

>[!NOTE]
>
>**[!UICONTROL Item-Based]**/**[!UICONTROL Media with Similar Attributes]**&#x200B;を[!UICONTROL Algorithm Type]および[!UICONTROL Algorithm]として選択した場合は、コンテンツの類似性ルールを設定するオプションがあります。

コンテンツの類似性では、アイテム属性キーワードを比較し、複数の項目に共通するキーワードの数に基づいてレコメンデーションを作成します。 コンテンツの類似性に基づくレコメンデーションでは、過去のデータがなくても質の高い結果が得られます。

コンテンツの類似性を使用してレコメンデーションを生成することは、新しい項目に対して特に効果的です。新しい項目は、*これを閲覧した人物、また閲覧した人物*&#x200B;および過去の行動に基づくその他のロジックを使用してレコメンデーションに表示される可能性が低くなります。 また、コンテンツの類似性を使用すると、過去の購入などの履歴データがない新規訪問者に対する便利なレコメンデーションを生成することもできます。

**[!UICONTROL Item-Based]**/**[!UICONTROL Media with Similar Attributes]**&#x200B;を選択すると、レコメンデーションを決定する際に、特定の項目属性の重要性を増減するルールを作成するオプションがあります。 本などの項目については、*ジャンル*、*著者*、*シリーズ*&#x200B;などの属性の重要度を高くして、類似する本を推奨することができます。

コンテンツの類似性ではキーワードを使用して項目を比較しているため、*メッセージ*&#x200B;や&#x200B;*説明*&#x200B;などの一部の属性により比較に「邪魔」が入ることがあります。 このような属性については、ルールを作成して無視することができます。

デフォルトでは、すべての属性は「*ベースライン*」に設定されています。 この設定を変更しない場合、ルールを作成する必要はありません。

>[!NOTE]
>
>コンテンツ類似性アルゴリズムは、項目間の類似性を計算する際にランダムサンプリングを使用する場合があります。 その結果、アイテム間の類似度の評価は、アルゴリズム実行によって異なる場合があります。

## インクルージョンルール {#inclusion}

いくつかのオプションを使用して、レコメンデーションに表示する品目を絞り込むことができます。 条件やプロモーションの作成時にインクルージョンルールを使用できます。

インクルージョンルールはオプションです。ただし、これらの詳細を設定すると、レコメンデーションに表示される項目をさらに制御できるようになります。 詳細を設定するたびに、表示基準をより詳細に絞り込むことができます。

例えば、在庫数が 50 を超えていて、価格が $25～$45 の婦人靴だけを表示するよう選択できます。 また、ビジネス上非常に重要な品目が最も表示されやすくなるように各属性に対して重みを付けることもできます。

別の例として、サイトにアクセスした訪問者のうち、特定の都市にいて、特定の学位を取得している訪問者に求人情報を表示できます。

インクルージョンルールのオプションは、業種によって異なります。 デフォルトでは、インクルージョンルールは代替レコメンデーションに適用されます。

>[!IMPORTANT]
>
>インクルージョンルールは使用する際に注意が必要です。 例えば、会社で、あるブランドが表示されているときに別のブランドをレコメンデーションしないというルールがある場合に、このフィルターは便利です。 ただし、この機能には機会費用が伴う場合があります。 アクティビティ条件によって通常表示されると考えられる一部の品目を、表示しないように制限することで、上昇率が減少する可能性があります。

インクルージョンルールは、AND で結合されます。 品目がレコメンデーションに含まれるためには、すべてのルールを満たす必要があります。

上述の例のように、在庫数が 50 を超えていて、価格が $25～$45 の婦人靴だけを表示するシンプルなインクルージョンルールは、次の手順で作成できます。

1. （条件付き） **[!UICONTROL Allow recently purchased items to be recommended?]** トグルを「オン」の位置にスライドさせます。

   この設定は、`productPurchasedId` に基づいています。 デフォルトの動作では、以前に購入された品目はレコメンドされません。 ほとんどの場合、顧客が最近購入した品目を再び推奨することは望ましくありません。 カヤックなど、通常 1 回しか購入しない品目を販売する場合に便利です。 シャンプーやその他の個人用アイテムなど、繰り返し購入を繰り返すユーザーが再購入するアイテムを販売する場合は、このオプションを有効にする必要があります。

1. レコメンデーションする商品の価格帯を設定します。
1. レコメンデーションする商品の最小在庫数を設定します。
1. 特定の基準を満たす場合のみ品目を表示するよう、レコメンデーションを設定します。

   一覧にある属性のいずれかが、1 つまたは複数の指定の条件を満たす、あるいは満たさない場合のみ、品目を含めるよう指定できます。

   使用できる評価演算子は、最初のドロップダウンで選択する値によって異なります。 複数の品目を指定することができます。 この品目は、OR で評価されます。

   複数のルールは、AND で結合できます。

   >[!NOTE]
   >
   >このオプションは、レコメンデーションに表示される品目を限定します。 そのレコメンデーションがどのページに表示されるかには影響しません。 レコメンデーションを表示する場所を制限するには、Experience Composer でページを選択します。

詳しくは、[動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)を参照してください。

## 属性の重み付け {#weighting}

コンテンツカタログに関する重要な情報やメタデータに基づいてアルゴリズムを「ナッジ」するために複数のルールを追加して、特定の項目が表示される可能性を高めることができます。

例えば、セール品に対してより大きな重み付けを適用して、より頻繁にレコメンデーションに表示されるようにできます。 その結果、非セール品は完全に除外されませんが、表示される頻度は低くなります。 複数の重み付け属性を同じアルゴリズムに適用することができ、レコメンデーションの分割したトラフィックについて重み付け属性をテストできます。

1. 値を選択します。

   この値は、利用可能な条件のいずれかに基づいて、より表示される可能性の高くなる品目のタイプを決定します。

1. 評価基準を選択します。

1. キーワードを入力して、ルール属性を完成させます。

   例えば、完全なルールは「カテゴリにサブストリングの靴が含まれる」です。

1. ルールに割り当てる重みを選択します。

   オプションの範囲は 0 ～ 100（25 単位の増分）です。

1. 必要に応じて、その他のルールを追加します。

完了したら、**[!UICONTROL Create]**&#x200B;をクリックします。

新しい[!UICONTROL Recommendations] アクティビティを作成するか、既存のアクティビティを編集する場合は、デフォルトで&#x200B;**[!UICONTROL Save criteria for later]** チェックボックスが選択されます。 他のアクティビティで条件を使用したくない場合、保存する前にチェックボックスをオフにします。
