---
keywords: Recommendations;設定;環境設定;業種;非互換の条件をフィルター;デフォルトホストグループ;サムネールのベース URL;Recommendation API トークン
description: 'Adobe ターゲットで推奨事項を実装する方法について説明します。 '
title: 推奨事項の実装方法を教えてください。
feature: Recommendations
exl-id: b6edb504-a8b6-4379-99c1-6907e71601f9
source-git-commit: 68670f0b7753ee34c186a380004620ae4ba0cfd1
workflow-type: tm+mt
source-wordcount: '1290'
ht-degree: 37%

---

# ![高度なアドバイス ](/help/assets/premium.png) および実装に関する推奨事項

に最初のアクティビティを設定する前に [!DNL Recommendations] [!DNL Adobe Target] 、以下の手順を実行します。

| 手順 | 詳細 |
|--- |--- |
| ![手順 1](/help/c-recommendations/assets/step1_red.png) | [ [!DNL Adobe Target]](#implement-target)Web およびモバイルアプリケーションサーフェスに実装し、ユーザーの操作をキャプチャして推奨事項を提供します。 |
| ![手順 2](/help/c-recommendations/assets/step2_red.png) | [ [!DNL Recommendations]  ](#rec-catalog) ユーザーにおすすめさせる製品またはコンテンツのカタログを設定します。 |
| ![手順 3](/help/c-recommendations/assets/step3_red.png) | [行動情報とコンテキストを ](#pass-behavioral) 渡し [!DNL Adobe Target Recommendations] て、カスタマイズされた推奨内容を配信できるようにします。 |
| ![手順 4](/help/c-recommendations/assets/step4_red.png) | [グローバルな除外 ](#exclusions) を設定します。 |
| ![手順 5](/help/c-recommendations/assets/step5_red.png) | [ [!DNL Recommendations] 設定 ](#concept_C1E1E2351413468692D6C21145EF0B84) を構成します。 |

## Adobe ターゲットの実装 {#implement-target}

[!DNL Target Recommendations] (または、以降の) .js 0.9.2 を実装する必要があり [!DNL Adobe Experience Platform Web SDK] ます。 詳しく [ は、ターゲットの実装を参照してください ](/help/c-implementing-target/implementing-target.md) 。

## おすすめ候補カタログの設定 {#rec-catalog}

高画質なお勧め情報を提供するには、 [!DNL Target] 推奨される製品またはコンテンツについて知っておく必要があります。 通常、カタログには、推奨される項目に関する3種類の情報が含まれている必要があります。 ムービーを推奨する場合を考えてみましょう。 次のものが含まれます。

1. レコメンデーションを受け取るユーザーに表示したいデータ。例えば、ムービーの名前を表示したり、ムービーポスターのサムネールイメージの URL を表示したりすることができます。
1. マーケティングおよびマーチャンダイジング制御に便利なデータ。例えば、ムービーの定格を表示して、NC 17 のムービーを使用しないようにすることができます。
1. アイテムが他のアイテムに類似しているかどうかを調べるために使用されるデータです。 例えば、ムービーとビデオの監督のジャンルを表示することができます。

[!DNL Target] には、カタログを作成するための複数の統合オプションが用意されています。 これらのオプションを組み合わせて使用して、カタログ内の様々なアイテムを更新したり、異なる頻度で様々なアイテム属性を更新することができます。

| メソッド | その内容 | 使用するタイミング | 追加情報 |
| --- | --- | --- | --- |
| カタログフィード | 定期的に、アップロードと ingested のフィードを予約 [!DNL Analytics Product Classifications] するように設定します。 | (一度に複数の項目に関する情報を送信するために使用します)。 を使用して、頻繁に変更される情報を送信します。 | [フィードを参照してください ](/help/c-recommendations/c-products/feeds.md) 。 |
| Entities API | 1つの項目について、毎分更新を送信する API を呼び出します。 | では、一度に1つのアイテムを更新することができます。 頻繁に変更される情報 (価格、在庫、在庫レベルなど) を送信する場合に使用します。 | [ENTITIES API 開発者向けドキュメントを参照してください ](https://developers.adobetarget.com/api/recommendations/#tag/Entities) 。 |
| ページへの更新のパス | ページ上の JavaScript を使用して1つのアイテムについて、または配信 API を使用して、1つのアイテムを更新することができます。 | では、一度に1つのアイテムを更新することができます。 頻繁に変更される情報 (価格、在庫、在庫レベルなど) を送信する場合に使用します。 | 詳しくは、以下の項目ビュー/製品ページを参照してください。 |

ほとんどのユーザーは、少なくとも1つのフィードを実装する必要があります。 これにより、「エンティティー API」または「ページ上」メソッドのいずれかを使用して、頻繁に変更される属性やアイテムの更新を使用して、フィードを補うようにすることができます。

## 行動情報とコンテキストの引き渡し {#pass-behavioral}

実行する必要がある動作の情報とコンテキストは、ユーザーが実行する [!DNL Target] 操作によって異なります。これは、ユーザーが操作するページのタイプに関係することがよくあります。

### 項目ビュー/製品ページ

ユーザーが製品詳細ページなどの1つの項目を表示しているページでは、ビジターが表示する項目の id を渡す必要があります。 また、閲覧者が表示しているアイテムの最も細分化されたカテゴリを渡して、現在のカテゴリに対するフィルター選択を許可する必要があります。

製品ページには、すばやい変更属性を渡すこともできます。 例えば、price ( `value` ) および inventory/stock の各レベルを渡すことができます。

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

### カテゴリビューまたはカテゴリページ

カテゴリページで、そのカテゴリ内の製品またはコンテンツに対する推奨事項を制限することができます。 そのためには、現在表示されているカテゴリの id を渡すようにします。

```
function targetPageParams() { 
   return { 
      "entity": { 
         "categoryId": "running-shoes" 
      } 
   } 
}
```

### カート/カートビュー/チェックアウトページ

カートページに、訪問者の現在のカートの内容に基づいておすすめのアイテムが表示されます。 そのためには、ビジターが現在使用しているカート内のすべてのアイテムの Id を特殊パラメーターで渡し `cartIds` ます。

```
function targetPageParams() {
   return {
      "cartIds": ["352", "223", "23432", "432", "553"]
      }
}
```

### ビジターのカートに既に存在するアイテムは除外します。

サイト全体のページで、一部のアイテムを推奨設定から除外することができます。 例えば、ビジターの現在のカートに登録されているアイテムを推奨することはできません。 そのためには、特別なパラメーターを使用して、除外するすべての項目の Id を渡し `excludedIds` ます。

```
function targetPageParams() {
   return {
      "excludedIds": ["352", "223", "23432", "432", "553"]
      }
}
```

### 購入/注文確認ページ

購買イベントが発生した場合は、購入した品目の id を渡します。 [ ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053) *[!DNL Target] タグマネージャーを使用せずに、実装内のトラックの変換を参照してください* 。

## グローバル除外の設定 {#exclusions}

ユーザーに対して推奨されていないグローバルレベルのアイテムは除外します。 [除外](/help/c-recommendations/c-products/exclusions.md)を参照してください。

## 設定の構成 [!DNL Recommendations] {#concept_C1E1E2351413468692D6C21145EF0B84}

設定を使用して [!DNL Recommendations] の実装を管理します。

推奨設定オプションにアクセスするには、  でを開き [!DNL Target] [!DNL Adobe Experience Cloud] 、「 **[!UICONTROL 推奨事項 > 設定」をクリックし]** **** ます。

![](assets/recs_settings.png)

以下のオプションがあります。

| 設定 | 説明 |
|--- |--- |
| カスタムグローバル mbox | （オプション）[!DNL Target] アクティビティを提供するために使用するカスタムグローバル mbox を指定します。デフォルトでは、[!DNL Target] によって使用されるグローバル mbox が [!DNL Recommendations] に使用されます。<br>注意: このオプションは管理ページに設定されて [!DNL Target]  います。 を起動して [!DNL Target] 、「管理 >」をクリックし   ます。 |
| 業種 | 業種は、レコメンデーション条件の分類に使用されます。この情報は、ショッピングカートページやメディアページに最適な条件など、特定のページにとって有用な条件を、チームのメンバーが検索できるようにするために役立ちます。 |
| 非互換の条件をフィルター | このオプションを選択すると、選択されたページが必要なデータを渡す条件のみが表示されます。すべての条件が各ページで正しく実行されるわけではありません。 ページまたは mbox は、 `entity.id` `entity.categoryId` 現在のアイテムまたは現在の項目について、互換性のある項目についてのアドバイスを受ける必要があります。 通常は、互換性のある条件のみを表示するようにします。ただし、アクティビティで互換性のない条件を有効にしたい場合は、このオプションのチェックを外します。<br>タグ管理ソリューションを使用している場合は、このオプションを無効にすることをお勧めします。<br>このオプションについて詳しくは、[Recommendations FAQ](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) を参照してください。 |
| デフォルトホストグループ | デフォルトホストグループを選択します。<br>ホストグループを使用して、カタログの利用可能な項目をさまざまな用途に分割できます。例えば、ホストグループは開発環境と実稼動環境、さまざまなブランド、またはさまざまな地域に使用できます。デフォルトでは、カタログ検索、コレクションおよび除外のプレビュー結果はデフォルトのホストグループに基づいています。（環境フィルターを使用して、結果をプレビューする別のホストグループを選択することもできます）デフォルトでは、項目の作成または更新時に環境 ID が指定されている場合を除き、新しく追加された項目はすべてのホストグループで使用できます。配信される Recommendations は、リクエストで指定したホストグループによって異なります。<br>商品が表示されていない場合は、適切なホストグループが使用されていることを確認してください。例えば、ステージング環境を使用するようにレコメンデーションを設定し、ホストグループをステージングに設定した場合、商品を表示するために、ステージング環境のコレクションを再作成する必要がある可能性があります。各環境でどの商品が利用できるかを確認するには、各環境でカタログ検索を利用します。選択した環境（ホストグループ）の Recommendations コレクションと除外のコンテンツをプレビューすることもできます。<br>**注意：** 選択した環境を変更した後、 「検索」をクリックして返された結果を更新する必要があります。<br>[!UICONTROL 環境]フィルターは [!DNL Target] UI の次の場所で利用できます。<ul><li>カタログ検索（Recommendations／カタログ検索）</li><li>「コレクションを作成」ダイアログボックス（[!UICONTROL Recommendations／コレクション／新規作成]）</li><li>「コレクションを更新」ダイアログボックス（[!UICONTROL Recommendations／コレクション／編集]）</li><li>「除外を作成」ダイアログボックス（[!UICONTROL Recommendations／除外／新規作成]）</li><li>「除外を更新」ダイアログボックス（[!UICONTROL Recommendations／除外／編集]）</li></ul>詳しくは、[ホスト](/help/administrating-target/hosts.md)を参照してください。 |
| サムネールのベース URL | 商品カタログのベース URL を設定すると、商品のサムネールの指定でサムネール URL を渡す場合に、相対 URL を使用できます。<br>例：<br>`"entity.thumbnailURL=/Images/Homepage/product1.jpg"`<br> はサムネールのベース URL に対する相対 URL を設定します。 |
| Recommendations API トークン | Download API などの Recommendations API 呼び出しで、このトークンを使用します。 |
