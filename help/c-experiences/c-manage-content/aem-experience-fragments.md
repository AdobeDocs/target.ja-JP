---
description: Adobe Experience Manager（AEM）で作成したエクスペリエンスフラグメントを Target アクティビティで使用し、最適化やパーソナライゼーションを助けることに関する情報。
keywords: エクスペリエンス;AEM, Adobe Experience Manager;Adobe Target へのエクスポート;エクスペリエンスフラグメント;フラグメント;XF
seo-description: Adobe Experience Manager（AEM）で作成したエクスペリエンスフラグメントを Target アクティビティで使用し、最適化やパーソナライゼーションを助けることに関する情報。
seo-title: AEM エクスペリエンスフラグメント
solution: 'Target '
title: AEM エクスペリエンスフラグメント
topic: Standard
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# AEM エクスペリエンスフラグメント{#aem-experience-fragments}

Adobe Experience Manager（AEM）で作成したエクスペリエンスフラグメントを Target アクティビティで使用し、最適化やパーソナライゼーションを助けることに関する情報。

## AEM エクスペリエンスフラグメント {#topic_1E1E4EA01F074349B2CF8785387B5FE8}

Adobe Experience Manager（AEM）で作成したエクスペリエンスフラグメントを Target アクティビティで使用し、最適化やパーソナライゼーションを助けることに関する情報。

>[!NOTE]
>
>この機能を使用するには、Adobe Experience Manager（AEM）のユーザーである必要があります。詳しくは、以下の「[要件](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A)」を参照してください。

## 概要 {#section_95A91830530F493B81C5C9CDB9B783EA}

AEM で作成したエクスペリエンスフラグメントを Target アクティビティで使用すると、AEM の使いやすさおよび機能性と、Target の強力な自動インテリジェンス（AI）機能および機械学習（ML）機能を組み合わせ、幅広くエクスペリエンスをテストしてパーソナライズできます。

AEM では、パーソナライゼーション戦略に生かせるよう、すべてのコンテンツとアセットが一元化されます。コードを記述しなくても、デスクトップ、タブレット、モバイルデバイス向けのコンテンツを 1 か所で簡単に作成できます。デバイスごとにページを作成する必要はありません。コンテンツを基に、各デバイスのエクスペリエンスが自動調整されます。

Target では、行動、コンテキスト、オフラインの変数を組み込んだルールベースの手法と AI 駆動の機械学習手法を組み合わせ、それを土台にしてパーソナライズされたエクスペリエンスを幅広く提供できます。  A/B テストや多変量分析（MVT）アクティビティを簡単に設定して実施し、最適なオファー、コンテンツ、エクスペリエンスを見極めることができます。

エクスペリエンスフラグメントは、コンテンツ／エクスペリエンスの作成者や管理者と、ビジネス成果の向上に Target を使用している最適化／パーソナライゼーションの専門家との連携を大幅に強化できる機能です。

## 要件 {#section_AE6F0971E1574B3AA324003599B96E5A}

Target 内でエクスペリエンスフラグメント機能のプロビジョニングがおこなわれている必要があります。さらに、適切なサービスパックまたは AEM 6.4（またはそれ以降）と共に AEM 6.3 を使用する必要があります。アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

* Adobe Experience Manager 6.4（またはそれ以降）。
* Adobe Experience Manager 6.3 SP2（またはそれ以降）。
* Adobe Target Standard または Adobe Target Premium アカウント。
* 統合の有効化と認証の詳細の提供については Adobe Target カスタマーケアにお問い合わせください。

## AEM でエクスペリエンスフラグメントを作成および設定する {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

AEM エクスペリエンスフラグメントを Target で使用する手順は次のとおりです。

### ステップ 1：AEM と Target を統合する

詳しくは、次を参照してください。

* **Adobe Experience Manager 6.3** のドキュメントの [AEM 6.3：](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html)_Adobe Analytics と Adobe Target のオプトイン_。
* **Adobe Experience Manager 6.4** のドキュメントの [AEM 6.4：](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html)_Adobe Analytics と Adobe Target のオプトイン_。

### 手順 2：エクスペリエンスフラグメントを作成する

エクスペリエンスフラグメントは AEM 内に作成されます。詳しくは、次を参照してください。

* **Adobe Experience Manager 6.3** のドキュメントの [AEM 6.3：](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html)*エクスペリエンスフラグメント*。
* **Adobe Experience Manager 6.4** のドキュメントの [AEM 6.4：](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html)*エクスペリエンスフラグメント*。

### ステップ 3：AEM でエクスペリエンスフラグメントを Target と共有するよう設定する

1. AEM で、対象のエクスペリエンスフラグメントまたはそれを含むフォルダーを選択してから、[!UICONTROL プロパティ]をクリックします。
2. 「[!UICONTROL クラウドサービス]」タブをクリックし、[!UICONTROL クラウドサービスの設定]ドロップダウンリストから「[!UICONTROL Adobe Target]」を選択します。

   >[!NOTE]
   >
   >前の手順は、組織内のユーザーによって Adobe Target の設定が作成されていることを前提としています。

3. 「[!UICONTROL 保存して閉じる]」をクリックします。

