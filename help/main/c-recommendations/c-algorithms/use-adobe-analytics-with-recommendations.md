---
keywords: 行動データソース；analytics;recommendations；条件；製品変数
description: '[!DNL Adobe Analytics]を[!DNL Target Recommendations]の行動データソースとして使用する方法を説明します。'
title: Adobe Analytics をレコメンデーションと併用する
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
TQID: 'https://experienceleague.adobe.com/2ryixOT-YoKjDlMbqs8g2DJElNVmlCUFhbdZzpfSnNs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
source-git-commit: 374d176c5c40826d958a8b87d220422466433690
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 19%
---
# [!DNL Adobe Analytics] での[!DNL Recommendations] の使用 {#use-analytics-with-recommendations}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、[!DNL Adobe Analytics]を[!DNL Adobe Target Recommendations] アクティビティの行動データソースとして使用する方法を説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Analytics]を行動データソースとして使用すると、[!DNL Adobe Target Recommendations]のアクティビティで、[!DNL Analytics]のビューベースおよび購入ベースの行動データを使用できます。 これは、[!DNL Target Recommendations]設定が新しく、[!DNL Analytics]に使用する履歴データが多い場合に便利です。 データには、サードパーティのソースまたはフィードからの情報も含まれている可能性があります。この情報は、[!DNL Analytics]とのみ共有されます。

データソースは、**[!UICONTROL ビヘイビアーデータ Source]** オプションを使用して選択されます。一方、[!DNL Recommendations]で[条件を作成](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#data-source): **[!UICONTROL Adobe Target]**&#x200B;または&#x200B;**[!UICONTROL Analytics]**。

>[!NOTE]
>
>これらの2つのオプションがアカウントに表示されない場合は、[&#x200B; カスタマーケア &#x200B;](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## [!DNL Target]の[!DNL Analytics] データの使用例 {#use-cases}

[!DNL Analytics]を行動データソースとして使用すると、特定のユースケースを、すべての[!DNL Target] エンティティパラメーターでエンティティページをタグ付けすることなくデプロイすることもできます。 これには特定の前提条件が必要であり、「製品変数」の利用は最も重要です。 通常のeVarとpropでは、[!DNL Analytics]と[!DNL Target]がこのデータを自動的に交換するには十分ではありません。

[!DNL Analytics]を行動データソースとして使用すると、次のことが可能になります。

* [!DNL Analytics] のデータを使用して、先月に同じカテゴリで購入した他のユーザーに基づいて、小売サイトでレコメンデーションを製品詳細ページで表示します。
* [!DNL Analytics] のデータに基づいて、現在トレンドとなっている特定のカテゴリ内で最も人気のあるコンテンツのコンテンツをメディアサイトのホーム画面に表示します。

## [!DNL Analytics] での実装

### 前提条件：[!DNL Analytics] での製品変数の設定 {#prerequisites}

[!DNL Target Recommendations]に必要な属性を使用して、[!DNL Analytics]に製品変数を実装します。 [!DNL Target Recommendations]のサンプル フィード形式は、製品変数で定義する必要がある属性をガイドします。 これらの値は、後で[!DNL Target] UIでそれぞれの[!DNL Target] エンティティ値に「マッピング」する必要があります。

>[!NOTE]
>
>コンテンツサイトの場合は、それぞれのコンテンツ部分を「製品」として扱い、そのコンテンツの関連する属性を属性として渡す必要があります。 このような属性には、作成者名、公開日、コンテンツタイトル、リリース月などが含まれます。 企業は、ユースケースの要件にもとづいて、カテゴリーレベルまたはカテゴリータイプの詳細を決定する必要があります。

product 変数の設定方法について詳しくは、『 [Adobe Analyticsの実装 *ガイドの* products](https://experienceleague.adobe.com/ja/docs/analytics/implementation/vars/page-vars/products) を参照してください。 このドキュメントの一部のメモ（例えば、カテゴリに関するメモ）は、それをデプロイするチームの判断を必要とします。 このアクティビティを推奨する前に、[!DNL Adobe]に相談してください。

### 注意点 {#considerations}

[!DNL Analytics]個のデータが毎日フィードを通じて送信されます。 行動結果は、サイト上のレコメンデーション結果に反映されるまでに最大24時間かかる場合があります。 すべての[!DNL Recommendations]条件の設定と同様に、このデータソースをテストする必要があります。

データソースを選択するには：

* ユーザーが毎日、多くのオーガニックデータを生成し、過去のデータへの依存をほとんど必要としない場合、[!DNL Target] mboxは適しています。
* [!DNL Analytics]は、最近生成されたオーガニックデータが少なく、[!DNL Analytics] データを使用する必要がある場合に適しています。

`entity.id`と`entity.categoryId`の値は、[!DNL Target] mbox呼び出しで引き続き渡す必要があります。 他の属性は、このページで説明されているように、[!DNL Analytics] フィードを通じて渡すことができます。

エンティティ パラメーターとプロファイル属性の照合などの動的インクルージョン ルールは、[!DNL Analytics] フィード アプローチで使用できます。 この方法は、[!DNL Target] スタンドアロンの使用と似ていますが、タイミングを考慮する必要があります。プロファイル変数と一致すると想定されるエンティティ変数は、データ層によって異なり、ページではずっと後に表示される可能性があります。

## [!DNL Target] への実装 {#implement-target}

製品変数は、行動データを継続的に提供するために[!DNL Target]にマッピングされます。

1. [!DNL Target]で「**[!UICONTROL Recommendations]**」をクリックし、「**[!UICONTROL フィード]**」タブをクリックします。

1. 「**[!UICONTROL フィードを作成]**」をクリックします。

   「フィードを作成」ボタンがハイライト表示された![&#x200B; フィードのページ &#x200B;](../assets/feeds_1.png)

1. 「**[!UICONTROL Analytics Classifications]**」を選択し、レポートスイートを指定します。

1. **[!UICONTROL 次]**&#x200B;をクリックして&#x200B;**[!UICONTROL スケジュール]**&#x200B;設定に進み、フィードの頻度を選択します：**[!UICONTROL 毎日]**、**[!UICONTROL 毎週]**、**[!UICONTROL 2週間ごとに]**、または&#x200B;**[!UICONTROL 絶対]**。 フィードを処理する時間帯も選択できます。

   ![頻度オプション（毎日、毎週、2週間ごと、なし、時間帯フィールド）を使用して、フィードを作成ダイアログボックスのスケジュール手順](../assets/feeds_3.png)

1. 「**[!UICONTROL 次へ]**」をクリックして&#x200B;**[!UICONTROL マッピング]**&#x200B;設定に進み、フィールド列ヘッダーを適切な&#x200B;**[!UICONTROL 推奨事項]** フィールド名にマッピングします。

1. 「**[!UICONTROL Save]**」をクリックします。

フィードの作成について詳しくは、[&#x200B; フィードの作成](/help/main/c-recommendations/c-products/feeds.md#steps)を参照してください。
