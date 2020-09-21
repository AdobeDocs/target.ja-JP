---
keywords: create recommendations;recommendations activity;new recommendations;recommendations overview
description: Target の Visual Experience Composer（VEC）を使用すると、Target を有効にしたページ上に Recommendations アクティビティを作成し、Target 内でページの一部を変更することができます。
title: Recommendations アクティビティの作成
feature: recs creation
uuid: c3f22cce-204a-4509-92c4-8fec43fbaebe
translation-type: tm+mt
source-git-commit: d14c57c5ebbbe1902d71ad60dd95ef697ee6411e
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 78%

---


# ![PREMIUM](/help/assets/premium.png) Recommendations アクティビティの作成{#create-a-recommendations-activity}

Target の Visual Experience Composer（VEC）を使用すると、Target を有効にしたページ上に Recommendations アクティビティを作成し、Target 内でページの一部を変更することができます。

1. **[!UICONTROL アクティビティを作成]**／**[!UICONTROL レコメンデーション]**&#x200B;をクリックします。

   ![Recommendations アクティビティの作成](/help/c-recommendations/t-create-recs-activity/assets/Menu_CreateActivity.png)

1. 必要に応じて、「**[!UICONTROL ビジュアル (デフォルト)]**」を選択します。

   ![Recommendations アクティビティを作成ダイアログボックス](/help/c-recommendations/t-create-recs-activity/assets/DB_NewRecAct.png)

   フォームベースの Experience Composer を使用する場合、「[!UICONTROL フォーム]」を選択します。詳しくは、[フォームベースの Experience Composer](/help/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VEC およびフォームベースの Experience Composer に加えて、Target はシングルページアプリケーション VEC およびモバイルアプリ向け VEC を提供します。様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/c-experiences/experiences.md)を参照してください。
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。
   >
   >The [!UICONTROL [Choose Workplace]](/help/administrating-target/c-user-management/property-channel/property-channel.md) option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. このオプションが表示されない場合、お客様の組織は Target Standard ライセンスを所有しています。

1. （条件付き）[Target Premium](/help/c-intro/intro.md#premium) のお客様の場合、[ワークスペース](/help/administrating-target/c-user-management/property-channel/property-channel.md)を選択します。

1. アクティビティ URL を指定し、「**[!UICONTROL 次へ]**」をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `http://www.adobe.com`] と [!DNL `https://wwww.adobe.com`] の両方が一致します。

   アクティビティ URL は、レコメンデーションが表示されるページです。

   「[!UICONTROL 次へ]」をクリックすると、VEC が開き、ページが表示されます。現在の要素をレコメンデーションで置き換えたり、レコメンデーションを挿入したりすることができます。

