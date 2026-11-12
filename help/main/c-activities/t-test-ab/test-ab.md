---
keywords: AB;A/B;AB...n；エクスペリエンスの比較；ターゲティング；コンテンツの比較；自動ターゲット；自動割り当て
description: '[!DNL Target] - [!UICONTROL 手動]、[!UICONTROL 自動割り当て]、[!UICONTROL 自動ターゲット &#x200B;]のA/B テスト アクティビティを確認します。'
title: '[!DNL Target]で利用可能なA/B テスト アクティビティを確認します。'
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
TQID: 'https://experienceleague.adobe.com/wcflYDj0VB7dJODNO6XjFHB0PPIhN4aUrBJxbKPoNdg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: d887712962ad4e3cecd6b3b86ee33a4bcb99f2a8
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 19%
---
# A/B テストの概要 {#test-ab}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;手動A/B テストとは何か、多変量テストの代わりにそれを使用するタイミング、および自動配分と自動ターゲット アクティビティの種類との関係について説明します。

>[!ENDSHADEBOX]

手動の&#x200B;**[!UICONTROL A/B テスト]** アクティビティ（「A/B...N テスト」とも呼ばれます）は、Web サイトのコンテンツの2つ以上のバージョンを比較し、どのバージョンがコンバージョン、売上、またはその他の指標を最も向上させるかを確認します。 A/B テストを使用して、ページに加えた変更をデフォルトのページデザインと比較することで、最も適した結果を生成するエクスペリエンスを決定できます。

## 手動A/B テストを使用するケース {#when-to-use}

次の場合は、手動のA/B テストを使用します。

* 成功指標や代替コンテンツの配信にもとづいて、ページのパフォーマンスを向上させる方法について明確な仮説を立てることができます。
* 新しいレイアウトや、要素の大幅な処理など、大きな変更をテストする場合に使用します。 テスト デザインが個々のページ要素に簡単に分解されない場合は、[多変量テスト &#x200B;](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)を実行する前に、A/B テストを実行する必要があります。
* 各エクスペリエンスを閲覧した訪問者の割合を決定できます。 たとえば、コントロールと2つ目のエクスペリエンスの間でトラフィックを均等に分配したり、オーディエンスの5%に表示することで、よりリスクの高い新しいエクスペリエンスをテストしたりすることができます。

A/B テストのサンプルサイズの決定について詳しくは、[A/B テストの計画](/help/main/c-activities/t-test-ab/sample-size-determination.md)を参照してください。

### 多変量分析テストとA/B テストの組み合わせ

異なるエクスペリエンスの数が5を超え、2つ以上の場所にまたがる場合は、A/B テストを実行する前に[MVT テスト &#x200B;](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)を検討することをお勧めします。

1. **多変量テスト**&#x200B;を実行して、ページのどの領域がコンバージョンを改善する可能性が最も高いかを確認します。 これらの領域は、マーケターが注力すべき場所です。 例えば、MVT テストによって、目標を満たすために最も重要な場所はコールトゥアクションであることがわかったとします。

1. **これらの場所で1つ以上のA/B テスト**&#x200B;を実行して、結果をさらに絞り込みます。 例えば、2つの特定の画像を比較したり、call to actionの表現や色を比較したりします。

MVT テストの後に 1 つ以上の A/B テストをおこなうことで、目的の結果を得るための最良のコンテンツを判断できます。

## A/B テスト活動の種類 {#types}

手動の&#x200B;**[!UICONTROL A/B テスト]** アクティビティに加えて、[!DNL Target]には、**[!UICONTROL A/B テスト]** アクティビティの2つの追加タイプが用意されています：**[!UICONTROL 自動配分]**&#x200B;と&#x200B;**[!UICONTROL 自動ターゲット]**。

| アクティビティタイプ | 説明 |
| --- | --- |
| **[!UICONTROL 手動A/B テスト]** | 複数のエクスペリエンスを比較して、事前に指定したテスト期間内で最もコンバージョンが向上したエクスペリエンスを確認します。<P>この節では、**[!UICONTROL A/B テスト]** アクティビティを手動で設定する方法について説明しますが、**[!UICONTROL A/B テスト]** アクティビティのその他の種類の手順は同様です。 |
| **[!UICONTROL 自動配分]** | 2つ以上のエクスペリエンスの中から勝者を特定し、その勝者にトラフィックをリダイレクトして、テストの実行と学習に応じてコンバージョンを向上させます。<P>**[!UICONTROL 自動配分]** アクティビティを使用する利点について詳しくは、*の[自動配分](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate)を参照してください。A/B テストを実行する時間*&#x200B;と[自動配分の概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| ![&#x200B; プレミアムバッジ &#x200B;](/help/main/assets/premium.png) **[!UICONTROL 自動ターゲット]** | 高度なマシンラーニング（機械学習）を利用して、パフォーマンスに優れたマーケター定義のエクスペリエンスを複数特定し、コンテンツをパーソナライズしてコンバージョンを促進できます。 訪問者には、個々の顧客プロファイルや類似する訪問者の過去の行動にもとづいて、最もカスタマイズされた体験が提供されます。<P>詳しくは、[自動ターゲット &#x200B;](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を参照してください。 |

これらの&#x200B;**[!UICONTROL A/B テスト]** アクティビティのうち、お客様に適しているアクティビティについて詳しくは、インタラクティブな[Adobe Target アクティビティ ガイド PDF](/help/main/c-activities/target-activities-guide.md)を参照してください。

>[!NOTE]
>
>**[!UICONTROL A/B テスト]**、**[!UICONTROL 自動割り当て]**、**[!UICONTROL 自動ターゲット]** アクティビティ（および&#x200B;**[!UICONTROL エクスペリエンスのターゲット設定]** （XT） アクティビティ）内に推奨事項を含めることができます。 詳しくは、[オファーとしてのレコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md)をご覧ください。 この機能を使用するには、[Target Premium ライセンス](/help/main/c-intro/intro.md#premium)が必要です。
