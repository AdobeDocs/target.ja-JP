---
keywords: レポート；統計的手法；統計計算；統計；平均；コンバージョン率；訪問者あたりの売上高；rpv；信頼区間；上昇率；ウェルチ t テスト；オフライン計算
description: ' [!DNL Adobe Target]の[!UICONTROL A/B テスト &#x200B;]手動アクティビティで使用される統計計算について説明します。'
title: '[!UICONTROL A/B テスト &#x200B;] アクティビティで使用される統計計算について学習するにはどうすればよいですか？'
feature: Reports
exl-id: 5f7377b9-0567-4b6f-8968-4696b2088d0a
TQID: https://experienceleague.adobe.com/LEFFg6KjhxYM0jMRGOPcHwLzZ07SOBh-Faf3JK3Pfn4
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 224dafac8d5d0ba17baa4ee998ca7dd89b73b898
workflow-type: tm+mt
source-wordcount: 1506
ht-degree: 3%

---

# A/Bn テストによる統計計算

この記事では、[!DNL Adobe Target]の手動A/Bn テストで使用される詳細な統計計算について説明します。 定義は、**[!UICONTROL コンバージョン率]**、**[!UICONTROL コンバージョン率]**&#x200B;の信頼区間、**[!UICONTROL 上昇率]**、**[!UICONTROL 上昇率]**、**[!UICONTROL 信頼性]**&#x200B;および&#x200B;**[!UICONTROL ベイジアン]**&#x200B;の決定指標に対して提供されます。

**[!UICONTROL A/B テスト]** （手動）アクティビティは、[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_13119392051044FBA6387D9B3B1C43CF)のアクティビティごとに選択された2つの統計的手法をサポートしています。

