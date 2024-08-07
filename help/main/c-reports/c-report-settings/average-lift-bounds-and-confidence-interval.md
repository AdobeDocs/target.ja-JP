---
keywords: Target、レポート、レポート設定、environment、上昇率、上昇率バインド、平方偏差、confidence、control
description: アクティビティの上昇率範囲と信頼性レベルを理解するのに役立つ、データポイントとビジュアライゼーション表示域を含んだAdobe [!DNL Target]  レポートを解釈する方法を説明します。
title: 平均上昇率、上昇率範囲および信頼区間はどのように表示されますか。
feature: Reports
exl-id: 0453aec1-cca5-462c-8eed-0d40bb4cf323
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 60%

---

# 平均上昇率、上昇率範囲および信頼区間

レポートには、[!DNL Adobe Target] アクティビティに関連する上昇率範囲と信頼性レベルを理解して、勝者をより正確に判断するのに役立つ、複数のデータポイントとビジュアライゼーション表示域が含まれています。

>[!NOTE]
>
>この機能は、レポートを [!UICONTROL Table] ビューで表示している場合にのみ使用できます。 この機能は、Analytics をレポートソースに使用する（A4T）[アクティビティでは利用できません。](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)。

## データの解釈 {#section_62C0D7E76F3D49A7B3C371C82AEF27D5}

次の図に、[!UICONTROL Lift Bounds and Confidence Level] の情報を示します。

![平均上昇率および信頼性レベルレポート](/help/main/c-reports/c-report-settings/assets/lift-screenshot-new.png)

[!DNL Target] レポート UI の上昇率および信頼性に関する情報には、次が含まれます。

### 上昇率

数値の大きさと矢印が上昇率の推定値を表しています。この数値は上昇率の範囲の中間値です。推定上昇率の矢印は、信頼度が 95％に達するまでは灰色で表示されます。このしきい値を超えると、矢印の色は赤（マイナス）または緑（プラス）になります。

### 上昇範囲

上昇率の 95％信頼区間を表します。平均上昇率の下に範囲として表示されます。これらの上昇率範囲の計算方法の例については、以下の [ 計算例 ](#example) を参照してください。

### ボックスプロットグラフ

[!DNL Target] インターフェイスのボックス図グラフは、問題の成功指標の期待値と 95% の信頼区間を表します。 上昇率と上昇率範囲の情報を視覚的に表したものと言えます。

信頼性情報の解釈に役立つ重要な方法 [!DNL Target] いくつかありますが、その 1 つは色です。 このグラフでは、特定のエクスペリエンスの信頼区間とコントロールの信頼区間の重複が灰色で表示されます。特定のエクスペリエンスの信頼区間の範囲は、コントロールの信頼区間より高い部分は緑、低い部分は赤で表示されます。

箱ひげのバーの長さを見れば、信頼区間の大きさがすぐにわかります。アクティビティのデータが蓄積されていくと、バーが変化していきます。信頼区間は平方偏差とサンプルサイズ（訪問者数）から求められます。平方偏差が小さくサンプルサイズが大きいほど、信頼区間は狭くなります。

### 信頼性

表示されるエクスペリエンスまたはオファーの信頼性は、結果が実際に観測された確率 _null 仮説が true の場合_ つまり、そのエクスペリエンスまたはオファーとコントロールのエクスペリエンスまたはオファーのコンバージョン率に違いがない場合 _よりも、結果が得られる確率_ 極端でない割合で表される）です。 p 値に関しては、表示されるこの信頼性は `1 - p-value` です。 より簡単に言えば、コントロールのオファー/エクスペリエンスとコントロール以外のオファー/エクスペリエンスのコンバージョン率が等しいという仮定の下では、信頼性が高くなるほどデータの一貫性が低くなります。

## 上昇率の信頼区間の決定方法を理解します {#pdf}

詳しくは、[ 上昇率 PDF ファイルの信頼区間 ](/help/main/assets/confidence_interval_lift.pdf) をダウンロードしてください。

## 上昇率範囲の計算方法 {#section_1D360781D972483693680BE0F07AEAD1}

上昇率範囲は、コントロールエクスペリエンスまたはオファーに対する、特定のエクスペリエンスまたはオファーの上昇率の 95％信頼区間を表します。簡単に言えば、実際の上昇率は 95％の確率でこの範囲内に収まるという意味になります。

上昇率範囲の計算式は次のとおりです。

![lift_diagram image](assets/lift_diagram.png)

上昇率範囲の数値の算出には、他にもいくつかの要素が考慮されます。

* **t 値：** 95% の信頼性レベルの重要な統計は 1.96 です。[t 値について詳しくは、こちらを参照してください ](https://en.wikipedia.org/wiki/T-statistic)。
* **上昇率の平方偏差：**&#x200B;上昇率の平方偏差を求めるためには、エクスペリエンス N の成功指標の標準誤差と、コントロールエクスペリエンスの成功指標の標準誤差が必要です。計算式は次のとおりです（成功指標をコンバージョンとした場合の例です）。

  ![lift_variance image](assets/lift_variance.png)

* **コンバージョン率／成功指標の標準誤差：**&#x200B;標準誤差の算出方法は、次のように、エクスペリエンス N とコントロールで同じです（成功指標をコンバージョンとした場合の例です）。詳しくは、[標準誤差の詳細](https://en.wikipedia.org/wiki/Standard_error)を参照してください。

  ![standard_error 画像 ](assets/standard_error.png)

  >[!NOTE]
  >
  >売上高成功指標アクティビティの標準エラーは、売上高のサンプル分散に基づいています。

## 計算の例 {#example}

2 つのエクスペリエンスで構成されるアクティビティがあり、次のような結果が出たとします。

| エクスペリエンス | 訪問者数 | コンバージョン | コンバージョン率 |
|--- |--- |--- |--- |
| エクスペリエンス A（コントロール） | 219、328 | 2,466 | 1.12％ |
| エクスペリエンス B | 218、362 | 3,040 | 1.39％ |

アドビの計算式を使用し、これらの情報から上昇率範囲を求めることができます。

**エクスペリエンス A の標準誤差（コントロール）**

![standard_error_A 画像 ](assets/standard_error_A.png)

**エクスペリエンス B の標準誤差**

![standard_error_B 画像 ](assets/standard_error_B.png)

**エクスペリエンス B の上昇率の平方偏差**

![lift_variance_B 画像 ](assets/lift_variance_B.png)

**エクスペリエンス B の上昇率範囲**

エクスペリエンス B の推定上昇率は次のとおりです。

![lift_bounds_B 画像 ](assets/lift_bounds_B.png)

以上の計算から、エクスペリエンス B の上昇率範囲は次のようになります。

![lift_bounds_B2 画像 ](assets/lift_bounds_B2.png)

>[!NOTE]
>
>上記の数式とレポートに表示される数値を使用して、手動の計算の差異を最小にします。この差の原因は、手動計算で使用されるページビュー数が丸められていることにあります。[!DNL Target] のレポートに表示される上昇率は、エンゲージメントの合計とエンゲージメント数から得られた正確な数値に基づいています。 エンゲージメントの数値は、パフォーマンスレポート API を介して取得できます。

## 上昇率範囲が表示されないのはどのような場合ですか。 {#section_C5622E1E94684DAD937249B51A9E42CC}

場合によっては、[!DNL Target] にリフト範囲が表示されません。

* アクティビティの訪問数または訪問者数が 30 に達していない。
* [!UICONTROL Auto-Allocate] アクティビティの場合、1 つのエクスペリエンスの信頼性が 60% に達するまで、上昇率範囲は表示されません。
