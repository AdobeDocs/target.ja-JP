---
keywords: A/B テストの作成、A/B アクティビティの作成、新しいA/B アクティビティ、A/b テストの作成
description: '[!UICONTROL Visual Experience Composer] （VEC）を使用して、[!DNL Target]対応ページで直接A/B テスト アクティビティを作成します。'
title: A/B テストの作成方法？
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
TQID: 'https://experienceleague.adobe.com/3oJeJ1q8KeFLZhUJseG6hOe6xJqH4CKILIUglcL7E3M'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: 9f1aaf5c0b172b4bbe89266800708881306e4592
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 10%
---
# A/B テストアクティビティの作成 {#create-ab-activity}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、**[!UICONTROL Visual Experience Composer]** （VEC）で&#x200B;**[!UICONTROL A/B テスト]**&#x200B;手動アクティビティを作成する方法について説明します。 エクスペリエンスを構築し、ターゲティングとトラフィックの割り当てを設定し、目標と設定を設定します。

>[!ENDSHADEBOX]

[!DNL Adobe Target]の&#x200B;**[!UICONTROL Visual Experience Composer]** （VEC）を活用して、[!DNL Target]対応ページで&#x200B;**[!UICONTROL A/B テスト]** アクティビティを直接作成し、[!DNL Target]内のページセクションを変更します。

>[!NOTE]
>
>**[!UICONTROL 手動]** （デフォルト） **[!UICONTROL A/B テスト]** アクティビティ （この記事で説明）に加えて、[!DNL Target]には、**[!UICONTROL A/B テスト]** アクティビティの2つの追加タイプが用意されています：**[!UICONTROL 自動配分]**&#x200B;と&#x200B;**[!UICONTROL 自動ターゲット]**。
>
>*A/B テストの概要*&#x200B;の[A/B テスト アクティビティの種類](/help/main/c-activities/t-test-ab/test-ab.md#types)を参照してください。

このアクティビティは、VECの3段階のガイド付きワークフローに従います。

