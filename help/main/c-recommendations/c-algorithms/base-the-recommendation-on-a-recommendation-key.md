---
keywords: レコメンデーションキー；レコメンデーションロジック；現在のカテゴリ；カスタム属性；最後に購入した項目；最後に閲覧した項目；最も閲覧した項目；最も閲覧した項目；お気に入りのカテゴリ；人気；最近閲覧した項目；最後に購入した項目；最も閲覧した項目；最近閲覧した項目
description: 訪問者の行動コンテキストを使用して関連する結果を[!UICONTROL Recommendations] アクティビティに表示するキーに基づくレコメンデーションの使用方法について説明します。
title: '[!UICONTROL Recommendation]を[!UICONTROL Recommendation Key]に基にするにはどうすればよいですか？'
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
TQID: https://experienceleague.adobe.com/1gI3rMMf9s5ogc4BvBz4fMUqxed1Nqad0XoaR8SlU58
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 3510
ht-degree: 28%

---

# レコメンデーションキーに基づくレコメンデーションの設定

アルゴリズムに基づくレコメンデーションは、訪問者の行動コンテキストを使用して、[!DNL Adobe Target] [!DNL Recommendations]のアクティビティで関連する結果を表示します。

次の表に示すように、各アルゴリズムタイプは、そのタイプに適した異なるアルゴリズムを提供します。

| アルゴリズムタイプ | 使用するタイミング/使用可能なアルゴリズム |
| --- | --- |
| [!UICONTROL Cart-Based] | ユーザーのカートの内容に基づいてレコメンデーションを行います。<ul><li>[!UICONTROL People Who Viewed These, Also Viewed]</li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul> |
| [!UICONTROL Popularity-Based] | サイト全体でのアイテムの人気度や、ユーザーが好むカテゴリーや最も閲覧されたカテゴリー、ブランド、ジャンルなどの中でのアイテムの人気度にもとづいて、レコメンデーションを行うことができます。 <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
| [!UICONTROL Item-Based] | 利用者が現在閲覧している項目や最近閲覧した項目と類似する項目を見つけることで、レコメンデーションを行うことができます。 <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
| [!UICONTROL User-Based] | 利用者の行動にもとづいてレコメンデーションする： <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
| [!UICONTROL Custom Criteria] | アップロードしたカスタムファイルにもとづいて、レコメンデーションを作成できます。 <ul><li>カスタムアルゴリズム</li></ul> |

各条件は独自のタブで定義されます。 トラフィックは、異なる条件のテスト全体で等しく分割されます。 つまり、2 つの条件がある場合、トラフィックは等しく 2 分割されます。 2 つの条件と 2 つのデザインがある場合、トラフィックは 4 つの組み合わせに対して等しく分割されます。 さらに、比較のために、デフォルトコンテンツを表示するサイト訪問者の割合も指定できます。 その場合、指定した訪問者の割合にデフォルトのコンテンツが表示され、残りは条件とデザインの組み合わせに分割されます。

条件の作成とそのアルゴリズムのタイプとアルゴリズムの定義について詳しくは、[条件の作成](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)を参照してください。

レコメンデーションアルゴリズムが異なれば、異なるタイプのページに配置することができます。 各アルゴリズムタイプとその使用可能なアルゴリズムについて詳しくは、次の節を参照してください。

## カートベース {#cart-based}

[!UICONTROL Cart-Based] アルゴリズムの種類では、訪問者の現在の買い物かごの内容に基づいてアイテムをレコメンドできます。 レコメンデーションキーは、[mbox パラメーター`cartIds`](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=ja){target=_blank}を通じてコンマ区切りの値で指定されます。 最初の 10 個の値のみが考慮されます。

カートベースのレコメンデーションロジックは、「[!UICONTROL Recommended For You]」ユーザーベースのアルゴリズムと、「[!UICONTROL People Who Viewed These, Bought Those]」および「[!UICONTROL People Who Bought These, Bought Those]」アイテムベースのアルゴリズムに類似しています。

[!DNL Target]は、共同フィルタリング技術を使用して、訪問者のカート内の各項目の類似点を特定し、各項目でこれらの行動の類似点を組み合わせて、結合リストを取得します。

