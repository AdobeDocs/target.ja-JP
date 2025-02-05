---
keywords: レコメンデーションキー；レコメンデーションロジック；現在のカテゴリ；カスタム属性；最後に購入された項目；最後に閲覧された項目；最後に閲覧された項目；最も多く閲覧された項目；最も多く閲覧された項目；お気に入りのカテゴリ；人気度；最近閲覧された項目；最後に購入された項目；最後に閲覧された；お気に入り；最近閲覧された項目
description: 訪問者の行動コンテキストを使用して [!UICONTROL Recommendations] アクティビティに関連する結果を表示する、キーに基づくレコメンデーションの使用方法を説明します。
title: '[!UICONTROL Recommendation Key] に基づいて [!UICONTROL Recommendation] を作成するにはどうすればよいですか？'
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '3463'
ht-degree: 27%

---

# レコメンデーションキーに基づくレコメンデーションの設定

アルゴリズムに基づくRecommendationsは、訪問者行動コンテキストを使用して、[!DNL Recommendations] のアクティビティに関連する結果 [!DNL Adobe Target] 表示します。

次の表に示すように、各アルゴリズムタイプは、タイプに適した異なるアルゴリズムを提供します。

| アルゴリズムタイプ | 使用すべき/使用可能なアルゴリズム |
| --- | --- |
| [!UICONTROL Cart-Based] | ユーザーの買い物かごの中身に基づいてお勧めを紹介します。<ul><li>[!UICONTROL People Who Viewed These, Also Viewed]</li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul> |
| [!UICONTROL Popularity-Based] | サイト全体でのアイテムの全体的な人気度に基づいて、またはユーザーのお気に入りのカテゴリや最も多く閲覧されたカテゴリ、ブランド、ジャンルなどのアイテムの人気度に基づいて、レコメンデーションを作成します。 <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
| [!UICONTROL Item-Based] | ユーザーが現在表示している項目または最近表示した項目に類似した項目を見つけることに基づいてお勧めを紹介します。 <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
| [!UICONTROL User-Based] | ユーザーの行動に基づいてお勧めを紹介します。 <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
| [!UICONTROL Custom Criteria] | アップロードしたカスタムファイルに基づいてお勧めを紹介します。 <ul><li>カスタムアルゴリズム</li></ul> |

各条件は独自のタブで定義されます。トラフィックは、異なる条件のテスト全体で等しく分割されます。つまり、2 つの条件がある場合、トラフィックは等しく 2 分割されます。2 つの条件と 2 つのデザインがある場合、トラフィックは 4 つの組み合わせに対して等しく分割されます。さらに、比較のために、デフォルトコンテンツを表示するサイト訪問者の割合も指定できます。その場合、指定した割合の訪問者にはデフォルトコンテンツが表示され、残りは条件とデザインの組み合わせで分割されます。

条件の作成、およびアルゴリズムのタイプとアルゴリズムの定義について詳しくは、「[ 条件の作成 ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)」を参照してください。

様々なレコメンデーションアルゴリズムが、様々なタイプのページ上の配置に役立ちます。 各アルゴリズムタイプとその使用可能なアルゴリズムの詳細については、次の節を参照してください。

## 買い物かごベース {#cart-based}

[!UICONTROL Cart-Based] アルゴリズムタイプを使用すると、訪問者の現在の買い物かごの内容に基づいて、アイテムをレコメンデーションできます。 レコメンデーションキーは、コンマ区切り値の [mbox パラメーター `cartIds`](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} を介して提供されます。 最初の 10 個の値のみが考慮されます。

買い物かごベースのレコメンデーションロジックは、「[!UICONTROL Recommended For You]」ユーザーベースのアルゴリズムと、「[!UICONTROL People Who Viewed These, Bought Those]」および「[!UICONTROL People Who Bought These, Bought Those]」項目ベースのアルゴリズムに似ています。

共同フィルタリング手法を使用し [!DNL Target]、訪問者の買い物かごの中の各アイテムの類似性を判断したあと、各アイテムにおけるこれらの行動の類似性を組み合わせて、結合リストを取得します。

[!DNL Target] た、マーケターは、単一のセッション内または複数のセッションをまたいで訪問者の行動を確認することもできます。

