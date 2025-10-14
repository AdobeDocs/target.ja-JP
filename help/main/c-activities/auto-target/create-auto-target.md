---
keywords: 自動ターゲットの作成；A/B テスト；自動ターゲットアクティビティ；新しい A/B アクティビティ；自動ターゲット；パーソナライズされたエクスペリエンスの自動ターゲット；パーソナライズされた；最適化
description: '[!UICONTROL Visual Experience Composer] （VEC）を使用して [!UICONTROL Auto-Target] A/B テスト アクティビティを作成する方法を説明します。'
title: '[!UICONTROL Auto-Target] アクティビティの作成方法'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 20%

---

# [!UICONTROL Auto-Target] アクティビティの作成

[!UICONTROL Visual Experience Composer] の [!DNL Adobe Target] （VEC）を使用して、[!UICONTROL Auto-Target] [!UICONTROL A/B Test] アクティビティを [!DNL Target] 対応ページに直接作成したり、[!DNL Target] 内のページの一部を変更したりします。

>[!NOTE]
>
>[!UICONTROL Auto-Target] は、[!DNL Target Premium] ソリューションの一部として利用できます。 この機能は、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では使用できません。このライセンスで提供される高度な機能について詳しくは、[Target Premium](/help/main/c-intro/intro.md) を参照してください。

[!UICONTROL Auto-Target] アクティビティを作成するには：