また、[!DNL Target]では、マーケターは1つのセッション内または複数のセッション間で訪問者の行動を調べることもできます。

* **[!UICONTROL Single Session]**：他の訪問者が1回のセッション内に実行した内容に基づきます。

  単一のセッション内の行動を見ることは、製品が使用状況、機会、イベントにもとづいて互いに「緊密に連携している」という感覚がある場合に意味があります。 例えば、プリンターを購入する場合、インクと紙が必要になります。 または、訪問者がピーナッツバターを購入しており、パンとゼリーが必要な場合もあります。

* **[!UICONTROL Across Sessions]**：他の訪問者が複数のセッションで行った内容に基づきます。

  複数のセッションにまたがる行動を見ることで、訪問者の好みや好みにもとづいて製品が互いに「合っている」という感覚を理解することができます。 例えば、スター・ウォーズが好きな訪問者や、インディアナ・ジョーンズが好きな訪問者は、必ずしも両方の映画を同じ席で見たいとは限らない場合でも、その訪問者を惹きつけることができます。 また、両方のゲームを同時にプレイできない場合でも、訪問者はボードゲーム「コードネーム」を好み、ボードゲーム「アバロン」を好むかもしれません。

[!DNL Target]は、1つのセッション内の訪問者の行動を見るか、複数のセッションを見るかに関係なく、現在のカート内のアイテムに基づいて、各訪問者に対するレコメンデーションを行います。

次のアルゴリズムは、[!UICONTROL Cart-Based] アルゴリズムタイプで使用できます。

### [!UICONTROL People Who Viewed This, Also Viewed]

指定した品目が閲覧された同じセッションで、閲覧される頻度が最も高い品目をレコメンドします。

このロジックは、このロジックを表示した後に表示された他の製品を返します。 指定した製品は結果セットに含まれていません。

このロジックにより、ある商品を閲覧した他の訪問者が閲覧した商品をレコメンドすることで、追加のコンバージョン機会を創出することができます。 例えば、サイトでロードバイクを閲覧した訪問者は、自転車のヘルメット、サイクリングキット、ロックなどを閲覧できます。 このロジックを使用して、レコメンデーションを作成することで、売上の向上に役立つ他の製品を提案できます。

このアルゴリズムを選択した場合は、次のレコメンデーションキーを選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Viewed This, Also Bought]

指定した品目が閲覧された同じセッションで、購入される頻度が最も高い品目をレコメンドします。

このロジックは、このロジックを閲覧した後に購入した他の製品を返します。 指定した製品は結果セットに含まれていません。

このロジックにより、たとえば、購入した商品を閲覧した他の訪問者の商品を表示する商品ページにレコメンデーションを表示することで、クロスセルの機会を増やすことができます。 例えば、釣り竿を閲覧している訪問者に対して、レコメンデーションには、タックルボックス、賭け金、釣りルールなど、他の訪問者が購入した追加のアイテムを表示することができます。 訪問者がサイトを閲覧するたびに、新たな購買レコメンデーションが提供されます。

このアルゴリズムを選択した場合は、次のレコメンデーションキーを選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Bought This, Also Bought]

指定した品目と同時に顧客に購入される頻度が最も高い品目をレコメンドします。

このロジックは、この商品を購入した後に購入した他の商品を返します。 指定した製品は結果セットに含まれていません。

このロジックにより、たとえば、ショッピングカートの概要ページにレコメンデーションを表示することで、クロスセルの機会を増やすことができます。このページには、他の購入者も購入した商品が表示されます。 例えば、訪問者がスーツを購入する場合、他の訪問者がスーツと一緒に購入した追加のアイテム（ネクタイ、ドレスシューズ、カフリンクなど）を表示することをお勧めします。 訪問者が購入をレビューする際には、関連するレコメンデーションを提供します。

このアルゴリズムを選択した場合は、次のレコメンデーションキーを選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

## [!UICONTROL Popularity-Based]

[!UICONTROL Popularity-Based] アルゴリズムの種類では、サイト全体でのアイテムの全体的な人気度に基づいて、またはユーザーのお気に入りまたは最も閲覧されたカテゴリ、ブランド、ジャンルなどの中のアイテムの人気度に基づいてレコメンデーションを行うことができます。

