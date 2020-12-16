---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: Adobe Analyticsを行動データソースとして使用すると、クライアントはAdobe RecommendationsのAnalyticsの表示ベースおよび購入ベースの行動データを使用できます。
title: Adobe AnalyticsとターゲットRecommendationsを使う
feature: criteria
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 2%

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

どのデータソースを使用するかを迅速に判断するために、ユーザーが毎日生成するオーガニックデータが多く、履歴データへの依存度が低い場合は、[!DNL Target] mboxを行動データソースとして使用するのが最適です。 最近生成されたオーガニックデータの入手が少ない場合に、[!DNL Analytics]データを&lt;a0/>データの上に置き換えたいなら、[!DNL Analytics]を行動データソースとして使うのが適当です。

### 導入手順

すべての前提条件が満たされている場合は、次のタスクを[!DNL Adobe Target Recommendations]チームが実行する必要があります。

>[!IMPORTANT]
>
>以下の手順は、例示的な目的でのみ使用します。 [!DNL Recommendations]チームのメンバーは、現在これらの手順を実行する必要があります。 [詳しくは、カスタマー](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) ケアにお問い合わせください。

1. [!DNL Target]で、**[!UICONTROL 管理]**/**[!UICONTROL 実装]**&#x200B;をクリックして、[!DNL Target]クライアントコードを取得します。

   ![クライアントコード](/help/c-recommendations/c-algorithms/assets/client-code.png)

1. [!DNL Analytics]レポートスイートを取得します。

   [!DNL Analytics]実稼働サイトのレポートスイートを使用します。 これは、[!DNL Recommendations]がデプロイ済みのサイトを追跡するレポートスイートです。

1. [!DNL Analytics]で、**[!UICONTROL 管理者]**/**[!UICONTROL データフィード]**&#x200B;をクリックします。

   ![設定/データフィード](/help/c-recommendations/c-algorithms/assets/data-feed.png)

1. **[!UICONTROL 追加]**&#x200B;をクリックして、新しいフィードを作成します。

   ![追加飼料](/help/c-recommendations/c-algorithms/assets/add-feed.png)

1. フィード情報を入力します。

   * **名前**:製品フィードを再利用
   * **レポートスイート**:事前に決定されたレポートスイート
   * **電子メール**:管理者ユーザーに適したアドレスを指定します
   * **フィード間隔**:目的の間隔を選択します
   * **遅延処理**:遅延なし。
   * **開始日と終了日**:連続フィード

   ![「フィード情報」セクション](/help/c-recommendations/c-algorithms/assets/feed-information.png)

1. **[!UICONTROL 宛先]**&#x200B;セクションの詳細を入力します。

   >[!NOTE]
   > 
   >この手順を実行する前に、[!DNL Adobe Analytics]チームに問い合わせてください。

   * **タイプ**:FTP
   * **Host**: `xxx.yyy.com`
   * **パス**:お使いの [!DNL Target] クライアントコード
   * **ユーザー名**:ユーザー名を指定します
   * **パスワード**:パスワードの指定

   スクリーンショットは参照用です。 展開には異なる資格情報が含まれます。 この手順を実行する際は、[!DNL Adobe Analytics]チームまたはカスタマーケアにお問い合わせください。

   ![宛先セクション](/help/c-recommendations/c-algorithms/assets/destination.png)

1. **[!UICONTROL データ列]**&#x200B;の定義を入力します。

   * **圧縮形式**:Gzip
   * **パッケージの種類**:単一ファイル
   * **マニフェスト：** 終了ファイル

      ![圧縮形式、パッケージ化タイプ、マニフェストの設定](/help/c-recommendations/c-algorithms/assets/compression.png)

   * **含まれる列**:

      >[!IMPORTANT]
      >
      >列は、ここに記載されているのと同じ順序で追加する必要があります。 次の順序で列を選択し、各列に対して&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックします。

      * hit_time_gmt
      * visid_high
      * visid_low
      * event_list
      * product_list
      * visit_num

1. 「**[!UICONTROL 保存]**」をクリックします。

   ![データ列の定義の節](/help/c-recommendations/c-algorithms/assets/data-column-definitions.png)

これで[!DNL Analytics]側の設定は完了です。 今こそ、行動データを継続的に提供するために[!DNL Target]側でこれらの変数をマッピングする時です。

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

