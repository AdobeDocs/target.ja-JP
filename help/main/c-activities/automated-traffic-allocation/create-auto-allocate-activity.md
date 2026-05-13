---
keywords: 自動割り当てを作成；A/B テスト；自動割り当てアクティビティ；新しいa/b アクティビティ；自動割り当て；最適なエクスペリエンスに自動割り当て；割り当て；自動割り当て
description: '[!UICONTROL Visual Experience Composer] （VEC）を使用して[!UICONTROL Auto-Allocate]個のA/B テスト アクティビティを作成する方法を説明します。'
title: '[!UICONTROL Auto-Allocate] アクティビティを作成するにはどうすればよいですか？'
feature: Auto-Allocate
exl-id: 30bc95e0-4f5e-4d1f-bad2-7b20b8f3c7d2
TQID: https://experienceleague.adobe.com/dInypDH72qyoj5UygbEt-BWpq1gZkbxJiSXSheNPO54
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: eb30f47f-d87a-400f-8f78-63ce7979ff56id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 918
ht-degree: 15%

---

# [!UICONTROL Auto-Allocate] アクティビティの作成

[!DNL Adobe Target]の[!UICONTROL Visual Experience Composer] （VEC）を使用して、[!DNL Target]対応ページで[!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] アクティビティを直接作成し、[!DNL Target]内のページの一部を変更します。

[!DNL Target]には、[!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] アクティビティに加えて、[!UICONTROL Manual (Default)]と[!UICONTROL Auto-Target]の2種類の[!UICONTROL A/B Test] アクティビティが追加されています。 *A/B テストの概要*&#x200B;の[A/B テスト アクティビティの種類](/help/main/c-activities/t-test-ab/test-ab.md#types)を参照してください。

[!UICONTROL Auto-Allocate] アクティビティを作成するには：

