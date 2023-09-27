---
keywords: mvt；多変量分析テスト；オファー；組み合わせ
description: の使用方法を学ぶ [!UICONTROL Visual Experience Composer] (VEC)Adobe [!DNL Target] を使用して、 [!UICONTROL 多変量分析テスト] (MVT)。
title: 組み合わせを作成する方法 [!UICONTROL 多変量分析テスト] (MVT)?
feature: Multivariate Tests
exl-id: 8b5883de-de76-403d-ae20-c933a8665555
source-git-commit: 7853d8c5934e40d1026e067dfa413f520ecba931
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 71%

---

# 組み合わせの作成

以下を使用します。 [!UICONTROL Visual Experience Composer] (VEC) [!DNL Adobe Target] を使用して、 [!UICONTROL 多変量分析テスト] (MVT)。

VEC を使用したオファーの作成および編集について詳しくは、[Visual Experience Composer オプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

>[!NOTE]
>
>ページ上のオブジェクトを選択するときに「**[!UICONTROL 選択範囲を拡張]**」をクリックすると、選択した要素に加えて親要素を選択できます。親要素を選択しているときは、その要素のすべての子が自動的に選択されます。選択の拡張は繰り返し実行できます。
>
>また、[DOM パス](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)を使用して要素をナビゲートすることもできます。

## 画像オファー {#section_A48333211DB149ED926AE467D0032914}

複数の画像オファーを特定の場所でテストし、どの画像が最も効果が高いかを判断します。

1. ページ上の画像をクリックし、「**[!UICONTROL 画像を変更]**」を選択します。

   ![「画像を変更」オプション](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/changeimage.png)

1. テストに含めるすべての画像を選択し、 **[!UICONTROL 保存]**.

   ![画像を追加するのに使用されるコンテンツを選択ダイアログボックス](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/addimage.png)

各画像は、その場所での別々のエクスペリエンスになります。

## HTML オファー {#section_DF016101AFA9412C9B99862C23DE77B1}

複数のテキスト／HTML オファーを場所内でテストし、どのオファーが最も大きな成功を収めているか判断します。

1. ページのテキスト／HTML オファーをクリックし、「**[!UICONTROL テキスト/HTML を変更]**」をクリックします。

   ![テキスト／HTML を変更](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/changehtml.png)

1. 「**[!UICONTROL テキスト/HTML オファーを追加]**」をクリックし、オファーに名前を付けて、テキスト／HTML オ ファーのコードを入力または貼り付けます。

   ![オファーを編集](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   追加のテキスト／HTMLオファーを追加します。

1. 「**[!UICONTROL 保存]**」をクリックします。

各テキスト／HTML オファーは、その場所の個別のエクスペリエンスになります。

## ベストプラクティス {#section_2E98C23D2F1A460FA732A31799CE6291}

* テストに必要となる以上の場所を組み込まないでください。テストに組み込むエクスペリエンスの数が増えると、期待に添った結果を実現するために必要なトラフィック量および時間が大幅に増加します。例えば、それぞれ 3 つのオファーが組み込まれたページ要素がある場合は、9 つの組み合わせ（3 x 3）になります。3 つの要素があり、そのうちの 2 つの要素に 3 つのオファーが、1 つの要素に 2 つのオファーが組み込まれている場合は、組み合わせは 18（3 x 3 x 2）になります。要素やオファーの数が増えると、組み合わせの数は大きく増加します。
* 多変量分析テストを作成する場合、分析にオフラインレポートを使用する必要があるという警告を確認したら、テストから 10%以上のエクスペリエンスを除外できます。
* 望ましくないコンテンツの組み合わせを避けるためにプレビュー機能を利用します。例えば、同じ商品やサービスに対して異なる割引率を提供する 2 つの画像がある場合が考えられます。同じページにこれらの両方の画像を表示しても意味がなく、訪問者を混乱させるだけです。
* [トラフィック見積もり](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md)を使用して、ページで予想されるトラフィック量に合ったテストをおこないます。目的の結果を得られるように、トラフィック見積もりでテスト設定が緑色に表示されていることを確認します。
* テストする要素を 3 つ以上選択します。それより少ない場合は、一連のA/B テストを実行します。
* 各要素の代替オプションは、互いに大きく異なるものにする必要があります。
* 各要素に、同じ数の代替オプションを指定することをお勧めします（必須ではありません）。