* **[!UICONTROL Single Session]**:1 つのセッション内の他の訪問者の行動に基づいています。

  1 つのセッション内の動作を見ると、使用状況、機会、イベントに基づいて製品が相互に強く「連携」する感覚がある場合に意味を持つ場合があります。 例えば、訪問者がプリンターを購入する場合に、インクや紙も必要になることがあります。 または、ピーナッツバターを買う人は、パンやゼリーも必要な場合があります。

* **[!UICONTROL Across Sessions]**：複数のセッションにわたる他の訪問者の行動に基づきます。

  訪問者の好みや好みに基づいて製品が強く「連携」する感覚がある場合は、複数のセッションにわたる動作を確認することで意味を成す可能性があります。 例えば、訪問者が必ずしも両方の映画を同じ時間に見たいとは限らない場合でも、訪問者はスターウォーズが好きで、インディアナ・ジョーンズも好きかもしれません。 または、訪問者はボードゲーム「Codenames」が好きで、同時に両方のゲームをプレイできない場合でも、ボードゲーム「Avalon」が好きになる場合があります。

[!DNL Target] では、単一のセッション内または複数のセッション間での訪問者の行動を調べるかどうかに関係なく、現在の買い物かごの項目に基づいて各訪問者に対するレコメンデーションが作成されます。

[!UICONTROL Cart-Based] のアルゴリズムタイプでは、次のアルゴリズムを使用できます。

### [!UICONTROL People Who Viewed This, Also Viewed]

指定した品目が閲覧された同じセッションで、閲覧される頻度が最も高い品目をレコメンドします。

このロジックは、ユーザーがこの製品を表示した後に表示した他の製品を返します。 指定した製品は結果セットに含まれません。

このロジックを使用すると、アイテムを閲覧した他の訪問者も閲覧したアイテムをレコメンデーションすることで、追加のコンバージョン機会を作成できます。 例えば、サイトでロードバイクを閲覧する訪問者は、バイクのヘルメット、サイクリングキット、ロックなども参照する場合があります。 他の製品を提案するこのロジックを使用して、レコメンデーションを作成すると、売上高の増加に役立ちます。

このアルゴリズムを選択すると、次のRecommendations キーを選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Viewed This, Also Bought]

指定された項目を表示するセッションと同じセッションで最も頻繁に購入される項目を推奨します。

このロジックは、ユーザーがこの製品を表示した後に購入した他の製品を返します。 指定した製品は結果セットに含まれません。

このロジックを使用すると、商品ページにレコメンデーションを表示することで、クロス販売の機会を増やすことができます。例えば、商品を表示した他の訪問者が購入した商品を表示する場合などです。 例えば、訪問者が釣り竿を見ている場合、レコメンデーションでは、タックルボックス、ワダー、釣りルアーなど、他の訪問者が購入した追加のアイテムを表示できます。 訪問者がサイトを閲覧する際には、追加の購入レコメンデーションを提供します。

このアルゴリズムを選択すると、次のRecommendations キーを選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Bought This, Also Bought]

指定した品目と同時に顧客に購入される頻度が最も高い品目をレコメンドします。

このロジックは、これを購入した後に購入した他の製品を返します。 指定した製品は結果セットに含まれません。

このロジックを使用すると、他の購入者も購入した商品を表示するなど、買い物かごの概要ページにレコメンデーションを表示することで、クロス販売の機会を増やすことができます。 例えば、訪問者がスーツを購入した場合、そのスーツと共に購入した他の訪問者の追加アイテム（ネクタイ、ドレスシューズ、カフリンクなど）がレコメンデーションに表示されることがあります。 訪問者が購入をレビューする際に、追加のレコメンデーションを提供します。

このアルゴリズムを選択すると、次のRecommendations キーを選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

## [!UICONTROL Popularity-Based]

[!UICONTROL Popularity-Based] アルゴリズムタイプを使用すると、サイト全体でのアイテムの全体的な人気度に基づいて、またはユーザーのお気に入りのカテゴリや最も多く閲覧されたカテゴリ、ブランド、ジャンルなどのアイテムの人気度に基づいて、レコメンデーションを作成できます。

