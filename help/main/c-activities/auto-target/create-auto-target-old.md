---
keywords: 自動ターゲティングの作成；A/B テスト；自動ターゲティングアクティビティ；新しいA/B アクティビティ；自動ターゲティング；パーソナライズされたエクスペリエンスの自動ターゲティング；パーソナライズされた；最適化
description: ' [!DNL Adobe Target] の[!UICONTROL Visual Experience Composer] （VEC）を使用して、[!UICONTROL 自動ターゲット ] A/B テスト アクティビティを作成する方法を説明します。'
title: '[!UICONTROL 自動ターゲット ] アクティビティを作成するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 41%

---

# [!UICONTROL 自動ターゲット ] アクティビティの作成

[!DNL Adobe Target]の[!UICONTROL Visual Experience Composer] （VEC）を使用して、[!DNL Target]対応ページで[!UICONTROL 自動ターゲット ] [!UICONTROL A/B テスト ] アクティビティを直接作成し、[!DNL Target]内のページの一部を変更します。

>[!NOTE]
>
>[!UICONTROL 自動ターゲット ]は、[!DNL Target Premium] ソリューションの一部として利用できます。 この機能は、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では使用できません。 このライセンスで提供される高度な機能について詳しくは、[Target Premium](/help/main/c-intro/intro.md) を参照してください。

[!UICONTROL 自動ターゲット ] アクティビティを作成するには：

1. **[!UICONTROL アクティビティ]** リストから、**[!UICONTROL アクティビティの作成]** > **[!UICONTROL A/B テスト]**&#x200B;をクリックします。

   ![アクティビティを作成ドロップダウンリスト](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   利用可能なアクティビティタイプは、[!DNL Target] アカウントによって異なります。 一部のアクティビティタイプがリストに表示されない可能性があります。 例えば、[!UICONTROL Recommendations]は[Target Premium機能](/help/main/c-intro/intro.md#premium)です。 様々なアクティビティタイプについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md)および [Target アクティビティのガイド](/help/main/c-activities/target-activities-guide.md)を参照してください。

1. 必要に応じて、**[!UICONTROL Visual]**&#x200B;を選択します。

   [!UICONTROL  フォームベースのExperience Composer]を使用する場合は、[!UICONTROL Form]を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VECおよび[!UICONTROL  フォームベースのExperience Composer]に加えて、[!DNL Target]はシングルページアプリケーション VECを提供しています。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き）[Target Premium](/help/main/c-intro/intro.md#premium) のお客様の場合、[ワークスペース](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)を選択します。

1. [ アクティビティ URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)を指定し、**[!UICONTROL 次へ]**&#x200B;をクリックします。

   アカウントにデフォルトの URL が設定されている場合は、その URL がデフォルトで表示されます。 デフォルトの URL を別の URL に変更できます。

   [!UICONTROL Visual Experience Composer] が表示され、URL で指定したページが表示されます。

   ![VEC](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. 用意されている領域に、アクティビティの名前を入力します。

   ![「名前」フィールド](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   アクティビティ名の先頭に次の文字を使用することはできません：

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

1. ページ上の要素を変更することで、あらゆるエクスペリエンスを作成できます。

   アクティビティを作成すると、[!UICONTROL Visual Experience Composer]には、左側にエクスペリエンス Aとエクスペリエンス Bの2つのタブが表示されます。エクスペリエンス Aはコントロール エクスペリエンスです。 エクスペリエンス B タブに注目し、必要に応じて変更できます。 エクスペリエンス Bは、テストに追加できる代替エクスペリエンスです。 テストには複数のエクスペリエンスを追加できます。 デフォルトのサイトエクスペリエンスをオプションとして使用しない場合は、エクスペリエンス A をアクティビティから削除できます。

   [!UICONTROL Visual Experience Composer]でのエクスペリエンスの追加と変更について詳しくは、[ エクスペリエンスの追加](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md)を参照してください。 エクスペリエンス B を変更するには、ステップ 2 から始めます。

1. [!UICONTROL Visual Experience Composer]の上部にある&#x200B;**[!UICONTROL ターゲティング]**&#x200B;をクリックして、3段階のガイド付きワークフローの次のステップに移動します。

   フロー図が開きます。

   ![A/B テストのターゲティング手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   フロー図を使用すると、アクティビティに対するオーディエンスの選択およびエクスペリエンスの設定を順に実行できます。

1. [!UICONTROL  オーディエンス ] ボックスで、編集アイコン（垂直省略記号）をクリックし、**[!UICONTROL オーディエンスの置換]**&#x200B;をクリックしてから、[ アクティビティのオーディエンス ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)を選択します。

   デフォルトでは、オーディエンスは[!UICONTROL すべての訪問者]に設定されています。

1. アクティビティに参加する資格のある訪問者の割合を選択します。

   ![オーディエンスの割合](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. トラフィックの配分を設定します。

   同じオーディエンスに対して複数のエクスペリエンスを表示することができます。 選択したオーディエンスと、アクティビティに追加したエクスペリエンスを示す図が表示されます。

   必要なトラフィック配分方法を選択します。 [!UICONTROL 自動ターゲット ] アクティビティを作成するには、パーソナライズされたエクスペリエンス用に&#x200B;**[!UICONTROL 自動ターゲット]**&#x200B;を選択します。

   トラフィック配分には、次の3つのタイプがあります。

   * **[!UICONTROL 手動（デフォルト）]**：各エクスペリエンスを表示する参加者の割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。 全エクスペリエンスの合計が 100％になるようにします。 詳しくは、[A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)を参照してください。

   * **[!UICONTROL 最適なエクスペリエンスに自動割り当て]**：ほとんどのアクティビティ参加者は、パフォーマンスの高いエクスペリエンスに自動的に送信されます。 一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。 詳しくは、[自動配分の概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)を参照してください。

   * **[!UICONTROL パーソナライズされたエクスペリエンスのための自動ターゲット]**: [!DNL Target]は、高度な機械学習を使用して、コンテンツをパーソナライズし、コンバージョンを促進します。複数のパフォーマンスの高いマーケター定義エクスペリエンスを特定し、個々の顧客プロファイルと類似の訪問者の過去の行動に基づいて、訪問者に最もカスタマイズされたエクスペリエンスを提供します。

   「**[!UICONTROL 追加]**」をクリックして、別のエクスペリエンスをアクティビティに追加することもできます。

1. オーディエンス、エクスペリエンスの選択肢、トラフィック配分の選択肢に満足したら、**[!UICONTROL 次へ]**&#x200B;をクリックして、3段階のガイド付きワークフローの3番目のステップに移動します。

1. アクティビティの[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)を指定します。

   >[!NOTE]
   >
   >このアクティビティで[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用する場合は、[A4Tの自動配分および自動ターゲットアクティビティのサポート ](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)に関する重要な情報を参照してください。

1. **[!UICONTROL 保存して閉じる]**&#x200B;または&#x200B;**[!UICONTROL 保存]**&#x200B;をクリックします。

アクティビティを作成すると、「[!UICONTROL 概要]」タブに、アクティビティに関する情報（アクティビティの図を含む）が表示されます。

## トレーニング ビデオ：A/B テストの作成（8:36）

このビデオでは、[!DNL Target] で 3 ステップのガイドによるワークフローを使用して A/B テストを作成する方法を説明します。

* [!DNL Adobe Target]に[!UICONTROL A/B テスト ] アクティビティを作成します
* 手動分割または自動トラフィック配分によるトラフィックの配分

>[!VIDEO](https://video.tv.adobe.com/v/17391)
