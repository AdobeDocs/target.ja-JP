---
keywords: Create auto-target;A/B test;auto-target activity;new a/b activity;auto target;auto-target for personalized experiences;personalized
description: Adobe TargetのVisual Experience Composerを使用して、自動配分A/Bテストアクティビティをターゲット対応ページに直接作成し、ターゲット内でページの一部を変更します。
title: 自動ターゲットアクティビティの作成
feature: ab
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 59%

---


# ![PREMIUM自動ターゲットアクティビティの](/help/assets/premium.png) 作成

[!DNL Adobe Target]の[!UICONTROL Visual Experience Composer] (VEC)を使用して、[!DNL Target]対応ページに直接[!UICONTROL 自動ターゲット] [!UICONTROL A/Bテスト]アクティビティを作成し、[!DNL Target]内でページの一部を変更します。

>[!NOTE]
>
>[!UICONTROL 自動ターゲット] [!UICONTROL A/Bテスト]アクティビティ（この記事で説明）に加えて、[!DNL Target]には、[!UICONTROL A/Bテスト]アクティビティの2種類の追加タイプが用意されています。[!UICONTROL 手動（デフォルト）]と[!UICONTROL 自動配分]
>
>*A/Bテストの概要*&#x200B;の「[A/Bテストのアクティビティのタイプ](/help/c-activities/t-test-ab/test-ab.md#types)」を参照してください。

[!UICONTROL 自動ターゲット]アクティビティを作成するには：

1. **[!UICONTROL アクティビティ]**&#x200B;リストで、**[!UICONTROL アクティビティを作成]**／**[!UICONTROL A/B テスト]**&#x200B;を選択します。

   ![アクティビティを作成ドロップダウンリスト](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、[!DNL Target] アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。例えば、[!UICONTROL 自動ターゲット]と[!UICONTROL Recommendations]は[ターゲットプレミアム機能](/help/c-intro/intro.md#premium)です。
   >
   >様々なアクティビティタイプについて詳しくは、[アクティビティ](/help/c-activities/activities.md)および [Target アクティビティのガイド](/help/c-activities/target-activities-guide.md)を参照してください。

1. 必要に応じて、「**[!UICONTROL ビジュアル (デフォルト)]**」を選択します。

   ![A/Bテストアクティビティの作成](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   [!UICONTROL フォームベースのExperience Composer]を使用する場合は、「[!UICONTROL フォーム]」を選択します。 詳しくは、[フォームベースの Experience Composer](/help/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VECと[!UICONTROL フォームベースのExperience Composer]に加え、[!DNL Target]は、単一ページアプリのVECをオファーします。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/c-experiences/experiences.md)を参照してください。
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。
   >
   >前述の図の「[[!UICONTROL ワークスペースを選択]](/help/administrating-target/c-user-management/property-channel/property-channel.md)」オプションは、[Target Premium](/help/c-intro/intro.md) の機能です。このオプションが表示されない場合は、組織に[!UICONTROL Target Standard]ライセンスがあります。

1. [ワークスペース](/help/administrating-target/c-user-management/property-channel/property-channel.md)を選択します。

1. [アクティビティ URL](/help/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) を指定してから、「**[!UICONTROL 次へ]**」をクリックします。

   アカウントにデフォルトの URL が設定されている場合は、その URL がデフォルトで表示されます。デフォルトの URL を別の URL に変更できます。

   [!UICONTROL Visual Experience Composer] が表示され、URL で指定したページが表示されます。

   ![VEC](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. 用意されている領域に、アクティビティの名前を入力します。

   ![「名前」フィールド](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

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

   [!UICONTROL Visual Experience Composer] でのエクスペリエンスの追加と変更について詳しくは、[エクスペリエンスの追加](/help/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md).エクスペリエンス B を変更するには、ステップ 3 から始めます。

1. **[!UICONTROL Visual Experience Composer]** の上部にある[!UICONTROL ターゲット設定]をクリックして、3 ステップのガイドによるワークフロー内の次のステップに移ります。

   フロー図が開きます。

   ![A/B テストのターゲット設定手順](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   フロー図を使用すると、アクティビティに対するオーディエンスの選択およびエクスペリエンスの設定を順に実行できます。

1. 「[!UICONTROL オーディエンス]」ボックスで、編集アイコン（3つの垂直な楕円）をクリックし、「**[!UICONTROL オーディエンスを置換]**」をクリックしてから、[アクティビティのオーディエンス](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)を選択します。

   デフォルトでは、オーディエンスは[!UICONTROL すべての訪問者]に設定されます。

1. アクティビティに参加する資格のある訪問者の割合を選択します。

   ![オーディエンスの割合](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. トラフィックの配分を設定します。

   同じオーディエンスに対して複数のエクスペリエンスを表示することができます。選択したオーディエンスと、アクティビティに追加したエクスペリエンスが図に表示されます。

   目的のトラフィック配分方法を選択します。 [!UICONTROL 自動ターゲット]アクティビティを作成するには、「**[!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]**」を選択します。

   次に、3種類のトラフィック配分を示します。

   * **[!UICONTROL 手動（デフォルト）]**：各エクスペリエンスを表示する参加者の割合を指定します。この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。全エクスペリエンスの合計が 100％になるようにします。詳しくは、[A/Bテストの作成](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)を参照してください。

   * **[!UICONTROL 最良のエクスペリエンスに自動配分]**：ほとんどのアクティビティ参加者がパフォーマンスの高いエクスペリエンスに自動的にリダイレクトされます。一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。詳しくは、[自動配分の概要](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)を参照してください。

   * **[!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]**: [!DNL Target] 高度な機械学習機能を使用して、パフォーマンスの高いマーケティング担当者が定義した複数のエクスペリエンスを特定し、コンバージョンを促進し、個々の顧客プロファイルや類似訪問者の過去の行動に基づいて、最もカスタマイズされたエクスペリエンスを訪問者に提供します。
   **[!UICONTROL 追加]**&#x200B;をクリックして、別のエクスペリエンスをアクティビティに追加することもできます。

1. オーディエンス、エクスペリエンスの選択、トラフィックの配分の選択に満足したら、「**[!UICONTROL 次へ]**」をクリックして、3ステップのガイドによるワークフローの3番目のステップに移動します。

1. アクティビティの[目標と設定](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)を指定します。

   ![A/B アクティビティ設定](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. 「**[!UICONTROL 保存して閉じる]**」または「**[!UICONTROL 保存]**」をクリックします。

アクティビティを作成すると、「[!UICONTROL 概要]」タブに、アクティビティの図など、アクティビティに関する情報が表示されます。

## トレーニングビデオ：A/Bテストの作成(8:36) ![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオでは、[!DNL Target] で 3 ステップのガイドによるワークフローを使用して A/B テストを作成する方法を説明します。

* [!UICONTROL A/Bテスト]アクティビティを[!DNL Adobe Target]に作成
* 手動分割または自動トラフィック配分によるトラフィックの配分

>[!VIDEO](https://video.tv.adobe.com/v/17391)