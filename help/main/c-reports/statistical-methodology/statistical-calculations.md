---
keywords: レポート；統計手法；統計計算；統計；平均；コンバージョン率；訪問者あたりの売上高；rpv；信頼区間；上昇率；ウェルチ t テスト；オフライン計算
description: ' [!DNL Adobe Target] の手動 [!UICONTROL A/B Test] ータアクティビティで使用される統計計算について説明します。'
title: '[!UICONTROL A/B Test] アクティビティで使用される統計計算を学ぶにはどうすればよいですか？'
feature: Reports
exl-id: 5f7377b9-0567-4b6f-8968-4696b2088d0a
source-git-commit: bb95d160940737e23022d70cbe56567f79cbf255
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 2%

---

# A/Bn テストでの統計計算

この記事では、[!DNL Adobe Target] の手動 A/Bn テストで使用される統計計算を詳しく説明します。 定義は、[!UICONTROL Conversion Rate]、[!UICONTROL Confidence Interval of Conversion Rate]、[!UICONTROL Lift]、[!UICONTROL Confidence Interval for Lift] および [!UICONTROL Confidence] に対して提供されます。

>[!NOTE]
>
>この記事の情報は、以前このサイトでダウンロード可能だった *Adobe Target A/B テストの計算* の PDF ファイルに代わるものです。

![A/B テストアクティビティの [!UICONTROL Conversion Rate]、[!UICONTROL Average Lift and Confidence Interval]、[!UICONTROL Confidence] を示すターゲットレポート。](/help/main/c-reports/statistical-methodology/img/target_report.png)

## 平均性能

次の節では、前の図で使用した計算について説明します。

### 訪問者あたりのコンバージョン率と売上高（RPV）キャンペーン

次の図に、[!DNL Target] レポートの [!UICONTROL Conversion Rate]、[!UICONTROL Confidence Interval of Conversion Rate]、および [!UICONTROL Conversions] 数を示します。 例えば、最初の行は、エクスペリエンス A の場合、[!UICONTROL Conversion Rate] は 25.81% で、[!UICONTROL Confidence Interval] は±7.7% で、32 のコンバージョンが記録されたことを示しています。 124 人の訪問者がエクスペリエンスを閲覧した場合、これは 32/124 = 25.81% に等しくなります。

<p style="text-align:center;"><img width="25%" src="img/conv_rate.png"></p>

実験の各体験 **ν&#x200B;</sub>*のコンバージョン率または* 平均***μ<sub>ν* は、指標の合計と、その指標に割り当てられた単位数 *N<sub>ν</sub>* との比率として定義されます。

<p style="text-align:center;"><img width="125px" src="img/mean_definition.png"></p>

ここで、

* *Y<sub>iν</sub>* は、特定のエクスペリエンス *ν* に割り当てられた各単位 *i* の指標の値です。

* 単位 *i* の合計は、カウント方法の選択によって異なります。

   * カウント方法として *[!UICONTROL Visitors]* を使用する場合、各ユニットは、アクティビティの存続期間中、アクティビティのユニーク参加者として定義されるユニーク訪問者です。
   * カウント方法として *[!UICONTROL Visits]* を使用する場合、各ユニットは、[!DNL Target] セッション中のエクスペリエンスの一意の参加者として定義される一意の訪問（一意の `sessionId`）です。 `sessionId` が変更された場合、または訪問者がコンバージョンステップに到達した場合は、新しい訪問がカウントされます。
   * カウント方法として *[!UICONTROL Activity Impressions]* を使用する場合、各単位は、訪問者がアクティビティの任意のページを読み込むたびに定義される一意のインプレッションです。

## [!UICONTROL Confidence Interval of Mean]／[!UICONTROL Conversion Rate]

コンバージョン率の信頼区間は、基になるデータと一致する可能性のあるコンバージョン率の範囲として、直感的に定義されます。

実験を実行する場合、特定のエクスペリエンスのコンバージョン率は、「true」のコンバージョン率の *推定* です。 この推定値の不確実性を定量化するには、信頼区間 [!DNL Target] 使用します。 [!DNL Target] は常に 95% の信頼区間をレポートします。つまり、計算された信頼区間の 95% には、最終的にエクスペリエンスの真のコンバージョン率が含まれます。

コンバージョン率 *μ<sub>ν</sub>* の 95% の信頼区間は、値の範囲として定義されます。

<p style="text-align:center;"><img width="30%" src="img/confidence_interval.png"></p>

ここで、平均の標準誤差は次のように定義されます

<p style="text-align:center;"><img width="75px" src="img/se_conv_continuous.png"></p>

サンプルの標準偏差をバイアスなしで推定する場合：

<p style="text-align:center;"><img width="200px" src="img/stdev_definition.png"></p>

キャンペーンがコンバージョン率キャンペーンの場合（つまり、コンバージョン指標がバイナリの場合）、標準エラーは次のように減少します。

<p style="text-align:center;"><img width="150px" src="img/se_conv.png"></p>

## 上昇率

次の図は、[!DNL Target] レポートの [!UICONTROL Lift] と [!UICONTROL Confidence Interval of Lift] を示しています。 数値はリフト範囲の平均を表し、矢印はリフトが正か負かを反映します。 信頼性が 95% を超えるまで、矢印はグレーで表示されます。 信頼性がしきい値を通過した後、矢印は正または負の上昇率に基づいて緑または赤になります。

