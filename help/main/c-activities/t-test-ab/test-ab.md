---
keywords: AB;A/B;AB...n；エクスペリエンスの比較；ターゲット設定；コンテンツの比較；自動ターゲット；自動配分
description: Adobeでの様々なタイプの A/B テストアクティビティの詳細 [!DNL Target]  — 手動、自動配分、自動ターゲット。 お客様に合ったものを選択してください。
title: Target で使用できる A/B アクティビティのタイプはどれですか？
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 39%

---

# A/B テストの概要

マニュアル [!UICONTROL A/B テスト] 「 」アクティビティでは、事前に指定したテスト期間に、複数のバージョンの Web サイトコンテンツを比較し、どのバージョンがコンバージョンを最も多く増やしたかを確認します。

>[!NOTE]
>
>手動（デフォルト）に加えて [!UICONTROL A/B テスト] アクティビティ（この節で説明） [!DNL Target] は、さらに 2 つのタイプを提供します [!UICONTROL A/B テスト] アクティビティ： [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット].
>
>詳しくは、 [A/B テストアクティビティのタイプ](#types) 詳しくは、以下を参照してください。

マニュアル [!UICONTROL A/B テスト] アクティビティ（A/B...N テストとも呼ばれます）は、複数のバージョンの Web サイトコンテンツを比較して、特定したコンバージョン、販売または他の指標について最も高い上昇率を示す指標を確認します。 A/B テストを使用して、ページに加えた変更をデフォルトのページデザインと比較することで、最も適した結果を生成するエクスペリエンスを決定できます。

手動の A/B テストは、成功指標や代替コンテンツ配信に基づいてページのパフォーマンスを向上させる方法に関する明確な仮説がある場合に特に便利です。

手動の A/B テストは、新しいレイアウトが関わる場合や、要素の扱いが大幅に異なる場合がある大きな変更に適しています。 テストデザインで個々のページ要素に簡単に分類できない場合は、 [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

A/B テストを設定する際に、各エクスペリエンスを表示する訪問者の割合を決定できます。 例えば、コントロールエクスペリエンスと 2 つ目のエクスペリエンスの間でトラフィックを均等に分割することも、オーディエンスの 5％のみにリスクの高い新しいエクスペリエンスを表示してテストすることもできます。

>[!NOTE]
>
>A/B テストのサンプルサイズの決定について詳しくは、[A/B テストの計画](/help/main/c-activities/t-test-ab/sample-size-determination.md)を参照してください。

6 つ以上のエクスペリエンスがあり、2 つ以上の場所をまたがる場合は、A/B テストをおこなう前に [MVT テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)を検討することをお勧めします。多変量分析テストによって、コンバージョンが向上する可能性が最も高そうなページ領域を判定できます。マーケティング担当者はこれらの領域に注目する必要があります。例えば、MVT テストによって、目標を満たすために最も重要な場所はコールトゥアクションであることがわかったとします。目標の達成に最も役立つ場所とコンテンツを特定したら、A/B テストを実行して、2 つの特定の画像を相互にテストしたり、コールトゥアクションの言い回しや色を比較したりするなど、結果をさらに絞り込むことができます。 MVT テストの後に 1 つ以上の A/B テストをおこなうことで、目的の結果を得るための最良のコンテンツを判断できます。

## A/B テストアクティビティのタイプ {#types}

マニュアルに加えて [!UICONTROL A/B テスト] アクティビティ（この節で説明） [!DNL Target] には、次の 2 つのタイプの A/B テストアクティビティがあります。 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット].

| アクティビティタイプ | 説明 |
| --- | --- |
| [!UICONTROL 手動の A/B テスト] | 複数のエクスペリエンスを比較し、事前に指定したテスト期間内で最もコンバージョンを増やすことができたエクスペリエンスを見極めます。<br>この節では、手動の設定方法について説明します [!UICONTROL A/B テスト] アクティビティのみを表示する。 [!UICONTROL A/B テスト] アクティビティも同様です。 |
| [!UICONTROL 自動配分] | 2 つ以上のエクスペリエンスの中から勝者を特定してから、その勝者にトラフィックを配分し直すことで、テストと学習を続けながらコンバージョンを増やしていきます。<br>自動配分アクティビティを使用するメリットについては、 [自動配分](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) in *A/B テストを実行すべき期間* および [自動配分の概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Premium バッジ](/help/main/assets/premium.png) [!UICONTROL 自動ターゲット] | 高度な機械学習を使用してコンテンツをパーソナライズし、コンバージョンを促進します。その際は、マーケティング担当者が定義した高パフォーマンスのエクスペリエンスを複数特定したうえで、個々の顧客プロファイルや同様の訪問者の過去の行動を基にして、各訪問者に詳細にカスタマイズしたエクスペリエンスを配信します。<br>詳しくは、 [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

詳しくは、以下の [!UICONTROL A/B テスト] アクティビティは適切なものです。 [Adobe Target Activities ガイドPDF](/help/main/c-activities/target-activities-guide.md).

3 つのタイプの [!UICONTROL A/B テスト] アクティビティも同様です。 次の手順で [!UICONTROL 自動配分] または [!UICONTROL 自動ターゲット] アクティビティ、開始 [A/B テストアクティビティの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)でも、そこにたどり着いたら [!UICONTROL ターゲット設定] ページで、目的のトラフィック配分方法を選択します（下図を参照）。

* [!UICONTROL 最良のエクスペリエンスに自動配分]
* [!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]

![トラフィック配分方法の設定](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## トレーニングビデオ：アクティビティタイプ（9:03）![概要バッジ](/help/main/assets/overview.png)

このビデオでは、[!DNL Target Standard/Premium] で利用できるアクティビティタイプについて説明しています。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプに適用される 3 ステップのガイドによるワークフローについての説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)
