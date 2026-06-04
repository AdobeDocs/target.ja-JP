---
keywords: A/B テストの作成、A/B アクティビティの作成、新しいA/B アクティビティ、A/b テストの作成
description: '[!UICONTROL Visual Experience Composer] （VEC）を使用して、A/B テスト アクティビティを [!DNL Target]対応ページに直接作成します。'
title: A/B テストの作成方法？
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
TQID: https://experienceleague.adobe.com/3oJeJ1q8KeFLZhUJseG6hOe6xJqH4CKILIUglcL7E3M
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1019
ht-degree: 19%

---

# A/B テストアクティビティの作成

[!DNL Adobe Target]の[!UICONTROL Visual Experience Composer] （VEC）を活用して、[!DNL Target]対応ページで[!UICONTROL A/B テスト &#x200B;] アクティビティを直接作成し、[!DNL Target]内のページセクションを変更します。

>[!NOTE]
>
>[!UICONTROL 手動] （デフォルト） [!UICONTROL A/B テスト &#x200B;] アクティビティ （この記事で説明）に加えて、[!DNL Target]には、[!UICONTROL A/B テスト &#x200B;] アクティビティの2つの追加タイプが用意されています：[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット &#x200B;]。
>
>*A/B テストの概要*&#x200B;の[A/B テスト アクティビティの種類](/help/main/c-activities/t-test-ab/test-ab.md#types)を参照してください。

手動の[!UICONTROL A/B テスト &#x200B;] アクティビティを作成するには：

1. **[!UICONTROL アクティビティ]** リストから、**[!UICONTROL アクティビティの作成]** > **[!UICONTROL A/B テスト]**&#x200B;をクリックします。

1. [!UICONTROL A/B テスト アクティビティを作成] ダイアログから、必要に応じて&#x200B;**[!UICONTROL Visual]**&#x200B;を選択します。

   [!UICONTROL &#x200B; フォームベースのExperience Composer]を使用する場合は、[!UICONTROL Form]を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VECおよび[!UICONTROL &#x200B; フォームベースのExperience Composer]に加えて、[!DNL Target]は[!UICONTROL 単一ページアプリケーション &#x200B;]VECを提供しています。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >VECに関するトラブルシューティング情報については、[Visual Experience Composerのトラブルシューティング &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き）お客様が[Target Premiumのお客様](/help/main/c-intro/intro.md#premium)の場合、「**[!UICONTROL Workspaceを選択]**」ドロップダウンリストから「[&#x200B; ワークスペース &#x200B;](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)」を選択します。

   「[[!UICONTROL 職場を選択]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)」オプションは[Target Premium](/help/main/c-intro/intro.md)機能であり、組織が[!UICONTROL Target Standard] ライセンスを持っている場合は表示されない可能性があります。

1. 「**[!UICONTROL アクティビティ URLを入力]**」ボックスに、[&#x200B; アクティビティ URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)を指定します。

   アカウントに[デフォルトの URL が設定されている](/help/main/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。 必要に応じて、デフォルトから別のURLに変更できます。

1. 「**[!UICONTROL 作成]**」をクリックします。

   [!UICONTROL Visual Experience Composer] が表示され、URL で指定したページが表示されます。

1. アクティビティに名前を付けるには、「[!UICONTROL 名称未設定のアクティビティ &#x200B;]」の横にある&#x200B;**[!UICONTROL 編集]** アイコン （![編集アイコン &#x200B;](/help/main/assets/icons/Edit.svg)）をクリックし、アクティビティのわかりやすい名前を指定して、**[!UICONTROL 保存]**&#x200B;をクリックします。

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

   新しいアクティビティを作成すると、[!UICONTROL Visual Experience Composer] の左側に「エクスペリエンス A」と「エクスペリエンス B」の 2 つのタブが表示されます。エクスペリエンス A はコントロールエクスペリエンスです。 エクスペリエンス B タブに注目し、必要に応じて変更できます。 エクスペリエンス Bは、テストに追加できる代替エクスペリエンスです。 [!UICONTROL &#x200B; エクスペリエンス &#x200B;] ペインの上部にある[!UICONTROL 追加] アイコン （![追加アイコン &#x200B;](/help/main/assets/icons/Add.svg)）をクリックすると、テストに複数のエクスペリエンスを追加できます。 デフォルトのサイトエクスペリエンスをオプションとして使用しない場合は、エクスペリエンス A をアクティビティから削除できます。

   [!UICONTROL Visual Experience Composer]でのエクスペリエンスの追加と変更について詳しくは、[&#x200B; エクスペリエンスの追加](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)を参照してください。 エクスペリエンス B を変更するには、ステップ 2 から始めます。

1. [!UICONTROL Visual Experience Composer]の上部にある&#x200B;**[!UICONTROL ターゲティング]**&#x200B;をクリックして、3段階のガイド付きワークフローの次のステップに移動します。

   フロー図が開きます。

   ![A/B テストのターゲティング手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   フロー図では、オーディエンスとそのトラフィック率の割り当て、トラフィック配分方法の選択、アクティビティの各エクスペリエンスのトラフィック配分の指定の手順を順を追って説明します。

1. （条件付き）アクティビティの別のオーディエンスを選択するには、**[!UICONTROL すべての訪問者]** コントロールをクリックします。

   [!UICONTROL すべての訪問者] オーディエンスがデフォルトとして設定されます。 別のオーディエンスを選択すると、その名前が一番左のコントロールに表示されます。

   右側のフレームが表示され、オーディエンスを追加または削除し、アクティビティの訪問者パーセンテージを割り当てることができます。

   1. オーディエンスを変更するには、右側のフレームの&#x200B;**[!UICONTROL 置換] アイコン** （![置換アイコン &#x200B;](/help/main/assets/icons/Retweet.svg)）をクリックします。
   1. [!UICONTROL &#x200B; オーディエンスを追加] ダイアログボックスで、[目的のオーディエンス &#x200B;](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)を選択し、**[!UICONTROL オーディエンスを割り当て]**&#x200B;をクリックします。

      「**オーディエンスを結合**」をクリックして、[複数のオーディエンスを結合するオーディエンスを作成できます](/help/main/c-target/combining-multiple-audiences.md)。

      まだ[!UICONTROL &#x200B; オーディエンスライブラリ &#x200B;]にない新しいオーディエンスを作成する必要がある場合は、**オーディエンスの作成**&#x200B;をクリックします。 [create-audience ワークフロー](/help/main/c-target/c-audiences/audiences.md)中に、次のオプションから選択できます。

      * **[!UICONTROL オーディエンスライブラリ]**: [!UICONTROL &#x200B; オーディエンスライブラリ &#x200B;]に保存されるオンデマンドオーディエンスを作成し、他のアクティビティで再利用できます。
      * **[!UICONTROL このアクティビティのみ]**: [!UICONTROL &#x200B; オーディエンスライブラリ &#x200B;]に保存されていない[&#x200B; アクティビティ固有のオーディエンス &#x200B;](/help/main/c-target/creating-activity-only-audience.md)を作成し、現在のアクティビティでのみ使用できます。

   1. 右側のフレームで「**[!UICONTROL 訪問者の割合]**」をクリックし、アクティビティに参加する対象となる訪問者の割合を選択します。

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. 「**[!UICONTROL トラフィック配分]**」コントロールをクリックし、次に示すように、右側のペインで目的のトラフィック配分方法を選択します。

   ![&#x200B; トラフィック配分メソッドの設定](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

   目的のトラフィック配分方法を選択します。

   * **[!UICONTROL 手動（デフォルト）]**：各エクスペリエンスを表示する参加者の割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。 全エクスペリエンスの合計が 100％になるようにします。

   * **[!UICONTROL 最適なエクスペリエンスに自動割り当て]**：ほとんどのアクティビティ参加者は、パフォーマンスの高いエクスペリエンスに自動的に送信されます。 一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。 詳しくは、[[!UICONTROL 自動割り当て]の概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)を参照してください。

   * **[!UICONTROL パーソナライズされたエクスペリエンスのための自動ターゲット]**: [!DNL Target]は、高度な機械学習を使用して、コンテンツをパーソナライズし、コンバージョンを促進します。複数のパフォーマンスの高いマーケター定義エクスペリエンスを特定し、個々の顧客プロファイルと類似の訪問者の過去の行動に基づいて、訪問者に最もカスタマイズされたエクスペリエンスを提供します。 詳しくは、[自動ターゲットの概要](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を参照してください。

1. 右側のパネルで「**[!UICONTROL エクスペリエンス]**」をクリックし、各エクスペリエンスに対して目的のトラフィック割り当てを指定します。

1. オーディエンス、エクスペリエンスの選択肢、トラフィック配分の選択肢に満足したら、**[!UICONTROL 次へ]**&#x200B;をクリックして、3段階のガイド付きワークフローの3番目のステップに移動します。

1. アクティビティの[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)を指定します。

1. **[!UICONTROL 保存して閉じる]**&#x200B;または&#x200B;**[!UICONTROL 保存]**&#x200B;をクリックします。

アクティビティを作成すると、「[!UICONTROL 概要]」タブに、アクティビティに関する情報（アクティビティの図を含む）が表示されます。
