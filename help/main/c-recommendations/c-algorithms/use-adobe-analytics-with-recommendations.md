---
keywords: 行動データソース；analytics;recommendations；条件；製品変数
description: ' [!DNL Target Recommendations]の行動データソースとして [!DNL Adobe Analytics] を使用する方法を説明します。'
title: ' [!DNL Adobe Analytics]  [!DNL Target Recommendations]の使用方法'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
TQID: https://experienceleague.adobe.com/2ryixOT-YoKjDlMbqs8g2DJElNVmlCUFhbdZzpfSnNs
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 804
ht-degree: 81%

---

# [!DNL Adobe Analytics] での[!DNL Recommendations] の使用

[!DNL Adobe Analytics]を行動データソースとして使用すると、顧客は[!DNL Adobe Target Recommendations]のアクティビティで[!DNL Analytics]のビューベースおよび購入ベースの行動データを使用できます。 この機能は、[!DNL Target Recommendations]の設定が新しく、[!DNL Analytics]に使用する履歴データが多い場合に特に役立ちます。

[!DNL Analytics] を行動データソースとして使用すると、ユーザーの行動に関する豊富な情報のソースとして機能できます。 この情報には、[!DNL Analytics] とのみ共有されるサードパーティのソースやフィードからのデータが含まれる場合があります。

[!DNL Recommendations]で[条件を作成](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)していますが、使用するデータソースを選択できるラジオボタンが2つあります：[!UICONTROL mboxes]または[!UICONTROL Analytics]。 条件を作成するには、[!UICONTROL Recommendations] > [!UICONTROL Criteria] > [!UICONTROL 条件を作成] > [!UICONTROL 条件を作成]をクリックします。 詳しくは、 [条件の作成 &#x200B;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)を参照してください。

>[!NOTE]
>
>これら 2 つのボタンがアカウントに表示されない場合は、[&#x200B; カスタマーケア &#x200B;](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) にお問い合わせください。

## [!DNL Target]の[!DNL Analytics] データの使用例

レコメンデーションの行動データソースとして [!DNL Analytics] を使用すると、[!DNL Target] のすべてのエンティティパラメーターを使用してエンティティページにタグ付けしなくても、特定の使用例をデプロイできます。 それには特定の前提条件が必要ですが、その機能がシームレスに動作するためには、「製品変数」を使用できることが最も重要です。 通常の eVar および Prop では、このハンドシェイクが [!DNL Analytics] と [!DNL Target] の間で自動的に発生するだけでは不十分です。

[!DNL Analytics] を行動データソースとして使用すると、次の操作を行うことができます。

* [!DNL Analytics] のデータを使用して、先月に同じカテゴリで購入した他のユーザーに基づいて、小売サイトでレコメンデーションを製品詳細ページで表示します。
* [!DNL Analytics] のデータに基づいて、現在トレンドとなっている特定のカテゴリ内で最も人気のあるコンテンツのコンテンツをメディアサイトのホーム画面に表示します。

## [!DNL Analytics] での実装

次の節では、[!DNL Analytics] 側でこの機能を実装する方法について説明します。

### 前提条件：[!DNL Analytics] での製品変数の設定

[!DNL Target Recommendations] に必要な必要な属性を持つ [!DNL Analytics] の製品変数を実装します。

[!DNL Target Recommendations] のサンプルフィード形式は、製品変数ですべての属性を定義する必要があるガイドとして機能します。 後で、これらの値を、[!DNL Target] UI 内でそれぞれの [!DNL Target] エンティティ値に対して「マッピング」する必要があります。

>[!NOTE]
>
>コンテンツサイトの場合、それぞれのコンテンツ部分を「製品」として扱い、そのコンテンツに関する関連属性を属性として渡す必要があります。 このような属性には、作成者名、公開日、コンテンツタイトル、リリース月などが含まれます。 カテゴリレベルまたはカテゴリタイプの精度は、ユースケースの要件に基づいて、ビジネスで決定する必要があります。

product 変数の設定方法について詳しくは、『 [Adobe Analyticsの実装 *ガイドの* products](https://experienceleague.adobe.com/ja/docs/analytics/implementation/vars/page-vars/products) を参照してください。 このドキュメントのメモの一部は、デプロイするチームの裁量が必要です（例：カテゴリ）。 このアクティビティを行う前に、[!DNL Adobe] に相談することを常にお勧めします。

### 注意点

[!DNL Analytics] データは毎日のフィードで送信されます。 行動の結果がサイトのレコメンデーションの結果内に反映されるまでに、最大 24 時間かかる場合があります。 すべての条件 [!DNL Recommendations] 設定と同様に、このデータソースもテストでき、テストする必要があります。

どのデータソースを使用するかを迅速に決定するには、ユーザーが毎日生成するオーガニックデータが多く、履歴データに対する依存関係が少ない場合、[!DNL Target] mbox を行動データソースとして使用すると適しています。 最近生成された有機データの可用性が低い場合、[!DNL Analytics] のデータを基にバンキングする場合は、行動データソースとして [!DNL Analytics] を使用するのが適しています。

次に、行動データの継続的な供給のために、これらの変数 [!DNL Target] 側でマッピングする必要があります。

## [!DNL Target] への実装

1. [!DNL Target]で「**[!UICONTROL Recommendations]**」をクリックし、「**[!UICONTROL フィード]**」タブをクリックします。

1. 「**[!UICONTROL フィードを作成]**」をクリックします。

1. 「**[!UICONTROL Analytics Classifications]**」を選択し、レポートスイートを指定します。

1. 「**[!UICONTROL 次]**」をクリックして、**[!UICONTROL スケジュール]**&#x200B;設定に進み、フィードの頻度を選択します。

   * [!UICONTROL 日別]
   * [!UICONTROL 週単位]
   * [!UICONTROL 2週間ごと]
   * [!UICONTROL なし]

   フィードを処理する時刻を選択することもできます。

1. 「**[!UICONTROL 次へ]**」をクリックして&#x200B;**[!UICONTROL マッピング]**&#x200B;設定に進み、フィールド列ヘッダーを適切な[!UICONTROL 推奨事項] フィールド名にマッピングします。

1. 「**[!UICONTROL 保存]**」をクリックします。

## よくある質問

[!DNL Target] で [!DNL Analytics] を使用する際は、次の FAQ を考慮してください。

### [!DNL Target] mbox 呼び出し内で `entity.id` と `entity.categoryId` の値を渡す必要があるか。

はい、これら 2 つの値は引き続き必要です。 残りの属性は、このドキュメントで説明しているように、[!DNL Analytics] フィードを介して渡すことができます。

### [!DNL Analytics] フィードアプローチを使用してプロファイル属性に一致するエンティティパラメーターなどの動的な包含ルールを使用できますか？

はい、できます。 この方法は、[!DNL Target] を単体で使用する場合と同様です。 ただし、この場合は、タイミング要因に注意する必要があります。 プロファイル変数と一致すると想定されるエンティティ変数は、ページのずっと後に表示される可能性があるデータレイヤーに依存します。
