---
keywords: AB;A/B;AB...n；エクスペリエンスの比較；ターゲティング；コンテンツの比較；自動ターゲット；自動配分
description: A/B テスト アクティビティの様々なタイプ（Adobe [!DNL Target]  手動、自動配分、自動ターゲット）について説明します。 自分に合ったものを選びなさい。
title: Target で使用できる A/B アクティビティのタイプはどれですか？
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 974746e25724abf0e5edd3884331ec0975e5352e
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 25%

---

# A/B テストの概要

手動の [!UICONTROL A/B Test] アクティビティでは、複数のバージョンの web サイトコンテンツを比較し、事前に設定したテスト期間中に、どのバージョンがコンバージョンを最も多く増やすことができるのかを確認できます。

>[!NOTE]
>
>手動（デフォルト）の [!UICONTROL A/B Test] アクティビティ（このセクションで説明）に加えて、[!DNL Target] では、[!UICONTROL Auto-Allocate] と [!UICONTROL Auto-Target] の 2 種類の [!UICONTROL A/B Test] アクティビティが追加で提供されます。 詳しくは、以下の [A/B テストアクティビティのタイプ ](#types) を参照してください。

手動の [!UICONTROL A/B Test] アクティビティ（A/B...N テストとも呼ばれます）では、複数のバージョンの Web サイトコンテンツを比較して、特定したコンバージョン、売上高、その他の指標に最も適したバージョンを確認します。 A/B テストを使用して、ページに加えた変更をデフォルトのページデザインと比較することで、最も適した結果を生成するエクスペリエンスを決定できます。

手動の A/B テストは、成功指標や代替コンテンツ配信に基づいてページのパフォーマンスを向上させる方法の明確な仮説がある場合に役立ちます。

手動の A/B テストは、新しいレイアウトや要素の大幅に異なる処理を含む可能性のある大規模な変更に適しています。 テストデザインを個々のページ要素に分類することが容易でない場合は、[ 多変量分析テスト ](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) の前に A/B テストを実行する必要があります。

A/B テストを設定する際は、各エクスペリエンスを表示する訪問者の割合を決定できます。 例えば、コントロールエクスペリエンスと 2 つ目のエクスペリエンスの間でトラフィックを均等に分割することも、オーディエンスの 5％のみにリスクの高い新しいエクスペリエンスを表示してテストすることもできます。

>[!NOTE]
>
>A/B テストのサンプルサイズの決定について詳しくは、[A/B テストの計画](/help/main/c-activities/t-test-ab/sample-size-determination.md)を参照してください。

異なるエクスペリエンスの数が 5 を超え、2 つ以上の場所にまたがる場合は、A/B テストを実行する前に [MVT テスト ](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) を検討することをお勧めします。 多変量分析テストによって、コンバージョンが向上する可能性が最も高そうなページ領域を判定できます。これらの領域は、マーケターが注力すべき場所です。 例えば、MVT テストによって、目標を満たすために最も重要な場所はコールトゥアクションであることがわかったとします。目標を達成する上で最も役に立つ場所とコンテンツを判断したら、A/B テストを実行して結果をさらに絞り込むことができます。 例えば、2 つの特定の画像を相互にテストしたり、コールトゥアクションの文言や色を比較したりするために使用します。 MVT テストの後に 1 つ以上の A/B テストをおこなうことで、目的の結果を得るための最良のコンテンツを判断できます。

## A/B テストアクティビティのタイプ {#types}

手動の [!UICONTROL A/B Test] アクティビティ（この節で説明）に加えて、[!DNL Target] では、さらに 2 種類の A/B テスト アクティビティ（[!UICONTROL Auto-Allocate] と [!UICONTROL Auto-Target]）が提供されます。

| アクティビティタイプ | 説明 |
| --- | --- |
| [!UICONTROL Manual A/B Test] | 2 つ以上のエクスペリエンスを比較し、事前に指定されたテスト期間中、どのベストエクスペリエンスがコンバージョンを向上させるかを確認します。<P>この節では、手動の [!UICONTROL A/B Test] アクティビティを設定する方法について説明しますが、他のタイプの [!UICONTROL A/B Test] アクティビティの手順も似ています。 |
| [!UICONTROL Auto-Allocate] | 2 つ以上のエクスペリエンスの中から勝者を特定し、その勝者にトラフィックをリダイレクトすることで、テストの実行や学習に合わせてコンバージョンを増やします。<P>[!UICONTROL Auto-Allocate] アクティビティを使用するメリットについては、[&#128279;](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate)A/B テストを実行する必要がある期間 *および [ 自動配分の概要 ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) の* 自動配分  を参照してください。 |
| ![Premium バッジ ](/help/main/assets/premium.png) [!UICONTROL Auto-Target] | では、高度な機械学習を使用して、マーケターが定義した複数の高パフォーマンスのエクスペリエンスを特定することで、コンテンツをパーソナライズしコンバージョンを促進します。 次に、個々の顧客プロファイルと類似する訪問者の過去の行動に基づいて、訪問者に最適なエクスペリエンスが提供されます。<P>詳しくは、「[ 自動ターゲット ](/help/main/c-activities/auto-target/auto-target-to-optimize.md)」を参照してください。 |

これらの [!UICONTROL A/B Test] アクティビティのうちどれを使用するかについて詳しくは、インタラクティブな [Adobe Target アクティビティガイドのPDFを参照してください ](/help/main/c-activities/target-activities-guide.md)。

3 つのタイプの [!UICONTROL A/B Test] アクティビティを作成する手順は似ています。 [!UICONTROL Auto-Allocate] または [!UICONTROL Auto-Target] アクティビティを作成するには、[A/B テストアクティビティの作成 ](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) から開始しますが、[!UICONTROL Targeting] のページに移動したら、以下に示すように、目的のトラフィック配分方法を選択します。

* [!UICONTROL Auto-allocate to best experience]
* [!UICONTROL Auto-target for personalized experience]

![ トラフィック配分方法の設定 ](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## A/B アクティビティ内にレコメンデーションを含める

[!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target] の各アクティビティ（および [!UICONTROL Experience Targeting] （XT）アクティビティ）に Recommendations を含めることができます。 詳細については、「[ オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。

この機能を使用するには、[Target Premium ライセンスが必要で ](/help/main/c-intro/intro.md#premium)。

## トレーニングビデオ：アクティビティタイプ（9:03）![概要バッジ](/help/main/assets/overview.png)

このビデオでは、[!DNL Target Standard/Premium] で利用できるアクティビティタイプについて説明しています。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)