1. **[!UICONTROL Activities]** リストで、**[!UICONTROL Create Activity]**/**[!UICONTROL A/B Test]** をクリックします。

1. 必要に応じて、[!UICONTROL Create A/B Test Activity] ダイアログで「**[!UICONTROL Visual]**」を選択します。

   [!UICONTROL Form-Based Experience Composer] を使用する場合は、「[!UICONTROL Form]」を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VEC と [!UICONTROL Form-Based Experience Composer] に加えて、[!DNL Target] は [!UICONTROL Single Page Application] VEC を提供します。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md) を参照してください。

1. （条件付き） [Target Premium ユーザーの場合 &#x200B;](/help/main/c-intro/intro.md#premium)、「**[!UICONTROL Choose Workspace]**」ドロップダウンリストから [&#x200B; ワークスペース &#x200B;](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) を選択します。

   「[[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)」オプションは [Target Premium](/help/main/c-intro/intro.md) 機能であり、組織が [!UICONTROL Target Standard] ライセンスを保有している場合は表示されない可能性があります。

1. 「**[!UICONTROL Enter Activity URL]**」ボックスに [&#x200B; アクティビティ URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) を指定します。

   アカウントに[デフォルトの URL が設定されている](/help/main/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。必要に応じて、デフォルトの URL から別の URL に変更できます。

1. **[!UICONTROL Create]** をクリックします。

   [!UICONTROL Visual Experience Composer] が開き、URL で指定したページが表示されます。

1. **[!UICONTROL Rename]** アイコン（名前を変更アイコン ![&#x200B; をクリックし &#x200B;](/help/main/assets/icons/MoreSmallListVert.svg) 「名前を **[!UICONTROL Rename]** 更」をクリックしてアクティビティの名前を指定し、「名前を変更」をクリックし **[!UICONTROL Save]** す。

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

   [!UICONTROL Visual Experience Composer] では、新しいアクティビティを作成した後、左側に「[!UICONTROL Experience A]」および「[!UICONTROL Experience B]」の 2 つのタブが表示されます。 コントロールエクスペリエンスは [!UICONTROL Experience A] のとおりです。 フォーカスは「[!UICONTROL Experience B]」タブにあり、必要に応じて変更できます。 テストに追加できる代替エクスペリエンスは [!UICONTROL Experience B] のとおりです。 テストウィンドウの上部にあるエクスペリ [!UICONTROL Add] ンスアイコン ![&#x200B; 追加アイコン &#x200B;](/help/main/assets/icons/Add.svg)）をクリックして、複数のエクスペリ [!UICONTROL Experiences] ンスをテストに追加できます。 デフォルトのサイトエクスペリエンスをオプションとして使用しない場合は、エクスペリエンス A をアクティビティから削除できます。

   [!UICONTROL Visual Experience Composer] でのエクスペリエンスの追加および変更について詳しくは、[&#x200B; エクスペリエンスの追加 &#x200B;](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00) を参照してください。 エクスペリエンス B を変更するには、ステップ 2 から始めます。

1. **[!UICONTROL Targeting]** の上部にある「[!UICONTROL Visual Experience Composer]」をクリックして、3 ステップのガイドによるワークフローの次のステップに進みます。

   フロー図が開きます。

   ![A/B テストのターゲット設定手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   フロー図は、オーディエンスとそのトラフィックの割合を割り当て、トラフィックの割り当て方法を選択し、アクティビティ内の各エクスペリエンスのトラフィックの割り当てを指定する手順を示しています。

1. （条件付き）アクティビティに別のオーディエンスを選択するには、**[!UICONTROL All Visitors]** のコントロールをクリックします。

   [!UICONTROL All Visitors] オーディエンスがデフォルトとして設定されます。 別のオーディエンスを選択すると、その名前が一番左のコントロールに表示されます。

   右側のフレームが表示されます。ここでは、オーディエンスを追加または削除したり、アクティビティの訪問者の割合を割り当てたりできます。

   1. オーディエンスを変更するには **[!UICONTROL Replace]右側のフレームで** アイコン（![&#x200B; 置換アイコン &#x200B;](/help/main/assets/icons/Retweet.svg)）をクリックします。
   1. [!UICONTROL Add Audience] のダイアログボックスで [&#x200B; 目的のオーディエンスを選択 &#x200B;](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) し、「**[!UICONTROL Assign Audience]**」をクリックします。

      **オーディエンスを組み合わせる** をクリックして、[&#x200B; 複数のオーディエンスを組み合わせたオーディエンスを作成 &#x200B;](/help/main/c-target/combining-multiple-audiences.md) できます。

      [!UICONTROL Audience Library] ージにない新しいオーディエンスを作成する必要がある場合は、「**オーディエンスを作成**」をクリックします。 [&#x200B; オーディエンスを作成ワークフロー &#x200B;](/help/main/c-target/c-audiences/audiences.md) 中に、次のいずれかのオプションを選択できます。

      * **[!UICONTROL Audience Library]**:[!UICONTROL Audience Library] ージに保存され、他のアクティビティで再利用できるオンデマンドオーディエンスを作成します
      * **[!UICONTROL This activity only]**:[&#x200B; に保存されず、現在のアクティビティでのみ使用できる &#x200B;](/help/main/c-target/creating-activity-only-audience.md) アクティビティ固有のオーディエンス [!UICONTROL Audience Library] を作成します

   1. 右側のフレームで「**[!UICONTROL Visitor Percentage]**」をクリックし、アクティビティにエントリする選定訪問者の割合を選択します。

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. **[!UICONTROL Traffic Allocation]** コントロールをクリックし、右側のパネルで目的のトラフィック配分方法を選択します。 このシナリオでは、「**[!UICONTROL Auto-Taget for personalized experiences]**」をクリックします。

   ![&#x200B; トラフィック配分方法の設定 &#x200B;](/help/main/c-activities/assets/auto-target.png)

   次のトラフィック割り当て方法を使用できます。

   * **[!UICONTROL Manual (Default)]**：各エクスペリエンスを表示するエントリの割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。全エクスペリエンスの合計が 100％になるようにします。

   * **[!UICONTROL Auto-Allocate to best experience]**：ほとんどのアクティビティのエントリは、パフォーマンスの高いエクスペリエンスに自動的に移動します。 一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。詳しくは、[[!UICONTROL Auto-Allocate] の概要 &#x200B;](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) を参照してください。

   * **[!UICONTROL Auto-Target for personalized experiences]**:[!DNL Target] は、高度な機械学習を使用して、パフォーマンスの高い複数のマーケターが定義したエクスペリエンスを特定し、個々の顧客プロファイルと類似する訪問者の過去の行動に基づいて最適なエクスペリエンスを訪問者に提供することで、コンテンツをパーソナライズし、コンバージョンを促進します。 詳しくは、[&#x200B; 自動ターゲットの概要 &#x200B;](/help/main/c-activities/auto-target/auto-target-to-optimize.md) を参照してください。

1. 右側のパネルで「**[!UICONTROL Experiences]**」をクリックし、各エクスペリエンスに必要なトラフィック配分を指定します。

1. オーディエンス、エクスペリエンスの選択、トラフィック配分の選択に満足したら、「**[!UICONTROL Next]**」をクリックして、3 つの手順から成るガイド付きワークフローの 3 番目のステップに進みます。

1. アクティビティの[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)を指定します。

   >[!NOTE]
   >
   >このアクティビティで [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用する場合は、[A4T による自動配分と自動ターゲットアクティビティのサポート &#x200B;](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) を参照してください。

1. **[!UICONTROL Save & Close]** または **[!UICONTROL Save]** をクリックします。

アクティビティを作成すると、「[!UICONTROL Overview]」タブにアクティビティのダイアグラムなど、アクティビティに関する情報が表示されます。
