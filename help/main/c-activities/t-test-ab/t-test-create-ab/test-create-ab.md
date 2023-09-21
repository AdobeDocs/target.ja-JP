---
keywords: A/B の作成；A/B テスト；A/B アクティビティ；新しい A/B アクティビティ；A/B の作成
description: Adobeでの Visual Experience Composer(VEC) の使用方法を説明します [!DNL Target] A/B テストアクティビティを [!DNL Target] — 有効なページ。
title: A/B テストの作成方法
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
source-git-commit: ec1041fd1823d1ab7f1af147af5825c3ae8662b5
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 44%

---

# A/B テストの作成

以下を使用します。 [!UICONTROL Visual Experience Composer] (VEC) [!DNL Adobe Target] をクリックして、 [!UICONTROL A/B テスト] 直接に [!DNL Target] — 有効なページと、 [!DNL Target].

>[!NOTE]
>
>手動（デフォルト）に加えて [!UICONTROL A/B テスト] アクティビティ（この記事で説明） [!DNL Target] は、さらに 2 つのタイプを提供します [!UICONTROL A/B テスト] アクティビティ： [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット].
>
>詳しくは、 [A/B テストアクティビティのタイプ](/help/main/c-activities/t-test-ab/test-ab.md#types) in *A/B テストの概要*.

マニュアルを作成するには [!UICONTROL A/B テスト] アクティビティ：

1. **[!UICONTROL アクティビティ]**&#x200B;リストで、**[!UICONTROL アクティビティを作成]**／**[!UICONTROL A/B テスト]**&#x200B;を選択します。

   ![アクティビティを作成ドロップダウンリスト](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、[!DNL Target] アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。例えば、[!UICONTROL Recommendations] は [Target Premium 機能](/help/main/c-intro/intro.md#premium)です。
   >
   >様々なアクティビティタイプについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)および [Target アクティビティのガイド](/help/main/c-activities/target-activities-guide.md)を参照してください。

1. A/B テストアクティビティを作成ダイアログで、 **[!UICONTROL ビジュアル（デフォルト）]**（必要に応じて）

   を使用したい場合は、 [!UICONTROL フォームベースの Experience Composer]を選択します。 [!UICONTROL フォーム]. 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VEC および [!UICONTROL フォームベースの Experience Composer], [!DNL Target] は、シングルページアプリケーション VEC を提供します。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き） [Target Premium のお客様](/help/main/c-intro/intro.md#premium)、 **[!UICONTROL ワークスペースを選択]** ドロップダウンリストから、 [workspace](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   The [[!UICONTROL 職場を選択]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) 前述の図のオプションは、 [Target Premium](/help/main/c-intro/intro.md) 機能を使用している必要があり、組織が [!UICONTROL Target Standard] ライセンス。

1. Adobe Analytics の **[!UICONTROL アクティビティ URL を入力]** ボックスに、 [アクティビティ URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)を選択し、次に **[!UICONTROL 作成]**.

   アカウントに[デフォルトの URL が設定されている](/help/main/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。必要に応じて、デフォルトの URL を別の URL に変更できます。

   [!UICONTROL Visual Experience Composer] が表示され、URL で指定したページが表示されます。

1. クリック **[!UICONTROL 無題のアクティビティ]** VEC の上部で、用意されているスペースにアクティビティの名前を指定します。

   アクティビティ名の先頭に次の文字を使用することはできません。

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

   アクティビティ名に次の文字シーケンスを含めることはできません。

   | 文字シーケンス | 説明 |
   |--- |--- |
   | ;= | セミコロン、等しい |
   | ;+ | セミコロン、プラス |
   | ;- | セミコロン、マイナス |
   | ;@ | セミコロン、アットマーク |
   | ,= | コンマ、等しい |
   | ,+ | コンマ、プラス |
   | ,- | コンマ、マイナス |
   | ,@ | コンマ、アットマーク |
   | `[`&quot; | 開き角括弧、二重引用符 |
   | &quot;`]` | 二重引用符、閉じ角括弧 |

1. 新しいエクスペリエンスを作成します（ページ上の要素の変更）。

   新しいアクティビティを作成すると、[!UICONTROL Visual Experience Composer] の左側に「エクスペリエンス A」と「エクスペリエンス B」の 2 つのタブが表示されます。エクスペリエンス A はコントロールエクスペリエンスです。「エクスペリエンス B」タブがフォーカスされ、必要に応じて変更できます。 エクスペリエンス B は、テストに追加できる別のエクスペリエンスです。 テストには複数のエクスペリエンスを追加できます。デフォルトのサイトエクスペリエンスをオプションとして使用しない場合は、エクスペリエンス A をアクティビティから削除できます。

   [!UICONTROL Visual Experience Composer] でのエクスペリエンスの追加と変更について詳しくは、[エクスペリエンスの追加](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00).エクスペリエンス B を変更するには、ステップ 2 から始めます。

1. **[!UICONTROL Visual Experience Composer]** の上部にある[!UICONTROL ターゲット設定]をクリックして、3 ステップのガイドによるワークフロー内の次のステップに移ります。

   フロー図が開きます。

   ![A/B テストのターゲット設定手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   フロー図を使用すると、アクティビティに対するオーディエンスの選択およびエクスペリエンスの設定を順に実行できます。

1. Adobe Analytics の **[!UICONTROL 対象ユーザ]** 」ボックスで、編集アイコン（縦の省略記号）をクリックし、 **[!UICONTROL オーディエンスを置換]**&#x200B;を、 [オーディエンスを選択](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) 」をクリックします。

   デフォルトでは、オーディエンスは [!UICONTROL すべての訪問者].

1. アクティビティに参加する資格のある訪問者の割合を選択します。

   ![オーディエンスの割合](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. トラフィックの配分を設定します。

   同じオーディエンスに対して複数のエクスペリエンスを表示することができます。選択したオーディエンスと、アクティビティに追加したエクスペリエンスが図に表示されます。

   目的のトラフィック配分方法を選択します。

   * **[!UICONTROL 手動（デフォルト）]**：各エクスペリエンスを表示する参加者の割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。全エクスペリエンスの合計が 100％になるようにします。

   * **[!UICONTROL 最良のエクスペリエンスに自動配分]**：ほとんどのアクティビティ参加者がパフォーマンスの高いエクスペリエンスに自動的にリダイレクトされます。一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。詳しくは、 [[!UICONTROL 自動配分] 概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]**: [!DNL Target] は、高度な機械学習を利用して、パフォーマンスの高いマーケティング担当者が定義した複数のエクスペリエンスを識別し、類似の訪問者の個々の顧客プロファイルや過去の行動に基づいて訪問者に最適なエクスペリエンスを提供し、コンテンツをパーソナライズします。 詳しくは、 [自動ターゲットの概要](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   また、 **[!UICONTROL 追加]** をクリックして、別のエクスペリエンスをアクティビティに追加します。

1. オーディエンス、エクスペリエンスの選択、トラフィック配分の選択が完了したら、 **[!UICONTROL 次へ]** をクリックして、3 ステップのガイドによるワークフロー内の 3 番目のステップに移動します。

1. アクティビティの[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)を指定します。

1. クリック **[!UICONTROL 保存して閉じる]** または **[!UICONTROL 保存]**.

アクティビティを作成した後、 [!UICONTROL 概要] 「 」タブには、アクティビティの図など、アクティビティに関する情報が表示されます。

## トレーニングビデオ：A/B テストの作成(8:36) ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、[!DNL Target] で 3 ステップのガイドによるワークフローを使用して A/B テストを作成する方法を説明します。

* の作成 [!UICONTROL A/B テスト] アクティビティ [!DNL Adobe Target]
* 手動分割または自動トラフィック配分によるトラフィックの配分

>[!VIDEO](https://video.tv.adobe.com/v/17391)
