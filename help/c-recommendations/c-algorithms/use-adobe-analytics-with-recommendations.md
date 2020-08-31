---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: Adobe Analyticsを行動データソースとして使用すると、クライアントはAdobe RecommendationsのAnalyticsの表示ベースおよび購入ベースの行動データを使用できます。
title: Adobe AnalyticsとターゲットRecommendationsを使う
feature: criteria
translation-type: tm+mt
source-git-commit: 9bf30d6397fefdc85e51e2bd431ba163b10f6c09
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 1%

---


# RecommendationsでAdobe Analyticsを使用

行動データソース [!DNL Adobe Analytics] としてを使用すると、クライアントは、 [!DNL Analytics] recommendationsアクティビティからの表示ベースおよび購入ベースの行動データを使用でき [!DNL Adobe Target] ます。 この機能は、 [!DNL Target Recommendations] 設定が新しく、多くの履歴データを活用す [!DNL Analytics] る場合に特に便利です。

を行動データソース [!DNL Analytics] として使用すると、ユーザーの行動に関する豊富な情報源として機能します。 これには、サードパーティのソースまたはフィードのデータが含まれ、これらのソースまたはフィードは他のユーザーとのみ共有される場合があり [!DNL Analytics]ます。

Recommendationsで条件 [を作成する際](/help/c-recommendations/c-algorithms/create-new-algorithm.md) 、使用するデータソースを選択できるラジオボタンが2つあります。 [!UICONTROL mbox] 、 [!UICONTROL Analytics]。

![行動データソースボタン](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>この2つのボタンがアカウントに表示されない場合は、 [カスタマーケアにお問い合わせください](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

## ユースケース

をrecommendationsの行動データソース [!DNL Analytics] として使用すると、エンティティページにすべてのエンティティパラメーターをタグ付けする必要がなく、特定の使用例をデプロイする機能も提供され [!DNL Target] ます。 そのためには特定の前提条件を設定する必要がありますが、「製品変数」の利用は、その機能がシームレスに機能するために最も重要なことです。 このハンドシェイクがとの間で自動的に発生するには、通常のeVarとpropでは不十分 [!DNL Analytics] で [!DNL Target]す。

を行動データソース [!DNL Analytics] として使用して、次のことを行うことができます。

* Analyticsデータを使用して、先月同じカテゴリから他のユーザーが購入した購入内容に基づいて、PDPページのユーザーに小売サイトのレコメンデーションを表示します。
* データに基づいて、現在トレンドを示している特定のカテゴリで最も人気のあるコンテンツについて、メディアサイトのホーム画面にコンテンツを表示し [!DNL Analytics] ます。

## Analyticsでの実装

この機能は、次の節で [!DNL Analytics] 説明します。

### 前提条件：Analyticsの製品変数

に製品変数を実装し、に必要な属性 [!DNL Analytics] を設定する必要があり [!DNL Target Recommendations]ます。

サンプルのフィード形式は、すべての属性を製品変数で定義する必要があるガイドとして機能します。 [!DNL Target Recommendations] 後で、これらの値は、 [!DNL Target] UI内でそれぞれの [!DNL Target] エンティティ値に「マップ」する必要があります。

>[!NOTE]
>
>コンテンツサイトの場合、各コンテンツ部分は「製品」として扱われ、そのコンテンツに関する関連属性(例：著者名、発行日、コンテンツタイトル、リリース月など) を属性として渡す必要があります。 カテゴリレベルの精度やカテゴリタイプは、ユースケースの要件に基づいてビジネスで決定する必要があります。

製品変数の設定方法について詳しくは、 [Analytics導入ガイドの](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/products.html) 製品 *を参照してください*。 このドキュメントに記載されているメモの一部は、そのドキュメントを展開するチームに十分な注意を払う必要があります(例：カテゴリ)。 このアクティビティを行う前に、Adobeに問い合わせてください。

### 注意点

[!DNL Analytics] データは日別フィードを介して送信されます。 行動分析の結果がサイトのrecommendationsの結果に反映されるまでに最大24時間かかります。 すべての [!DNL Recommendations] 条件設定と同様に、このデータソースはテストが可能で、テストする必要があります。

どのデータソースを使用するかを迅速に判断するために、ユーザーが毎日大量に生成するオーガニックデータがあり、履歴データへの依存度が低い場合は、行動データソースとして [!DNL Target] mboxを使用するのが適切です。 最近生成されたオーガニックデータの可用性が低い場合に、データに基づいて銀行を行いたい場合は、行動データソースとしての使用 [!DNL Analytics][!DNL Analytics] が適切です。

### カスタマーケアに連絡して、データフィードを作成してもらう

すべての前提条件が満たされている場合は、 [カスタマーケアに連絡して、データフィードを作成してもらいます](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 。

## ターゲットでの実装

1. ターゲットで、 **[!UICONTROL Recommendationsをクリックし]**、「 **[!UICONTROL フィード]** 」タブをクリックします。

   ![フィード](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. 「フィードを **[!UICONTROL 作成]**」をクリックします。

1. 「 **[!UICONTROL Analytics分類]**」を選択し、レポートスイートを指定します。

   ![「Analytics分類」オプション](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. 「 **[!UICONTROL マッピング]**」をクリックし、フィールドの列見出しを適切な  Recommendationsフィールド名にマップします。

   ![「Mapping」セクション](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

## よくある質問

で使用するFAQを次 [!DNL Analytics] に示します [!DNL Target]。

### mbox呼び出し内で `entity.id` および `entity.categoryId`[!DNL Target] 値を渡す必要がありますか。

はい、この2つの値は必須です。 このドキュメントで説明するように、残りの属性は [!DNL Analytics] フィードを介して渡すことができます。

### フィードアプローチを使用して、エンティティパラメーターがプロファイル属性と一致するなど、動的な包含ルールを使用できま [!DNL Analytics] すか。

はい、できます。 この方法は、 [!DNL Target] スタンドアロンを使用する場合と同様です。 ただし、この場合は、タイミングに注意する必要があります。 プロファイル変数と一致すると想定されるエンティティ変数は、ページのかなり後で表示されるデータレイヤーに依存します。

