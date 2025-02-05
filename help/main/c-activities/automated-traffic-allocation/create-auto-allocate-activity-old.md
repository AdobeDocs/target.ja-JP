---
keywords: 自動配分の作成；A/B テスト；自動配分アクティビティ；新しい a/b アクティビティ；自動配分；最適なエクスペリエンスへの自動配分；配分；自動配分
description: '[!UICONTROL Visual Experience Composer] （VEC） in [!DNL Adobe Target]  を使用して、[!UICONTROL Auto-Allocate] A/B テストアクティビティを作成する方法を説明します。'
title: '[!UICONTROL Auto-Allocate] アクティビティの作成方法'
feature: Auto-Allocate
exl-id: 30bc95e0-4f5e-4d1f-bad2-7b20b8f3c7d2
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 37%

---

# [!UICONTROL Auto-Allocate] アクティビティの作成

[!DNL Adobe Target] の [!UICONTROL Visual Experience Composer] （VEC）を使用して、[!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] アクティビティを [!DNL Target] 対応ページに直接作成したり、[!DNL Target] 内のページの一部を変更したりします。

[!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] アクティビティ（この記事で説明）に加えて、[!DNL Target] では、さらに 2 種類の [!UICONTROL A/B Test] アクティビティ（[!UICONTROL Manual (Default)] と [!UICONTROL Auto-Target]）が提供されます。 [A/B テストの概要 ](/help/main/c-activities/t-test-ab/test-ab.md#types) の *A/B テスト アクティビティのタイプ* を参照してください。

[!UICONTROL Auto-Allocate] アクティビティを作成するには：

1. **[!UICONTROL Activities]** リストで、**[!UICONTROL Create Activity]**/**[!UICONTROL A/B Test]** をクリックします。

   ![アクティビティを作成ドロップダウンリスト](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   利用可能なアクティビティタイプは、[!DNL Target] アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。例えば、[!UICONTROL Recommendations] は [Target Premium機能 ](/help/main/c-intro/intro.md#premium) です。 様々なアクティビティタイプについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md)および [Target アクティビティのガイド](/help/main/c-activities/target-activities-guide.md)を参照してください。

1. **[!UICONTROL Create A/B Test Activity]** ダイアログボックスで、必要に応じて「**[!UICONTROL Visual]**」を選択します。

   [!UICONTROL Form-Based Experience Composer] を使用する場合は、「[!UICONTROL Form]」を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VEC と [!UICONTROL Form-Based Experience Composer] に加えて、[!DNL Target] は、シングルページアプリケーション VEC を提供しています。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き）[Target Premium](/help/main/c-intro/intro.md#premium) のお客様の場合、[ワークスペース](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)を選択します。

1. [ アクティビティ URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) を指定し、「**[!UICONTROL Create]**」をクリックします。

   アカウントにデフォルトの URL が設定されている場合は、その URL がデフォルトで表示されます。必要に応じて、デフォルトの URL から別の URL に変更できます。

   [!UICONTROL Visual Experience Composer] が開き、URL で指定したページが表示されます。

   ![VEC](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. 用意されている領域に、アクティビティの名前を入力します。

   ![「名前」フィールド](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   アクティビティ名は、次の文字で始めることはできません：

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

1. ページ上の要素を変更して、エクスペリエンスを作成します。

   この [!UICONTROL Visual Experience Composer] では、新しいアクティビティを作成した後、左側に「エクスペリエンス A」と「エクスペリエンス B」という 2 つのタブが表示されます。エクスペリエンス A はコントロールエクスペリエンスです。 フォーカスは「エクスペリエンス B」タブにあり、必要に応じて変更できます。 エクスペリエンス B は代替エクスペリエンスで、テストに追加することができます。テストには複数のエクスペリエンスを追加できます。デフォルトのサイトエクスペリエンスをオプションとして使用しない場合は、エクスペリエンス A をアクティビティから削除できます。

   [!UICONTROL Visual Experience Composer] でのエクスペリエンスの追加および変更について詳しくは、[ エクスペリエンスの追加 ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md) を参照してください。 エクスペリエンス B を変更するには、ステップ 2 から始めます。

1. [!UICONTROL Visual Experience Composer] の上部にある「**[!UICONTROL Targeting]**」をクリックして、3 ステップのガイドによるワークフローの次のステップに進みます。

   フロー図が開きます。

   ![A/B テストのターゲット設定手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   フロー図を使用すると、アクティビティに対するオーディエンスの選択およびエクスペリエンスの設定を順に実行できます。

1. [!UICONTROL Audience] ボックスで、アクティビティの編集アイコン（縦並びの省略記号）をクリックし、「**[!UICONTROL Replace Audience]**」をクリックして [ オーディエンスを選択 ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) します。

   デフォルトでは、オーディエンスは [!UICONTROL All Visitors] に設定されています。

1. アクティビティに参加する資格のある訪問者の割合を選択します。

   ![オーディエンスの割合](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. トラフィック配分方法を設定します。

   同じオーディエンスに対して複数のエクスペリエンスを表示することができます。選択したオーディエンスと、アクティビティに追加したエクスペリエンスを示す図が表示されます。

   目的のトラフィック配分方法を選択します。 [!UICONTROL Auto-Allocate] アクティビティを作成するには、「**[!UICONTROL Auto-Allocate to best experience]**」を選択します。

   トラフィック配分には、次の 3 つのタイプがあります。

   * **[!UICONTROL Manual (Default)]**：各エクスペリエンスを表示するエントリの割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。全エクスペリエンスの合計が 100％になるようにします。詳しくは、[A/B テストの作成 ](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) を参照してください。

   * **[!UICONTROL Auto-allocate to best experience]**：ほとんどのアクティビティのエントリは、パフォーマンスの高いエクスペリエンスに自動的に移動します。 一部の訪問者は、エクスペリエンスの探索を維持し、パフォーマンスのトレンドの変化を認識するために、すべてのエクスペリエンスに割り当てられます。

   * **[!UICONTROL Auto-target for personalized experiences]**:[!DNL Target] は、高度な機械学習を使用して、パフォーマンスの高い複数のマーケターが定義したエクスペリエンスを特定し、個々の顧客プロファイルと類似する訪問者の過去の行動に基づいて最適なエクスペリエンスを訪問者に提供することで、コンテンツをパーソナライズし、コンバージョンを促進します。 詳しくは、「[ 自動ターゲット ](/help/main/c-activities/auto-target/auto-target-to-optimize.md)」を参照してください。

   また、「**[!UICONTROL Add]**」をクリックして、アクティビティに別のエクスペリエンスを追加することもできます。

1. オーディエンス、エクスペリエンスの選択、トラフィック配分の選択に満足したら、「**[!UICONTROL Next]**」をクリックして、3 つの手順から成るガイド付きワークフローの 3 番目のステップに進みます。

1. アクティビティの[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)を指定します。

   >[!NOTE]
   >
   >このアクティビティで [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用する場合は、[A4T による自動配分と自動ターゲットアクティビティのサポート ](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) を参照してください。

1. **[!UICONTROL Save & Close]** または **[!UICONTROL Save]** をクリックします。

アクティビティを作成すると、「[!UICONTROL Overview]」タブにアクティビティのダイアグラムなど、アクティビティに関する情報が表示されます。

## トレーニングビデオ：A/Bテストの作成（8:36）

このビデオでは、[!DNL Target] で 3 ステップのガイドによるワークフローを使用して A/B テストを作成する方法を説明します。

* [!DNL Adobe Target] での [!UICONTROL A/B Test] アクティビティの作成
* 手動分割または自動トラフィック配分によるトラフィックの配分

>[!VIDEO](https://video.tv.adobe.com/v/17391)
