---
keywords: レコメンデーションの作成;レコメンデーションのアクティビティ;新しいレコメンデーション;レコメンデーションの概要
description: ' [!DNL Target] [!UICONTROL Visual Experience Composer] （VEC）を使用してアクティビティを作成する方法  [!DNL Recommendations]  説明します。'
title: アクティビティの作成方法  [!DNL Recommendations]  教えてください。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: b7c7e8d85f7f39024ed5e57177e5c9f628460e9c
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 52%

---

# [!DNL Recommendations] アクティビティの作成

[!DNL Target] [!UICONTROL Visual Experience Composer] （VEC）を使用して、[!DNL Target] 対応ページで [!DNL Recommendations] アクティビティを直接作成したり、[!DNL Target] 内のページの一部を変更したりします。

1. **[!UICONTROL Activities]**/**[!UICONTROL Create Activity]**/**[!UICONTROL Recommendations]** をクリックします。

1. 必要に応じて「**[!UICONTROL Visual]**」を選択します。

   [!UICONTROL Form-Based Experience Composer] を使用する場合は、「[!UICONTROL Form]」を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VEC と [!UICONTROL Form-Based Experience Composer] に加えて、[!DNL Target] は [!UICONTROL Single Page Application] VEC を提供します。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き） [ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) を選択します。

1. アクティビティ URL を指定し、「**[!UICONTROL Create]**」をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `http://www.adobe.com`] と [!DNL `https://wwww.adobe.com`] の両方が一致します。

   アクティビティ URL は、Recommendations が表示されるページです。

   「[!UICONTROL Create]」をクリックすると、VEC が開いてページが表示されます。 現在の要素をレコメンデーションで置き換えたり、レコメンデーションを挿入したりすることができます。