1. [エクスペリエンスの構築](#build-experiences)
1. [ターゲティングとトラフィック配分の設定](#set-targeting)
1. [目標と設定の設定](#configure-goals-and-settings)

## ステップ 1：エクスペリエンスの構築 {#build-experiences}

アクティビティを作成し、コントロールに対してテストする代替エクスペリエンスをデザインします。

### アクティビティの作成 {#create-activity}

**[!UICONTROL Visual Experience Composer]**&#x200B;でテストするページを開き、アクティビティに名前を付けます。

1. **[!UICONTROL アクティビティ]** リストから、**[!UICONTROL アクティビティの作成]** > **[!UICONTROL A/B テスト]**&#x200B;をクリックします。

   ![](../../assets/create-ab-1.png)

1. **[!UICONTROL A/B テスト アクティビティを作成]** ダイアログから、Experience Composerを選択します。

   * **[!UICONTROL ビジュアル]**。
   * **[!UICONTROL フォームベースのExperience Composer]**&#x200B;について詳しくは、[ フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を参照してください。

   >[!NOTE]
   >
   >VECおよび&#x200B;**[!UICONTROL フォームベースのExperience Composer]**&#x200B;に加えて、[!DNL Target]は&#x200B;**[!UICONTROL 単一ページアプリケーション]** VECを提供しています。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >VECに関するトラブルシューティング情報については、[Visual Experience Composerのトラブルシューティング ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き）お客様が[Target Premiumのお客様](/help/main/c-intro/intro.md#premium)の場合、「**[!UICONTROL Workspaceを選択]**」ドロップダウンリストから「[ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)」を選択します。

1. 「**[!UICONTROL アクティビティ URLを入力]**」ボックスに、[ アクティビティ URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)を指定します。

   アカウントに[デフォルトの URL が設定されている](/help/main/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。 必要に応じて、デフォルトから別のURLに変更できます。

1. 「**[!UICONTROL 作成]**」をクリックします。 **[!UICONTROL Visual Experience Composer]** が表示され、URL で指定したページが表示されます。

1. アクティビティに名前を付けるには、**[!UICONTROL 編集]** アイコン （![編集アイコン ](/help/main/assets/icons/Edit.svg)）をクリックし、アクティビティのわかりやすい名前を指定して、**[!UICONTROL 保存]**&#x200B;をクリックします。

   {{activity-name-rules}}

   ![](../../assets/create-ab-2.png)

### エクスペリエンスの設計 {#design-experiences}

ページ上の要素を変更して、新しいエクスペリエンスを作成します。

新しいアクティビティを作成すると、**[!UICONTROL Visual Experience Composer]**&#x200B;の左側に、エクスペリエンス Aとエクスペリエンス Bの2つのタブが表示されます。

* **エクスペリエンス A**&#x200B;はコントロール エクスペリエンスです。 デフォルトのサイトエクスペリエンスをオプションとして含めない場合は、このオプションを削除できます。
* **エクスペリエンス B**&#x200B;は、テストに追加する代替エクスペリエンスです。 このタブは目的に合わせて変更できます。

テストにさらにエクスペリエンスを追加するには、**[!UICONTROL 追加]** アイコン （![追加アイコン ](/help/main/assets/icons/Add.svg)）をクリックします。

![](../../assets/create-ab-3.png)

**[!UICONTROL Visual Experience Composer]**&#x200B;でのエクスペリエンスの追加と変更について詳しくは、[ エクスペリエンスの追加](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#ab-add-experience)を参照してください。

## ステップ 2：ターゲティングとトラフィック配分の設定 {#set-targeting}

**[!UICONTROL ターゲティング]** メニューにアクセスすると、フロー図が開きます。

![A/B テストのターゲティング手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

フロー図では、オーディエンスとそのトラフィック率の割り当て、トラフィック配分方法の選択、アクティビティ内の各エクスペリエンスのトラフィック配分の指定を順を追って行います。

1. （条件付き）アクティビティの別のオーディエンスを選択するには、**[!UICONTROL すべての訪問者]** コントロールをクリックします。

   **[!UICONTROL すべての訪問者]** オーディエンスがデフォルトとして設定されます。 別のオーディエンスを選択すると、その名前が一番左のコントロールに表示されます。 例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

   +++ 別のオーディエンスを選択する手順

   右側のフレームが表示され、オーディエンスを追加または削除し、アクティビティの訪問者パーセンテージを割り当てることができます。

   1. オーディエンスを変更するには、右側のフレームの&#x200B;**[!UICONTROL 置換]** アイコン（![置換アイコン ](/help/main/assets/icons/Retweet.svg)）をクリックします。
   1. **[!UICONTROL オーディエンスを追加]** ダイアログボックスで、[目的のオーディエンス ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)を選択し、**[!UICONTROL オーディエンスを割り当て]**&#x200B;をクリックします。

      複数のオーディエンスを組み合わせたオーディエンスを作成するには、**[!UICONTROL オーディエンスを組み合わせる]**&#x200B;をクリックします。 詳しくは、[複数のオーディエンスを組み合わせる](/help/main/c-target/combining-multiple-audiences.md)を参照してください。

      まだ&#x200B;**[!UICONTROL オーディエンスライブラリ]**&#x200B;にない新しいオーディエンスを作成するには、**[!UICONTROL オーディエンスの作成]**&#x200B;をクリックします。 [create-audience ワークフロー](/help/main/c-target/c-audiences/audiences.md)で、次のいずれかのオプションを選択します。

      * **[!UICONTROL オーディエンスライブラリ]**: **[!UICONTROL オーディエンスライブラリ]**&#x200B;に保存され、他のアクティビティで再利用できるオンデマンドオーディエンスを作成します。
      * **[!UICONTROL このアクティビティのみ]**: **[!UICONTROL オーディエンスライブラリ]**&#x200B;に保存されていない[ アクティビティ固有のオーディエンス ](/help/main/c-target/creating-activity-only-audience.md)を作成し、現在のアクティビティでのみ使用できます。

   1. 右側のフレームで「**[!UICONTROL 訪問者の割合]**」をクリックし、アクティビティに参加する対象となる訪問者の割合を選択します。

   +++

1. 「**[!UICONTROL トラフィック配分]**」コントロールをクリックし、右側のペインでトラフィック配分方法を選択します。 [ トラフィックの割り当て方法](#traffic-allocation-methods)を参照してください。

   ![トラフィック配分方法の設定](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

   +++トラフィック配分オプション

   | メソッド | 機能 |
   |---|---|
   | **[!UICONTROL 手動（既定）]** | 各エクスペリエンスを表示する参加者の割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。 全エクスペリエンスの合計が 100％になるようにします。 |
   | **[!UICONTROL 最適なエクスペリエンスに自動割り当て]** | 多くのアクティビティ参加者は、パフォーマンスの高いエクスペリエンスに自動的に誘導されます。 一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。 詳しくは、[**[!UICONTROL 自動割り当て&#x200B;]**の概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)を参照してください。 |
   | **[!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]** | [!DNL Target]は、高度な機械学習を使用して、コンテンツをパーソナライズし、コンバージョンを促進します。複数の効果的なマーケター定義エクスペリエンスを特定し、個々の顧客プロファイルと類似する訪問者の過去の行動に基づいて、訪問者に最もカスタマイズされたエクスペリエンスを提供します。 詳しくは、[自動ターゲットの概要](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を参照してください。 |

   +++

1. 右側のパネルで「**[!UICONTROL エクスペリエンス]**」をクリックし、各エクスペリエンスに対して目的のトラフィック割り当てを指定します。

1. オーディエンス、エクスペリエンスの選択肢、トラフィック配分の選択肢に満足したら、**[!UICONTROL 次へ]**&#x200B;をクリックして、3段階のガイド付きワークフローの3番目のステップに移動します。

## 手順3：目標と設定の設定 {#configure-goals-and-settings}

**[!UICONTROL 目標と設定]** ページで、アクティビティの測定方法を[!DNL Target]さんに伝えます。 使用可能な設定は、[!DNL Target]または[Analyticsをレポートソース ](/help/main/c-integrating-target-with-mac/a4t/a4t.md)として使用するかどうかに応じて異なります。

1. ページのセクションを確認し、必要なものを設定します。 「[目標と設定」ページで設定した内容](#goals-settings-overview)を参照してください。

   | セクション | 設定するもの |
   |---|---|
   | **[!UICONTROL アクティビティの設定]** | オプションの目的、**[!UICONTROL 優先度]** （複数のアクティビティが場所とオーディエンスを共有する場合に使用）、および&#x200B;**[!UICONTROL 期間]** （開始日と終了日）です。 |
   | **[!UICONTROL レポート設定]** | レポートソース、目標指標（例：**[!UICONTROL コンバージョン]**&#x200B;指標）、追加指標、レポート用オーディエンス、統計的手法。 |
   | **[!UICONTROL 詳細設定]** | 成功指標、訪問者が目標指標に達した後の処理、カウントの増分方法などの依存関係があります。 |
   | **[!UICONTROL その他のメタデータ]** | 自分または他のチームメンバーに役立つアクティビティに関するメモ。 |

1. **[!UICONTROL 保存して閉じる]**&#x200B;または&#x200B;**[!UICONTROL 保存]**&#x200B;をクリックします。

アクティビティを作成すると、「**[!UICONTROL 概要]**」タブに、アクティビティに関する情報（アクティビティの図を含む）が表示されます。