* [&#x200B; ウェルチのt テスト &#x200B;](#welchs-t-test)：固定標本サイズの仮説テストに基づいて&#x200B;**[!UICONTROL 信頼性]**&#x200B;の割合と信頼区間を報告する頻度論的手法です。 **[!UICONTROL 収益]**&#x200B;または&#x200B;**[!UICONTROL エンゲージメント]**&#x200B;の主な目標を持つアクティビティに使用されます。

* [&#x200B; ベイジアン &#x200B;](#bayesian-statistics)：各エクスペリエンスの目標指標の事後分布から計算して、**[!UICONTROL ビートコントロールの可能性]**&#x200B;や信頼性の高い間隔などの確率として結果を報告します。 この設定は、主な目標指標が&#x200B;**[!UICONTROL コンバージョン]**&#x200B;のアクティビティでのみ使用できます。

## ウェルチのt検定

### 平均性能

次の節では、次の図で使用する計算について説明します。

A/B テスト アクティビティの[!UICONTROL &#x200B; コンバージョン率]、[!UICONTROL 平均上昇率と信頼区間]、および[!UICONTROL 信頼性]を示す![Target レポート。](/help/main/c-reports/statistical-methodology/img/target_report.png)

#### 訪問者あたりのコンバージョン率と収益（RPV）キャンペーン

次の図は、[!DNL Target] レポートの&#x200B;**[!UICONTROL コンバージョン率]**、**[!UICONTROL コンバージョン率]**&#x200B;の信頼区間、および&#x200B;**[!UICONTROL コンバージョン数]**&#x200B;を示しています。 例えば、最初の行は、エクスペリエンス Aについて、**[!UICONTROL コンバージョン率]**&#x200B;は25.81%で、**[!UICONTROL 信頼区間]**&#x200B;は±7.7%で、コンバージョンは32件が記録されていることを示しています。 124人の訪問者がこのエクスペリエンスを視聴したことを考えると、これは32/124 = 25.81%に相当します。

<p style="text-align:center;"><img width="25%" src="img/conv_rate.png"></p>

実験の各エクスペリエンス *ν*&#x200B;に対するコンバージョン率（**平均**、*μ<sub>ν</sub>*）は、指標の合計と、その指標に割り当てられた単位数（*N<sub>ν</sub>*）の比率として定義されます。

<p style="text-align:center;"><img width="125px" src="img/mean_definition.png"></p>

ここで、

* *Y<sub>iν</sub>*&#x200B;は、特定のエクスペリエンス *ν*&#x200B;に割り当てられている各ユニット *i*&#x200B;の指標の値です。

* 単位&#x200B;*i*&#x200B;の合計は、カウント方法の選択によって異なります。

  * **[!UICONTROL 訪問者]**&#x200B;がカウント方法として使用される場合、各ユニットは、アクティビティのライフタイムのアクティビティにおける一意の参加者として定義された一意の訪問者です。
  * **[!UICONTROL 訪問]**&#x200B;がカウント方法として使用される場合、各単位は、[!DNL Target] セッション中にエクスペリエンスの一意の参加者として定義された一意の訪問です（一意の`sessionId`）。 `sessionId`が変更されたとき、または訪問者がコンバージョンステップに達したとき、新しい訪問がカウントされます。
  * **[!UICONTROL アクティビティ インプレッション]**&#x200B;がカウント方法として使用される場合、各単位は、訪問者がアクティビティの任意のページを読み込むたびに定義される一意のインプレッションです。

### 平均/[!UICONTROL &#x200B; コンバージョン率]の信頼区間

コンバージョン率の信頼区間は、基礎データと一貫性のある可能なコンバージョン率の範囲として直感的に定義されます。

実験を実行する場合、特定のエクスペリエンスのコンバージョン率は、「真」のコンバージョン率の&#x200B;*推定*&#x200B;です。 この見積もりの不確実性を定量化するために、[!DNL Target]は信頼区間を使用します。 [!DNL Target]は常に95%の信頼区間を報告します。つまり、最終的に計算された信頼区間の95%には、エクスペリエンスの真のコンバージョン率が含まれます。

現在リードしているエクスペリエンス、もしくは勝者のエクスペリエンスの横には「信頼性」の数値もレポートされます。 この数値は、最初のエクスペリエンスの&#x200B;**[!UICONTROL Confidence]**&#x200B;が60%以上に達するまで報告されません。 アクティビティに2つのエクスペリエンスが存在する場合、この数値は、エクスペリエンスが他のエクスペリエンスよりもパフォーマンスが高い信頼性レベルを表します。 アクティビティに2つ以上のエクスペリエンスが存在する場合、この数値は、エクスペリエンスが定義された「コントロール」エクスペリエンスよりも優れたパフォーマンスを示す信頼性レベルを表します。 「コントロール」エクスペリエンスが勝者である場合、「信頼性」の数値はレポートされません。

コンバージョン率&#x200B;*μ<sub>ν</sub>*&#x200B;の95%信頼区間は、次の値の範囲として定義されます。

<p style="text-align:center;"><img width="30%" src="img/confidence_interval.png"></p>

平均の標準誤差は、次のように定義されます

<p style="text-align:center;"><img width="75px" src="img/se_conv_continuous.png"></p>

サンプル標準偏差の偏りのない推定値を使用する場合：

<p style="text-align:center;"><img width="200px" src="img/stdev_definition.png"></p>

キャンペーンがコンバージョン率キャンペーンの場合（つまり、コンバージョン指標がバイナリの場合）、標準エラーは次のように減少します。

<p style="text-align:center;"><img width="150px" src="img/se_conv.png"></p>

### 上昇率

次の図は、[!DNL Target] レポートの&#x200B;**[!UICONTROL 上昇率]**&#x200B;と&#x200B;**[!UICONTROL 上昇率]**&#x200B;の信頼区間を示しています。 数値は、リフト境界の範囲の平均を表し、矢印はリフトが正または負の場合を反映します。 信頼度が95%に達するまで、矢印はグレーで表示されます。 信頼度がしきい値を通過すると、正または負の上昇率に基づいて矢印が緑色または赤になります。

<p style="text-align:center;"><img width="35%" src="img/lift.png"></p>

エクスペリエンス *ν*&#x200B;とコントロール エクスペリエンス *ν<sub>0</sub>*&#x200B;との間の上昇率は、コンバージョン率の相対的な「差分」です。次のように定義されます

<p style="text-align:center;"><img width="15%" src="img/lift_definition.png"></p>

各コンバージョン率は上記で定義したとおりです。 よりシンプルに，

```
Lift(Experience N) = (Performance_Experience_N - Performance_Control)/ Performance_Control
```

コントロールエクスペリエンス *ν<sub>0</sub>*&#x200B;のコンバージョン率が0の場合、上昇率はありません。

### [!DNL Confidence Interval of Lift]

**[!UICONTROL 平均上昇率と信頼区間]**&#x200B;列のボックスプロットグラフは、上昇率&#x200B;**の平均値と95%**&#x200B;信頼区間を表します。 ある非制御エクスペリエンスの信頼区間と制御エクスペリエンスの信頼区間に重複がある場合、ボックスプロットはグレーになります。 与えられたエクスペリエンスの信頼区間の範囲がコントロールエクスペリエンスの信頼区間の上下にある場合、ボクスプロットは緑または赤になります。

エクスペリエンス *ν*&#x200B;と制御エクスペリエンス *ν<sub>0</sub>*&#x200B;との間のリフトの標準エラーは、次のように定義されます。

<p style="text-align:center;"><img width="35%" src="img/se_lift.png" alt="指標の平均"></p>

そして、リフトの95%信頼区間は次のようになります。

<p style="text-align:center;"><img width="40%" src="img/lift_CI.png"></p>

この計算は、「Delta」メソッドを使用します。詳しくは、[このドキュメントで説明しています](/help/main/assets/confidence_interval_lift.pdf)

### [!UICONTROL 信頼性]

最後の列は、[!DNL Target] レポートの信頼性を示しています。 経験の信頼性は、帰無仮説が真であるとして、観察された結果として極端な結果を得る確率（パーセンテージとして表される）です。 p値に関しては、表示される信頼性は&#x200B;*1 - p値*&#x200B;です。 直感的には、信頼性が高いほど、コントロールされたエクスペリエンスとコントロールされていないエクスペリエンスのコンバージョン率が等しい可能性が低いことを意味します。

[!DNL Target]では、テスト エクスペリエンスと制御エクスペリエンスの間に2つのテール **Welchのt-test**&#x200B;が実行され、テスト エクスペリエンスと制御エクスペリエンスの手段が同じかどうかをテストします。 通常、実験を実行する前に、2つのグループのサンプルサイズと分散が同じかどうか分からず、また[!DNL Target]では、各エクスペリエンスに送信されるトラフィックの割合が同じになることも可能なので、各エクスペリエンスの分散が同じであるとは仮定しません。 したがって、ウェルチのt検定は、学生のt検定の代わりに選択されます。

ウェルチのt検定を実行するには、まずt統計量と自由度の計算を開始し、次に2 テールのt検定を実行してp値を生成します。 最後に、p値に基づいて信頼性を計算します。

*t* – 統計量は、*ν*&#x200B;と&#x200B;*ν<sub>0</sub>*&#x200B;の2つの独立確率変数の平均の差を、その差の標準誤差で割ったものと定義されています。

<p style="text-align:center;"><img width="100px" src="img/t_value.png"></p>

ここで、*μ<sub>v</sub>*&#x200B;および&#x200B;*μ<sub>v0</sub>*&#x200B;はそれぞれ&#x200B;*ν*&#x200B;および&#x200B;*ν<sub>0</sub>*&#x200B;の手段であり、*μ<sub>v</sub>*&#x200B;および&#x200B;*μ<sub>v0</sub>*&#x200B;の差の標準誤差は次のように与えられる：

<p style="text-align:center;"><img width="150px" src="img/standard_error_diff.png"></p>

*σ<sup>2</sup><sub>v</sub>*&#x200B;および&#x200B;*σ<sup>2</sup><sub>v<sub>0</sub></sub>*&#x200B;は、それぞれ2つのエクスペリエンス *ν*&#x200B;および&#x200B;*ν<sub>0</sub>*&#x200B;の分散であり、*N<sub>v</sub>*&#x200B;および&#x200B;*N<sub>v<sub>0</sub></sub>*&#x200B;はそれぞれ&#x200B;*ν<sub>のサンプルサイズです。**</sub>*

ウェルチのt検定では、自由度は次のように計算される：

<p style="text-align:center;"><img width="180px" src="img/degree_of_freedom.png"></p>

*ν*&#x200B;および&#x200B;*ν<sub>0</sub>*&#x200B;の自由度は、次のように定義されます。

<p style="text-align:center;"><img width="100px" src="img/df_v.png"></p>

<p style="text-align:center;"><img width="100px" src="img/df_v0.png"></p>

次に、p値は、*t*&#x200B;分布の末尾の領域から計算できます。

<p style="text-align:center;"><img width="20%" src="img/p_value.png"></p>

最後に、[!DNL Target]で報告された信頼性は、次のように定義されます。

<p style="text-align:center;"><img width="20%" src="img/confidence.png"></p>

## ベイズ統計

近似分布からp値を計算する代わりに、**[!UICONTROL ベイジアン]** アクティビティのレポートでは、各エクスペリエンスの目標指標の事後分布の全体から計算された結果を確率として表します。 これにより、**[!UICONTROL ベイズ]**&#x200B;報告書を継続的に監視しても安全です。これは、固定サンプルサイズに達する前に結果を確認する統計的ペナルティがなく、**[!UICONTROL ウェルチのt-test]**&#x200B;よりも小さいサンプルでより速く収束できるためです。

**[!UICONTROL ベイズ]**&#x200B;手法では、マーケターは過去の実験とコントロール バリアントの結果に基づいて仮説をフィードすることもできます。

**[!UICONTROL ベイズ]**&#x200B;手法は、主な目標指標が&#x200B;**[!UICONTROL コンバージョン]**&#x200B;のアクティビティでのみ使用できます。主な目標が&#x200B;**[!UICONTROL 収益]**&#x200B;または&#x200B;**[!UICONTROL エンゲージメント]**&#x200B;のアクティビティでは、常に&#x200B;**[!UICONTROL ウェルチのt-test]**&#x200B;を使用します。 方法論の選択について詳しくは、[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_13119392051044FBA6387D9B3B1C43CF)を参照してください。

### 平均上昇率と信頼区間

<p style="text-align:center;"><img width="35%" src="img/bayesian_1.png"></p>

平均上昇率と信頼性の高い間隔を合わせることで、**[!UICONTROL ベイズ]** アクティビティにおけるパフォーマンスの向上とその不確実性を測定します。 「平均上昇率」は、処理とコントロール間の平均変化率です。一方、「信頼性の高い」区間は、指定された確率で真の上昇率が低下する範囲を定義します。

### [!UICONTROL &#x200B; コントロールを打ち負かすチャンス &#x200B;]

<p style="text-align:center;"><img width="35%" src="img/bayesian_2.png"></p>

**[!UICONTROL ビートコントロールの可能性]**&#x200B;は、エクスペリエンスの目標指標が&#x200B;**[!UICONTROL コントロール]** エクスペリエンスを上回る可能性です（例：「92% chance B beats A」）。 これは、**[!UICONTROL ベイズ]** アクティビティの主な意思決定指標です。チャレンジャーエクスペリエンスは、**[!UICONTROL ビートコントロールのチャンス]**&#x200B;がアクティビティの意思決定閾値を満たす場合、**[!UICONTROL コントロール]**&#x200B;に代わる候補です。

<!--
### [!UICONTROL Probability to be Best]

[!UICONTROL Probability to be Best] is the probability that an experience is the single best of all experiences in the activity. Use this decision metric to pick which winner to ship in a test with more than one challenger experience.
-->

## オフラインでの計算の実行

[ダウンロードした CSV レポート](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) には生データのみが含まれ、A/B テストで使用される訪問者あたりの売上高、上昇率、信頼性などの計算指標は含まれません。

これらの統計量を計算するには、[!DNL Target] [信頼計算を完了](/help/main/assets/complete_confidence_calculator.xlsx) Excel ファイルをダウンロードして、アクティビティの値を入力します。