<p style="text-align:center;"><img width="35%" src="img/lift.png"></p>

エクスペリエンス *ν* とコントロールエクスペリエンス *ν<sub>0</sub>* の間の上昇率は、コンバージョン率の相対的な「デルタ」で、次のように定義されます

<p style="text-align:center;"><img width="15%" src="img/lift_definition.png"></p>

個々のコンバージョン率が上記で定義されている場合。 より簡単に言えば、

```
Lift(Experience N) = (Performance_Experience_N - Performance_Control)/ Performance_Control
```

コントロールエクスペリエンス *ν<sub>0</sub>* のコンバージョン率が 0 の場合、上昇率はありません。

## [!DNL Confidence Interval of Lift]

[!UICONTROL Average Lift and Confidence Interval] 列のボックス図グラフは、平均値と 95% の [!UICONTROL Confidence Interval of Lift] を表します。 特定の非制御エクスペリエンスの信頼区間と制御エクスペリエンスの信頼区間に重複がある場合、ボックスプロットはグレーになります。 指定されたエクスペリエンスの信頼区間の範囲が、コントロールエクスペリエンスの信頼区間の上または下の場合、ボックスプロットは緑または赤になります。

エクスペリエンス *ν* とコントロールエクスペリエンス *ν<sub>0</sub>* の間の上昇率の標準誤差は、次のように定義されます。

<p style="text-align:center;"><img width="35%" src="img/se_lift.png" alt="指標 – 平均"></p>

すると、上昇率の 95% 信頼区間は次のようになります。

<p style="text-align:center;"><img width="40%" src="img/lift_CI.png"></p>

この計算では「Delta」メソッドを使用します。詳しくは、このドキュメントで [ 説明します ](/help/main/assets/confidence_interval_lift.pdf)

## [!UICONTROL Confidence]

最後の列には、[!DNL Target] レポートの信頼性が表示されます。 エクスペリエンスの信頼性とは、null 仮説が true の場合に観測された結果と同じ極端な結果が得られる確率（パーセンテージで示されます）です。 p 値に関しては、表示される信頼性は *1 - p 値* です。 直感的には、信頼性が高いほど、コントロールエクスペリエンスとコントロール以外のエクスペリエンスのコンバージョン率が等しくなる可能性が低くなります。

ま [!DNL Target]、テストエクスペリエンスと制御エクスペリエンスの間で両側 **Welch の t 検定** が行われ、テストと制御のエクスペリエンスの手段が同じかどうかをテストします。 通常、実験を実行する前に、2 つのグループのサンプルサイズと相違が同じであるかどうかはわかりません。また、[!DNL Target] れにより、各エクスペリエンスに送信されるトラフィックの割合が等しくなくなるので、各エクスペリエンスの相違が等しいとは想定しません。 したがって、学生の t 検定の代わりにウェルチの t 検定が選択されます。

Welch の t 検定を行うには、まず t 統計量と自由度の計算を開始し、両側 t 検定を実行して p 値を生成します。 最後に、p 値に基づいて信頼性を計算します。

*t* 統計量は、*ν* と *ν<sub>0</sub>* という 2 つの独立した確率変数の平均値を、差の標準誤差で割った値と定義されます。

<p style="text-align:center;"><img width="100px" src="img/t_value.png"></p>

ここで、*μ<sub>v</sub>* 及び *μ<sub>v0</sub>* は、それぞれ *ν* 及び *ν<sub>0</sub>* の式であり、*μ<sub>v</sub>* 及び *μ<sub>v0</sub>* の差の標準誤差は次の式で表される。

<p style="text-align:center;"><img width="150px" src="img/standard_error_diff.png"></p>

ここで、*σ<sup>2</sup><sub>v</sub>* および *σ<sup>2</sup><sub>v<sub>0</sub></sub>* は、それぞれ 2 つの経験 *ν* および *ν<sub>0</sub>* の差異であり、*N<sub>v</sub>* および *N<sub>v<sub></sub></sub>* ** *<sub></sub>* 00 は、それぞれ試料サイズである。

Welch の t 検定では、自由度は次のように計算されます。

<p style="text-align:center;"><img width="180px" src="img/degree_of_freedom.png"></p>

また、*ν* と *ν<sub>0</sub>* の自由度は次のように定義されます。

<p style="text-align:center;"><img width="100px" src="img/df_v.png"></p>

<p style="text-align:center;"><img width="100px" src="img/df_v0.png"></p>

次に、*t* 分布の末尾の領域から p 値を計算できます。

<p style="text-align:center;"><img width="20%" src="img/p_value.png"></p>

最後に、[!DNL Target] で報告される信頼性は、次のように定義されます。

<p style="text-align:center;"><img width="20%" src="img/confidence.png"></p>

## オフラインでの計算の実行

[ダウンロードした CSV レポート](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) には生データのみが含まれ、A/B テストで使用される訪問者あたりの売上高、上昇率、信頼性などの計算指標は含まれません。

これらの統計量を計算するには、[!DNL Target] [ 完全信頼性計算ツール ](/help/main/assets/complete_confidence_calculator.xlsx) Excel ファイルをダウンロードして、アクティビティの値を入力します。