次のアルゴリズムは、[!UICONTROL Popularity-Based] アルゴリズムタイプで使用できます。

### [!UICONTROL Most Viewed Across the Site] {#most-viewed}

推奨は、最も頻繁に閲覧されたアイテムによって決まります。 これは次のように動作するリーセンシー／頻度条件により決定されます。

* 初回の商品閲覧は 10 ポイント
* 以降の閲覧は毎回 5 ポイント
* セッションの終わりにすべての値を 2 で割る

例えば、サーフボード A、サーフボード Bを1つのセッションで表示すると、A: 10、B: 5になります。 セッションが終了すると、A:5、B:2.5になります。 次のセッションで同じ項目を表示すると、値はA:15 B:7.5に変更されます。

このアルゴリズムは、ホームページやランディングページ、オフサイト広告などの一般的なページで使用します。

### [!UICONTROL Most Viewed by Category] {#most-viewed-category}

レコメンデーションは、最も多くのアクティビティを受信したカテゴリによって決定されます。商品ではなくカテゴリにポイントが付けられることを除き、「最も多く閲覧された品目」と同じメソッドを採用します。

これは次のように動作するリーセンシー／頻度条件により決定されます。

* 初回のカテゴリ閲覧は 10 ポイント
* 以降の閲覧は毎回 5 ポイント

最初に訪問したカテゴリには、10 ポイントが付与されます。 同じカテゴリへの次の訪問には、5 ポイントが付与されます。 訪問ごとに、以前表示した現在のカテゴリ以外のカテゴリは、1 ポイントずつ減点されます。

例えば、1つのセッションでカテゴリ A、カテゴリ Bを表示すると、A: 9、B: 10になります。 次のセッションで同じ品目を閲覧すると、値は 「A：20 B：9」 に変化します。

このアルゴリズムは、ホームページやランディングページ、オフサイト広告などの一般的なページで使用します。

カテゴリ別に最も表示されるアルゴリズムを選択した場合は、次のレコメンデーションキーを選択できます。

* [!UICONTROL Current Category]
* [!UICONTROL Favorite Category]

### [!UICONTROL Most Viewed by Item Attribute]

サイトで最も閲覧されたアイテムやメディアと類似したアイテムやメディアをレコメンドします。

このアルゴリズムでは、「名前」や「ブランド」など、レコメンデーションのベースとなる項目属性を選択できます。

次に、「お気に入りブランド」、「最後にカートに追加されたアイテム」、「最も閲覧された番組」など、訪問者のプロファイルに一致するように保存されているプロファイル属性を選択します。

### [!UICONTROL Top Sellers Across the Site] {#top-sellers}

サイト全体から最も完了済みの注文に含まれるアイテムが表示されます。 1 回の注文で同じ品目が複数含まれていても、1 回の注文としてカウントします。

このアルゴリズムにより、サイトで売れ筋商品に関するレコメンデーションを作成し、コンバージョンと収益を向上させることができます。 このロジックは、サイトへの初回訪問者に特に適しています。

### [!UICONTROL Top Sellers by Category]

最も完了済みの注文に含まれる品目をカテゴリ別に表示します。 1 回の注文で同じ品目が複数含まれていても、1 回の注文としてカウントします。

このアルゴリズムを利用すれば、カテゴリーにもとづいてサイトで売れ筋商品に関するレコメンデーションを作成し、コンバージョンと収益を向上させることができます。 このロジックは、サイトへの初回訪問者に特に適しています。

[!UICONTROL Most Viewed by Category] アルゴリズムを選択した場合は、次の[!UICONTROL Recommendations Keys]を選択できます。

* [!UICONTROL Current Category]
* [!UICONTROL Favorite Category]

### [!UICONTROL Top Sellers by Item Attribute]

サイトで最も購入された商品やメディアと類似した商品やメディアをレコメンドできます。

このアルゴリズムでは、「名前」や「ブランド」など、レコメンデーションのベースとなる項目属性を選択できます。

