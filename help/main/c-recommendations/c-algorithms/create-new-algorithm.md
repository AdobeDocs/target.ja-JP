---
keywords: 条件；アルゴリズム；業界の垂直方向；ページタイプ；レコメンデーションキー；レコメンデーションロジック；ロジック；データ範囲；ルックバックウィンドウ；行動データソース；部分的な設計；バックアップレコメンデーション；インクルージョンルール；属性の重み付け；現在のカテゴリ；カスタム属性；最後に購入された項目；最後に表示された項目；最も多く表示された項目；最も多く表示された項目；人気度；最後に購入された項目；最に表示されたされた；お気に入入り；最近表示
description: アクティビティのコンテンツを制御する条件を作成して  [!DNL Recommendations]  アクティビティに最も適したレコメンデーションを表示する方法を説明します。
title: '[!UICONTROL Criteria] で  [!DNL Recommendations] を作成するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 3f4f59b2-6637-4c33-bf17-bff11bef7173
source-git-commit: e45ac15a60c83e35b8b2b2ba29a42727faf746df
workflow-type: tm+mt
source-wordcount: '2554'
ht-degree: 48%

---

# 条件の作成

[!UICONTROL Adobe Target] の条件は、[!UICONTROL Recommendations] アクティビティのコンテンツを制御で [!UICONTROL Recommendations] ます。 条件を作成して、アクティビティに最も適したレコメンデーションを表示します。 これらの条件では、訪問者のアクションを使用して、表示するコンテンツや製品を決定します。

次のセクションでは、新しい条件の作成方法について説明します。

## 新規条件の作成画面にアクセスします

[!UICONTROL Create New Criteria] 画面に到達する方法は複数あります。 一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL Recommendations]** / **[!UICONTROL Criteria]** ライブラリ画面で、**[!UICONTROL Create Criteria]** / **[!UICONTROL Create Criteria]** をクリックします。 ここで作成した条件は、自動的にすべての [!DNL Recommendations] アクティビティで利用できるようになります。
* [!DNL Recommendations] （VEC）を使用して [!UICONTROL Visual Experience Composer] アクティビティを作成している場合は、ページで要素を選択して [!UICONTROL Select Criteria]、[!UICONTROL Replace w/ Recommendations] または [!UICONTROL Insert Recommendations Before] をクリックすると、すぐに [!UICONTROL Insert Recommendations After] の画面が表示されます。 使用可能な条件を選択するか、「**[!UICONTROL Create Criteria]**」をクリックします。 新しい条件を作成する場合は、他の [!DNL Recommendations] アクティビティで使用する条件を保存するオプションがあります。 詳しくは、[Recommendations アクティビティの作成 ](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) を参照してください。
* [!DNL Recommendations] アクティビティを編集する場合は、ページの [!UICONTROL Recommendations Location] ボックスをクリックし、「**[!UICONTROL Change Criteria]**」を選択します。 [!UICONTROL Select Criteria] の画面で、「**[!UICONTROL Create Criteria]**」をクリックします。 他の [!DNL Recommendations] アクティビティで使用するために新しい条件を保存するオプションがあります。

以下の手順では、最初のメソッド（[!UICONTROL Create New Criteria] / **[!UICONTROL Recommendations]** ライブラリ画面）を使用して **[!UICONTROL Criteria]** ール画面にアクセスすることを想定しています。

1. **[!UICONTROL Recommendations]**／**[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL Create Criteria]**／**[!UICONTROL Create Criteria]**&#x200B;をクリックします。

1. 以下の節で説明する情報を設定します。

## [!UICONTROL Basic Information] {#info}

1. **[!UICONTROL Criteria Name]** を入力します。

   これは、条件の説明に使用される「内部」名です。例えば、条件を「利幅の高い商品」と呼びたいが、正式に表示されるタイトルにはそれを使いたくないという場合があります。公開されるタイトルを設定するには、次の手順を参照してください。

1. この条件を使用するレコメンデーションに対してページに表示する、公開 **[!UICONTROL Display Title]** を入力します。

   例えば、この条件を使用してレコメンデーションを表示する際に、「これを表示したひとはこれも表示しています」または「類似の商品」と表示したい場合があります。

