---
keywords: A/B テストの作成、A/B アクティビティの作成、新しいA/B アクティビティ、A/b テストの作成
description: Adobe [!DNL Target] のVisual Experience Composer （VEC）を使用して、A/B テスト アクティビティをa [!DNL Target]対応ページで直接作成する方法について説明します。
title: A/B テストの作成方法？
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 36%

---

# A/B テストの作成

[!DNL Adobe Target]の[!UICONTROL Visual Experience Composer] （VEC）を使用して、[!DNL Target]対応ページで[!UICONTROL A/B テスト ] アクティビティを直接作成し、[!DNL Target]内のページの一部を変更します。

>[!NOTE]
>
>手動（デフォルト）の[!UICONTROL A/B テスト ] アクティビティ（この記事で説明）に加えて、[!DNL Target]には、[!UICONTROL A/B テスト ] アクティビティの2つの追加タイプが用意されています（[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット ]）。
>
>*A/B テストの概要*&#x200B;の[A/B テスト アクティビティの種類](/help/main/c-activities/t-test-ab/test-ab.md#types)を参照してください。

手動の[!UICONTROL A/B テスト ] アクティビティを作成するには：

1. **[!UICONTROL アクティビティ]** リストから、**[!UICONTROL アクティビティの作成]** > **[!UICONTROL A/B テスト]**&#x200B;をクリックします。

   ![アクティビティを作成ドロップダウンリスト](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、[!DNL Target] アカウントによって異なります。 一部のアクティビティタイプがリストに表示されない可能性があります。 例えば、[!UICONTROL Recommendations]は[Target Premium機能](/help/main/c-intro/intro.md#premium)です。
   >
   >様々なアクティビティタイプについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)および [Target アクティビティのガイド](/help/main/c-activities/target-activities-guide.md)を参照してください。

1. A/B テスト アクティビティを作成ダイアログから、必要に応じて&#x200B;**[!UICONTROL ビジュアル（デフォルト）]**&#x200B;を選択します。

   [!UICONTROL  フォームベースのExperience Composer]を使用する場合は、[!UICONTROL Form]を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VECおよび[!UICONTROL  フォームベースのExperience Composer]に加えて、[!DNL Target]はシングルページアプリケーション VECを提供しています。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き）お客様が[Target Premiumのお客様](/help/main/c-intro/intro.md#premium)の場合、「**[!UICONTROL Workspaceを選択]**」ドロップダウンリストから「[ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)」を選択します。

   前の図の「[[!UICONTROL 職場を選択]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)」オプションは[Target Premium](/help/main/c-intro/intro.md)機能であり、組織が[!UICONTROL Target Standard] ライセンスを持っている場合は表示されない可能性があります。

1. **[!UICONTROL アクティビティ URLを入力]** ボックスで、[ アクティビティ URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)を指定し、**[!UICONTROL 作成]**&#x200B;をクリックします。

   アカウントに[デフォルトの URL が設定されている](/help/main/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。 必要に応じて、デフォルトから別のURLに変更できます。

   [!UICONTROL Visual Experience Composer] が表示され、URL で指定したページが表示されます。

1. VECの上部にある&#x200B;**[!UICONTROL 名称未設定のアクティビティ]**&#x200B;をクリックし、指定されたスペースでアクティビティの名前を指定します。

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

1. 新しいエクスペリエンスを作成します（ページ上の要素の変更）。

   新しいアクティビティを作成すると、[!UICONTROL Visual Experience Composer] の左側に「エクスペリエンス A」と「エクスペリエンス B」の 2 つのタブが表示されます。エクスペリエンス A はコントロールエクスペリエンスです。 エクスペリエンス B タブに注目し、必要に応じて変更できます。 エクスペリエンス Bは、テストに追加できる代替エクスペリエンスです。 テストには複数のエクスペリエンスを追加できます。 デフォルトのサイトエクスペリエンスをオプションとして使用しない場合は、エクスペリエンス A をアクティビティから削除できます。

   [!UICONTROL Visual Experience Composer]でのエクスペリエンスの追加と変更について詳しくは、[ エクスペリエンスの追加](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)を参照してください。 エクスペリエンス B を変更するには、ステップ 2 から始めます。

1. [!UICONTROL Visual Experience Composer]の上部にある&#x200B;**[!UICONTROL ターゲティング]**&#x200B;をクリックして、3段階のガイド付きワークフローの次のステップに移動します。

   フロー図が開きます。

   ![A/B テストのターゲティング手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   フロー図を使用すると、アクティビティに対するオーディエンスの選択およびエクスペリエンスの設定を順に実行できます。

1. **[!UICONTROL オーディエンス]** ボックスで、編集アイコン（垂直省略記号）をクリックし、**[!UICONTROL オーディエンスの置換]**&#x200B;をクリックしてから、[ アクティビティのオーディエンス ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)を選択します。

   デフォルトでは、オーディエンスは[!UICONTROL すべての訪問者]に設定されています。

1. アクティビティに参加する資格のある訪問者の割合を選択します。

   ![オーディエンスの割合](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. トラフィックの配分を設定します。

   同じオーディエンスに対して複数のエクスペリエンスを表示することができます。 選択したオーディエンスと、アクティビティに追加したエクスペリエンスを示す図が表示されます。

   目的のトラフィック配分方法を選択します。

   * **[!UICONTROL 手動（デフォルト）]**：各エクスペリエンスを表示する参加者の割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。 全エクスペリエンスの合計が 100％になるようにします。

   * **[!UICONTROL 最適なエクスペリエンスに自動割り当て]**：ほとんどのアクティビティ参加者は、パフォーマンスの高いエクスペリエンスに自動的に送信されます。 一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。 詳しくは、[[!UICONTROL 自動割り当て]の概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)を参照してください。

   * **[!UICONTROL パーソナライズされたエクスペリエンスのための自動ターゲティング]**: [!DNL Target]は、高度な機械学習を使用して、コンテンツをパーソナライズし、コンバージョンを促進します。複数のパフォーマンスの高いマーケター定義エクスペリエンスを特定し、個々の顧客プロファイルと類似の訪問者の過去の行動に基づいて、訪問者に最もカスタマイズされたエクスペリエンスを提供します。 詳しくは、[自動ターゲットの概要](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を参照してください。

   「**[!UICONTROL 追加]**」をクリックして、別のエクスペリエンスをアクティビティに追加することもできます。

1. オーディエンス、エクスペリエンスの選択肢、トラフィック配分の選択肢に満足したら、**[!UICONTROL 次へ]**&#x200B;をクリックして、3段階のガイド付きワークフローの3番目のステップに移動します。

1. アクティビティの[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)を指定します。

1. **[!UICONTROL 保存して閉じる]**&#x200B;または&#x200B;**[!UICONTROL 保存]**&#x200B;をクリックします。

アクティビティを作成すると、「[!UICONTROL 概要]」タブに、アクティビティに関する情報（アクティビティの図を含む）が表示されます。

## トレーニングビデオ：A/B テストの作成（8:36） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、[!DNL Target] で 3 ステップのガイドによるワークフローを使用して A/B テストを作成する方法を説明します。

* [!DNL Adobe Target]に[!UICONTROL A/B テスト ] アクティビティを作成します
* 手動分割または自動トラフィック配分によるトラフィックの配分

>[!VIDEO](https://video.tv.adobe.com/v/17391)
