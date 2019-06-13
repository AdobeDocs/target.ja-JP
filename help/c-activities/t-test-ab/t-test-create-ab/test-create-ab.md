---
description: Target の Visual Experience Composer を使用すると、Target を有効にしたページに直接テストを作成し、Target 内でページの一部を変更することができます。
keywords: A/B の作成;A/B テスト;A/B アクティビティ;新しい A/B アクティビティ
seo-description: Target の Visual Experience Composer を使用すると、Target を有効にしたページに直接テストを作成し、Target 内でページの一部を変更することができます。
seo-title: A/B テストの作成
solution: 'Target '
title: A/B テストの作成
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
translation-type: tm+mt
source-git-commit: f81d3ab49dc2cd01b4025f542d3174abf0a3c0d6

---


# A/B テストの作成{#create-an-a-b-test}

Target の Visual Experience Composer を使用すると、Target を有効にしたページに直接テストを作成し、Target 内でページの一部を変更することができます。

1. 「[!UICONTROL アクティビティ]」リストで、**[!UICONTROL アクティビティを作成]**／**[!UICONTROL A/B テスト]** を選択します。

   ![アクティビティを作成ドロップダウンリスト](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、[!DNL Target] アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。例えば [!UICONTROL 、Recommendations] は [Target Premium機能](/help/c-intro/intro.md#premium)です。

   各種アクティビティのタイプについて詳しくは [、アクティビティ](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) および [Targetアクティビティガイド](/help/c-activities/target-activities-guide.md)を参照してください。

   ![A/Bテストアクティビティの作成ダイアログボックス](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newactivityurl-new.png)

1. 必要に応じて **[!UICONTROL 、「ビジュアル（デフォルト）]**」を選択します。

   フォームベースの Experience Composer を使用する場合、「[!UICONTROL フォーム]」を選択します。詳しくは [、フォームベースのExperience Composer](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) を参照してください。

   >[!NOTE]
   >
   >VECおよびフォームベースのExperience Composerに加えて、Targetは単一ページアプリケーションVECおよびVEC forモバイルアプリを提供します。様々なコンポーザーについて詳しくは [、エクスペリエンスとオファー](/help/c-experiences/experiences.md)を参照してください。

   問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4)を参照してください。

1. （条件付き） [Target Premium](/help/c-intro/intro.md#premium) のお客様の場合は [、ワークスペースを選択](/help/administrating-target/c-user-management/property-channel/property-channel.md)します。


1. [アクティビティURLを指定](../../../c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)し、「 **[!UICONTROL 次へ]**」をクリックします。

   アカウントにデフォルトの URL が設定されている場合は、その URL がデフォルトで表示されます。デフォルトの URL を別の URL に変更できます。

   [!UICONTROL Visual Experience Composer] が表示され、URL で指定したページが表示されます。

   ![VEC](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. 用意されている領域に、アクティビティの名前を入力します。

   ![名前フィールド](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   次の文字はアクティビティ名として入力できません。

   | 文字 | 説明 |
   |--- |--- |
   | `/` | フォワードスラッシュ |
   | `?` | 疑問符 |
   | `#` | 番号記号 |
   | `:` | コロン |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

1. 新しいエクスペリエンスを作成します（ページ上の要素の変更）。

   新しいアクティビティを作成すると、[!UICONTROL Visual Experience Composer] の左側に「エクスペリエンス A」と「エクスペリエンス B」の 2 つのタブが表示されます。エクスペリエンス A はコントロールエクスペリエンスです。ここで注目するのは、必要に応じて変更が可能な「エクスペリエンス B」タブの方です。エクスペリエンス B は代替エクスペリエンスで、テストに追加することができます。テストには複数のエクスペリエンスを追加できます。デフォルトのサイトエクスペリエンスをオプションとして使用しない場合は、エクスペリエンス A をアクティビティから削除できます。

   [!UICONTROL Visual Experience Composer] でのエクスペリエンスの追加と変更について詳しくは、[エクスペリエンスの追加](../../../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00).エクスペリエンス B を変更するには、ステップ 3 から始めます。

1. Visual **[!UICONTROL Experience]** [!UICONTROL Composer] の上部にある「ターゲット設定」をクリックして、3ステップのガイドによるワークフローの次の手順に進みます。

   フロー図が開きます。

   ![A/Bテストターゲットステップ](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   フロー図を使用すると、アクティビティに対するオーディエンスの選択、およびエクスペリエンスの設定を順に実行できます。
1. [!UICONTROL オーディエンス]ボックスで編集アイコンをクリックし、アクティビティの[オーディエンスを選択](../../../c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087)します。

   デフォルトで、オーディエンスはすべての訪問者に設定されています。

1. アクティビティに参加する資格のある訪問者の割合を選択します。

   ![オーディエンスの割合](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. トラフィックの配分を設定します。

   同じオーディエンスに対して複数のエクスペリエンスを表示することができます。選択したオーディエンスと、アクティビティに追加したエクスペリエンスが図に表示されます。

   目的のトラフィック配分方法を選択します。

   * **[!UICONTROL 手動（デフォルト）]**:各エクスペリエンスを表示する参加者の割合を指定します。この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。全エクスペリエンスの合計が 100％になるようにします。

   * **[!UICONTROL 最高のエクスペリエンスへの自動配分]**:ほとんどのアクティビティ参加者は、パフォーマンスの高いエクスペリエンスに自動的に誘導されます。一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。[自動トラフィック配分](../../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)を参照してください。

   * **[!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]**:Targetは高度な機械学習アルゴリズムを使用して、目標を最大化するために、訪問者を自動的に最適なエクスペリエンスに誘導します。詳しくは、[自動ターゲットで最適化](../../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3)を参照してください。
   「**[!UICONTROL エクスペリエンスを追加]」をクリックして別のエクスペリエンスをアクティビティに追加することもできます。**

1. オーディエンスとエクスペリエンスの選択が完了したら、「**[!UICONTROL 次へ]**」をクリックして、3 ステップのガイドによるワークフロー内の 3 番目のステップに移ります。

1. アクティビティの[目標と設定](../../../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)を指定します。

   ![A/Bアクティビティの設定](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

アクティビティの作成後、「概要」タブに、アクティビティの図などアクティビティに関する情報が表示されます。

## トレーニングビデオ：A/Bテストの作成（8:36）

このビデオでは、[!DNL Target] で 3 ステップのガイドによるワークフローを使用して A/B テストを作成する方法を説明します。

* Adobe Target での A/B アクティビティの作成
* 手動分割または自動トラフィック配分によるトラフィックの配分

>[!VIDEO](https://video.tv.adobe.com/v/17391?captions=jpn)