1. ページ上の要素をクリックし、その要素がある場所にレコメンデーションがある場合は、「**[!UICONTROL Replace w/ Recommendations]**」、「**[!UICONTROL Insert Recommendations Before]**」または「**[!UICONTROL Insert Recommendations After]**」をクリックします。

   サイトへの訪問者には、レコメンデーションの対象となる場合にのみ、推奨コンテンツが表示されます。 レコメンデーションに該当しない訪問者には、デフォルトコンテンツが表示されます。

   ![Recommendations オプション](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   * **[!UICONTROL Replace w/ Recommendations]**：要素をレコメンデーションに置き換えると、現在のコンテンツが削除され、レコメンデーションに置き換えられます。 訪問者がサイトを訪問してレコメンデーションの対象になると、既存のコンテンツではなく、指定された領域に推奨アイテムが表示されます。
   * **[!UICONTROL Insert Recommendations Before]**：選択した要素の前にレコメンデーションを挿入すると、その要素の前にレコメンデーションのコンテンツが配置されます。 ページの構成に応じて、選択した要素の上または左にレコメンデーションが表示されます。
   * **[!UICONTROL Insert Recommendations After]**：選択した要素の後にレコメンデーションを挿入すると、その要素の後にレコメンデーションのコンテンツが配置されます。 ページの構成に応じて、選択した要素の下または右にレコメンデーションが表示されます。

   **[!UICONTROL Expand Selection]** オプションを使用すると、選択した場所（親コンテナ）を展開して、目的のページ要素を簡単に識別して含めることができます。

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

   ![「ページタイプを選択」オプション](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. 1 つ以上の[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を選択します。

   条件が、それぞれの情報を表示するカードとして表示されます。デフォルトでは、[!UICONTROL Select Criteria] 画面には、業種および前の手順で選択したページタイプと互換性のある条件が表示されます。 これらのオプションを変更すると、他の条件を表示できます。

   >[!NOTE]
   >
   >すべてのページですべての条件が正しく実行されるわけではありません。現在の品目／現在のカテゴリーのレコメンデーションと互換性を持たせるために、ページや mbox には `entity.id` か `entity.categoryId` を渡す必要があります。通常は、互換性のある条件のみを表示するようにします。ただし、互換性のない条件をアクティビティで使用できるようにする場合は、「**[!UICONTROL Compatible]**」チェックボックスをオフにします。 Recommendationsの設定（**[!UICONTROL Recommendations]**/**[!UICONTROL Settings]**/**[!UICONTROL Filter Incompatible Criteria]**）によっては、「[!UICONTROL Compatible]」オプションが表示されない場合があります。 詳しくは、[ 設定 ](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} を参照してください。

   ![条件を選択ダイアログボックス](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   複数の条件を選択すると、トラフィックは選択した条件間で等しく分割されます。例えば、2 つの条件が選択されており、アクティビティ参加者の 20％にデフォルトコンテンツを表示するようにアクティビティがデザインされている場合、各条件によって制御されるレコメンデーションがアクティビティ参加者の 40％に表示されます。各条件の割合を変更するオプションはありません。

   * 既存の条件（たとえば、多数の条件カードが表示されている場合など）を検索するには、目的の条件が表示されるまで検索フィールドに入力し、条件を選択して [**[!UICONTROL Next]**] をクリックします。

     [!DNL Recommendations] によって提供される条件もあります。カスタムの条件を作成することも可能です。

   * 新しい条件を作成するには、**[!UICONTROL Create Criteria]**/**[!UICONTROL Create Criteria]** をクリックし、新しい条件の情報を入力します。 新しい条件の作成について詳しくは、[条件の作成](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)を参照してください。
   * また、条件をシーケンスにグループ化することもできます。新しい条件シーケンスを作成するには、**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]** をクリックします。 詳しくは、[ 条件シーケンスを作成 ](/help/main/c-recommendations/c-algorithms/create-criteria-sequence.md) を参照してください。

1. **[!UICONTROL Next]** をクリックします。
1. [デザイン](/help/main/c-recommendations/c-design-overview/design-overview.md)を選択します。

   デザインとは、ページ上の場所の表示方法を決めるテンプレートです。[!DNL Target] には、事前設定済みのデザインがいくつか含まれています。 カスタムのデザインを作成することも可能です。詳しくは、[ デザインの作成 ](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14) および [ デザインのカスタマイズ ](/help/main/c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59) を参照してください。

   ![デザインを選択ダイアログボックス](/help/main/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   各デザインには、見え方のグラフィカル表示と、現在そのデザインで使用されているライブアクティビティおよび非アクティブなアクティビティの数を示すアイコンが表示されます。

   * 既存のデザインを 1 つ以上選択するには、デザインをクリックしてから **[!UICONTROL Next]** をクリックします。

     複数の条件を選択した場合は、1 つのデザインのみ選択できます。

   * カスタムデザインを作成するには、「**[!UICONTROL Create Design]**」をクリックして、新しいデザインの名前とコードを入力します。 「**[!UICONTROL Next]**」をクリックし、画像を選択またはアップロードして、**[!UICONTROL Done]**/**[!UICONTROL Done]** をクリックします。 新しいデザインの作成について詳しくは、[デザインの作成](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14)を参照してください。

1. **[!UICONTROL Next]** をクリックします。

   レコメンデーションにプロモーションを追加することもできます。前後の販促の追加の詳細は、「[ 販促の追加 ](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)」を参照してください。

1. **[!UICONTROL Save]** をクリックします。

   VEC 画面に、ページのレコメンデーションデザインが表示されます。

1. （任意）「**[!UICONTROL Preview]**」をクリックして、訪問者にアクティビティがどのように表示されるかを確認します。

   [!UICONTROL Preview] モードを使用すると、訪問者と同じように、レコメンデーションを操作できます。

   お勧めのプレビューが完了したら、「**[!UICONTROL Compose]**」をクリックします。

1. VEC でレコメンデーションを確認し、「**[!UICONTROL Next]**」をクリックします。

1. フロー図で [!DNL Recommendations] アクティビティを確認し、必要に応じて変更します。

   ![Recommendations フロー図](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   フロー図を使用すると、アクティビティに対するオーディエンスの選択、エクスペリエンスの設定、成功指標の指定の手順を順に実行できます。

   フロー図から、次のことを実行できます。

   * レコメンデーションが表示されるオーディエンスを変更する

     >[!NOTE]
     >
     >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、[アクティビティのみのオーディエンスを作成](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)したり、[複数のオーディエンスを結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)してアドホックな結合オーディエンスを作成することができます。

     デフォルトでは、すべてのユーザーにレコメンデーションが表示されますが、レコメンデーションの対象を特定のオーディエンスのみにすることもできます。

     [!DNL Recommendations] アクティビティでは、制御グループはレコメンデーションなしでページが表示されます。

   * 条件を表示します。
   * コレクション（[!UICONTROL Criteria] ラベルの横）を変更します
   * コントロールエクスペリエンスを表示する参加者の割合を変更します。
   * デザインコードを表示します。
   * デザインを変更または削除します。

1. 終了したら「**[!UICONTROL Next]**」をクリックします。
1. アクティビティを設定します。

   例えば、アクティビティの名前（必須）および目標（任意）を入力します。この設定について詳しくは、[Recommendations アクティビティの設定 ](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB) を参照してください。

   >[!NOTE]
   >
   >[!DNL Recommendations Classic] の別のアクティビティとして既に存在する [!DNL Recommendation] アクティビティ名を指定すると、新しいアクティビティは、新しい名前で再同期されます。新しい名前は、一意なものにするために、元の名前にタイムスタンプが追加されたものになります。この新しい名前は、[!DNL Target Standard/Premium] と [!DNL Recommendations Classic] の両方で表示されます。

1. 終了したら、「**[!UICONTROL Save & Close]**」をクリックします。

   アクティビティの概要が表示されます。

   [!UICONTROL Overview] ページから、次の操作を実行できます。

   * アクティビティをアクティブ化します。
   * アクティビティを編集します。
   * アクティビティをExperience Cloudフィードに共有
   * アクティビティの QA
   * エクスペリエンスの URL を表示します。
   * データをダウンロードします。
   * コントロールエクスペリエンスを表示するアクティビティ参加者の割合を変更します。
   * キャンペーンの詳細情報の表示や非表示をおこないます。
   * デザインのコードを表示します。

1. （オプション） [!UICONTROL Reports] のページを開いて、[!DNL Recommendations] アクティビティのパフォーマンスを示すレポートを表示します。

1. （オプション） [!UICONTROL Collisions] ページを開いて、発生する可能性のある [ アクティビティの衝突 ](/help/main/c-experiences/c-visual-experience-composer/activity-collisions.md) を表示します。

   複数のアクティビティから同一のページにコンテンツが配信されるように設定されている場合に、アクティビティの衝突が発生します。その場合、予期しないコンテンツが表示されることがあります。

## トレーニングビデオ：Recommendations アクティビティの作成（7:15） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/27688)