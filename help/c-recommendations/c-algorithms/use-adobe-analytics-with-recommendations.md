---
keywords: 行動データソース；analytics；レコメンデーション；条件；製品変数
description: Adobe Analyticsを行動データソースとして使用し、Analytics の [!DNL Target] Recommendations。
title: Adobe Analyticsを [!DNL Target] Recommendations?
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 2a4cae206bf634bf3fbec65c5c4b289aadefede1
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 1%

---

# Adobe Analytics を Recommendations と併用する

使用 [!DNL Adobe Analytics] 行動データソースにより、クライアントは、 [!DNL Analytics] in [!DNL Adobe Target] recommendations アクティビティ。 この機能は、特に [!DNL Target Recommendations] 設定が新しく、 [!DNL Analytics] には、活用する履歴データが多数あります。

使用 [!DNL Analytics] 行動データソースは、ユーザーの行動に関する豊富な情報のソースとして機能する場合があります。 これには、とのみ共有されるサードパーティのソースまたはフィードからのデータが含まれる場合があります [!DNL Analytics].

While [条件の作成](/help/c-recommendations/c-algorithms/create-new-algorithm.md) Recommendationsには、使用するデータソースを選択できる 2 つのラジオボタンがあります。 [!UICONTROL mbox] または [!UICONTROL Analytics].

![行動データソースボタン](assets/behavioral-data-source.png)

>[!NOTE]
>
>これらの 2 つのボタンがアカウントに表示されない場合は、 [カスタマーケア](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Target での Analytics データの使用例

使用 [!DNL Analytics] また、recommendations の行動データソースでは、エンティティページにすべての [!DNL Target] エンティティのパラメーター。 その場合は特定の前提条件を満たす必要がありますが、「製品変数」の可用性が、その機能をシームレスに機能させる上で最も重要な要素です。 通常の eVar と Prop は、このハンドシェイクが次の間で自動的に発生するには不十分です [!DNL Analytics] および [!DNL Target].

以下を使用できます。 [!DNL Analytics] を次の行動データソースに設定します。

* Analytics データを使用して、先月同じカテゴリから他のユーザーが購入した内容に基づいて、小売サイトのユーザーに PDP ページ上のユーザーにレコメンデーションを表示する。
* トレンド分析を行っている特定のカテゴリの最頻訪問コンテンツを、 [!DNL Analytics] データ。

## Analytics での実装

以下の節では、 [!DNL Analytics] サイド。

### 前提条件：Analytics での製品変数の設定

製品変数は、 [!DNL Analytics] 必要な属性を持つ [!DNL Target Recommendations].

A [!DNL Target Recommendations] サンプルフィード形式は、すべての属性を製品変数で定義する必要があるガイドとして機能します。 後で、これらの値は [!DNL Target] 各 [!DNL Target] エンティティの値。

>[!NOTE]
>
>コンテンツサイトの場合は、各コンテンツピースを「products」として扱い、そのコンテンツに関連する属性 ( 例：作成者名、公開日、コンテンツタイトル、リリース月など ) は、属性として渡す必要があります。 カテゴリレベルまたはカテゴリタイプの精度は、ユースケースの要件に基づいて、ビジネスで決定する必要があります。

製品変数の設定方法について詳しくは、 [製品](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) 内 *Analytics 実装ガイド*. このドキュメントのメモの一部は、デプロイ先のチームの裁量が必要です ( 例：カテゴリ )。 このアクティビティをおこなう前に、必ずAdobeにお問い合わせください。

### 注意点

[!DNL Analytics] データは日別フィードで送信されます。 行動の結果がサイトのレコメンデーションの結果に反映されるまでに最大 24 時間かかります。 すべてと同様 [!DNL Recommendations] 条件の設定に基づいて、このデータソースはテスト可能で、テストが必要です。

使用するデータソースを迅速に決定するために、ユーザーが毎日大量のオーガニックデータを生成し、履歴データへの依存度が低い場合は、 [!DNL Target] mbox は、行動データソースに適しています。 最近生成された有機的データの可用性が低い場合、 [!DNL Analytics] データを、次に [!DNL Analytics] 行動データソースは適切なデータソースです。

次に、これらの変数を [!DNL Target] 行動データの継続的な供給のための側。

## Target での実装

1. Target で、 **[!UICONTROL Recommendations]**」、「 **[!UICONTROL フィード]** タブをクリックします。

   ![フィード](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. クリック **[!UICONTROL フィードを作成]**.

1. 選択 **[!UICONTROL Analytics 分類]**」をクリックし、レポートスイートを指定します。

   ![Analytics 分類オプション](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. クリック **[!UICONTROL マッピング]**&#x200B;を使用して、フィールドの列ヘッダーを適切な [!UICONTROL Recommendations] フィールド名。

   ![「Mapping」セクション](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

## よくある質問

次の FAQ を考慮してください [!DNL Analytics] と [!DNL Target]:

### は `entity.id` および `entity.categoryId` 内で渡す必要のある値 [!DNL Target] mbox 呼び出し？

はい、この 2 つの値は引き続き必要です。 残りの属性は、 [!DNL Analytics] フィードに書き込むことができます。

### 動的インクルージョンルールを使用できますか。例えば、エンティティパラメーターが [!DNL Analytics] フィードアプローチ？

はい、できます。 メソッドは、 [!DNL Target] スタンドアロン。 ただし、この場合は、タイミング要因に注意する必要があります。 プロファイル変数と一致するエンティティ変数は、ページ上ではるか後に現れる可能性のあるデータレイヤーに依存します。