次に、「お気に入りブランド」、「最後にカートに追加されたアイテム」、「最も閲覧された番組」など、訪問者のプロファイルに一致するように保存されているプロファイル属性を選択します。

### [!UICONTROL Top by Analytics Metric]

*x*&#x200B;が任意の[!DNL Analytics]指標である「上位x」を表示します。 mboxの行動データを使用する場合は、[!UICONTROL Top Sold]または[!UICONTROL Top Viewed]を使用できます（x = &quot;Sold&quot;またはx = &quot;Viewed&quot;）。 [!DNL Adobe Analytics]の行動データを使用している場合は、x = &quot;買い物かごの追加&quot;またはその他の[!DNL Analytics]指標を使用できます。

## [!UICONTROL Item-Based]

[!UICONTROL Item-Based]のレコメンデーションタイプを使用すると、ユーザーが現在表示している項目または最近表示した項目と類似する項目を見つけることに基づいてレコメンデーションを行うことができます。

次のアルゴリズムは、[!UICONTROL Item-Based] アルゴリズムタイプで使用できます。

### [!UICONTROL People Who Viewed This, Viewed That] {#viewed-viewed}

指定した品目が閲覧された同じセッションで、閲覧される頻度が最も高い品目をレコメンドします。

このロジックは、このロジックを表示した後に表示された他の製品を返します。指定した製品は結果セットに含まれません。

このロジックにより、ある商品を閲覧した他の訪問者が閲覧した商品をレコメンドすることで、追加のコンバージョン機会を創出することができます。 例えば、サイトでロードバイクを閲覧した訪問者は、自転車のヘルメット、サイクリングキット、ロックなどを閲覧できます。 このロジックを使用して、レコメンデーションを作成することで、売上の向上に役立つ他の製品を提案できます。