[!UICONTROL Popularity-Based] のアルゴリズムタイプでは、次のアルゴリズムを使用できます。

### [!UICONTROL Most Viewed Across the Site] {#most-viewed}

レコメンデーションは、最も頻繁に表示された項目によって決定されます。 これは次のように動作するリーセンシー／頻度条件により決定されます。

* 初回の商品閲覧は 10 ポイント
* 以降の閲覧は毎回 5 ポイント
* セッションの終わりにすべての値を 2 で割る

たとえば、サーフボード A とサーフボード B を 1 つのセッションで表示すると、A: 10、B: 5 という結果になります。 セッションが終了すると、A:5、B:2.5 になります。次のセッションで同じ項目を表示すると、値が A:15 B:7.5 に変わります。

このアルゴリズムは、ホームページやランディングページ、オフサイト広告など、一般的なページで使用します。

### [!UICONTROL Most Viewed by Category] {#most-viewed-category}

レコメンデーションは、最も多くのアクティビティを受信したカテゴリによって決定されます。商品ではなくカテゴリにポイントが付けられることを除き、「最も多く閲覧された品目」と同じメソッドを採用します。

これは次のように動作するリーセンシー／頻度条件により決定されます。

* 初回のカテゴリ閲覧は 10 ポイント
* 以降の閲覧は毎回 5 ポイント

最初に訪問したカテゴリには、10 ポイントが付与されます。同じカテゴリへの次の訪問には、5 ポイントが付与されます。訪問ごとに、以前表示した現在のカテゴリ以外のカテゴリは、1 ポイントずつ減点されます。

例えば、あるセッションでカテゴリ A を表示し、次にカテゴリ B を表示すると、A:9、B:10 という結果になります。 次のセッションで同じ品目を閲覧すると、値は 「A：20 B：9」 に変化します。

このアルゴリズムは、ホームページやランディングページ、オフサイト広告など、一般的なページで使用します。

カテゴリ別で最も多く閲覧されたアルゴリズムを選択した場合は、次のRecommendations キーを選択できます。

* [!UICONTROL Current Category]
* [!UICONTROL Favorite Category]

### [!UICONTROL Most Viewed by Item Attribute]

サイトで最も多く閲覧された項目やメディアに類似した項目やメディアをお勧めします。

このアルゴリズムを使用すると、レコメンデーションのベースにする項目属性（例：「名前」、「ブランド」）を選択できます。

次に、訪問者のプロファイルに保存されている、一致させるプロファイル属性（「お気に入りのブランド」、「買い物かごに最後に追加された項目」、「最も多く閲覧された番組」など）を選択します。

### [!UICONTROL Top Sellers Across the Site] {#top-sellers}

サイト全体で最も多く完了した注文に含まれる項目を表示します。 1 回の注文で同じ品目が複数含まれていても、1 回の注文としてカウントします。

このアルゴリズムを使用すると、サイトで売れ筋商品のレコメンデーションを作成して、コンバージョンと売上高を増やすことができます。 このロジックは、サイトへの初回の訪問者に特に適しています。

### [!UICONTROL Top Sellers by Category]

最も完了した注文に含まれる項目をカテゴリ別に表示します。 1 回の注文で同じ品目が複数含まれていても、1 回の注文としてカウントします。

このアルゴリズムを使用すると、カテゴリに基づいてサイトで売れ筋商品のレコメンデーションを作成し、コンバージョンと売上高を増やすことができます。 このロジックは、サイトへの初回の訪問者に特に適しています。

[!UICONTROL Most Viewed by Category] のアルゴリズムを選択した場合は、次の [!UICONTROL Recommendations Keys] を選択できます。

* [!UICONTROL Current Category]
* [!UICONTROL Favorite Category]

### [!UICONTROL Top Sellers by Item Attribute]

サイトで最も購入された項目やメディアに類似した項目やメディアをお勧めします。

このアルゴリズムを使用すると、レコメンデーションのベースにする項目属性（例：「名前」、「ブランド」）を選択できます。

次に、訪問者のプロファイルに保存されている、一致させるプロファイル属性（「お気に入りのブランド」、「買い物かごに最後に追加された項目」、「最も多く閲覧された番組」など）を選択します。

