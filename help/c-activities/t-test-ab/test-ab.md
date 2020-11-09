---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content;auto-target;auto-allocate
description: 手動のA/Bテストアクティビティでは、事前に指定したテスト期間中に、Webサイトコンテンツの複数のバージョンを比較して、どのバージョンが最もコンバージョンの向上に役立つかを確認します。
title: A/Bテストの概要
feature: ab
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 38%

---


# A/Bテストの概要

A manual [!UICONTROL A/B Test] activity compares two or more versions of your website content to see which version best improves your conversions during a pre-specified test period.

>[!NOTE]
>
>「手動（デフォルト）」 [!UICONTROL A/B Test] アクティビティ（この節で説明）に加えて、次の2種類の [!DNL Target] A/B Test [!UICONTROL アクティビティも] 追加で提供されます。 [!UICONTROL 自動配分] と [!UICONTROL 自動ターゲット]。
>
>詳しくは、 [以下の「A/Bテストアクティビティの](#types) タイプ」を参照してください。

A manual [!UICONTROL A/B Test] activity (sometimes referred to as an A/B...N test) compares two or more versions of your Web site content to see which best lifts your conversions, sales, or other metrics you identify. A/B テストを使用して、ページに加えた変更をデフォルトのページデザインと比較することで、最も適した結果を生成するエクスペリエンスを決定できます。

手動のA/Bテストは、成功指標や別のコンテンツ配信に基づいてページのパフォーマンスを向上させる方法を明確に仮説している場合に特に役立ちます。

手動のA/Bテストは、新しいレイアウトが関わる場合や、要素の扱いが大幅に異なる場合など、変更が大きい場合に適しています。 If your test design does not easily break down into individual page elements, you should run an A/B test before a [multivariate test](/help/c-activities/c-multivariate-testing/multivariate-testing.md).

A/Bテストを設定する際に、各エクスペリエンスを表示する訪問者の割合を指定できます。 例えば、コントロールエクスペリエンスと 2 つ目のエクスペリエンスの間でトラフィックを均等に分割することも、オーディエンスの 5％のみにリスクの高い新しいエクスペリエンスを表示してテストすることもできます。

>[!NOTE]
>
>A/B テストのサンプルサイズの決定について詳しくは、[A/B テストの計画](/help/c-activities/t-test-ab/sample-size-determination.md)を参照してください。

6 つ以上のエクスペリエンスがあり、2 つ以上の場所をまたがる場合は、A/B テストをおこなう前に [MVT テスト](/help/c-activities/c-multivariate-testing/multivariate-testing.md)を検討することをお勧めします。多変量分析テストによって、コンバージョンが向上する可能性が最も高そうなページ領域を判定できます。マーケティング担当者はこれらの領域に注目する必要があります。例えば、MVT テストによって、目標を満たすために最も重要な場所はコールトゥアクションであることがわかったとします。目標の達成に最も役立つ場所とコンテンツを特定したら、A/Bテストを実行して2つの特定の画像を相互にテストしたり、誘い文句（CTA：コールトゥアクション）の言い回しや色を比較したりして、結果をさらに絞り込むことができます。 MVT テストの後に 1 つ以上の A/B テストをおこなうことで、目的の結果を得るための最良のコンテンツを判断できます。

## A/Bテストアクティビティのタイプ {#types}

手動の [!UICONTROL A/Bテスト] アクティビティ（この節で説明）に加えて、次の2種類のA/Bテストアクティビティが [!DNL Target] 追加で用意されています。 [!UICONTROL 自動配分] と [!UICONTROL 自動ターゲット]。

| アクティビティのタイプ | 説明 |
| --- | --- |
| [!UICONTROL 手動の A/B テスト] | 複数のエクスペリエンスを比較し、事前に指定したテスト期間内で最もコンバージョンを増やすことができたエクスペリエンスを見極めます。<br>この節では、手動の [!UICONTROL A/B Test] アクティビティを設定する方法を説明しますが、他のタイプの [!UICONTROL A/B Test] アクティビティの手順は似ています。 |
| [!UICONTROL 自動配分] | 2 つ以上のエクスペリエンスの中から勝者を特定してから、その勝者にトラフィックを配分し直すことで、テストと学習を続けながらコンバージョンを増やしていきます。<br>自動配分アクティビティを使用する利点については、A/Bテストと [自動配分の概要の](/help/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) 自動配分 *(* Whow ling the run an A/B Test [and](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)Auto-Allocate overview)を参照してください。 |
| ![プレミアムバッジ](/help/assets/premium.png)[!UICONTROL 自動ターゲット] | 高度な機械学習を使用してコンテンツをパーソナライズし、コンバージョンを促進します。その際は、マーケティング担当者が定義した高パフォーマンスのエクスペリエンスを複数特定したうえで、個々の顧客プロファイルや同様の訪問者の過去の行動を基にして、各訪問者に詳細にカスタマイズしたエクスペリエンスを配信します。<br>詳しくは、 [自動ターゲットを参照してください](/help/c-activities/auto-target/auto-target-to-optimize.md)。 |

これらの [!UICONTROL A/B Test] アクティビティのうちどれが適切かについて詳しくは、インタラクティブな [Adobe TargetアクティビティガイドPDFを参照してください](/help/c-activities/target-activities-guide.md)。

3種類の [!UICONTROL A/Bテスト] アクティビティの作成手順は似ています。 自動配分 [!UICONTROL または] 自動ターゲット [!UICONTROL アクティビティを作成するには、A/Bテストアクティビティを] 作成して開始しますが、ターゲット設定ページに移動した場合は、次のように必要なトラフィック配分方法を [](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) 選択します。

* [!UICONTROL 最高のエクスペリエンスへの自動配分]
* [!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]

![トラフィック配分方法の設定](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## トレーニングビデオ：アクティビティタイプ(9:03) ![概要バッジ](/help/assets/overview.png)

このビデオでは、[!DNL Target Standard/Premium] で利用できるアクティビティのタイプについて説明しています。

* [!DNL Adobe Target] に含まれるアクティビティのタイプの説明
* 目標達成に適したアクティビティのタイプの選択
* すべてのアクティビティのタイプに適用される 3 ステップのガイドによるワークフローについての説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)
