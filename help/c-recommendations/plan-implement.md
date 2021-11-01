---
keywords: Recommendations;設定;環境設定;業種;非互換の条件をフィルター;デフォルトホストグループ;サムネールのベース URL;Recommendation API トークン
description: 'Adobe TargetでRecommendationsアクティビティを実装する方法を説明します。 '
title: Recommendations Activities の実装方法
feature: Recommendations
exl-id: b6edb504-a8b6-4379-99c1-6907e71601f9
source-git-commit: cc260620cf87feebcd4c43f45f05406ac845cf5b
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 37%

---

# ![プレミアム](/help/assets/premium.png) 計画と実装 [!DNL Recommendations]

最初の [!DNL Recommendations] アクティビティ [!DNL Adobe Target]、次の手順を実行します。

1. [実装方法 [!DNL Target]](#implement-target) Web およびモバイルアプリ上で、ユーザーの行動をキャプチャし、レコメンデーションを配信する際に使用するを設定できます。
1. [の設定 [!DNL Recommendations] カタログ](#rec-catalog) ユーザーにレコメンデーションする製品またはコンテンツの数を指定します。
1. [行動情報とコンテキストを渡す](#pass-behavioral) から [!DNL Target Recommendations] パーソナライズされたレコメンデーションを配信できるようにします。
1. [グローバル除外の設定](#exclusions).
1. [設定 [!DNL Recommendations] 設定](#concept_C1E1E2351413468692D6C21145EF0B84).

## 実装方法 [!DNL Target] {#implement-target}

[!DNL Target Recommendations] requires you to implement the [!DNL Adobe Experience Platform Web SDK] or at.js 0.9.2 (or later). See [Implement [!DNL Target]](/help/c-implementing-target/implementing-target.md) for more information.

## Set up your Recommendations catalog {#rec-catalog}

To deliver high-quality recommendations, [!DNL Target] must know about the products or content that you want to recommend. Your catalog should usually include three types of information about the items you want to recommend. 映画をレコメンデーションするとします。 以下を含めます。

1. レコメンデーションを受け取るユーザーに表示したいデータ。For example, you can display the name of the movie and a URL for a thumbnail image of the movie poster.
1. マーケティングおよびマーチャンダイジング制御に便利なデータ。例えば、映画の評価を表示して、NC-17 映画をレコメンデーションしないようにすることができます。
1. Data that is useful for determining the similarity of items to other pieces of items. 例えば、映画のジャンルや映画の監督を表示できます。

[!DNL Target] は、カタログに入力するための複数の統合オプションを提供します。 これらのオプションを組み合わせて使用して、カタログ内の異なる項目を更新したり、異なる頻度で異なる項目属性を更新したりできます。

| メソッド | 内容 | 使用するタイミング | 追加情報 |
| --- | --- | --- | --- |
| カタログフィード | フィードのスケジュール設定 (CSV、Google Product XML、または [!DNL Analytics Product Classifications]) が毎日アップロードされ、取り込まれます。 | 一度に複数の項目に関する情報を送信する場合。 頻繁に変更されない情報を送信する場合。 | 詳しくは、 [フィード](/help/c-recommendations/c-products/feeds.md). |
| エンティティ API | Call an API to send to-the-minute updates for a single item. | 一度に 1 つの項目に関する更新が発生した場合に送信するためのものです。 頻繁に変更される情報（価格、在庫/在庫レベルなど）を送信する場合。 | See the [Entities API developer documentation](https://developers.adobetarget.com/api/recommendations/#tag/Entities). |
| Pass updates on the page | Send to-the-minute updates for a single item using JavaScript on the page or using the Delivery API. | For sending updates as they happen about one item at a time. 頻繁に変更される情報（価格、在庫/在庫レベルなど）を送信する場合。 | 詳しくは、 [品目ビュー/製品ページ](#items-product-pages) 下 |

Most customers should implement at least one feed. You can then choose to complement your feed with updates for frequently changed attributes or items using either the Entities API or on-the-page method.

## 行動情報とコンテキストを渡す {#pass-behavioral}

に渡す必要がある行動情報とコンテキスト [!DNL Target] は、訪問者がおこなうアクションに依存します。これは、多くの場合、訪問者がやり取りしているページのタイプに関連しています。

### 品目ビュー/製品ページ {#items-product-pages}

訪問者が製品の詳細ページなど、単一の品目を表示しているページでは、訪問者が表示している品目の ID を渡す必要があります。 また、現在のカテゴリに対するレコメンデーションをフィルタリングできるように、訪問者が表示する品目の最も詳細なカテゴリを渡す必要があります。

また、製品ページ自体で、すばやく変更された特定の属性を渡すこともできます。 例えば、`value`) および在庫/在庫レベル。

```
<script type="text/javascript">
function targetPageParams() { 
   return { 
      "entity": { 
         "id": "32323", 
         "categoryId": "running-shoes", 
         "value": 119.99, 
         "inventory": 329 
      } 
   } 
}
</script>
```

### Category views/category pages

On a category page, you likely want to restrict your recommendations to products or content within that category. To do so, ensure you pass the identity of the currently viewed category.

```
function targetPageParams() { 
   return { 
      "entity": { 
         "categoryId": "running-shoes" 
      } 
   } 
}
```

### 買い物かごへの追加/買い物かごの表示/チェックアウトページ {#cart}

On a cart page, you can recommend items based on the contents of the visitor&#39;s current cart. To do so, pass the IDs of all items in the visitor&#39;s current cart using the special parameter `cartIds`.

```
function targetPageParams() {
   return {
      "cartIds": ["352", "223", "23432", "432", "553"]
      }
}
```

詳しくは、 [!UICONTROL 買い物かごベース] recommendations, 「 [買い物かごベース](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) in *レコメンデーションキーに基づくレコメンデーションの設定*.

### 訪問者の買い物かごに既にある項目を除外

サイト全体のページで、レコメンデーションから一部の品目を除外できます。 例えば、訪問者の現在の買い物かごに既に含まれている品目をレコメンデーションしたくない場合があります。 それには、特別なパラメーターを使用して、除外するすべての項目の ID を渡します `excludedIds`.

```
function targetPageParams() {
   return {
      "excludedIds": ["352", "223", "23432", "432", "553"]
      }
}
```

### Purchases/order confirmation pages

購入イベントが発生したら、購入した品目の ID を渡します。 詳しくは、 [コンバージョンの追跡](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053) in *実装方法 [!DNL Target] タグマネージャーなし*.

## グローバル除外の設定 {#exclusions}

訪問者にレコメンデーションしたくないグローバルレベルの品目を除外します。 [除外](/help/c-recommendations/c-products/exclusions.md)を参照してください。

## 設定 [!DNL Recommendations] 設定 {#concept_C1E1E2351413468692D6C21145EF0B84}

設定を使用して [!DNL Recommendations] の実装を管理します。

次の手順で [!UICONTROL Recommendations Settings] オプション、開く [!DNL Target] 内 [!DNL Adobe Experience Cloud]を選択し、「 **[!UICONTROL Recommendations]** > **[!UICONTROL 設定]**.

![](assets/recs_settings.png)

以下のオプションがあります。

| 設定 | 説明 |
|--- |--- |
| カスタムグローバル mbox | （オプション）[!DNL Target] アクティビティを提供するために使用するカスタムグローバル mbox を指定します。デフォルトでは、[!DNL Target] によって使用されるグローバル mbox が [!DNL Recommendations] に使用されます。<br>注意：このオプションは、 [!DNL Target] [!UICONTROL 管理] ページ。 開く [!DNL Target]を選択し、「 [!UICONTROL 管理] > [!UICONTROL Visual Experience Composer]. |
| 業種 | 業種は、レコメンデーション条件の分類に使用されます。この情報は、買い物かごページやメディアページに最適な条件など、特定のページに適した条件をチームのメンバーが見つけるのに役立ちます。 |
| 非互換の条件をフィルター | このオプションを選択すると、選択されたページが必要なデータを渡す条件のみが表示されます。すべてのページですべての条件が正しく実行されるわけではありません。 ページまたは mbox にが渡される必要がある `entity.id` または `entity.categoryId` 現在の品目/現在のカテゴリのレコメンデーションと互換性を持たせるため。 通常は、互換性のある条件のみを表示するようにします。ただし、アクティビティで互換性のない条件を有効にしたい場合は、このオプションのチェックを外します。<br>タグ管理ソリューションを使用している場合は、このオプションを無効にすることをお勧めします。<br>このオプションについて詳しくは、[Recommendations FAQ](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) を参照してください。 |
| デフォルトホストグループ | デフォルトホストグループを選択します。<br>ホストグループを使用して、カタログの利用可能な項目をさまざまな用途に分割できます。例えば、ホストグループは開発環境と実稼動環境、さまざまなブランド、またはさまざまな地域に使用できます。デフォルトでは、カタログ検索、コレクションおよび除外のプレビュー結果はデフォルトのホストグループに基づいています。（環境フィルターを使用して、結果をプレビューする別のホストグループを選択することもできます）デフォルトでは、項目の作成または更新時に環境 ID が指定されている場合を除き、新しく追加された項目はすべてのホストグループで使用できます。配信される Recommendations は、リクエストで指定したホストグループによって異なります。<br>商品が表示されていない場合は、適切なホストグループが使用されていることを確認してください。例えば、ステージング環境を使用するようにレコメンデーションを設定し、ホストグループをステージングに設定した場合、商品を表示するために、ステージング環境のコレクションを再作成する必要がある可能性があります。各環境でどの商品が利用できるかを確認するには、各環境でカタログ検索を利用します。選択した環境（ホストグループ）の Recommendations コレクションと除外のコンテンツをプレビューすることもできます。<br>**注意：** 選択した環境を変更した後、 「検索」をクリックして返された結果を更新する必要があります。<br>[!UICONTROL 環境]フィルターは [!DNL Target] UI の次の場所で利用できます。<ul><li>カタログ検索（Recommendations／カタログ検索）</li><li>「コレクションを作成」ダイアログボックス（[!UICONTROL Recommendations／コレクション／新規作成]）</li><li>「コレクションを更新」ダイアログボックス（[!UICONTROL Recommendations／コレクション／編集]）</li><li>「除外を作成」ダイアログボックス（[!UICONTROL Recommendations／除外／新規作成]）</li><li>「除外を更新」ダイアログボックス（[!UICONTROL Recommendations／除外／編集]）</li></ul>詳しくは、[ホスト](/help/administrating-target/hosts.md)を参照してください。 |
| サムネールのベース URL | 商品カタログのベース URL を設定すると、商品のサムネールの指定でサムネール URL を渡す場合に、相対 URL を使用できます。<br>例：<br>`"entity.thumbnailURL=/Images/Homepage/product1.jpg"`<br> はサムネールのベース URL に対する相対 URL を設定します。 |
| Recommendations API トークン | Download API などの Recommendations API 呼び出しで、このトークンを使用します。 |