### [!UICONTROL Top by Analytics Metric]

「上位 x」を表示します。ここで *x* は任意の [!DNL Analytics] 指標です。 mbox の行動データを使用する場合は、[!UICONTROL Top Sold] または [!UICONTROL Top Viewed] （x = 「Sold」または x = 「Viewed」）を使用できます。 [!DNL Adobe Analytics] の行動データを使用している場合は、x = 「買い物かごへの追加」またはその他の [!DNL Analytics] 指標を使用できます。

## [!UICONTROL Item-Based]

[!UICONTROL Item-Based] レコメンデーションタイプを使用すると、ユーザーが現在表示している項目または最近表示した項目に類似した項目の検索に基づいてレコメンデーションを行うことができます。

[!UICONTROL Item-Based] のアルゴリズムタイプでは、次のアルゴリズムを使用できます。

### [!UICONTROL People Who Viewed This, Viewed That] {#viewed-viewed}

指定した品目が閲覧された同じセッションで、閲覧される頻度が最も高い品目をレコメンドします。

このロジックは、この製品を表示した後に表示された他の製品を返します。指定された製品は結果セットに含まれません。

このロジックを使用すると、アイテムを閲覧した他の訪問者も閲覧したアイテムをレコメンデーションすることで、追加のコンバージョン機会を作成できます。 例えば、サイトでロードバイクを閲覧する訪問者は、バイクのヘルメット、サイクリングキット、ロックなども参照する場合があります。 他の製品を提案するこのロジックを使用して、レコメンデーションを作成すると、売上高の増加に役立ちます。