1. 条件の短い **[!UICONTROL Description]** を入力します。

   説明は、条件の識別に役立ち、条件の目的に関する情報が含まれる場合があります。

1. Recommendations アクティビティの目標に基づいて、業界の業種を選択します。

   | 業種 | 目標 |
   |--- |--- |
   | [!UICONTROL Retail/Ecommerce] | 購入をもたらすコンバージョン |
   | [!UICONTROL Lead Generation/B2B/Financial Services] | 購入を伴わないコンバージョン |
   | [!UICONTROL Media/Publishing] | エンゲージメント |

   その他の条件オプションは、選択した業種に応じて変わります。

1. **[!UICONTROL Page Type]** を選択します。

   複数のページタイプを選択できます。

   業界の垂直方向とページのタイプを組み合わせると、保存した条件を分類するのに役立ち、他の [!DNL Recommendations] アクティビティで条件を簡単に再利用できます。

## [!UICONTROL Recommendations Algorithm] {#rec-algo}

1. **[!UICONTROL Algorithm Type]** と **[!UICONTROL Algorithm]** を選択：

   ![ 推奨されるアルゴリズムの節 ](assets/recommended-algorithm.png)

   | アルゴリズムタイプ | 使用すべき/使用可能なアルゴリズム |
   | --- | --- |
   | [!UICONTROL Cart-Based] | ユーザーの買い物かごの中身に基づいてお勧めを紹介します。 <ul><li>[!UICONTROL People Who Viewed These, Also Viewed] </li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul> |
   | [!UICONTROL Popularity-Based] | サイト全体でのアイテムの全体的な人気度に基づいて、またはユーザーのお気に入りのカテゴリや最も多く閲覧されたカテゴリ、ブランド、ジャンルなどのアイテムの人気度に基づいて、レコメンデーションを作成します。 <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
   | [!UICONTROL Item-Based] | ユーザーが現在表示している項目または最近表示した項目に類似した項目を見つけることに基づいてお勧めを紹介します。 <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
   | [!UICONTROL User-Based] | ユーザーの行動に基づいてお勧めを紹介します。<ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
   | [!UICONTROL Custom Criteria] | アップロードしたカスタムファイルに基づいてお勧めを紹介します。<ul><li>カスタムアルゴリズム</li></ul> |

   >[!NOTE]
   >
   >**[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]** を選択した場合は、「コンテンツの類似性ルール [ を設定するオプションが表示さ ](#similarity) ます。

1. 必要に応じて、**項目属性** と **一致するプロファイル属性**、**レコメンデーションキー**、**フィルタリングキー**、**分析指標** を選択して、アルゴリズムを設定します。

残りのアルゴリズム設定オプションは、選択したアルゴリズムによって異なります。 アルゴリズムの設定を完了するには、[!UICONTROL Recommendation Key]、[!UICONTROL Filtering Key]、[!UICONTROL Co-Occurrence Basis]、[!UICONTROL Analytics Metric]、[!UICONTROL Item Attribute] および [!UICONTROL Profile Attribute to Match] を選択します。

レコメンデーシ [!UICONTROL Recommendation Key] ンの選択について詳しくは、[ レコメンデーションキーに基づくレコメンデーションのベース ](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) を参照してください。

## [!UICONTROL Backup Content] {#content}

[!UICONTROL Backup Content] のルールは、推奨項目数が [recommendations のデザイン ](/help/main/c-recommendations/c-design-overview/design-overview.md) を満たさない場合の動作を決定します。 [!DNL Recommendations] の条件で返されるレコメンデーションは、デザインで要求されるレコメンデーションよりも少なくなる可能性があります。 例えば、デザインに 4 つのアイテムのスロットがあるものの、条件によって 2 つのアイテムしか推奨されない場合は、残りのスロットを空のままにするか、バックアップ レコメンデーションを使用して余分なスロットを埋めるか、レコメンデーションを表示しないように選択できます。

1. （オプション） **[!UICONTROL Partial Design Rendering]** トグルを「オン」の位置にスライドさせます。

   可能な限り多くのスロットが埋められますが、デザイン テンプレートには残りのスロットの空白スペースが含まれる場合があります。 このオプションが無効になっていて、使用可能なすべてのスロットに入るのに十分なコンテンツがない場合、レコメンデーションは提供されず、代わりにデフォルトコンテンツが表示されます。

   レコメンデーションを空のスロットで提供する場合は、このオプションを有効にします。 次の手順で説明するように、条件に基づいてレコメンデーションスロットにコンテンツを入力し、サイトの類似コンテンツや人気コンテンツが空のスロットに入力する場合は、バックアップのレコメンデーションを使用します。

1. （オプション） **[!UICONTROL Show Backup Content]** トグルを「オン」の位置にスライドさせます。

   サイト全体から最も多く閲覧された製品をランダムに選択して、デザインの残りの空のスロットを埋めます。

   バックアップのレコメンデーションを使用すると、レコメンデーションの設計が使用可能なすべてのスロットに確実に適用されます。 次の図に示すように、4 x 1 のデザインがあるとします。

   ![4 x 1 デザイン ](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

   条件によって、2 つの項目のみが推奨されるとします。 [!UICONTROL Partial Design Rendering] オプションを有効にした場合、最初の 2 つのスロットは埋められますが、残りの 2 つのスロットは空のままです。 ただし、「[!UICONTROL Show Backup Recommendations]」オプションを有効にすると、最初の 2 つのスロットは指定した基準に基づいて入力され、残りの 2 つのスロットはバックアップの推奨事項に基づいて入力されます。

   次のマトリックスは、[!UICONTROL Partial Design Rendering] および [!UICONTROL Backup Content] オプションを使用する際に確認できる結果を示しています。

   | デザインの部分レンダリング | コンテンツのバックアップ | 結果 |
   |--- |--- |--- |
   | 無効 | 無効 | 返されたレコメンデーションがデザインで指定されているよりも少ない場合、レコメンデーションデザインはデフォルトコンテンツに置き換えられ、レコメンデーションは表示されません。 |
   | 有効 | 無効 | デザインはレンダリングされますが、返されたレコメンデーションがデザインで指定されているよりも少ない場合、空白スペースが含まれることがあります。 |
   | 有効 | 有効 | 使用可能なデザインの「スロット」に代替レコメンデーションが挿入され、デザインが完全にレンダリングされます。<br>インクルージョンルールを代替レコメンデーションに適用するとデザインに挿入できなくなるほど適格な代替レコメンデーションの数が制限される場合、デザインは部分的にレンダリングされます。<br>この基準がレコメンデーションを返さず、インクルージョンルールが代替レコメンデーションをゼロに制限する場合、デザインはデフォルトコンテンツで置き換えられます。 |
   | 無効 | 有効 | 使用可能なデザインの「スロット」に代替レコメンデーションが挿入され、デザインが完全にレンダリングされます。<br>インクルージョンルールを代替レコメンデーションに適用するとデザインに挿入できなくなるほど適格な代替レコメンデーションの数が制限される場合、デザインはデフォルトコンテンツに置き換えられ、レコメンデーションは表示されません。 |

   詳しくは、[ 代替レコメンデーションの使用 ](/help/main/c-recommendations/c-algorithms/backup-recs.md) を参照してください。

1. （条件付き）前の手順で **[!UICONTROL Show Backup Content]** を選択した場合は、**[!UICONTROL Apply inclusion rules to backup recommendations]** を有効にできます。

   包含ルールは、レコメンデーションに含める項目を決定します。 使用できるオプションは、業種によって異なります。

   詳しくは、以下の [ インクルージョンルールの指定 ](#inclusion) を参照してください。

## [!UICONTROL Data Source] {#data-source}

1. **[!UICONTROL Behavioral Data Source]** または [!UICONTROL Adobe Target] から目的の [!UICONTROL Analytics] を選択します。

   >[!NOTE]
   >
   >「[!UICONTROL Behavioral Data Source]」セクションは、実装で [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用している場合にのみ表示されます。

   ![ 行動データのSourceセクション ](assets/data-source.png)

   [!UICONTROL Analytics] を選択した場合は、目的のレポートスイートを選択します。

   条件で [!DNL Adobe Analytics] を行動データソースとして使用する場合、作成後、条件を使用できるまでの時間は、選択したレポートスイートとルックバックウィンドウが他の条件にも使用されたかどうかで異なります（下図を参照）。

   * **1 回限りのレポートスイート設定**：指定されたデータ範囲のルックバックウィンドウで最初にレポートスイートが使用されると、[!DNL Target Recommendations] は、選択されたレポートスイートの行動データを [!DNL Analytics] から完全にダウンロードするまで 2 ～ 7 日間かかる可能性があります。この時間枠は、[!DNL Analytics] のシステム負荷によって異なります。
   * **新しい条件または既に使用可能なレポートスイートを使用して編集した条件**：新しい条件を作成したり既存の条件を編集したりする場合、選択されたレポートスイートが選択されたデータ範囲以下のデータ範囲で既に [!DNL Target Recommendations] で使用されていれば、データは即座に使用でき、1 回限りの設定は必要ありません。この場合、または選択されたレポートスイートまたはデータ範囲が変更されずにアルゴリズムの設定が編集されると、12 時間以内にアルゴリズムが実行または再実行されます。
   * **進行中のアルゴリズム実行**：毎日の [!DNL Analytics] から [!DNL Target Recommendations] へのデータフロー。例えば、[!UICONTROL Viewed Affinity] のレコメンデーションでは、ユーザーが製品を閲覧すると、製品ビューのトラッキングコールがにリアルタイムに近い [!DNL Analytics] で渡されます。 [!DNL Analytics] データが翌日早くに [!DNL Target] にプッシュされ、[!DNL Target] が 12 時間以内にアルゴリズムを実行します。

   詳しくは、[Adobe Analyticsを Target Recommendations と併用する ](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md) を参照してください。

1. **[!UICONTROL Lookback Window]** を設定して、表示するレコメンデーションを決定する際に使用できる、過去のユーザー行動データの時間範囲を決定します。 このオプションは、[!UICONTROL Items with Similar Attributes] と [!UICONTROL Custom Algorithms] を除くすべてのアルゴリズムで使用できます。

   ![ ルックバックウィンドウのスライダー ](assets/data-range.png)

   サイトのトラフィックが多く、行動が頻繁に変わる場合は、データの範囲を狭めます。[!DNL Recommendations] は、範囲を狭くするほどマーケットやビジネスの変化に反応しやすくなります。例えば、範囲を狭く設定した場合、訪問者が新学期やクリスマスなどの季節の製品の購入を始めると、[!DNL Recommendations] は訪問者の行動の変化を検知して季節に適した品目をレコメンデーションするようになります。

   データ量が多くない場合や、訪問者の行動が頻繁に変化しない場合は、範囲を長くすることもできます。ただし、多くのサイトでは、ウィンドウが短いほど、レコメンデーションの品質が高くなります。

   有効なデータ範囲は、次のとおりです。

   | ルックバックウィンドウオプション | 更新された頻度（ホバーしたときに表示） | サポートされるアルゴリズム |
   | --- | --- | --- |
   | 6 時間 | アルゴリズムは 3～6 時間ごとに実行されます | 選択した [!UICONTROL Popularity-Based] が [!UICONTROL Behavioral Data Source] の場合の [!DNL Adobe Target] アルゴリズム |
   | 1 日 | アルゴリズムは 12 ～ 24 時間ごとに実行されます | [!UICONTROL Popularity-Based] アルゴリズム |
   | 2 日 | アルゴリズムは 12 ～ 24 時間ごとに実行されます | <ul><li>[!UICONTROL Popularity-Based] アルゴリズム</li><li>[!UICONTROL Item-Based] アルゴリズム</li><li>[!UICONTROL User-Based] アルゴリズム</li><li>[!UICONTROL Cart-Based] アルゴリズム</li></ul> |
   | 1 週間 | アルゴリズムは 24 ～ 48 時間ごとに実行されます | <ul><li>[!UICONTROL Popularity-Based] アルゴリズム</li><li>[!UICONTROL Item-Based] アルゴリズム</li><li>[!UICONTROL User-Based] アルゴリズム</li><li>[!UICONTROL Cart-Based] アルゴリズム</li></ul> |
   | 2 週間 | アルゴリズムは 24 ～ 48 時間ごとに実行されます | <ul><li>[!UICONTROL Popularity-Based] アルゴリズム</li><li>[!UICONTROL Item-Based] アルゴリズム</li><li>すべての [!UICONTROL User-Based] アルゴリズム</li><li>[!UICONTROL Cart-Based] アルゴリズム</li></ul> |
   | 1 か月（30 日） | アルゴリズムは 24 ～ 48 時間ごとに実行されます | <ul><li>[!UICONTROL Popularity-Based] アルゴリズム</li><li>[!UICONTROL Item-Based] アルゴリズム</li><li>[!UICONTROL User-Based] アルゴリズム</li><li>[!UICONTROL Cart-Based] アルゴリズム</li></ul> |
   | 2 か月（61 日） | アルゴリズムは 24 ～ 48 時間ごとに実行されます | <ul><li>[!UICONTROL Popularity-Based] アルゴリズム</li><li>[!UICONTROL Item-Based] アルゴリズム</li><li>[!UICONTROL User-Based] アルゴリズム</li><li>[!UICONTROL Cart-Based] アルゴリズム</li></ul> |

## コンテンツの類似性 {#similarity}

[!UICONTROL Content Similarity] ルールを使用して、項目またはメディアの属性に基づいてお勧めを紹介します。

>[!NOTE]
>
>**[!UICONTROL Item-Based]** および **[!UICONTROL Media with Similar Attributes]** として [!UICONTROL Algorithm Type]/ [!UICONTROL Algorithm] を選択した場合は、コンテンツの類似性ルールを設定するオプションがあります。

コンテンツの類似性では、アイテム属性キーワードを比較し、複数の項目に共通するキーワードの数に基づいてレコメンデーションを作成します。コンテンツの類似性に基づくレコメンデーションでは、過去のデータがなくても質の高い結果が得られます。

コンテンツの類似性を使用したレコメンデーションの生成は、新しいアイテムでは特に効果的です。新しいアイテムでは、過去の行動に基づいて *これを閲覧したユーザー、これも閲覧したユーザー* およびその他のロジックを使用したレコメンデーションに表示されない可能性が高くなります。 また、コンテンツの類似性を使用すると、過去の購入などの履歴データがない新規訪問者に対する便利なレコメンデーションを生成することもできます。

**[!UICONTROL Item-Based]**/**[!UICONTROL Media with Similar Attributes]** を選択する場合は、レコメンデーションを決定する際の特定の項目属性の重要性を増減させるルールを作成することもできます。 本などの項目については、*ジャンル*、*著者*、*シリーズ*&#x200B;などの属性の重要度を高くして、類似する本を推奨することができます。

コンテンツの類似性ではキーワードを使用して項目を比較しているため、*メッセージ*&#x200B;や&#x200B;*説明*&#x200B;などの一部の属性により比較に「邪魔」が入ることがあります。このような属性については、ルールを作成して無視することができます。

デフォルトでは、すべての属性は「*ベースライン*」に設定されています。この設定を変更しない場合、ルールを作成する必要はありません。

>[!NOTE]
>
>コンテンツの類似性アルゴリズムでは、項目間の類似性の計算にランダムサンプリングを使用する場合があります。 その結果、項目間の類似性評価は、アルゴリズム実行間で異なる場合があります。

## インクルージョンルール {#inclusion}

いくつかのオプションを使用して、レコメンデーションに表示する品目を絞り込むことができます。条件やプロモーションの作成時にインクルージョンルールを使用できます。

インクルージョンルールはオプションです。ただし、これらの詳細を設定すると、レコメンデーションに表示される項目をさらに制御できるようになります。詳細を設定するたびに、表示基準をより詳細に絞り込むことができます。

例えば、在庫数が 50 を超えていて、価格が $25～$45 の婦人靴だけを表示するよう選択できます。また、ビジネス上非常に重要な品目が最も表示されやすくなるように各属性に対して重みを付けることもできます。

別の例として、サイトにアクセスした訪問者のうち、特定の都市にいて、特定の学位を取得している訪問者に求人情報を表示できます。

インクルージョンルールのオプションは、業種によって異なります。デフォルトでは、インクルージョンルールは代替レコメンデーションに適用されます。

>[!IMPORTANT]
>
>インクルージョンルールは使用する際に注意が必要です。例えば、会社で、あるブランドが表示されているときに別のブランドをレコメンデーションしないというルールがある場合に、このフィルターは便利です。ただし、この機能には機会費用が伴う場合があります。アクティビティ条件によって通常表示されると考えられる一部の品目を、表示しないように制限することで、上昇率が減少する可能性があります。

インクルージョンルールは、AND で結合されます。品目がレコメンデーションに含まれるためには、すべてのルールを満たす必要があります。

上述の例のように、在庫数が 50 を超えていて、価格が $25～$45 の婦人靴だけを表示するシンプルなインクルージョンルールは、次の手順で作成できます。

1. （条件付き） **[!UICONTROL Allow recently purchased items to be recommended?]** 切り替えスイッチを「オン」の位置にスライドします。

   この設定は、`productPurchasedId` に基づいています。デフォルトの動作では、以前に購入された品目はレコメンドされません。ほとんどの場合、顧客が最近購入した品目を再び推奨することは望ましくありません。カヤックなど、通常 1 回しか購入しない品目を販売する場合に便利です。シャンプーやその他の個人的なアイテムなど、人々が繰り返し購入するために戻ってくるアイテムを販売する場合は、このオプションを有効にする必要があります。

1. レコメンデーションする商品の価格帯を設定します。
1. レコメンデーションする商品の最小在庫数を設定します。
1. 特定の基準を満たす場合のみ品目を表示するよう、レコメンデーションを設定します。

   一覧にある属性のいずれかが、1 つまたは複数の指定の条件を満たす、あるいは満たさない場合のみ、品目を含めるよう指定できます。

   使用できる評価演算子は、最初のドロップダウンで選択する値によって異なります。複数の品目を指定することができます。この品目は、OR で評価されます。

   複数のルールは、AND で結合できます。

   >[!NOTE]
   >
   >このオプションは、レコメンデーションに表示される品目を限定します。そのレコメンデーションがどのページに表示されるかには影響しません。レコメンデーションを表示する場所を制限するには、Experience Composer でページを選択します。

詳しくは、[ 動的および静的インクルージョンルールの使用 ](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) を参照してください。

## 属性の重み付け {#weighting}

コンテンツカタログに関する重要な情報やメタデータに基づいてアルゴリズムを「微調整」する複数のルールを追加して、特定の項目が表示される可能性を高めることができます。

例えば、販売中の項目に高い重み付けを適用して、レコメンデーションにより頻繁に表示されるようにすることができます。 その結果、非セール品は完全に除外されませんが、表示される頻度は低くなります。複数の重み付け属性を同じアルゴリズムに適用することができ、レコメンデーションの分割したトラフィックについて重み付け属性をテストできます。

1. 値を選択します。

   この値は、利用可能な条件のいずれかに基づいて、より表示される可能性の高くなる品目のタイプを決定します。

1. 評価基準を選択します。

1. キーワードを入力して、ルール属性を完成させます。

   例えば、完全なルールは、「カテゴリに部分文字列シューズが含まれる」のようになります。

1. ルールに割り当てる重みを選択します。

   オプションの範囲は 0 ～ 100（25 単位の増分）です。

1. 必要に応じて、その他のルールを追加します。

終了したら、「**[!UICONTROL Create]**」をクリックします。

新しい [!UICONTROL Recommendations] アクティビティを作成する場合、または既存のアクティビティを編集する場合、「**[!UICONTROL Save criteria for later]**」チェックボックスはデフォルトで選択されています。 他のアクティビティで条件を使用したくない場合、保存する前にチェックボックスをオフにします。
