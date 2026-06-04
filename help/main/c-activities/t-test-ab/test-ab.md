---
keywords: AB;A/B;AB...n；エクスペリエンスの比較；ターゲティング；コンテンツの比較；自動ターゲット；自動割り当て
description: ' [!DNL Target] ～[!UICONTROL 手動]、[!UICONTROL 自動割り当て]、[!UICONTROL 自動ターゲット &#x200B;]のA/B テスト アクティビティを確認します。'
title: ' [!DNL Target]で利用可能なA/B テスト アクティビティを確認します。'
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
TQID: https://experienceleague.adobe.com/wcflYDj0VB7dJODNO6XjFHB0PPIhN4aUrBJxbKPoNdg
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 757
ht-degree: 19%

---

# A/B テストの概要

手動の[!UICONTROL A/B テスト &#x200B;] アクティビティ（「A/B...N テスト」とも呼ばれます）は、Web サイトのコンテンツの2つ以上のバージョンを比較し、どのバージョンがコンバージョン、売上、またはその他の指標を最も向上させるかを確認します。 A/B テストを使用して、ページに加えた変更をデフォルトのページデザインと比較することで、最も適した結果を生成するエクスペリエンスを決定できます。

>[!TIP]
>
>[!UICONTROL 手動] （デフォルト） [!UICONTROL A/B テスト &#x200B;] アクティビティ （この記事で説明）に加えて、[!DNL Target]には、[!UICONTROL A/B テスト &#x200B;] アクティビティの2つの追加タイプが用意されています：[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット &#x200B;]。 詳しくは、以下の「[A/B テストアクティビティの種類](#types)」を参照してください。

手作業によるA/B テストは、成功指標や代替コンテンツの配信にもとづいて、ページのパフォーマンスを向上させる方法を明確に予測できる場合に役立ちます。

手動A/B テストは、新しいレイアウトや、要素の処理が大幅に異なる可能性がある大規模な変更に適しています。 テスト デザインが個々のページ要素に簡単に分解されない場合は、[多変量テスト &#x200B;](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)を実行する前に、A/B テストを実行する必要があります。

A/B テストを設定することで、各エクスペリエンスを利用している訪問者の割合を特定できます。 たとえば、コントロールと2つ目のエクスペリエンスの間でトラフィックを均等に分配したり、オーディエンスの5%に表示することで、よりリスクの高い新しいエクスペリエンスをテストしたりすることができます。

>[!NOTE]
>
>A/B テストのサンプルサイズの決定について詳しくは、[A/B テストの計画](/help/main/c-activities/t-test-ab/sample-size-determination.md)を参照してください。

異なるエクスペリエンスの数が5を超え、2つ以上の場所にまたがる場合は、A/B テストを実行する前に[MVT テスト &#x200B;](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)を検討することをお勧めします。 多変量分析テストによって、コンバージョンが向上する可能性が最も高そうなページ領域を判定できます。 これらの領域は、マーケターが注力すべき場所です。 例えば、MVT テストによって、目標を満たすために最も重要な場所はコールトゥアクションであることがわかったとします。 目標を達成するのに最も役立つ場所とコンテンツを決定したら、A/B テストを実施して、結果をさらに絞り込むことができます。 例えば、2つの特定の画像を比較したり、call to actionの表現や色を比較したりします。 MVT テストの後に 1 つ以上の A/B テストをおこなうことで、目的の結果を得るための最良のコンテンツを判断できます。

## A/B テスト活動の種類 {#types}

手動の[!UICONTROL A/B テスト &#x200B;] アクティビティに加えて、[!DNL Target]には、[!UICONTROL A/B テスト &#x200B;] アクティビティの2つの追加タイプが用意されています：[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット &#x200B;]。

| アクティビティタイプ | 説明 |
| --- | --- |
| [!UICONTROL 手動A/B テスト &#x200B;] | 複数のエクスペリエンスを比較して、事前に指定したテスト期間内で最もコンバージョンが向上したエクスペリエンスを確認します。<P>この節では、[!UICONTROL A/B テスト &#x200B;] アクティビティを手動で設定する方法について説明しますが、[!UICONTROL A/B テスト &#x200B;] アクティビティのその他の種類の手順は同様です。 |
| [!UICONTROL 自動配分] | 2つ以上のエクスペリエンスの中から勝者を特定し、その勝者にトラフィックをリダイレクトして、テストの実行と学習に応じてコンバージョンを向上させます。<P>[!UICONTROL 自動配分] アクティビティを使用する利点について詳しくは、*の[自動配分](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate)を参照してください。A/B テストを実行する時間*&#x200B;と[自動配分の概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| ![&#x200B; プレミアムバッジ &#x200B;](/help/main/assets/premium.png) [!UICONTROL 自動ターゲット &#x200B;] | 高度なマシンラーニング（機械学習）を利用して、パフォーマンスに優れたマーケター定義のエクスペリエンスを複数特定し、コンテンツをパーソナライズしてコンバージョンを促進できます。 訪問者には、個々の顧客プロファイルや類似する訪問者の過去の行動にもとづいて、最もカスタマイズされた体験が提供されます。<P>詳しくは、[自動ターゲット &#x200B;](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を参照してください。 |

これらの[!UICONTROL A/B テスト &#x200B;] アクティビティのうち、お客様に適しているアクティビティについて詳しくは、インタラクティブな[Adobe Target アクティビティ ガイド PDF](/help/main/c-activities/target-activities-guide.md)を参照してください。

3種類の[!UICONTROL A/B テスト &#x200B;] アクティビティを作成する手順は似ています。 [!UICONTROL 自動配分]または[!UICONTROL 自動ターゲット &#x200B;] アクティビティを作成するには：

1. [A/B テストアクティビティの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)から開始します。
1. 「[!UICONTROL &#x200B; ターゲティング &#x200B;]」ページに移動したら、「[!UICONTROL &#x200B; トラフィック配分]」コントロールをクリックし、次に示すように、右側のペインで目的のトラフィック配分方法を選択します。

   * [!UICONTROL 最適なエクスペリエンスに自動割り当て]
   * [!UICONTROL &#x200B; パーソナライズされたエクスペリエンスの自動ターゲット &#x200B;]

   ![&#x200B; トラフィック配分メソッドの設定](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

## A/B アクティビティにレコメンデーションを含める

[!UICONTROL A/B テスト &#x200B;]、[!UICONTROL 自動割り当て]、[!UICONTROL 自動ターゲット &#x200B;] アクティビティ（および[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （XT） アクティビティ）内に推奨事項を含めることができます。 詳しくは、[オファーとしてのレコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md)をご覧ください。

この機能を使用するには、[Target Premium ライセンス](/help/main/c-intro/intro.md#premium)が必要です。
