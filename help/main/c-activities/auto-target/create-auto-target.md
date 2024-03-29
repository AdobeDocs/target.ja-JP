---
keywords: 自動ターゲットの作成；A/B テスト；自動ターゲットアクティビティ；新しい A/B アクティビティ；自動ターゲット；パーソナライズされたエクスペリエンスの自動ターゲット；パーソナライズ；最適化
description: の使用方法を学ぶ [!UICONTROL Visual Experience Composer] (VEC) [!DNL Adobe Target] を作成するには、 [!UICONTROL 自動ターゲット] A/B テストアクティビティ
title: 作成方法 [!UICONTROL 自動ターゲット] 活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 50%

---

# の作成 [!UICONTROL 自動ターゲット] アクティビティ

以下を使用します。 [!UICONTROL Visual Experience Composer] (VEC) [!DNL Adobe Target] をクリックして、 [!UICONTROL 自動ターゲット] [!UICONTROL A/B テスト] 直接に [!DNL Target] — 有効なページと、 [!DNL Target].

>[!NOTE]
>
>[!UICONTROL 自動ターゲット] は、この [!DNL Target Premium] ソリューションの一部として使用できます。この機能は、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では使用できません。このライセンスで提供される高度な機能について詳しくは、[Target Premium](/help/main/c-intro/intro.md) を参照してください。

次の手順で、 [!UICONTROL 自動ターゲット] アクティビティ：

1. **[!UICONTROL アクティビティ]**&#x200B;リストで、**[!UICONTROL アクティビティを作成]**／**[!UICONTROL A/B テスト]**&#x200B;を選択します。

   ![アクティビティを作成ドロップダウンリスト](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   利用可能なアクティビティタイプは、[!DNL Target] アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。例えば、[!UICONTROL Recommendations] は [Target Premium 機能](/help/main/c-intro/intro.md#premium)です。様々なアクティビティタイプについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md)および [Target アクティビティのガイド](/help/main/c-activities/target-activities-guide.md)を参照してください。

1. 選択 **[!UICONTROL ビジュアル]**（必要に応じて）

   を使用したい場合は、 [!UICONTROL フォームベースの Experience Composer]を選択します。 [!UICONTROL フォーム]. 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VEC および [!UICONTROL フォームベースの Experience Composer], [!DNL Target] は、シングルページアプリケーション VEC を提供します。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き）[Target Premium](/help/main/c-intro/intro.md#premium) のお客様の場合、[ワークスペース](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)を選択します。

1. [アクティビティ URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) を指定してから、「**[!UICONTROL 次へ]**」をクリックします。

   アカウントにデフォルトの URL が設定されている場合は、その URL がデフォルトで表示されます。デフォルトの URL を別の URL に変更できます。

   [!UICONTROL Visual Experience Composer] が表示され、URL で指定したページが表示されます。

   ![VEC](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. 用意されている領域に、アクティビティの名前を入力します。

   ![「名前」フィールド](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   アクティビティ名の先頭に次の文字を使用することはできません。

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

1. ページ上の要素を変更して、エクスペリエンスを作成します。

   The [!UICONTROL Visual Experience Composer] アクティビティを作成すると、左側に「エクスペリエンス A」と「エクスペリエンス B」の 2 つのタブが表示されます。「エクスペリエンス A」は、コントロールエクスペリエンスです。 「エクスペリエンス B」タブがフォーカスされ、必要に応じて変更できます。 エクスペリエンス B は、テストに追加できる別のエクスペリエンスです。 テストには複数のエクスペリエンスを追加できます。デフォルトのサイトエクスペリエンスをオプションとして使用しない場合は、エクスペリエンス A をアクティビティから削除できます。

   [!UICONTROL Visual Experience Composer] でのエクスペリエンスの追加と変更について詳しくは、[エクスペリエンスの追加](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md).エクスペリエンス B を変更するには、ステップ 2 から始めます。

1. **[!UICONTROL Visual Experience Composer]** の上部にある[!UICONTROL ターゲット設定]をクリックして、3 ステップのガイドによるワークフロー内の次のステップに移ります。

   フロー図が開きます。

   ![A/B テストのターゲット設定手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   フロー図を使用すると、アクティビティに対するオーディエンスの選択およびエクスペリエンスの設定を順に実行できます。

1. Adobe Analytics の [!UICONTROL 対象ユーザ] 」ボックスで、編集アイコン（縦の省略記号）をクリックし、 **[!UICONTROL オーディエンスを置換]**&#x200B;を、 [オーディエンスを選択](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) 」をクリックします。

   デフォルトでは、オーディエンスは [!UICONTROL すべての訪問者].

1. アクティビティに参加する資格のある訪問者の割合を選択します。

   ![オーディエンスの割合](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. トラフィックの配分を設定します。

   同じオーディエンスに対して複数のエクスペリエンスを表示することができます。選択したオーディエンスと、アクティビティに追加したエクスペリエンスが図に表示されます。

   目的のトラフィック配分方法を選択します。 次の手順で、 [!UICONTROL 自動ターゲット] アクティビティ、選択 **[!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]**.

   トラフィックの配分には、次の 3 種類があります。

   * **[!UICONTROL 手動（デフォルト）]**：各エクスペリエンスを表示する参加者の割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。全エクスペリエンスの合計が 100％になるようにします。詳しくは、 [A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL 最良のエクスペリエンスに自動配分]**：ほとんどのアクティビティ参加者は、パフォーマンスの高いエクスペリエンスに自動的にリダイレクトされます。 一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。詳しくは、 [自動配分の概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]**: [!DNL Target] は、高度な機械学習を利用して、パフォーマンスの高いマーケティング担当者が定義した複数のエクスペリエンスを識別し、類似の訪問者の個々の顧客プロファイルや過去の行動に基づいて訪問者に最適なエクスペリエンスを提供し、コンテンツをパーソナライズします。

   また、 **[!UICONTROL 追加]** をクリックして、別のエクスペリエンスをアクティビティに追加します。

1. オーディエンス、エクスペリエンスの選択、トラフィック配分の選択が完了したら、 **[!UICONTROL 次へ]** をクリックして、3 ステップのガイドによるワークフロー内の 3 番目のステップに移動します。

1. アクティビティの[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)を指定します。

   >[!NOTE]
   >
   >を使用する場合は、 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) このアクティビティに関しては、 [自動配分と自動ターゲットアクティビティに対する A4T のサポート](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. クリック **[!UICONTROL 保存して閉じる]** または **[!UICONTROL 保存]**.

アクティビティを作成した後、 [!UICONTROL 概要] 「 」タブには、アクティビティの図など、アクティビティに関する情報が表示されます。

## トレーニングビデオ：A/Bテストの作成（8:36）

このビデオでは、[!DNL Target] で 3 ステップのガイドによるワークフローを使用して A/B テストを作成する方法を説明します。

* の作成 [!UICONTROL A/B テスト] アクティビティ [!DNL Adobe Target]
* 手動分割または自動トラフィック配分によるトラフィックの配分

>[!VIDEO](https://video.tv.adobe.com/v/17391)