### ステップ 4：エクスペリエンスフラグメントを発行し、Target にエクスポートする

**AEM 6.3：**

1. AEM で対象のエクスペリエンスフラグメントを選択し、「[!UICONTROL 発行]」タブ、「[!UICONTROL 発行]」ボタンの順にクリックします。
2. AEM で対象のエクスペリエンスフラグメントを選択し、「[!UICONTROL Adobe Target に書き出し]」、「[!UICONTROL OK]」の順にクリックします。

   ![](assets/experience_fragment_export_to_target.png)

**AEM 6.4：**

1. AEM で対象のエクスペリエンスフラグメントを選択し、「[!UICONTROL Adobe Target に書き出し]」をクリックします。

   ![](assets/experience_fragment_export_to_target.png)

2. 表示されるダイアログボックスで、「[!UICONTROL 発行]」を選択し、エクスペリエンスフラグメント内のすべてのアセットを [!DNL Target] に発行します。

## Target アクティビティでエクスペリエンスフラグメントを使用する {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

ここまでのタスクを完了すると、エクスペリエンスフラグメントが Target の[!UICONTROL オファー]ページに表示されます。

>[!NOTE]
>
>Target は現在、読み込むエクスペリエンスフラグメントを 10 分ごとに検索します。読み込まれたエクスペリエンスフラグメントは 10 分以内に Target で利用可能となるはずで、今後この時間は短縮されます。

>[!IMPORTANT]
>
>エクスペリエンスフラグメントは現在、HTML オファーとして Target に読み込まれます。エクスペリエンスフラグメントの「マスター」バージョンは、AEM 内に残ります。Target でエクスペリエンスフラグメントを編集することはできません。

リストのエクスペリエンスフラグメントにカーソルを合わせ、表示アイコン（![](assets/icon_info.png)

）をクリックすると、公開オファー配信 URL、AEM パス、および AEM 内のエクスペリエンスフラグメントを開くためのディープリンクを含む、エクスペリエンスフラグメントに関する追加情報が表示されます。

Visual Experience Composer（VEC）またはフォームベースの Experience Composer を使用して、Target アクティビティ内でエクスペリエンスフラグメントを使用できます。

>[!NOTE]
>
>Target の AI および ML 機能を最大活用するには、A/B テスト作成時に[自動配分](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)または [Automated Personalization](../../c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) を選択できます。

**VEC でエクスペリエンスフラグメントを使用するには：**

1. Target で、[Visual Experience Composer](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) を使用してエクスペリエンスを作成または編集しているときに、AEM コンテンツを挿入したいページの場所をクリックしてから「**[!UICONTROL エクスペリエンスフラグメントと交換]**」を選択し、[!UICONTROL エクスペリエンスフラグメントを選択]リストを表示します。

   >[!NOTE]
   >
   >「[!UICONTROL エクスペリエンスフラグメントと交換]」オプションは、画像には使用できません。画像にこのオプションを使用する場合は、目的の画像を含むコンテナ要素をクリックします。

   [!UICONTROL エクスペリエンスフラグメント]リストに、AEM で作成され、Target からネイティブで利用できるようになったコンテンツがすべて表示されます。

   ![](assets/experience_fragment_list.png)

1. 対象のエクスペリエンスフラグメントを選択し、「**[!UICONTROL 保存]**」をクリックします。
1. アクティビティの設定を終了します。

   各タイプのアクティビティを設定する方法について詳しくは、次のトピックを参照してください。

   * **A/B テスト：** [A/B テストの作成](../../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
   * **自動配分：** [自動配分](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動ターゲット：** [パーソナライズされたエクスペリエンスの自動ターゲット](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3)
   * **自動パーソナライゼーションアクティビティ（AP）：**[自動パーソナライゼーションアクティビティの作成](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **エクスペリエンスターゲット設定（XT）：** [エクスペリエンスのターゲット設定アクティビティの作成](../../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **多変量分析テスト（MVT）：** [多変量分析テストの作成](../../c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations：** [Recommendations アクティビティの作成](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**フォームベースの Experience Composer でエクスペリエンスフラグメントを使用するには：**

1. Target で、[フォームベースの Experience Composer](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) を使用してエクスペリエンスを作成または編集しているときに、AEM コンテンツを挿入したいページの場所を選択してから「**[!UICONTROL エクスペリエンスフラグメントを変更]**」を選択し、[!UICONTROL エクスペリエンスフラグメントを選択]リストを表示します。

   ![](assets/experience_fragment_list.png)

   [!UICONTROL エクスペリエンスフラグメント]リストに、AEM で作成され、Target からネイティブで利用できるようになったコンテンツがすべて表示されます。

1. 対象のエクスペリエンスフラグメントを選択し、「**[!UICONTROL 保存]**」をクリックします。
1. アクティビティの設定を終了します。

## トレーニングビデオ：AEM エクスペリエンスフラグメントと Adobe Target の使用{#section_C0EDC54063464F41A182492D2045BC64}

次のビデオでは、エクスペリエンスフラグメントの設定および使用方法について説明します。[Adobe Target での AEM エクスペリエンスフラグメントの使用](https://helpx.adobe.com/experience-manager/kt/sites/using/experience-fragment-target-feature-video-use.html)
