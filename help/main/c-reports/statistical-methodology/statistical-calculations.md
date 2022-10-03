---
keywords: レポート，統計的手法，統計的計算，統計，平均，コンバージョン率，訪問者あたりの売上高， rpv，信頼区間，上昇率，ウェルチ t-test，オフライン計算
description: 手動で使用する統計指標について説明します [!UICONTROL A/B テスト] アクティビティ [!DNL Adobe Target].
title: 統計指標については、 [!UICONTROL A/B テスト] アクティビティ？
feature: Reports
source-git-commit: 4fc3de2a15f117a4356d67fcffd7f9b881e1179a
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 2%

---

# A/Bn テストの統計指標

このページでは、 [!DNL Adobe Target]. コンバージョン率、コンバージョン率の信頼区間、上昇率、上昇率の信頼区間および信頼性の定義が提供されます。

![A/B テストアクティビティのコンバージョン率、平均上昇率と信頼区間および信頼性を示す Target レポート。](/help/main/c-reports/statistical-methodology/img/target_report.png)

## 平均性能

次の節では、前の図で使用した計算方法を説明します。

### 訪問者 (RPV) キャンペーンあたりのコンバージョン率と売上高

次の図にを示します。 [!UICONTROL コンバージョン率], [!UICONTROL コンバージョン率の信頼区間]、および [!UICONTROL コンバージョン] 内 [!DNL Target] レポート。 例えば、最初の行には、エクスペリエンス A の場合は次のように表示されます。の [!UICONTROL コンバージョン率] は 25.81%で、 [!UICONTROL 信頼区間] が±7.7%および 32 コンバージョンと記録されました。 124 人の訪問者がエクスペリエンスを閲覧したと仮定すると、これは32/124 = 25.81%と同じです。

<p style="text-align:center;"><img width="25%" src="img/conv_rate.png"></p>

コンバージョン率、または **mean**, *μ<sub>ν</sub>*（各エクスペリエンスに対して） *ν* 実験では、指標の合計と、その指標に割り当てられた単位数との比率を定義します。 *N<sub>ν</sub>*:

<p style="text-align:center;"><img width="125px" src="img/mean_definition.png"></p>

ここで、

* *Y<sub>iν</sub>* は、各単位の指標の値です *i*（特定のエクスペリエンスに割り当てられている） *ν*.

* 単位の合計 *i* カウント手法の選択に応じて異なります。

   * If *訪問者* はカウント手法として使用され、各ユニットは、アクティビティの全期間にわたるアクティビティの個別参加者として定義される個別訪問者です。
   * If *訪問回数* はカウント手法として使用され、各ユニットは、 [!DNL Target] セッション ( 一意の `sessionId`) をクリックします。 次の場合に `sessionId` を変更した場合、または訪問者がコンバージョンステップに到達した場合、新しい訪問がカウントされます。
   * If *アクティビティのインプレッション* はカウント手法として使用され、各ユニットは、訪問者がアクティビティのページを読み込むたびに定義される一意のインプレッションです。

## 平均/コンバージョン率の信頼区間

コンバージョン率の信頼区間は、基礎となるデータと一致する可能なコンバージョン率の範囲として直感的に定義されます。

実験を実行する場合、特定のエクスペリエンスに対して観察されるコンバージョン率は *見積もり* 」の値が含まれます。 この見積もりで不確実性を定量化するために、信頼区間を使用できます。 [!DNL Target] は常に 95%の信頼区間をレポートします。つまり、長期的に計算される信頼区間の 95%には、エクスペリエンスの真のコンバージョン率が含まれます。

コンバージョン率の 95%信頼区間 *μ<sub>ν</sub>* は値の範囲として定義されます。

<p style="text-align:center;"><img width="30%" src="img/confidence_interval.png"></p>

平均値の標準誤差は

<p style="text-align:center;"><img width="75px" src="img/se_conv_continuous.png"></p>

サンプルの標準偏差の偏りのない推定値が使用される場合：

<p style="text-align:center;"><img width="200px" src="img/stdev_definition.png"></p>

キャンペーンがコンバージョン率キャンペーンの場合（つまり、コンバージョン指標がバイナリの場合）、標準エラーは次のようになります。

<p style="text-align:center;"><img width="150px" src="img/se_conv.png"></p>

## 上昇率

次の図に、上昇率と上昇率の信頼区間を [!DNL Target] レポート。 数値は、上昇率範囲の平均を表し、上昇率が正または負の場合に矢印が反映されます。 信頼性が 95%を超えるまで、矢印は灰色で表示されます。 信頼性がしきい値を超えると、矢印は、正または負の上昇率に基づいて緑または赤になります。

<p style="text-align:center;"><img width="35%" src="img/lift.png"></p>

エクスペリエンス間の上昇率  *ν*、およびコントロールエクスペリエンス *ν<sub>0</sub>* は、コンバージョン率の相対的な「デルタ」で、