このアルゴリズムを選択すると、次の [!UICONTROL Recommendations Keys] を選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Viewed This, Bought That] {#viewed-bought}

指定した品目が閲覧された同じセッションで、購入される頻度が最も高い品目をレコメンドします。この条件によって、顧客が指定の商品を閲覧した後で購入した他の商品が返されるので、指定した商品は結果セットに含まれません。

このロジックは、この製品を表示した後に購入した他の製品を返します。指定された製品は結果セットに含まれません。

このロジックを使用すると、商品ページにレコメンデーションを表示することで、クロス販売の機会を増やすことができます。例えば、商品を表示した他の訪問者が購入した商品を表示する場合などです。 例えば、訪問者が釣り竿を見ている場合、レコメンデーションでは、タックルボックス、ワダー、釣りルアーなど、他の訪問者が購入した追加のアイテムを表示できます。 訪問者がサイトを閲覧する際には、追加の購入レコメンデーションを提供します。

このアルゴリズムを選択すると、次の [!UICONTROL Recommendations Keys] を選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Bought This, Bought That] {#bought-bought}

指定した品目と同時に顧客に購入される頻度が最も高い品目をレコメンドします。

このロジックは、これを購入した後に購入した他の製品を返します。 指定した製品は結果セットに含まれません。

このロジックを使用すると、他の購入者も購入した商品を表示するなど、買い物かごの概要ページにレコメンデーションを表示することで、クロス販売の機会を増やすことができます。 例えば、訪問者がスーツを購入した場合、そのスーツと共に購入した他の訪問者の追加アイテム（ネクタイ、ドレスシューズ、カフリンクなど）がレコメンデーションに表示されることがあります。 訪問者が購入をレビューする際に、追加のレコメンデーションを提供します。

このアルゴリズムを選択すると、次の [!UICONTROL Recommendations Keys] を選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL Items with Similar Attributes] {#similar-attributes}

現在のページアクティビティまたは過去の訪問者の行動に基づいた品目またはメディアに類似した品目またはメディアをレコメンドします。

[!UICONTROL Items with Similar Attributes] または [!UICONTROL Media with Similar Attributes] を選択した場合は、コンテンツの類似性ルールを設定することもできます。

コンテンツの類似性を使用してレコメンデーションを生成すると、過去の行動に基づいた [!UICONTROL People Who Viewed This]、[!UICONTROL Viewed That]、その他のロジックを使用したレコメンデーションには表示されない可能性が高い、新しい項目に対して特に効果的です。 また、コンテンツの類似性を使用すると、過去の購入などの履歴データがない新規訪問者に対する便利なレコメンデーションを生成することもできます。

このアルゴリズムを選択すると、次の [!UICONTROL Recommendations Keys] を選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

詳しくは、[ コンテンツの類似性 ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity) を参照してください。

## [!UICONTROL User-Based]

[!UICONTROL User-Based] アルゴリズムタイプを使用すると、ユーザーの行動に基づいてお勧めを紹介できます。

[!UICONTROL User-Based] のアルゴリズムタイプでは、次のアルゴリズムを使用できます。

### [!UICONTROL Recently Viewed Items] {#recently-viewed}

訪問者の履歴（複数セッションにわたる）を使用して、デザインのスロット数に基づいて、訪問者が閲覧した最後の *x* 品目を提示します。

[!UICONTROL Recently Viewed Items] アルゴリズムは、指定された [ 環境 ](/help/main/administrating-target/hosts.md) に固有の結果を返します。 別々の環境に属する 2 つのサイトがあり、訪問者がそれらのサイト間を移動した場合、各サイトでは、そのサイトで最近表示された項目のみが表示されます。2 つのサイトが同じ環境にあり、訪問者が 2 つのサイト間を切り替えると、訪問者には、両方のサイトで最近閲覧された同じ項目が表示されます。

>[!NOTE]
>
>バックアップの推奨事項に [!UICONTROL Recently Viewed Items] の条件を使用することはできません。

[!UICONTROL Recently Viewed Items] または [!UICONTROL Recently Viewed Media] は、特定の属性を持つ項目のみが表示されるようにフィルタリングできます。

* recommendations の他の条件と同様に、[!UICONTROL Recently Viewed] の条件も設定できます。
* [ 収集 ](/help/main/c-recommendations/c-products/collections.md)、[ 除外 ](/help/main/c-recommendations/c-products/exclusions.md) および [ 含む ](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) （価格と在庫の特別ルールを含む）は、他の条件と同じように使用できます。

考えられるユースケースとしては、複数の企業を抱える多国籍企業では、複数のデジタルプロパティをまたいで訪問者ビューの項目を持つ場合があります。 その場合は、最近表示した項目をレコメンデーションする場所を、それが表示された各プロパティのみに制限できます。これにより、最近閲覧された項目が別のデジタルプロパティのサイトに表示されるのを防ぐことができます。

このアルゴリズムは、ホームページやランディングページ、オフサイト広告など、一般的なページで使用します。

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] は、除外のグローバル設定と、アクティビティで選択したコレクション設定の両方を尊重します。 グローバルな除外によって除外されている項目、または選択したコレクションに含まれていない項目は表示されません。 したがって、[!UICONTROL Recently Viewed Items] 条件を使用する場合は、通常、「すべてのコレクション」設定を使用する必要があります。

### [!UICONTROL Recommended for You] {#recommended-for-you}

各訪問者のブラウジング、表示および購入履歴に基づいて項目をレコメンドします。

このアルゴリズムにより、新規訪問者と再訪問者の両方に対して、パーソナライズされたコンテンツとエクスペリエンスを提供できます。 Recommendations のリストは、訪問者の最新のアクティビティに対して重み付けされます。また、セッション内で更新され、ユーザーがサイトを閲覧するにつれてより詳細にパーソナライズされます。

表示と購入の両方を使用して、推奨項目を決定します。 指定したレコメンデーションキー（[!UICONTROL Current Item] など）は、選択したインクルージョンルールフィルターの適用に使用されます。

例えば、次のことができます。

* 特定の条件を満たさない項目（在庫切れの製品、30 日以上前に公開された記事、R に評価された映画など）を除外します。
* 含める項目を 1 つのカテゴリまたは現在のカテゴリに制限します。

このアルゴリズムを選択すると、次のフィルタリングキーを選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

## カスタム条件 {#custom}

[!UICONTROL Custom Criteria] のアルゴリズムタイプを使用すると、アップロードしたカスタムファイルに基づいてお勧めを紹介できます。

レコメンデーションは、2 つの属性（user.*x* または profile.*x* 属性）のどちらかを使用して、訪問者のプロファイルに格納された品目によって決定されます。

