---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: Adobe Analyticsを行動データソースとして使用すると、クライアントはAdobe RecommendationsのAnalyticsの表示ベースおよび購入ベースの行動データを使用できます。
title: Adobe AnalyticsとターゲットRecommendationsを使う
feature: criteria
translation-type: tm+mt
source-git-commit: 205850df6108db962a4ab514c027b7d04effaa76
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 2%

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

### 導入手順

すべての前提条件が満たされていると仮定し、次のタスクを実行します。

1. で、 [!DNL Target]管理 **[!UICONTROL /]** 導入 **[!UICONTROL をクリックして、]**[!DNL Target] クライアントコードを取得します。

   ![クライアントコード](/help/c-recommendations/c-algorithms/assets/client-code.png)

1. レポートスイートを取得し [!DNL Analytics] ます。

   実 [!DNL Analytics] 稼動サイトのレポートスイートを使用します。 これは、デプロイしたサイトを追跡するレポートスイートで [!DNL Recommendations] す。

1. で、 [!DNL Analytics]管理者 **[!UICONTROL /]** データフィードをクリックします ****。

   ![設定/データフィード](/help/c-recommendations/c-algorithms/assets/data-feed.png)

1. Click **[!UICONTROL Add]** to create a new feed.

   ![追加飼料](/help/c-recommendations/c-algorithms/assets/add-feed.png)

1. フィード情報を入力します。

   * **名前**:製品フィードを再利用
   * **レポートスイート**:事前に決定されたレポートスイート
   * **電子メール**:管理者ユーザーに適したアドレスを指定します
   * **フィード間隔**:目的の間隔を選択します
   * **遅延処理**:遅延なし。
   * **開始日と終了日**:連続フィード

   ![「フィード情報」セクション](/help/c-recommendations/c-algorithms/assets/feed-information.png)

1. Fill in the details in the **[!UICONTROL Destination]** section:

   >[!NOTE]
   > 
   >この手順を実行する前に、 [!DNL Adobe Analytics] チームに問い合わせてください。

   * **タイプ**:FTP
   * **Host**: `xxx.yyy.com`
   * **パス**:クライアント [!DNL Target] コード
   * **ユーザー名**:ユーザー名を指定します
   * **パスワード**:パスワードの指定

   スクリーンショットは参照用です。 展開には異なる資格情報が含まれます。 この手順を実行する際は、 [!DNL Adobe Analytics] チームまたはカスタマーケアにお問い合わせください。

   ![宛先セクション](/help/c-recommendations/c-algorithms/assets/destination.png)

1. 「 **[!UICONTROL データ列]** 」の定義を入力します。

   * **圧縮形式**:Gzip
   * **パッケージの種類**: 単一ファイル
   * **マニフェスト：** ファイルを終了

      ![圧縮形式、パッケージ化タイプ、マニフェストの設定](/help/c-recommendations/c-algorithms/assets/compression.png)

   * **含まれる列**:

      >[!IMPORTANT]
      >
      >列は、ここに記載されているのと同じ順序で追加する必要があります。 次の順序で列を選択し、各列の **** 追加をクリックします。

      * hit_time_gmt
      * visid_high
      * visid_low
      * event_list
      * product_list
      * visit_num

1. 「**[!UICONTROL 保存]**」をクリックします。

   ![データ列の定義の節](/help/c-recommendations/c-algorithms/assets/data-column-definitions.png)

これでセットアップは [!DNL Analytics] 終了です。 次に、行動データを継続的に提供するために、これらの変数を [!DNL Target] 同時にマップします。

## ターゲットでの実装

1. ターゲットで、 **[!UICONTROL Recommendationsをクリックし]**、「 **[!UICONTROL フィード]** 」タブをクリックします。

   ![フィード](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. 「フィードを **[!UICONTROL 作成]**」をクリックします。

1. 「 **[!UICONTROL Analytics分類]**」を選択し、レポートスイートを指定します。

   ![「Analytics分類」オプション](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. 「 **[!UICONTROL マッピング]**」をクリックし、フィールドの列見出しを適切な  Recommendationsフィールド名にマップします。

   ![「Mapping」セクション](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. 「**[!UICONTROL 保存]**」をクリックします。