1. Click an element on your page, then if recommendations are available where that element is located, click **[!UICONTROL Replace w/ Recommendations]**, **[!UICONTROL Insert Recommendations Before]**, or **[!UICONTROL Insert Recommendations After]**.

   サイトの訪問者は、レコメンデーションに該当する場合にのみ、レコメンデーションコンテンツを表示します。 レコメンデーションに適合しない訪問者には、デフォルトコンテンツが表示されます。

   ![Recommendations オプション](/help/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   * **[!UICONTROL 置き換え(Recommendations]**):エレメントをレコメンデーションと置き換えると、現在のコンテンツが削除され、レコメンデーションと置き換えられます。 訪問者がサイトを訪問し、レコメンデーションの条件を満たすと、既存のコンテンツではなく、指定された領域にレコメンデーション品目が表示されます。
   * **[!UICONTROL 前にRecommendationsを挿入]**:選択した要素の前にレコメンデーションを挿入すると、レコメンデーションされたコンテンツがその要素の前に配置されます。 ページの構築に応じて、レコメンデーションは、選択した要素の上または左に表示されます。
   * **[!UICONTROL 後にRecommendationsを挿入]**:選択した要素の後にレコメンデーションを挿入すると、その要素の後にレコメンデーションコンテンツが配置されます。 ページの構築に応じて、選択した要素の下または右にレコメンデーションが表示されます。

   「 **[!UICONTROL 選択範囲を拡張]** 」オプションを使用すると、選択した場所(親コンテナ)を拡張して、目的のページエレメントを簡単に特定し、含めることができます。

1. ページタイプを選択します。

   ページタイプには、以下が含まれます。

   * 買い物かごページ
   * カテゴリページ
   * ホームページ
   * ランディングページ
   * 製品紹介ページ
   * 検索結果ページ
   * 「ありがとうございます」ページ
   * その他

   ![「ページタイプを選択」オプション](/help/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. 1 つ以上の[条件](/help/c-recommendations/c-algorithms/algorithms.md)を選択します。

   条件が、それぞれの情報を表示するカードとして表示されます。By default, the [!UICONTROL Select Criteria] screen displays criteria that are compatible with your industry vertical and the page type you selected in the previous step. これらのオプションを変更すると、他の条件を表示できます。

   >[!NOTE]
   >
   >すべてのページですべての条件が正しく実行されるわけではありません。現在の品目／現在のカテゴリーのレコメンデーションと互換性を持たせるために、ページや mbox には `entity.id` か `entity.categoryId` を渡す必要があります。通常は、互換性のある条件のみを表示するようにします。ただし、アクティビティで互換性のない条件を有効にしたい場合は、「**[!UICONTROL 互換性あり]**」チェックボックスのチェックを外します。お使いの Recommendations の設定（[!UICONTROL Recommendations]／**[!UICONTROL 設定]**／**[!UICONTROL 非互換の条件をフィルター]**）によっては、**[!UICONTROL 互換性]**&#x200B;オプションが表示されない場合があります。詳しくは、[設定](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84)を参照してください。

   ![条件を選択ダイアログボックス](/help/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   複数の条件を選択すると、トラフィックは選択した条件間で等しく分割されます。例えば、2 つの条件が選択されており、アクティビティ参加者の 20％にデフォルトコンテンツを表示するようにアクティビティがデザインされている場合、各条件によって制御されるレコメンデーションがアクティビティ参加者の 40％に表示されます。各条件の割合を変更するオプションはありません。

   * （例えば、多くの条件カードが表示されている場合に）既存の条件を検索するには、必要な条件が表示されるまで検索フィールドに入力し、条件を選択して「**[!UICONTROL 次へ]**」をクリックします。

      [!DNL Recommendations] によって提供される条件もあります。カスタムの条件を作成することも可能です。

   * To create a new criteria, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**, then fill in the information for the new criteria. 新しい条件の作成について詳しくは、[条件の作成](../../c-recommendations/c-algorithms/create-new-algorithm.md)を参照してください。
   * また、条件をシーケンスにグループ化することもできます。To create a new criteria sequence, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. 詳しくは、「条件のシーケンス [を作成](/help/c-recommendations/c-algorithms/create-criteria-sequence.md) 」を参照してください。

1. 「**[!UICONTROL 次へ]**」をクリックします。
1. [デザイン](/help/c-recommendations/c-design-overview/design-overview.md)を選択します。

   デザインとは、ページ上の場所の表示方法を決めるテンプレートです。[!DNL Target] には、事前設定済みのデザインがいくつか含まれています。 カスタムのデザインを作成することも可能です。詳しくは、[デザインの作成](../../c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14)と[デザインのカスタマイズ](../../c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59)を参照してください。

   ![デザインを選択ダイアログボックス](/help/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   各デザインには、見え方のグラフィカル表示と、現在そのデザインで使用されているライブアクティビティおよび非アクティブなアクティビティの数を示すアイコンが表示されます。

   * 1 つ以上の既存のデザインを選択するには、デザインをクリックしてから「**[!UICONTROL 次へ]**」をクリックします。

      複数の条件を選択した場合は、1 つのデザインのみ選択できます。

   * 新しいデザインを作成するには、「**[!UICONTROL デザインを作成]**」をクリックしてから、新しいデザインの名前とコードを入力します。「**[!UICONTROL 次へ]**」をクリックし、画像を選択またはアップロードして&#x200B;**[!UICONTROL 完了]**／**[!UICONTROL 完了]**&#x200B;をクリックします。新しいデザインの作成について詳しくは、[デザインの作成](../../c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14)を参照してください。

1. 「**[!UICONTROL 次へ]**」をクリックします。

   レコメンデーションにプロモーションを追加することもできます。プロモーション - 前とプロモーション - 後の追加について詳しくは、[プロモーションの追加](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. 「**[!UICONTROL 保存]**」をクリックします。

   VEC 画面に、ページのレコメンデーションデザインが表示されます。

1. （オプション）「**[!UICONTROL プレビュー]**」をクリックして、アクティビティが訪問者にどのように表示されるかを確認します。

   [!UICONTROL プレビュー]モードを使用すると、訪問者と同様にレコメンデーションを操作できます。

   レコメンデーションのプレビューを完了したら、「**[!UICONTROL 作成]**」をクリックします。

1. VEC でレコメンデーションを確認し、「**[!UICONTROL 次へ]**」をクリックします。

1. フロー図で [!DNL Recommendations] アクティビティを確認し、必要に応じて変更します。

   ![Recommendations フロー図](/help/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   フロー図を使用すると、アクティビティに対するオーディエンスの選択、エクスペリエンスの設定、成功指標の指定の手順を順に実行できます。

   フロー図から、次のことを実行できます。

   * レコメンデーションが表示されるオーディエンスを変更する

      >[!NOTE]
      >
      >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、[アクティビティのみのオーディエンスを作成](../../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)したり、[複数のオーディエンスを結合](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)してアドホックな結合オーディエンスを作成することができます。

      デフォルトでは、すべてのユーザーにレコメンデーションが表示されますが、レコメンデーションの対象を特定のオーディエンスのみにすることもできます。

      [!DNL Recommendations] アクティビティでは、制御グループはレコメンデーションなしでページが表示されます。

   * 条件を表示します。
   * コレクションを変更します（「[!UICONTROL 条件]」ラベルの横）。
   * コントロールエクスペリエンスを表示する参加者の割合を変更します。
   * デザインコードを表示します。
   * デザインを変更または削除します。

1. 終了したら「**[!UICONTROL 次へ]**」をクリックします。
1. アクティビティを設定します。

   例えば、アクティビティの名前（必須）および目標（任意）を入力します。設定について詳しくは、[Recommendations アクティビティの設定](../../c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB).

   >[!NOTE]
   >
   >[!DNL Recommendations Classic] の別のアクティビティとして既に存在する [!DNL Recommendation] アクティビティ名を指定すると、新しいアクティビティは、新しい名前で再同期されます。新しい名前は、一意なものにするために、元の名前にタイムスタンプが追加されたものになります。この新しい名前は、[!DNL Target Standard/Premium] と [!DNL Recommendations Classic] の両方で表示されます。

1. 終了したら「**[!UICONTROL 保存して閉じる]**」をクリックします。

   アクティビティの概要が表示されます。

   [!UICONTROL 概要]ページから、次のことを実行できます。

   * アクティビティをアクティブ化します。
   * アクティビティを編集します。
   * アクティビティをExperience Cloudフィードと共有する
   * アクティビティのQA
   * エクスペリエンスの URL を表示します。
   * データをダウンロードします。
   * コントロールエクスペリエンスを表示するアクティビティ参加者の割合を変更します。
   * キャンペーンの詳細情報の表示や非表示をおこないます。
   * デザインのコードを表示します。

1. （オプション）[!UICONTROL レポート]ページを開いて、[!DNL Recommendations] アクティビティのパフォーマンスのレポートを表示します。

1. （オプション）[!UICONTROL 衝突]ページを開いて、発生した可能性がある[アクティビティの衝突](/help/c-experiences/c-visual-experience-composer/activity-collisions.md)を表示します。

   複数のアクティビティから同一のページにコンテンツが配信されるように設定されている場合に、アクティビティの衝突が発生します。その場合、予期しないコンテンツが表示されることがあります。

## トレーニングビデオ：Recommendations アクティビティの作成（7:15） ![チュートリアルバッジ](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/27688)