このオプションを選択した場合、`entity.id` の値がプロファイル属性に存在する必要があります。

レコメンデーションをカスタム属性に基づいておこなう場合、カスタム属性を選択してからレコメンデーションタイプを選択する必要があります。

カスタム条件の出力にリアルタイムでフィルターを適用することができます。例えばレコメンデーション品目を、訪問者のお気に入りのカテゴリやブランドのものに絞ることができます。オフラインの計算結果とリアルタイムのフィルタリングを組み合わせることができます。

つまり、[!DNL Target] を使用して、オフラインで計算されたレコメンデーションやカスタムキュレートされたリストにパーソナライゼーションを追加できます。 これにより、データサイエンティストのスキルと、配信、ランタイムフィルタリング、A/B テスト、ターゲティング、レポート、統合などのアドビの実証済みの機能を連携させることができます。

[!UICONTROL Custom Criteria] にインクルージョンルールを追加すると、静的なレコメンデーションが訪問者の興味に基づく動的なレコメンデーションに変換されます。

* カスタム条件は、レコメンデーションの他の条件と同じように変更可能です。
* [ 収集 ](/help/main/c-recommendations/c-products/collections.md)、[ 除外 ](/help/main/c-recommendations/c-products/exclusions.md) および [ 含む ](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) （価格と在庫の特別ルールを含む）は、他の条件と同じように使用できます。

主な使用例は次のとおりです。

* 独自に作成したリストのムービーをレコメンデーションしようと考えているが、まだ対象のムービーを視聴していない訪問者のみをターゲットにしたい。
* オフラインアルゴリズムを実行し、その結果を使用してレコメンデーションを強化しますが、在庫切れの項目が推奨されないようにする必要があります。
* 訪問者のお気に入りのカテゴリの品目のみに対象を絞りたい。

## レコメンデーションキー {#keys}

次のレコメンデーションキーが [!UICONTROL Recommendation Key] ドロップダウンリストから表示されます。

### [!UICONTROL Current Item] {#current-item}

レコメンデーションは、訪問者が現在閲覧中の品目によって決定されます。

レコメンデーションは、指定した品目に興味を示している訪問者が興味を示す可能性のある他の品目を表示します。

このオプションを選択した場合、`entity.id` の値を表示 mbox でパラメーターとして渡す必要があります。

次のアルゴリズムで使用できます。

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

サイトの [!UICONTROL Current Item] Recommendations キーを次の場所で使用します。

* 商品ページなどの、単一の品目ページ。
* 検索結果が null のページに使用しないでください。

### [!UICONTROL Last Purchased Item] {#last-purchased}

レコメンデーションは、各ユニーク訪問者が購入した最後の品目によって決定されます。これは自動的に取り込まれるので、ページで値を渡さないでください。

次のアルゴリズムで使用できます。

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

サイトの [!UICONTROL Last Purchased Item] Recommendations キーを次の場所で使用します。

* ホームページ、マイアカウントページ、オフサイト広告。
* 商品ページまたは購入に関連するページには使用しないでください。

#### カスタム Recommendations キー

カスタムプロファイル属性の値に基づいてレコメンデーションを設定できます。例えば、訪問者が最後にキューに追加したムービーに基づいて、お勧めのムービーを表示するとします。

1. **[!UICONTROL Recommendation Key]** ドロップダウンリストからカスタムプロファイル属性（例：「[!UICONTROL Last Show Added to Watchlist]」）を選択します。
1. 次に、**[!UICONTROL Recommendation Logic]** を選択します（例：「[!UICONTROL People Who Viewed This, Viewed That]」）。

カスタムプロファイル属性と直接一致するエンティティ ID がない場合は、エンティティとの照合方法を [!DNL Recommendations] に指示する必要があります。例えば、訪問者のお気に入りのブランドの売れ筋商品を表示するとします。

1. **[!UICONTROL Recommendation Key]** ドロップダウンリストからカスタムプロファイル属性（「お気に入りのブランド」など）を選択します。

1. 次に、このキーで使用する **[!UICONTROL Recommendation Logic]** を選択します（例：「[!UICONTROL Top Sellers]」）。

   [!UICONTROL Group By Unique Value Of] オプションが表示されます。

