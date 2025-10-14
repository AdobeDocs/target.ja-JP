---
keywords: mvt；多変量分析テスト；オファー；組み合わせ
description: Adobeの [!UICONTROL Visual Experience Composer] （VEC）を使用して、 [!DNL Target]  （MVT[!UICONTROL Multivariate Test] に含めるオファーを作成する方法を説明します。
title: '[!UICONTROL Multivariate Test] （MVT）での組み合わせの作成方法'
feature: Multivariate Tests
exl-id: 8b5883de-de76-403d-ae20-c933a8665555
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 54%

---

# 組み合わせの作成

[!UICONTROL Visual Experience Composer] の [!DNL Adobe Target] （VEC）を使用して、[!UICONTROL Multivariate Test] （MVT）に含めるオファーを作成します。

VEC を使用したオファーの作成および編集について詳しくは、[Visual Experience Composer オプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

>[!NOTE]
>
>ページ上のオブジェクトを選択するときに **[!UICONTROL Expand Selection]** をクリックすると、最初に選択した要素に加えて親要素も選択できます。 親要素を選択しているときは、その要素のすべての子が自動的に選択されます。選択の拡張は繰り返し実行できます。
>
>また、[DOM パス](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)を使用して要素をナビゲートすることもできます。

## 画像オファー {#section_A48333211DB149ED926AE467D0032914}

1 つの場所で複数の画像オファーをテストし、どの画像が最も成功しているかを判断します。

1. ページ上の画像をクリックし、「**[!UICONTROL Change Image Offer]**」を選択します。

1. [!UICONTROL Image Offer] ダイアログボックスで、テストに含めるすべての画像を選択し、「**[!UICONTROL Add]**」をクリックします。

各画像は、その場所での別々のエクスペリエンスになります。

## HTML オファー {#section_DF016101AFA9412C9B99862C23DE77B1}

複数の HTML オファーを特定の場所でテストして、どのオファーが最も効果が高いかを判断します。

1. ページでHTML オファーをクリックし、「**[!UICONTROL Change HTML Offer]**」をクリックします。

1. 「**[!UICONTROL Create Offer]**」をクリックし、「**[!UICONTROL HTML Offer]**」をクリックしてオファーに名前を付け、HTML オファーのコードを入力または貼り付けて、「**[!UICONTROL Create]**」をクリックします。

   追加で組み込む HTML オファーに対して同じ手順を繰り返します。

1. **[!UICONTROL Save]** をクリックします。

各 HTML オファーは、その場所での別々のエクスペリエンスになります。

## ベストプラクティス {#section_2E98C23D2F1A460FA732A31799CE6291}

* テストに必要となる以上の場所を組み込まないでください。テストに組み込むエクスペリエンスの数が増えると、期待に添った結果を実現するために必要なトラフィック量および時間が大幅に増加します。例えば、それぞれ 3 つのオファーが組み込まれたページ要素がある場合は、9 つの組み合わせ（3 x 3）になります。3 つの要素があり、そのうちの 2 つの要素に 3 つのオファーが、1 つの要素に 2 つのオファーが組み込まれている場合は、組み合わせは 18（3 x 3 x 2）になります。要素やオファーの数が増えると、組み合わせの数は大きく増加します。
* 多変量分析テストを作成する場合、分析にオフラインレポートを使用する必要があるという警告を確認すると、10% 以上のエクスペリエンスをテストから除外できます。
* 望ましくないコンテンツの組み合わせを避けるためにプレビュー機能を利用します。例えば、同じ商品やサービスに対して異なる割引率を提供する 2 つの画像がある場合が考えられます。同じページにこれらの両方の画像を表示しても意味がなく、訪問者を混乱させるだけです。
* [&#x200B; トラフィック見積もり &#x200B;](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) を使用して、テストがページが受信するトラフィック量に合わせて設計されていることを確認します。 希望する結果を得ることができるように、トラフィック見積もりでテスト設定の信号が緑になっていることを確認します。
* テストする要素を 3 つ以上選択します。3 つ未満の場合は、一連の A/B テストを実行します。
* 各要素の代替値は、互いに大きく異なる必要があります。
* 各要素に、同じ数の代替オプションを指定することをお勧めします（必須ではありません）。
