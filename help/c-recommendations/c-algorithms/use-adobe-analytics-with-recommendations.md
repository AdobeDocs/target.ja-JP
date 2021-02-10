---
keywords: 行動データソース；分析；レコメンデーション；条件；製品変数
description: ターゲットRecommendationsのAnalyticsで、Adobe Analyticsを行動データソースとして使用し、表示ベースおよび購入ベースの行動データを使用する方法について説明します。
title: Adobe AnalyticsとターゲットRecommendationsの使い方
feature: Recommendations
translation-type: tm+mt
source-git-commit: 87877502d25fe8da830f70126820d1ca825ebc9d
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 0%

---


# RecommendationsでAdobe Analyticsを使用

[!DNL Adobe Analytics]を行動データソースとして使用すると、クライアントは[!DNL Adobe Target] recommendationsアクティビティーで、[!DNL Analytics]の表示ベースおよび購入ベースの行動データを使用できます。 この機能は、[!DNL Target Recommendations]の設定が新しく、[!DNL Analytics]に多くの履歴データがある場合に特に役立ちます。

[!DNL Analytics]を行動データソースとして使用すると、ユーザーの行動に関する豊富な情報源として機能できます。 これには、[!DNL Analytics]とのみ共有されるサードパーティのソースまたはフィードのデータが含まれる場合があります。

Recommendationsで[条件](/help/c-recommendations/c-algorithms/create-new-algorithm.md)を作成する際、使用するデータソースを選択できるラジオボタンが2つあります。[!UICONTROL mboxs]または[!UICONTROL Analytics]。

![行動データソースボタン](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>この2つのボタンがアカウントに表示されない場合は、[カスタマーケア](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## ターゲットのAnalyticsデータの使用例

[!DNL Analytics]をrecommendationsの行動データソースとして使用すると、エンティティページにすべての[!DNL Target]エンティティパラメーターをタグ付けする必要がなく、特定の使用例をデプロイすることもできます。 そのためには特定の前提条件を設定する必要がありますが、「製品変数」の利用は、その機能がシームレスに機能するために最も重要なことです。 正規のeVarおよびpropは、このハンドシェイクが[!DNL Analytics]と[!DNL Target]の間で自動的に発生するのに十分ではありません。

[!DNL Analytics]を行動データソースとして使用すると、次のことができます。

* Analyticsデータを使用して、先月同じカテゴリから他のユーザーが購入した購入内容に基づいて、PDPページのユーザーに小売サイトのレコメンデーションを表示します。
* [!DNL Analytics]データに基づき、現在トレンドを示している特定のカテゴリで最も人気のあるコンテンツについて、メディアサイトのホーム画面にコンテンツを表示します。

## Analyticsでの実装

次の節は、この機能を[!DNL Analytics]側で実装する際に役立ちます。

### 前提条件：Analyticsでの製品変数の設定

[!DNL Analytics]に製品変数を実装し、[!DNL Target Recommendations]に必要な属性を指定する必要があります。

[!DNL Target Recommendations]サンプルフィード形式は、すべての属性を製品変数で定義する必要があるガイドとして機能します。 後で、これらの値は、それぞれの[!DNL Target]エンティティ値の[!DNL Target] UI内で「マップ」される必要があります。

>[!NOTE]
>
>コンテンツサイトの場合、各コンテンツ部分は「製品」として扱われ、そのコンテンツに関する関連属性(例：著者名、発行日、コンテンツタイトル、リリース月など) を属性として渡す必要があります。 カテゴリレベルの精度やカテゴリタイプは、ユースケースの要件に基づいてビジネスで決定する必要があります。

製品変数の設定方法について詳しくは、『*Analytics導入ガイド*』の[製品](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html)を参照してください。 このドキュメントに記載されているメモの一部は、そのドキュメントを展開するチームに十分な注意を払う必要があります(例：カテゴリ)。 このアクティビティを行う前に、Adobeに問い合わせてください。

### 注意点

[!DNL Analytics] データは日別フィードを介して送信されます。行動分析の結果がサイトのrecommendationsの結果に反映されるまでに最大24時間かかります。 すべての[!DNL Recommendations]条件設定と同様に、このデータソースはテストできます。

どのデータソースを使用するかを迅速に判断するために、ユーザーが毎日生成するオーガニックデータが多く、履歴データへの依存度が低い場合は、[!DNL Target] mboxを行動データソースとして使用するのが最適です。 最近生成されたオーガニックデータの入手が少ない場合に、[!DNL Analytics]データをデータの上に置き換えたいなら、[!DNL Analytics]を行動データソースとして使うのが適当です。

今こそ、行動データを継続的に提供するために[!DNL Target]側でこれらの変数をマッピングする時です。

## ターゲットでの実装

1. ターゲットで、「**[!UICONTROL Recommendations]**」をクリックし、「**[!UICONTROL フィード]**」タブをクリックします。

   ![フィード](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. 「**[!UICONTROL フィードを作成]**」をクリックします。

1. 「**[!UICONTROL Analytics分類]**」を選択し、レポートスイートを指定します。

   ![「Analytics分類」オプション](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. 「**[!UICONTROL マッピング]**」をクリックし、フィールドの列見出しを適切な[!UICONTROL Recommendations]フィールド名にマップします。

   ![「Mapping」セクション](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

## よくある質問

[!DNL Analytics]を[!DNL Target]と共に使用する場合は、次のFAQを考慮してください。

### `entity.id`と`entity.categoryId`の値は、[!DNL Target] mbox呼び出し内で渡す必要がありますか。

はい、この2つの値は必須です。 このドキュメントで説明するように、残りの属性は[!DNL Analytics]フィードを介して渡すことができます。

### [!DNL Analytics]フィードアプローチを使用して、エンティティパラメーターがプロファイル属性と一致するなど、動的な包含ルールを使用できますか。

はい、できます。 この方法は、[!DNL Target]スタンドアロンを使用する場合と同様です。 ただし、この場合は、タイミングに注意する必要があります。 プロファイル変数と一致すると想定されるエンティティ変数は、ページのかなり後で表示されるデータレイヤーに依存します。