1. 選択したキーに一致するエンティティ属性を選択します。 この場合、「[!UICONTROL Favorite Brand]」は `entity.brand` と一致します。

   [!DNL Recommendations] では、ブランドごとに「[!UICONTROL Top Sellers]」リストを生成し、訪問者の [!UICONTROL Favorite Brand] プロファイル属性に格納された値に基づいて適切な「[!UICONTROL Top Sellers]」リストを訪問者に表示するようになりました。

### [!UICONTROL Last Viewed Item] {#last-viewed}

レコメンデーションは、各ユニーク訪問者が閲覧した最後の品目によって決定されます。これは自動的に取り込まれるので、ページで値を渡さないでください。

次のアルゴリズムで使用できます。

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

サイトの [!UICONTROL Last Viewed Item] Recommendations キーを次の場所で使用します。

* ホームページ、マイアカウントページ、オフサイト広告。
* 商品ページまたは購入に関連するページには使用しないでください。

### [!UICONTROL Most Viewed Item] {#most-viewed-logic}

サイトで最も頻繁に表示される項目またはメディアを表示します。

このロジックを使用すると、サイトで最も多く表示されたアイテムに基づいてお勧めを表示し、他のアイテムのコンバージョンを増やすことができます。 例えば、メディアサイトでは、最も多く視聴されたビデオに関するレコメンデーションをホームページに表示して、訪問者に追加のビデオを視聴するよう促すことができます。

このレコメンデーションキーは、次のアルゴリズムで使用できます。

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

### [!UICONTROL Current Category] {#current-category}

レコメンデーションは、訪問者が現在閲覧中の商品カテゴリによって決定されます。

レコメンデーションは、指定した商品カテゴリの品目を表示します。

このオプションを選択した場合、`entity.categoryId` の値を表示 mbox にパラメーターとして渡す必要があります。

このレコメンデーションキーは、次のアルゴリズムで使用できます。

* [!UICONTROL Top Sellers]
* [!UICONTROL Most Viewed]

サイトの [!UICONTROL Current Category] Recommendations キーを次の場所で使用します。

* 単一のカテゴリページ。
* 検索結果が null のページに使用しないでください。

### [!UICONTROL Favorite Category] {#favorite-category}

レコメンデーションは、訪問者のお気に入りの製品カテゴリによって決定されます。

レコメンデーションは、指定した商品カテゴリの品目を表示します。

このオプションを選択した場合、`entity.categoryId` の値を表示 mbox にパラメーターとして渡す必要があります。

このレコメンデーションキーは、次のアルゴリズムで使用できます。

* [!UICONTROL Top Sellers]
* [!UICONTROL Most Viewed]

サイトの [!UICONTROL Current Category] Recommendations キーを次の場所で使用します。

* 単一のカテゴリページ。
* 検索結果が null のページに使用しないでください。

### [!UICONTROL Site Affinity] {#site-affinity}

品目間の関係の確実性に基づいて品目をレコメンドします。この条件を設定して、レコメンデーションスライダーを使用してレコメンデーションが表示されるまで必要なデータの量を決定で [!UICONTROL Inclusion Rules] ます。 例えば、「強」を選択した場合は、一致の確実性が最も高い製品を推奨します。

例えば、非常に強い親和性を設定して、デザインに 5 つの品目を含め、そのうちの 3 つが結びつきの強さのしきい値を満たしている場合、強さの最低要件を満たさない 2 つの品目は、レコメンデーションには表示されず、あらかじめ定義された代替品目が代わりに表示されます。最も強い親和性を持つ品目が最初に表示されます。

例えば、オンライン小売業者は、訪問者が過去のセッションで興味を示した項目を、その後の訪問でレコメンデーションできます。 各訪問者のセッションのアクティビティがキャプチャされ、最新性と頻度モデルに基づいてアフィニティを計算します。 この訪問者がサイトに戻ると、サイトのアフィニティを使用して、サイトでの過去のアクションに基づいてお勧めが表示されます。

多様な商品コレクションや多様なサイト行動のある顧客の場合は、サイトの親和性を弱く設定した方が、最適な結果が得られることがあります。

このロジックは、次のレコメンデーションキーで使用できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]
