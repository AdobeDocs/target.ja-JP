---
keywords: A/B の作成；A/B テスト；A/B アクティビティ；新しい a/b アクティビティ；a/b の作成
description: Adobeの Visual Experience Composer （VEC）を使用して、A [!DNL Target] B テスト アクティビティを  [!DNL Target] 対応ページに直接作成する方法を説明します。
title: A/B テストの作成方法
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 35%

---

# A/B テストの作成

[!UICONTROL Visual Experience Composer] で [!DNL Adobe Target] （VEC）を使用して、[!UICONTROL A/B Test] アクティビティを [!DNL Target] 対応ページに直接作成したり、[!DNL Target] 内のページの一部を変更したりします。

>[!NOTE]
>
>[!UICONTROL A/B Test] では、（この記事で説明した）手動（デフォルト）の [!DNL Target] アクティビティに加えて、[!UICONTROL A/B Test] と [!UICONTROL Auto-Allocate] の 2 種類の [!UICONTROL Auto-Target] アクティビティが追加で提供されています。
>
>[A/B テストの概要 ](/help/main/c-activities/t-test-ab/test-ab.md#types) の *A/B テスト アクティビティのタイプ* を参照してください。

手動 [!UICONTROL A/B Test] アクティビティを作成するには：

1. **[!UICONTROL Activities]** リストで、**[!UICONTROL Create Activity]**/**[!UICONTROL A/B Test]** をクリックします。

   ![アクティビティを作成ドロップダウンリスト](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、[!DNL Target] アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。例えば、[!UICONTROL Recommendations] は [Target Premium機能 ](/help/main/c-intro/intro.md#premium) です。
   >
   >様々なアクティビティタイプについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)および [Target アクティビティのガイド](/help/main/c-activities/target-activities-guide.md)を参照してください。

1. 必要に応じて、「A/B テストアクティビティを作成」ダイアログで「**[!UICONTROL Visual (Default)]**」を選択します。

   [!UICONTROL Form-Based Experience Composer] を使用する場合は、「[!UICONTROL Form]」を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VEC と [!UICONTROL Form-Based Experience Composer] に加えて、[!DNL Target] は、シングルページアプリケーション VEC を提供しています。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き） [Target Premium ユーザーの場合 ](/help/main/c-intro/intro.md#premium)、「**[!UICONTROL Choose Workspace]**」ドロップダウンリストから [ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) を選択します。

   上の図の [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) オプションは [Target Premium](/help/main/c-intro/intro.md) 機能であり、組織が [!UICONTROL Target Standard] ライセンスを保有している場合は表示されない可能性があります。

1. **[!UICONTROL Enter Activity URL]** ボックスで [ アクティビティ URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) を指定し、「**[!UICONTROL Create]**」をクリックします。

   アカウントに[デフォルトの URL が設定されている](/help/main/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。必要に応じて、デフォルトの URL から別の URL に変更できます。

   [!UICONTROL Visual Experience Composer] が開き、URL で指定したページが表示されます。

1. VEC の上部にある「**[!UICONTROL Untitled Activity]**」をクリックし、表示されたスペースでアクティビティの名前を指定します。

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

1. 新しいエクスペリエンスを作成します（ページ上の要素の変更）。

   この [!UICONTROL Visual Experience Composer] では、新しいアクティビティを作成した後、左側に「エクスペリエンス A」と「エクスペリエンス B」という 2 つのタブが表示されます。エクスペリエンス A はコントロールエクスペリエンスです。 フォーカスは「エクスペリエンス B」タブにあり、必要に応じて変更できます。 エクスペリエンス B は、テストに追加できる代替エクスペリエンスです。 テストには複数のエクスペリエンスを追加できます。デフォルトのサイトエクスペリエンスをオプションとして使用しない場合は、エクスペリエンス A をアクティビティから削除できます。

   [!UICONTROL Visual Experience Composer] でのエクスペリエンスの追加および変更について詳しくは、[ エクスペリエンスの追加 ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00) を参照してください。 エクスペリエンス B を変更するには、ステップ 2 から始めます。

1. **[!UICONTROL Targeting]** の上部にある「[!UICONTROL Visual Experience Composer]」をクリックして、3 ステップのガイドによるワークフローの次のステップに進みます。

   フロー図が開きます。

   ![A/B テストのターゲット設定手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   フロー図を使用すると、アクティビティに対するオーディエンスの選択およびエクスペリエンスの設定を順に実行できます。

1. **[!UICONTROL Audience]** ボックスで、アクティビティの編集アイコン（縦並びの省略記号）をクリックし、「**[!UICONTROL Replace Audience]**」をクリックして [ オーディエンスを選択 ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) します。

   デフォルトでは、オーディエンスは [!UICONTROL All Visitors] に設定されています。

1. アクティビティに参加する資格のある訪問者の割合を選択します。

   ![オーディエンスの割合](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. トラフィックの配分を設定します。

   同じオーディエンスに対して複数のエクスペリエンスを表示することができます。選択したオーディエンスと、アクティビティに追加したエクスペリエンスを示す図が表示されます。

   目的のトラフィック配分方法を選択します。

   * **[!UICONTROL Manual (Default)]**：各エクスペリエンスを表示するエントリの割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。全エクスペリエンスの合計が 100％になるようにします。

   * **[!UICONTROL Auto-allocate to best experience]**：ほとんどのアクティビティのエントリは、パフォーマンスの高いエクスペリエンスに自動的に移動します。 一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。詳しくは、[[!UICONTROL Auto-Allocate] の概要 ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) を参照してください。

   * **[!UICONTROL Auto-target for personalized experiences]**:[!DNL Target] は、高度な機械学習を使用して、パフォーマンスの高い複数のマーケターが定義したエクスペリエンスを特定し、個々の顧客プロファイルと類似する訪問者の過去の行動に基づいて最適なエクスペリエンスを訪問者に提供することで、コンテンツをパーソナライズし、コンバージョンを促進します。 詳しくは、[ 自動ターゲットの概要 ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) を参照してください。

   また、「**[!UICONTROL Add]**」をクリックして、アクティビティに別のエクスペリエンスを追加することもできます。

1. オーディエンス、エクスペリエンスの選択、トラフィック配分の選択に満足したら、「**[!UICONTROL Next]**」をクリックして、3 つの手順から成るガイド付きワークフローの 3 番目のステップに進みます。

1. アクティビティの[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)を指定します。

1. **[!UICONTROL Save & Close]** または **[!UICONTROL Save]** をクリックします。

アクティビティを作成すると、「[!UICONTROL Overview]」タブにアクティビティのダイアグラムなど、アクティビティに関する情報が表示されます。

## トレーニングビデオ：A/B テストの作成（8:36） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、[!DNL Target] で 3 ステップのガイドによるワークフローを使用して A/B テストを作成する方法を説明します。

* [!UICONTROL A/B Test] での [!DNL Adobe Target] アクティビティの作成
* 手動分割または自動トラフィック配分によるトラフィックの配分

>[!VIDEO](https://video.tv.adobe.com/v/29958?captions=jpn)