<p style="text-align:center;"><img width="15%" src="img/lift_definition.png"></p>

個々のコンバージョン率は、上で定義したとおりです。 もっと簡単に言えば

```
Lift(Experience N) = (Performance_Experience_N - Performance_Control)/ Performance_Control
```

コントロールエクスペリエンスのコンバージョン率 *ν<sub>0</sub>* が 0 の場合、上昇率はありません。

## 上昇率の信頼区間

の箱ひげグラフ [!UICONTROL 平均上昇率と信頼区間] 列は、平均値と上昇率の 95%信頼区間を表します。 特定の非制御エクスペリエンスの信頼区間に、コントロールエクスペリエンスの信頼区間との重複がある場合、箱ひげは灰色になり、特定のエクスペリエンスの信頼区間の範囲がコントロールエクスペリエンスの信頼区間の上または下にある場合は緑または赤になります。

エクスペリエンス間の上昇率の標準誤差  *ν*、およびコントロールエクスペリエンス  *ν<sub>0</sub>* は次のように定義されます。

<p style="text-align:center;"><img width="35%" src="img/se_lift.png" alt="metric-mean"></p>

上昇率の 95%信頼区間は次のようになります。

<p style="text-align:center;"><img width="40%" src="img/lift_CI.png"></p>

この計算では「差分」方式を使用し、次の手順で説明します [このドキュメントの詳細](/help/main/assets/confidence_interval_lift.pdf)

## 信頼性

最後の列には、 [!DNL Target] レポート。 エクスペリエンスの信頼性とは、null の仮説が真の場合に、実際に観測された結果よりも低い極端な結果が得られる確率（パーセントで示されます）です。 p 値の観点から、表示される信頼性は次のようになります。 *1 - p 値*. 直感的に、信頼性が高いと、コントロールエクスペリエンスと非コントロールエクスペリエンスのコンバージョン率が等しくなる可能性が低くなります。

In [!DNL Target]，両側 **ウェルチ t 検定** は、テストエクスペリエンスとコントロールエクスペリエンスの間で実行され、テストエクスペリエンスとコントロールエクスペリエンスの手段が同じかどうかをテストします。 2 つのグループのサンプルサイズと相違が同じかどうかは、実験を実行する前に通常はわからないので、 [!DNL Target] また、各エクスペリエンスに同等のトラフィックの割合を送信することもできます。各エクスペリエンスの分散が等しいとはみなされません。 したがって、ウェルチの t 検定は、学生の t 検定の代わりに選択されます。

ウェルチの t 検定を行うには、まず t 統計と自由度の計算を開始し、次に t 検定を実行して p 値を生成します。 最後に、p 値に基づいて信頼性を計算します。

この *t*-statistic は、2 つの独立したランダム変数の手段の違いと定義されます。 *ν* および *ν<sub>0</sub>*&#x200B;を、差の標準誤差で割った値になります。

<p style="text-align:center;"><img width="100px" src="img/t_value.png"></p>

場所 *μ<sub>v</sub>* および *μ<sub>v0</sub>* は *ν*  および *ν<sub>0</sub>* それぞれ、および *μ<sub>v</sub>* および *μ<sub>v0</sub>* は次の方法で指定します。

<p style="text-align:center;"><img width="150px" src="img/standard_error_diff.png"></p>

場所 *σ<sup>2</sup><sub>v</sub>* および *σ<sup>2</sup><sub>v<sub>0</sub></sub>* は、2 つのエクスペリエンスの相違です *ν*  および *ν<sub>0</sub>* それぞれおよび *N<sub>v</sub>* および *N<sub>v<sub>0</sub></sub>* はサンプルサイズです。 *ν* および *ν<sub>0</sub>* それぞれ

ウェルチの t 検定では、自由度は次のように計算されます。

<p style="text-align:center;"><img width="180px" src="img/degree_of_freedom.png"></p>

自由度 *ν*  および *ν<sub>0</sub>* は次のように定義されます。

<p style="text-align:center;"><img width="100px" src="img/df_v.png"></p>

<p style="text-align:center;"><img width="100px" src="img/df_v0.png"></p>

次に、p 値を *t*-distribution:

<p style="text-align:center;"><img width="20%" src="img/p_value.png"></p>

最後に、 [!DNL Target] は次のように定義されます。

<p style="text-align:center;"><img width="20%" src="img/confidence.png"></p>

## オフラインでの計算の実行

[ダウンロードした CSV レポート](/help/main/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) には生データのみが含まれ、A/B テストで使用される訪問者あたりの売上高、上昇率、信頼性などの計算指標は含まれません。

これらの統計量を計算するには、Target の [Complete Confidence Calculator](/help/main/assets/complete_confidence_calculator.xlsx) アクティビティの値を入力する Excel ファイル。