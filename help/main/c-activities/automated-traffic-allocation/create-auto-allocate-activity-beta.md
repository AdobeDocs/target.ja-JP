---
keywords: 自動配分の作成；A/B テスト；自動配分アクティビティ；新しい a/b アクティビティ；自動配分；最適なエクスペリエンスへの自動配分；配分；自動配分
description: '[!UICONTROL Visual Experience Composer] （VEC）を使用して [!UICONTROL Auto-Allocate] A/B テストアクティビティを作成する方法を説明します。'
title: '[!UICONTROL Auto-Allocate] アクティビティの作成方法'
feature: Auto-Allocate
hide: true
hidefromtoc: true
exl-id: 1bfa311a-cbd9-48be-9b28-840be55b1118
source-git-commit: 8bfad2fe6804c241deec6c8ea70e2f8e7d79d8c6
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 15%

---

# [!UICONTROL Auto-Allocate] アクティビティの作成

[!DNL Adobe Target] の [!UICONTROL Visual Experience Composer] （VEC）を使用して、[!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] アクティビティを [!DNL Target] 対応ページに直接作成したり、[!DNL Target] 内のページの一部を変更したりします。

[!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] アクティビティ（この記事で説明）に加えて、[!DNL Target] では、さらに 2 種類の [!UICONTROL A/B Test] アクティビティ（[!UICONTROL Manual (Default)] と [!UICONTROL Auto-Target]）が提供されます。 [A/B テストの概要 ](/help/main/c-activities/t-test-ab/test-ab.md#types) の *A/B テスト アクティビティのタイプ* を参照してください。

[!UICONTROL Auto-Allocate] アクティビティを作成するには：

1. **[!UICONTROL Activities]** リストで、**[!UICONTROL Create Activity]**/**[!UICONTROL A/B Test]** をクリックします。

1. 必要に応じて、[!UICONTROL Create A/B Test Activity] ダイアログで「**[!UICONTROL Visual]**」を選択します。

   [!UICONTROL Form-Based Experience Composer] を使用する場合は、「[!UICONTROL Form]」を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VEC と [!UICONTROL Form-Based Experience Composer] に加えて、[!DNL Target] は [!UICONTROL Single Page Application] VEC を提供します。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md) を参照してください。

1. （条件付き） [Target Premium ユーザーの場合 ](/help/main/c-intro/intro.md#premium)、「**[!UICONTROL Choose Workspace]**」ドロップダウンリストから [ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) を選択します。

   「[[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)」オプションは [Target Premium](/help/main/c-intro/intro.md) 機能であり、組織が [!UICONTROL Target Standard] ライセンスを保有している場合は表示されない可能性があります。

1. 「**[!UICONTROL Enter Activity URL]**」ボックスに [ アクティビティ URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) を指定します。

   アカウントに[デフォルトの URL が設定されている](/help/main/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。必要に応じて、デフォルトの URL から別の URL に変更できます。

1. **[!UICONTROL Create]** をクリックします。

   [!UICONTROL Visual Experience Composer] が開き、URL で指定したページが表示されます。

1. **[!UICONTROL Rename]** アイコン（名前を変更アイコン ![ をクリックし ](/help/main/assets/icons/MoreSmallListVert.svg) 「名前を **[!UICONTROL Rename]** 更」をクリックしてアクティビティの名前を指定し、「名前を変更」をクリックし **[!UICONTROL Save]** す。

   アクティビティ名は、次の文字で始めることはできません：

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

   アクティビティ名には、次の文字シーケンスを含めることはできません：

   | 文字シーケンス | 説明 |
   |--- |--- |
   | ;= | セミコロン、次と等しい |
   | ;+ | セミコロン、プラス |
   | ;- | セミコロン マイナス |
   | ;@ | セミコロン、アットサイン |
   | ,= | コンマ、次と等しい |
   | ,+ | コンマ、プラス |
   | ,- | コンマ，マイナス |
   | ,@ | コンマ、アットサイン |
   | `[`&quot; | 左角括弧、二重引用符 |
   | &quot;`]` | 二重引用符、閉じ角括弧 |

1. ページ上の要素を変更して、新しいエクスペリエンスを作成します。

   [!UICONTROL Visual Experience Composer] では、新しいアクティビティを作成した後、左側に「[!UICONTROL Experience A]」および「[!UICONTROL Experience B]」の 2 つのタブが表示されます。 コントロールエクスペリエンスは [!UICONTROL Experience A] のとおりです。 フォーカスは「[!UICONTROL Experience B]」タブにあり、必要に応じて変更できます。 テストに追加できる代替エクスペリエンスは [!UICONTROL Experience B] のとおりです。 テストウィンドウの上部にあるエクスペリ [!UICONTROL Add] ンスアイコン ![ 追加アイコン ](/help/main/assets/icons/Add.svg)）をクリックして、複数のエクスペリ [!UICONTROL Experiences] ンスをテストに追加できます。 デフォルトのサイトエクスペリエンスをオプションとして使用しない場合は、エクスペリエンス A をアクティビティから削除できます。

   [!UICONTROL Visual Experience Composer] でのエクスペリエンスの追加および変更について詳しくは、[ エクスペリエンスの追加 ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00) を参照してください。 [!UICONTROL Experience B] を変更するには、手順 2 から開始します。

1. [!UICONTROL Visual Experience Composer] の上部にある「**[!UICONTROL Targeting]**」をクリックして、3 ステップのガイドによるワークフローの次のステップに進みます。

   フロー図が開きます。

   ![A/B テストのターゲット設定手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   フロー図は、オーディエンスとそのトラフィックの割合を割り当て、トラフィックの割り当て方法を選択し、アクティビティ内の各エクスペリエンスのトラフィックの割り当てを指定する手順を示しています。

1. （条件付き）アクティビティに別のオーディエンスを選択するには、**[!UICONTROL All Visitors]** のコントロールをクリックします。

   [!UICONTROL All Visitors] オーディエンスがデフォルトとして設定されます。 別のオーディエンスを選択すると、その名前が一番左のコントロールに表示されます。

   右側のフレームが表示されます。ここでは、オーディエンスを追加または削除したり、アクティビティの訪問者の割合を割り当てたりできます。

   1. オーディエンスを変更するには **右側のフレームで**[!UICONTROL Replace] アイコン（![ 置換アイコン ](/help/main/assets/icons/Retweet.svg)）をクリックします。
   1. [!UICONTROL Add Audience] のダイアログボックスで [ 目的のオーディエンスを選択 ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) し、「**[!UICONTROL Assign Audience]**」をクリックします。

      **オーディエンスを組み合わせる** をクリックして、[ 複数のオーディエンスを組み合わせたオーディエンスを作成 ](/help/main/c-target/combining-multiple-audiences.md) できます。

      [!UICONTROL Audience Library] ージにない新しいオーディエンスを作成する必要がある場合は、「**オーディエンスを作成**」をクリックします。 [ オーディエンスを作成ワークフロー ](/help/main/c-target/c-audiences/audiences.md) 中に、次のいずれかのオプションを選択できます。

      * **[!UICONTROL Audience Library]**:[!UICONTROL Audience Library] ージに保存され、他のアクティビティで再利用できるオンデマンドオーディエンスを作成します
      * **このアクティビティのみ**:[!UICONTROL Audience Library] に保存されず、現在のアクティビティでのみ使用できる [ アクティビティ固有のオーディエンス ](/help/main/c-target/creating-activity-only-audience.md) を作成します

   1. 右側のフレームで「**[!UICONTROL Visitor Percentage]**」をクリックし、アクティビティにエントリする選定訪問者の割合を選択します。

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. **[!UICONTROL Traffic Allocation]** コントロールをクリックし、右側のパネルで目的のトラフィック配分方法を選択します。 このシナリオでは、「**[!UICONTROL Auto-Allocate to best experience]**」をクリックします。

   ![ トラフィック配分方法の設定 ](/help/main/c-activities/automated-traffic-allocation/assets/auto-allocate-to-best-exp.png)

   次のトラフィック割り当て方法を使用できます。

   * **[!UICONTROL Manual (Default)]**：各エクスペリエンスを表示するエントリの割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。全エクスペリエンスの合計が 100％になるようにします。

   * **[!UICONTROL Auto-Allocate to best experience]**：ほとんどのアクティビティのエントリは、パフォーマンスの高いエクスペリエンスに自動的に移動します。 一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。詳しくは、[[!UICONTROL Auto-Allocate] の概要 ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) を参照してください。

   * **[!UICONTROL Auto-Target for personalized experiences]**:[!DNL Target] は、高度な機械学習を使用して、パフォーマンスの高い複数のマーケターが定義したエクスペリエンスを特定し、個々の顧客プロファイルと類似する訪問者の過去の行動に基づいて最適なエクスペリエンスを訪問者に提供することで、コンテンツをパーソナライズし、コンバージョンを促進します。 詳しくは、[ 自動ターゲットの概要 ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) を参照してください。

1. 右側のパネルで「**[!UICONTROL Experiences]**」をクリックし、各エクスペリエンスに必要なトラフィック配分を指定します。

1. オーディエンス、エクスペリエンスの選択、トラフィック配分の選択に満足したら、「**[!UICONTROL Next]**」をクリックして、3 つの手順から成るガイド付きワークフローの 3 番目のステップに進みます。

1. アクティビティの[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)を指定します。

   >[!NOTE]
   >
   >このアクティビティで [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用する場合は、[A4T による自動配分と自動ターゲットアクティビティのサポート ](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) を参照してください。

1. **[!UICONTROL Save & Close]** または **[!UICONTROL Save]** をクリックします。

アクティビティを作成すると、「[!UICONTROL Overview]」タブにアクティビティのダイアグラムなど、アクティビティに関する情報が表示されます。
