---
keywords: AB;A/B;AB...n；エクスペリエンスの比較；ターゲティング；コンテンツの比較；自動ターゲット；自動配分
description: ' [!DNL Target] - [!UICONTROL Manual]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target] の A/B テスト アクティビティを探索します。'
title: ' [!DNL Target] で利用できる A/B テストアクティビティについて説明します。'
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 974746e25724abf0e5edd3884331ec0975e5352e
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 21%

---

# A/B テストの概要

手動の [!UICONTROL A/B Test] アクティビティ（A/B...N テストとも呼ばれます）では、複数のバージョンの Web サイトコンテンツを比較して、特定したコンバージョン、売上高、その他の指標に最も適したバージョンを確認します。 A/B テストを使用して、ページに加えた変更をデフォルトのページデザインと比較することで、最も適した結果を生成するエクスペリエンスを決定できます。

>[!TIP]
>
>[!UICONTROL Manual] （デフォルト）の [!UICONTROL A/B Test] アクティビティ（この記事で説明）に加えて、[!DNL Target] では、さらに 2 種類の [!UICONTROL A/B Test] アクティビティ（[!UICONTROL Auto-Allocate] と [!UICONTROL Auto-Target]）が提供されます。 詳しくは、以下の [A/B テストアクティビティのタイプ ](#types) を参照してください。

手動の A/B テストは、成功指標や代替コンテンツ配信に基づいてページのパフォーマンスを向上させる方法の明確な仮説がある場合に役立ちます。

手動の A/B テストは、新しいレイアウトや要素の大幅に異なる処理を含む可能性のある大規模な変更に適しています。 テストデザインを個々のページ要素に分類することが容易でない場合は、[ 多変量分析テスト ](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) を実行する前に A/B テストを実行する必要があります。

A/B テストを設定する際は、各エクスペリエンスを表示する訪問者の割合を決定できます。 例えば、トラフィックをコントロールと 2 番目のエクスペリエンスに均等に分割したり、オーディエンスの 5% のみに表示することで、リスクの高い新しいエクスペリエンスをテストしたりできます。

>[!NOTE]
>
>A/B テストのサンプルサイズの決定について詳しくは、[A/B テストの計画](/help/main/c-activities/t-test-ab/sample-size-determination.md)を参照してください。

異なるエクスペリエンスの数が 5 を超え、2 つ以上の場所にまたがる場合は、A/B テストを実行する前に [MVT テスト ](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) を検討することをお勧めします。 多変量分析テストによって、コンバージョンが向上する可能性が最も高そうなページ領域を判定できます。これらの領域は、マーケターが注力すべき場所です。 例えば、MVT テストによって、目標を満たすために最も重要な場所はコールトゥアクションであることがわかったとします。目標を達成する上で最も役に立つ場所とコンテンツを判断したら、A/B テストを実行して結果をさらに絞り込むことができます。 例えば、2 つの特定の画像を相互にテストしたり、call to actionの語句や色を比較したりします。 MVT テストの後に 1 つ以上の A/B テストをおこなうことで、目的の結果を得るための最良のコンテンツを判断できます。

## A/B テストアクティビティのタイプ {#types}

手動の [!UICONTROL A/B Test] アクティビティに加えて、[!DNL Target] には、さらに 2 種類の [!UICONTROL A/B Testing] アクティビティ（[!UICONTROL Auto-Allocate] と [!UICONTROL Auto-Target]）が用意されています。

| アクティビティタイプ | 説明 |
| --- | --- |
| [!UICONTROL Manual A/B Test] | 複数のエクスペリエンスを比較して、事前に指定したテスト期間内で最もコンバージョンが向上したエクスペリエンスを確認します。<P>この節では、手動の [!UICONTROL A/B Test] アクティビティを設定する方法について説明しますが、他のタイプの [!UICONTROL A/B Test] アクティビティの手順も似ています。 |
| [!UICONTROL Auto-Allocate] | 2 つ以上のエクスペリエンスの中から勝者を特定し、その勝者にトラフィックをリダイレクトすることで、テストの実行や学習に合わせてコンバージョンを増やします。<P>[!UICONTROL Auto-Allocate] アクティビティを使用するメリットについては、[A/B テストを実行する必要がある期間 ](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) および *自動配分の概要* の [ 自動配分 ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) を参照してください。 |
| ![Premium バッジ ](/help/main/assets/premium.png) [!UICONTROL Auto-Target] | では、高度な機械学習を使用して、マーケターが定義した複数の高パフォーマンスのエクスペリエンスを特定することで、コンテンツをパーソナライズしコンバージョンを促進します。 次に、個々の顧客プロファイルと類似する訪問者の過去の行動に基づいて、訪問者に最適なエクスペリエンスが提供されます。<P>詳しくは、「[ 自動ターゲット ](/help/main/c-activities/auto-target/auto-target-to-optimize.md)」を参照してください。 |

これらの [!UICONTROL A/B Test] アクティビティのうちどれを使用するかについて詳しくは、インタラクティブな [Adobe Target アクティビティガイドのPDF](/help/main/c-activities/target-activities-guide.md) を参照してください。

3 つのタイプの [!UICONTROL A/B Test] アクティビティを作成する手順は似ています。 [!UICONTROL Auto-Allocate] または [!UICONTROL Auto-Target] アクティビティを作成するには：

1. 最初に [A/B テストアクティビティの作成 ](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) を行います。
1. [!UICONTROL Targeting] ページに移動したら、「[!UICONTROL Traffic Allocation]」コントロールをクリックし、右側のパネルで目的のトラフィック配分方法を選択します（下図を参照）。

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experience]

   ![ トラフィック配分方法の設定 ](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

## A/B アクティビティ内にレコメンデーションを含める

[!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target] の各アクティビティ（および [!UICONTROL Experience Targeting] （XT）アクティビティ）に Recommendations を含めることができます。 詳細については、「[ オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。

この機能を使用するには、[Target Premium ライセンス](/help/main/c-intro/intro.md#premium)が必要です。