このアルゴリズムを選択した場合は、次の[!UICONTROL Recommendations Keys]を選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Viewed This, Bought That] {#viewed-bought}

指定した品目が閲覧された同じセッションで、購入される頻度が最も高い品目をレコメンドします。 この条件によって、顧客が指定の商品を閲覧した後で購入した他の商品が返されるので、指定した商品は結果セットに含まれません。

このロジックは、このロジックを表示した後に購入した他の製品を返します。指定した製品は結果セットに含まれません。

このロジックにより、たとえば、購入した商品を閲覧した他の訪問者の商品を表示する商品ページにレコメンデーションを表示することで、クロスセルの機会を増やすことができます。 例えば、釣り竿を閲覧している訪問者に対して、レコメンデーションには、タックルボックス、賭け金、釣りルールなど、他の訪問者が購入した追加のアイテムを表示することができます。 訪問者がサイトを閲覧するたびに、新たな購買レコメンデーションが提供されます。

このアルゴリズムを選択した場合は、次の[!UICONTROL Recommendations Keys]を選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Bought This, Bought That] {#bought-bought}

指定した品目と同時に顧客に購入される頻度が最も高い品目をレコメンドします。

このロジックは、この商品を購入した後に購入した他の商品を返します。 指定した製品は結果セットに含まれていません。

このロジックにより、たとえば、ショッピングカートの概要ページにレコメンデーションを表示することで、クロスセルの機会を増やすことができます。このページには、他の購入者も購入した商品が表示されます。 例えば、訪問者がスーツを購入する場合、他の訪問者がスーツと一緒に購入した追加のアイテム（ネクタイ、ドレスシューズ、カフリンクなど）を表示することをお勧めします。 訪問者が購入をレビューする際には、関連するレコメンデーションを提供します。

このアルゴリズムを選択した場合は、次の[!UICONTROL Recommendations Keys]を選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL Items with Similar Attributes] {#similar-attributes}

現在のページアクティビティまたは過去の訪問者の行動に基づいた品目またはメディアに類似した品目またはメディアをレコメンドします。

[!UICONTROL Items with Similar Attributes]または[!UICONTROL Media with Similar Attributes]を選択した場合は、コンテンツの類似性ルールを設定するオプションがあります。

コンテンツの類似性を使用してレコメンデーションを生成することは、新しいアイテムに特に効果的です。過去の行動にもとづいて、[!UICONTROL People Who Viewed This]、[!UICONTROL Viewed That]およびその他のロジックを使用してレコメンデーションに表示される可能性は低くなります。 また、コンテンツの類似性を使用すると、過去の購入などの履歴データがない新規訪問者に対する便利なレコメンデーションを生成することもできます。

このアルゴリズムを選択した場合は、次の[!UICONTROL Recommendations Keys]を選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

詳しくは、[&#x200B; コンテンツの類似性](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity)を参照してください。

## [!UICONTROL User-Based]

[!UICONTROL User-Based] アルゴリズムの種類では、ユーザーの行動に基づいてレコメンデーションを行うことができます。

次のアルゴリズムは、[!UICONTROL User-Based] アルゴリズムタイプで使用できます。

### [!UICONTROL Recently Viewed Items] {#recently-viewed}

訪問者の履歴（複数セッションにわたる）を使用して、デザインのスロット数に基づいて、訪問者が閲覧した最後の *x* 品目を提示します。

[!UICONTROL Recently Viewed Items] アルゴリズムは、特定の[環境](/help/main/administrating-target/hosts.md)に固有の結果を返します。 別々の環境に属する 2 つのサイトがあり、訪問者がそれらのサイト間を移動した場合、各サイトでは、そのサイトで最近表示された項目のみが表示されます。 2つのサイトが同じ環境にあり、訪問者が2つのサイトを切り替えると、訪問者は両方のサイトで同じ最近表示された項目を見ることができます。

>[!NOTE]
>
>バックアップの推奨事項に[!UICONTROL Recently Viewed Items]条件を使用することはできません。

[!UICONTROL Recently Viewed Items]または[!UICONTROL Recently Viewed Media]をフィルタリングして、特定の属性を持つ項目のみを表示できます。

* [!UICONTROL Recently Viewed]条件は、レコメンデーションの他の条件と同様に設定可能です。
* [&#x200B; コレクション &#x200B;](/help/main/c-recommendations/c-products/collections.md)、[除外](/help/main/c-recommendations/c-products/exclusions.md)、[包含](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) （価格と在庫に関する特別なルールを含む）は、他の条件と同じように使用できます。

考えられるユースケースとしては、複数の企業を持つ多国籍企業が、複数のデジタルプロパティにまたがる訪問者ビュー項目を持っている場合があります。 その場合は、最近表示した項目をレコメンデーションする場所を、それが表示された各プロパティのみに制限できます。 これにより、最近閲覧した商品が、他のデジタルプロパティのサイトに表示されるのを防ぐことができます。

このアルゴリズムは、ホームページやランディングページ、オフサイト広告などの一般的なページで使用します。

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items]は、除外グローバル設定とアクティビティに対して選択したコレクション設定の両方を尊重します。 アイテムがグローバル除外によって除外されるか、選択したコレクションに含まれていない場合、アイテムは表示されません。 したがって、[!UICONTROL Recently Viewed Items]条件を使用する場合は、通常、「すべてのコレクション」設定を使用する必要があります。

### [!UICONTROL Recommended for You] {#recommended-for-you}

各訪問者の閲覧履歴、閲覧履歴、購入履歴にもとづいて、商品をレコメンデーションします。

このアルゴリズムにより、新規訪問者と再訪問者の両方にパーソナライズされたコンテンツとエクスペリエンスを提供できます。 レコメンデーションのリストは、訪問者の最新のアクティビティに合わせて調整され、セッション中に更新されます。ユーザーがサイトを閲覧するにつれて、よりパーソナライズされます。

ビューと購入の両方を使用して、推奨項目を決定します。 指定されたレコメンデーションキー（例：[!UICONTROL Current Item]）は、選択した包含ルールフィルターを適用するために使用されます。

例えば、次のことができます。

* 特定の基準を満たさない商品（在庫切れ、30日以上前に公開された記事、Rと評価された映画など）は除外します。
* 含まれる項目を1つのカテゴリまたは現在のカテゴリに制限します。

このアルゴリズムを選択した場合は、次のフィルタリングキーを選択できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

## カスタム条件 {#custom}

[!UICONTROL Custom Criteria] アルゴリズムの種類では、アップロードしたカスタム ファイルに基づいてレコメンデーションを行うことができます。

推奨事項は、ユーザー&#x200B;*x*&#x200B;またはプロファイル *x*&#x200B;属性を使用して、訪問者のプロファイルに保存されている項目によって決定されます。

このオプションを選択した場合、`entity.id` の値がプロファイル属性に存在する必要があります。

レコメンデーションをカスタム属性に基づいておこなう場合、カスタム属性を選択してからレコメンデーションタイプを選択する必要があります。

カスタム条件の出力にリアルタイムでフィルターを適用することができます。 例えばレコメンデーション品目を、訪問者のお気に入りのカテゴリやブランドのものに絞ることができます。 オフラインの計算結果とリアルタイムのフィルタリングを組み合わせることができます。

この機能により、[!DNL Target]を使用して、オフラインの計算されたレコメンデーションまたはカスタムでキュレートされたリストの上にパーソナライゼーションを追加できます。 これにより、データサイエンティストのスキルと、配信、ランタイムフィルタリング、A/B テスト、ターゲティング、レポート、統合などのアドビの実証済みの機能を連携させることができます。

[!UICONTROL Custom Criteria]に包含ルールが追加されたことで、訪問者の興味に基づいて、静的なレコメンデーションが動的なレコメンデーションに変換されます。

* カスタム条件は、レコメンデーションの他の条件と同じように変更可能です。
* [&#x200B; コレクション &#x200B;](/help/main/c-recommendations/c-products/collections.md)、[除外](/help/main/c-recommendations/c-products/exclusions.md)、[包含](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) （価格と在庫に関する特別なルールを含む）は、他の条件と同じように使用できます。

主な使用例は次のとおりです。

* 独自に作成したリストのムービーをレコメンデーションしようと考えているが、まだ対象のムービーを視聴していない訪問者のみをターゲットにしたい。
* オフラインアルゴリズムを実行し、その結果をレコメンデーションの参考にすることは重要です。しかし、在庫切れの商品がレコメンデーションされないようにする必要があります。
* 訪問者のお気に入りのカテゴリの品目のみに対象を絞りたい。

## レコメンデーションキー {#keys}

次のレコメンデーションキーは、[!UICONTROL Recommendation Key] ドロップダウンリストから使用できます。

### [!UICONTROL Current Item] {#current-item}

レコメンデーションは、訪問者が現在閲覧中の品目によって決定されます。

レコメンデーションは、指定した品目に興味を示している訪問者が興味を示す可能性のある他の品目を表示します。

このオプションを選択した場合、`entity.id` の値を表示 mbox でパラメーターとして渡す必要があります。

次のアルゴリズムで使用できます。

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

サイトの[!UICONTROL Current Item] レコメンデーションキーを次の場所で使用します。

* 商品ページなどの、単一の品目ページ。
* 検索結果が null のページに使用しないでください。

### [!UICONTROL Last Purchased Item] {#last-purchased}

レコメンデーションは、各ユニーク訪問者が購入した最後の品目によって決定されます。 これは自動的にキャプチャされるので、値をページに渡す必要はありません。

次のアルゴリズムで使用できます。

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

サイトの[!UICONTROL Last Purchased Item] レコメンデーションキーを次の場所で使用します。

* ホームページ、マイアカウントページ、オフサイト広告。
* 商品ページまたは購入に関連するページには使用しないでください。

#### カスタムレコメンデーションキー

カスタムプロファイル属性の値に基づいてレコメンデーションを設定できます。 例えば、訪問者が最後にキューに追加したムービーに基づいて、推奨ムービーを表示するとします。

1. **[!UICONTROL Recommendation Key]** ドロップダウンリストからカスタムプロファイル属性を選択します（例：「[!UICONTROL Last Show Added to Watchlist]」）。
1. 次に、**[!UICONTROL Recommendation Logic]** （例：「[!UICONTROL People Who Viewed This, Viewed That]」）を選択します。

カスタムプロファイル属性と直接一致するエンティティ ID がない場合は、エンティティとの照合方法を [!DNL Recommendations] に指示する必要があります。 例えば、訪問者のお気に入りのブランドの販売上位アイテムを表示するとします。

1. **[!UICONTROL Recommendation Key]** ドロップダウンリストからカスタムプロファイル属性を選択します（「お気に入りブランド」など）。

1. 次に、このキーで使用する&#x200B;**[!UICONTROL Recommendation Logic]**&#x200B;を選択します（例：「[!UICONTROL Top Sellers]」）。

   [!UICONTROL Group By Unique Value Of] オプションが表示されます。

1. 選択したキーに一致するエンティティ属性を選択します。 この場合、「[!UICONTROL Favorite Brand]」は`entity.brand`と一致します。

   [!DNL Recommendations]は、ブランドごとに「[!UICONTROL Top Sellers]」リストを生成し、訪問者の[!UICONTROL Favorite Brand] プロファイル属性に保存されている値に基づいて、訪問者に適切な「[!UICONTROL Top Sellers]」リストを表示するようになりました。

### [!UICONTROL Last Viewed Item] {#last-viewed}

レコメンデーションは、各ユニーク訪問者が閲覧した最後の品目によって決定されます。 これは自動的にキャプチャされるので、値をページに渡す必要はありません。

次のアルゴリズムで使用できます。

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

サイトの[!UICONTROL Last Viewed Item] レコメンデーションキーを次の場所で使用します。

* ホームページ、マイアカウントページ、オフサイト広告。
* 商品ページまたは購入に関連するページには使用しないでください。

### [!UICONTROL Most Viewed Item] {#most-viewed-logic}

サイトで最も頻繁に表示される項目またはメディアを表示します。

このロジックにより、サイトで最も閲覧されたアイテムに基づいてレコメンデーションを表示し、他のアイテムのコンバージョンを向上させることができます。 例えば、メディアサイトでは、最も閲覧された動画のレコメンデーションをホームページに表示し、訪問者に追加の動画を視聴するように促すことができます。

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

サイトの[!UICONTROL Current Category] レコメンデーションキーを次の場所で使用します。

* 単一のカテゴリページ。
* 検索結果が null のページに使用しないでください。

### [!UICONTROL Favorite Category] {#favorite-category}

レコメンデーションは、訪問者のお気に入りの商品カテゴリーによって決まります。

レコメンデーションは、指定した商品カテゴリの品目を表示します。

このオプションを選択した場合、`entity.categoryId` の値を表示 mbox にパラメーターとして渡す必要があります。

このレコメンデーションキーは、次のアルゴリズムで使用できます。

* [!UICONTROL Top Sellers]
* [!UICONTROL Most Viewed]

サイトの[!UICONTROL Current Category] レコメンデーションキーを次の場所で使用します。

* 単一のカテゴリページ。
* 検索結果が null のページに使用しないでください。

### [!UICONTROL Site Affinity] {#site-affinity}

品目間の関係の確実性に基づいて品目をレコメンドします。 この条件を設定すると、[!UICONTROL Inclusion Rules] スライダーを使用してレコメンデーションを表示する前にどの程度のデータが必要かを判断できます。 例えば、「非常に強い」を選択した場合、一致の確実性が最も高い製品が推奨されます。

例えば、非常に強い親和性を設定して、デザインに 5 つの品目を含め、そのうちの 3 つが結びつきの強さのしきい値を満たしている場合、強さの最低要件を満たさない 2 つの品目は、レコメンデーションには表示されず、あらかじめ定義された代替品目が代わりに表示されます。 最も強い親和性を持つ品目が最初に表示されます。

たとえば、オンラインのretailerでは、その後の訪問者の訪問時に、以前のセッションで興味を示した商品をレコメンドすることができます。 各訪問者のセッションのアクティビティをキャプチャし、最新性と頻度モデルにもとづいて親和性を計算します。 この訪問者がサイトに戻ってくると、サイト親和性は、サイトでの過去のアクションに基づいたレコメンデーションを表示するために使用されます。

多様な商品コレクションや多様なサイト行動のある顧客の場合は、サイトの親和性を弱く設定した方が、最適な結果が得られることがあります。

このロジックは、次のレコメンデーションキーで使用できます。

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]