1. **[!UICONTROL Activities]** リストから、**[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**&#x200B;をクリックします。

1. [!UICONTROL Create A/B Test Activity] ダイアログから、必要に応じて&#x200B;**[!UICONTROL Visual]**&#x200B;を選択します。

   [!UICONTROL Form-Based Experience Composer]を使用する場合は、[!UICONTROL Form]を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VECおよび[!UICONTROL Form-Based Experience Composer]に加えて、[!DNL Target]は[!UICONTROL Single Page Application] VECを提供しています。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >VECに関するトラブルシューティング情報については、[Visual Experience Composerのトラブルシューティング ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き）お客様が[Target Premiumのお客様](/help/main/c-intro/intro.md#premium)の場合、**[!UICONTROL Choose Workspace]** ドロップダウンリストから[ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)を選択します。

   [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) オプションは[Target Premium](/help/main/c-intro/intro.md)機能であり、組織が[!UICONTROL Target Standard] ライセンスを持っている場合は表示されない可能性があります。

1. **[!UICONTROL Enter Activity URL]** ボックスで、[ アクティビティ URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)を指定します。

   アカウントに[デフォルトの URL が設定されている](/help/main/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。 必要に応じて、デフォルトから別のURLに変更できます。

1. **[!UICONTROL Create]** をクリックします。

   [!UICONTROL Visual Experience Composer]が開き、URLで指定されたページが表示されます。

1. アクティビティに名前を付けるには、「[!UICONTROL Untitled Activity]」の横にある&#x200B;**[!UICONTROL Edit]** アイコン（![編集アイコン ](/help/main/assets/icons/Edit.svg)）をクリックし、アクティビティのわかりやすい名前を指定して、**[!UICONTROL Save]**&#x200B;をクリックします。

   アクティビティ名の先頭に次の文字を使用することはできません：

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

   アクティビティ名に次の文字シーケンスを含めることはできません。

   | 文字シーケンス | 説明 |
   |--- |--- |
   | ;= | セミコロン、次に等しい |
   | ;+ | セミコロン、プラス |
   | ;- | セミコロン、マイナス |
   | ;@ | セミコロン、記号 |
   | ,= | コンマ、次に等しい |
   | ,+ | コンマ、プラス |
   | ,- | コンマ、マイナス |
   | ,@ | コンマ、記号 |
   | `[`&quot; | 角括弧を開く、二重引用符 |
   | &quot;`]` | 二重引用符、角括弧を閉じる |

1. ページ上の要素を変更して、新しいエクスペリエンスを作成します。

   [!UICONTROL Visual Experience Composer]には、新しいアクティビティを作成した後、左側に2つのタブ（[!UICONTROL Experience A]と[!UICONTROL Experience B]）が表示されます。 [!UICONTROL Experience A]はコントロール エクスペリエンスです。 対象は[!UICONTROL Experience B] タブです。必要に応じて変更できます。 [!UICONTROL Experience B]は、テストに追加できる代替エクスペリエンスです。 [!UICONTROL Experiences] ペインの上部にある[!UICONTROL Add] アイコン （![追加アイコン ](/help/main/assets/icons/Add.svg)）をクリックすると、テストに複数のエクスペリエンスを追加できます。 デフォルトのサイトエクスペリエンスをオプションとして使用しない場合は、エクスペリエンス A をアクティビティから削除できます。

   [!UICONTROL Visual Experience Composer]でのエクスペリエンスの追加と変更について詳しくは、[ エクスペリエンスの追加](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)を参照してください。 [!UICONTROL Experience B]を変更するには、手順2から始めます。

1. [!UICONTROL Visual Experience Composer]の上部にある「**[!UICONTROL Targeting]**」をクリックして、3段階のガイド付きワークフローの次のステップに移動します。

   フロー図が開きます。

   ![A/B テストのターゲティング手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   フロー図では、オーディエンスとそのトラフィック率の割り当て、トラフィック配分方法の選択、アクティビティの各エクスペリエンスのトラフィック配分の指定の手順を順を追って説明します。

1. （条件付き）アクティビティの別のオーディエンスを選択するには、**[!UICONTROL All Visitors]** コントロールをクリックします。

   [!UICONTROL All Visitors] オーディエンスがデフォルトとして設定されています。 別のオーディエンスを選択すると、その名前が一番左のコントロールに表示されます。

   右側のフレームが表示され、オーディエンスを追加または削除し、アクティビティの訪問者パーセンテージを割り当てることができます。

   1. オーディエンスを変更するには、右側のフレームの&#x200B;**[!UICONTROL Replace]アイコン** （![置換アイコン ](/help/main/assets/icons/Retweet.svg)）をクリックします。
   1. [!UICONTROL Add Audience] ダイアログボックスで、[目的のオーディエンス ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)を選択し、**[!UICONTROL Assign Audience]**&#x200B;をクリックします。

      「**オーディエンスを結合**」をクリックして、[複数のオーディエンスを結合するオーディエンスを作成できます](/help/main/c-target/combining-multiple-audiences.md)。

      まだ[!UICONTROL Audience Library]にない新しいオーディエンスを作成する必要がある場合は、**オーディエンスの作成**&#x200B;をクリックします。 [create-audience ワークフロー](/help/main/c-target/c-audiences/audiences.md)中に、次のオプションから選択できます。

      * **[!UICONTROL Audience Library]**: [!UICONTROL Audience Library]に保存されたオンデマンドオーディエンスを作成し、他のアクティビティで再利用できます
      * **このアクティビティのみ**：現在のアクティビティでのみ使用できる[!UICONTROL Audience Library]に保存されていない[ アクティビティ固有のオーディエンス ](/help/main/c-target/creating-activity-only-audience.md)を作成します

   1. 右側のフレームで「**[!UICONTROL Visitor Percentage]**」をクリックし、アクティビティに参加する適格な訪問者の割合を選択します。

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. **[!UICONTROL Traffic Allocation]** コントロールをクリックし、右側のペインで目的のトラフィック割り当て方法を選択します。 このシナリオでは、**[!UICONTROL Auto-Allocate to best experience]**&#x200B;をクリックします。

   ![ トラフィック配分メソッドの設定](/help/main/c-activities/automated-traffic-allocation/assets/auto-allocate-to-best-exp.png)

   次のトラフィック割り当て方法を使用できます。

   * **[!UICONTROL Manual (Default)]**：各エクスペリエンスを表示する参加者の割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。 全エクスペリエンスの合計が 100％になるようにします。

   * **[!UICONTROL Auto-Allocate to best experience]**：ほとんどのアクティビティ参加者は、パフォーマンスの高いエクスペリエンスに自動的に送信されます。 一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。 詳しくは、[[!UICONTROL Auto-Allocate]の概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)を参照してください。

   * **[!UICONTROL Auto-Target for personalized experiences]**: [!DNL Target]は、高度な機械学習を使用して、コンテンツをパーソナライズし、コンバージョンを促進します。複数のパフォーマンスの高い、マーケターが定義したエクスペリエンスを特定し、個々の顧客プロファイルと類似する訪問者の過去の行動に基づいて、訪問者に最もカスタマイズされたエクスペリエンスを提供します。 詳しくは、[自動ターゲットの概要](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を参照してください。

1. 右側のペインで「**[!UICONTROL Experiences]**」をクリックし、各エクスペリエンスに対して目的のトラフィック割り当てを指定します。

1. オーディエンス、エクスペリエンスの選択肢、トラフィックの割り当ての選択肢に満足したら、**[!UICONTROL Next]**&#x200B;をクリックして、3段階のガイド付きワークフローの3番目のステップに移動します。

1. アクティビティの[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)を指定します。

   >[!NOTE]
   >
   >このアクティビティで[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用する場合は、[A4Tの自動配分および自動ターゲットアクティビティのサポート ](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)に関する重要な情報を参照してください。

1. **[!UICONTROL Save & Close]**&#x200B;または&#x200B;**[!UICONTROL Save]**&#x200B;をクリックします。

アクティビティを作成すると、「[!UICONTROL Overview]」タブに、アクティビティに関する情報（アクティビティの図を含む）が表示されます。
