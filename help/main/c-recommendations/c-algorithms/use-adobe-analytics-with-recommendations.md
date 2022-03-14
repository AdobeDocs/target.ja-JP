---
keywords: 行動データソース；analytics；レコメンデーション；条件；製品変数
description: 使用方法を学ぶ [!DNL Adobe Analytics] を行動データソースとして使用し、 [!DNL Analytics] in [!DNL Target Recommendations].
title: 使用方法 [!DNL Adobe Analytics] と [!DNL Target Recommendations]?
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 2%

---

# ![プレミアム](/help/main/assets/premium.png) 用途 [!DNL Adobe Analytics] と [!DNL Recommendations]

使用 [!DNL Adobe Analytics] 行動データソースにより、クライアントは、 [!DNL Analytics] in [!DNL Adobe Target] [!DNL Recommendations] アクティビティ。 この機能は、特に [!DNL Target Recommendations] 設定が新しく、 [!DNL Analytics] には、使用する履歴データが多数あります。

使用 [!DNL Analytics] 行動データソースは、ユーザーの行動に関する豊富な情報のソースとして機能する場合があります。 この情報には、とのみ共有されるサードパーティのソースまたはフィードのデータが含まれる場合があります [!DNL Analytics].

While [条件の作成](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) in [!DNL Recommendations]を使用する場合、使用するデータソースを選択できるラジオボタンが 2 つあります。 [!UICONTROL mbox] または [!UICONTROL Analytics]. 条件を作成するには、 [!UICONTROL Recommendations] > [!UICONTROL 条件] > [!UICONTROL 条件の作成] > [!UICONTROL 条件の作成]. 詳しくは、[条件の作成](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)を参照してください。

![行動データソースボタン](assets/behavioral-data-source.png)

>[!NOTE]
>
>これらの 2 つのボタンがアカウントに表示されない場合は、 [カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Target での Analytics データの使用例

使用 [!DNL Analytics] また、recommendations の行動データソースを使用すると、エンティティページにすべての [!DNL Target] エンティティのパラメーター。 その場合は特定の前提条件を満たす必要がありますが、「製品変数」の可用性が、その機能をシームレスに機能させる上で最も重要な要素です。 通常の eVar と Prop は、このハンドシェイクが次の間で自動的に発生するには不十分です [!DNL Analytics] および [!DNL Target].

以下を使用できます。 [!DNL Analytics] を次の行動データソースに設定します。

* を使用して、先月同じカテゴリから他のユーザーが購入した内容に基づいて、小売サイトのレコメンデーションを製品の詳細ページのユーザーに表示する [!DNL Analytics] データ。
* トレンド分析を行っている特定のカテゴリの最頻訪問コンテンツを、 [!DNL Analytics] データ。

## での実装 [!DNL Analytics]

以下の節では、 [!DNL Analytics] サイド。

### 前提条件：製品変数を [!DNL Analytics]

での製品変数の実装 [!DNL Analytics] 必要な属性を持つ [!DNL Target Recommendations].

A [!DNL Target Recommendations] サンプルフィード形式は、すべての属性を製品変数で定義する必要があるガイドとして機能します。 後で、これらの値は [!DNL Target] 各 [!DNL Target] エンティティの値。

>[!NOTE]
>
>コンテンツサイトの場合は、各コンテンツピースを「products」として扱い、そのコンテンツに関する関連属性を属性として渡す必要があります。 このような属性には、作成者名、公開日、コンテンツタイトル、リリース月などが含まれます。 カテゴリレベルまたはカテゴリタイプの精度は、ユースケースの要件に基づいて、ビジネスで決定する必要があります。

製品変数の設定方法について詳しくは、 [製品](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) 内 *Adobe Analyticsの実装* ガイド。 このドキュメントのメモの一部は、デプロイ先のチームの裁量が必要です ( 例：カテゴリ )。 必ずお問い合わせください。 [!DNL Adobe] このアクティビティを実行する前に

### 注意点

[!DNL Analytics] データは日別フィードで送信されます。 行動の結果がサイトのレコメンデーションの結果に反映されるまでに最大 24 時間かかる場合があります。 すべてと同様 [!DNL Recommendations] 条件の設定に基づいて、このデータソースはテスト可能で、テストが必要です。

どのデータソースを使用するかを迅速に決定するために、ユーザーが毎日大量の有機的データを生成し、履歴データへの依存度が低い場合は、 [!DNL Target] mbox は、行動データソースに適しています。 最近生成された有機的データの可用性が低い場合、 [!DNL Analytics] データを、次に [!DNL Analytics] 行動データソースは適切なデータソースです。

次に、これらの変数を [!DNL Target] 行動データの継続的な供給のための側。

## の実装 [!DNL Target]

1. In [!DNL Target]をクリックし、 **[!UICONTROL Recommendations]**」、「 **[!UICONTROL フィード]** タブをクリックします。

   ![フィード](/help/main/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. クリック **[!UICONTROL フィードを作成]**.

1. 選択 **[!UICONTROL Analytics 分類]**」をクリックし、レポートスイートを指定します。

   ![Analytics 分類オプション](/help/main/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. クリック **[!UICONTROL 次へ]** 先に進む **[!UICONTROL スケジュール]** 設定で、フィードの頻度期間を選択します。

   * [!UICONTROL 毎日]
   * [!UICONTROL 毎週]
   * [!UICONTROL 2 週間ごと]
   * [!UICONTROL なし]

   また、フィードを処理する時刻を選択することもできます。

1. クリック **[!UICONTROL 次へ]** 先に進む  **[!UICONTROL マッピング]** を設定し、フィールドの列見出しを適切な [!UICONTROL Recommendations] フィールド名。

   ![「Mapping」セクション](/help/main/c-recommendations/c-algorithms/assets/mapping.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

## よくある質問

次の FAQ を考慮してください [!DNL Analytics] と [!DNL Target]:

### は `entity.id` および `entity.categoryId` 内で渡す必要のある値 [!DNL Target] mbox 呼び出し？

はい、この 2 つの値は引き続き必要です。 残りの属性は、 [!DNL Analytics] フィードに書き込むことができます。

### 動的インクルージョンルールを使用できますか。例えば、エンティティパラメーターが [!DNL Analytics] フィードアプローチ？

はい、できます。 メソッドは、 [!DNL Target] スタンドアロン。 ただし、この場合は、タイミング要因に注意する必要があります。 プロファイル変数と一致するエンティティ変数は、ページ上ではるか後に現れるデータレイヤーによって異なります。
