---
keywords: レコメンデーションの作成;レコメンデーションのアクティビティ;新しいレコメンデーション;レコメンデーションの概要
description: ' [!DNL Target] [!UICONTROL Visual Experience Composer] （VEC）を使用して [!DNL Recommendations]  アクティビティを作成する方法を説明します。'
title: ' [!DNL Recommendations]  アクティビティを作成するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: c83073d5-f852-4f09-8343-e4658fbf6f43
TQID: https://experienceleague.adobe.com/rb9any1dsbk-E-ELV56A2D6X5f0z0cTziscrajmbYDA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1302
ht-degree: 54%

---

# [!DNL Recommendations] アクティビティの作成

[!DNL Target] [!UICONTROL Visual Experience Composer] （VEC）を使用して、[!DNL Target]対応ページで[!DNL Recommendations] アクティビティを直接作成し、[!DNL Target]内のページの一部を変更します。

1. **[!UICONTROL アクティビティ]**/**[!UICONTROL アクティビティの作成]**/**[!UICONTROL Recommendations]**&#x200B;をクリックします。

1. 必要に応じて、**[!UICONTROL Visual]**&#x200B;を選択します。

   [!UICONTROL &#x200B; フォームベースのExperience Composer]を使用する場合は、[!UICONTROL Form]を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VECおよび[!UICONTROL &#x200B; フォームベースのExperience Composer]に加えて、[!DNL Target]は[!UICONTROL 単一ページアプリケーション &#x200B;]VECを提供しています。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き） [&#x200B; ワークスペース &#x200B;](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)を選択します。

1. アクティビティ URLを指定し、**[!UICONTROL 作成]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。 結果、[!DNL `http://www.adobe.com`]と[!DNL `https://wwww.adobe.com`]は両方とも一致します。

   アクティビティ URLは、レコメンデーションが表示されるページです。

   [!UICONTROL 作成]をクリックすると、VECが開き、ページが表示されます。 現在の要素をレコメンデーションで置き換えたり、レコメンデーションを挿入したりすることができます。

1. ページ上の要素をクリックすると、その要素が配置されている場所でレコメンデーションが使用できる場合は、**[!UICONTROL レコメンデーションと置換]**、**[!UICONTROL レコメンデーションの挿入]**、または&#x200B;**[!UICONTROL レコメンデーションの挿入]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >[!UICONTROL Recommendations]のアクティビティでは、一度に1つの変更/レコメンデーションのみがサポートされます。 複数のレコメンデーションの場合は、複数の[!DNL Recommendations] アクティビティを作成するか、A/B テストまたはXT テストを使用できます。

   サイトへの訪問者は、レコメンデーションの対象となる場合にのみ、レコメンデーションされたコンテンツを表示します。 レコメンデーションの対象ではない訪問者には、デフォルトコンテンツが表示されます。

   ![レコメンデーションオプション](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   * **[!UICONTROL 推奨事項を含む置換]**：要素を推奨事項に置き換えると、現在のコンテンツが削除され、推奨事項に置き換えられます。 訪問者がサイトにアクセスし、レコメンデーションの対象となった場合、既存のコンテンツではなく、指定した領域に推奨項目が表示されます。
   * **[!UICONTROL 推奨事項を挿入]**：選択した要素の前に推奨事項を挿入すると、その要素の前に推奨コンテンツが配置されます。 ページ構成に応じて、レコメンデーションは選択した要素の上または左に表示されます。
   * **[!UICONTROL 推奨事項の挿入後]**：選択した要素の後に推奨事項を挿入すると、その要素の後に推奨コンテンツが配置されます。 ページ構成に応じて、選択した要素の下または右に推奨事項が表示されます。

   「**[!UICONTROL 選択範囲を拡張]**」オプションを使用すると、選択した場所（親コンテナ）を拡張して、目的のページ要素をより簡単に識別して含めることができます。

1. ページタイプを選択します。

   ページタイプには、以下が含まれます。

   * 買い物かごページ
   * カテゴリページ
   * ホームページ
   * ランディングページ
   * 製品ページ
   * 検索結果ページ
   * 「ありがとうございます」ページ
   * その他

   ![「ページタイプを選択」オプション](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. 1 つ以上の[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を選択します。

   条件が、それぞれの情報を表示するカードとして表示されます。 デフォルトでは、[!UICONTROL 条件を選択]画面には、業界の業種と互換性のある条件と、前の手順で選択したページタイプが表示されます。 これらのオプションを変更すると、他の条件を表示できます。

   >[!NOTE]
   >
   >すべてのページですべての条件が正しく実行されるわけではありません。 現在の品目／現在のカテゴリーのレコメンデーションと互換性を持たせるために、ページや mbox には `entity.id` か `entity.categoryId` を渡す必要があります。 通常は、互換性のある条件のみを表示するようにします。 ただし、アクティビティで互換性のない条件を有効にしたい場合は、「**[!UICONTROL 互換性あり]**」チェックボックスのチェックを外します。 Recommendationsの設定（**[!UICONTROL Recommendations]** > **[!UICONTROL Settings]** > **[!UICONTROL 互換性のない条件をフィルター]**）によっては、[!UICONTROL 互換性] オプションが表示されない場合があります。 詳しくは、[設定](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=ja){target=_blank}を参照してください。

   ![条件を選択ダイアログボックス](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   複数の条件を選択すると、トラフィックは選択した条件間で等しく分割されます。 例えば、2 つの条件が選択されており、アクティビティ参加者の 20％にデフォルトコンテンツを表示するようにアクティビティがデザインされている場合、各条件によって制御されるレコメンデーションがアクティビティ参加者の 40％に表示されます。 各条件の割合を変更するオプションはありません。

   * 既存の条件を検索するには（たとえば、多数の条件カードが表示されている場合など）、目的の条件が表示されるまで検索フィールドに入力し、条件を選択して「**[!UICONTROL 次へ]**」をクリックします。

     [!DNL Recommendations] によって提供される条件もあります。 カスタムの条件を作成することも可能です。

   * 新しい条件を作成するには、**[!UICONTROL 条件を作成]** > **[!UICONTROL 条件を作成]**&#x200B;をクリックし、新しい条件の情報を入力します。 新しい条件の作成について詳しくは、[条件の作成](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)を参照してください。
   * また、条件をシーケンスにグループ化することもできます。 新しい条件シーケンスを作成するには、**[!UICONTROL 条件を作成]** > **[!UICONTROL 条件シーケンスを作成]**&#x200B;をクリックします。 詳しくは、[条件シーケンスの作成](/help/main/c-recommendations/c-algorithms/create-criteria-sequence.md)を参照してください。

1. 「**[!UICONTROL 次へ]**」をクリックします。
1. [デザイン](/help/main/c-recommendations/c-design-overview/design-overview.md)を選択します。

   デザインとは、ページ上の場所の表示方法を決めるテンプレートです。 [!DNL Target]には、事前に設定された複数のデザインが含まれています。 カスタムのデザインを作成することも可能です。 詳細については、[&#x200B; デザインの作成](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14)および[&#x200B; デザインのカスタマイズ &#x200B;](/help/main/c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59)を参照してください。

   ![デザインを選択ダイアログボックス](/help/main/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   各デザインには、見え方のグラフィカル表示と、現在そのデザインで使用されているライブアクティビティおよび非アクティブなアクティビティの数を示すアイコンが表示されます。

   * 1つ以上の既存のデザインを選択するには、デザインをクリックし、**[!UICONTROL 次へ]**&#x200B;をクリックします。

     複数の条件を選択した場合は、1 つのデザインのみ選択できます。

   * カスタムデザインを作成するには、「**[!UICONTROL デザインを作成]**」をクリックし、新しいデザインの名前とコードを入力します。 「**[!UICONTROL 次へ]**」をクリックし、画像を選択またはアップロードして&#x200B;**[!UICONTROL 完了]**／**[!UICONTROL 完了]**&#x200B;をクリックします。 新しいデザインの作成について詳しくは、[デザインの作成](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14)を参照してください。

1. 「**[!UICONTROL 次へ]**」をクリックします。

   レコメンデーションにプロモーションを追加することもできます。 前面および背面のプロモーションの追加について詳しくは、[&#x200B; プロモーションの追加](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)を参照してください。

1. 「**[!UICONTROL 保存]**」をクリックします。

   VEC 画面に、ページのレコメンデーションデザインが表示されます。

1. （オプション）「**[!UICONTROL プレビュー]**」をクリックして、アクティビティが訪問者にどのように表示されるかを確認します。

   [!UICONTROL プレビュー]モードを使用すると、訪問者と同様にレコメンデーションを操作できます。

   レコメンデーションのプレビューを完了したら、「**[!UICONTROL 作成]**」をクリックします。

1. VECで推奨事項を確認し、**[!UICONTROL 次へ]**&#x200B;をクリックします。

1. フロー図で [!DNL Recommendations] アクティビティを確認し、必要に応じて変更します。

   ![レコメンデーションフロー図](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   フロー図を使用すると、アクティビティに対するオーディエンスの選択、エクスペリエンスの設定、成功指標の指定の手順を順に実行できます。

   フロー図から、次のことを実行できます。

   * レコメンデーションが表示されるオーディエンスを変更する

     >[!NOTE]
     >
     >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、[アクティビティのみのオーディエンスを作成](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)したり、[複数のオーディエンスを結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)してアドホックな結合オーディエンスを作成することができます。

     デフォルトでは、すべてのユーザーにレコメンデーションが表示されますが、 レコメンデーションの対象を特定のオーディエンスのみにすることもできます。

     [!DNL Recommendations] アクティビティでは、制御グループはレコメンデーションなしでページが表示されます。

   * 条件を表示します。
   * コレクションを変更します（「[!UICONTROL 条件]」ラベルの横）。
   * コントロールエクスペリエンスを表示する参加者の割合を変更します。
   * デザインコードを表示します。
   * デザインを変更または削除します。

1. 終了したら「**[!UICONTROL 次へ]**」をクリックします。
1. アクティビティを設定します。

   例えば、アクティビティの名前（必須）および目標（任意）を入力します。 設定について詳しくは、[Recommendations アクティビティ設定](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)を参照してください。

   >[!NOTE]
   >
   >[!DNL Recommendations Classic] の別のアクティビティとして既に存在する [!DNL Recommendation] アクティビティ名を指定すると、新しいアクティビティは、新しい名前で再同期されます。 新しい名前は、一意なものにするために、元の名前にタイムスタンプが追加されたものになります。 この新しい名前は、[!DNL Target Standard/Premium] と [!DNL Recommendations Classic] の両方で表示されます。

1. 完了したら、**[!UICONTROL 保存して閉じる]**&#x200B;をクリックします。

   アクティビティの概要が表示されます。

   [!UICONTROL 概要]ページから、次のことを実行できます。

   * アクティビティをアクティブ化します。
   * アクティビティを編集します。
   * Experience Cloud フィードへのアクティビティの共有
   * アクティビティのQA
   * エクスペリエンスの URL を表示します。
   * データをダウンロードします。
   * コントロールエクスペリエンスを表示するアクティビティ参加者の割合を変更します。
   * キャンペーンの詳細情報の表示や非表示をおこないます。
   * デザインのコードを表示します。

1. （オプション）「[!UICONTROL &#x200B; レポート &#x200B;]」ページを開き、[!DNL Recommendations] アクティビティのパフォーマンスを示すレポートを表示します。

1. （オプション）発生する可能性のある[&#x200B; アクティビティの衝突](/help/main/c-experiences/c-visual-experience-composer/activity-collisions.md)を表示するには、[!UICONTROL 衝突] ページを開きます。

   複数のアクティビティから同一のページにコンテンツが配信されるように設定されている場合に、アクティビティの衝突が発生します。その場合、予期しないコンテンツが表示されることがあります。

## トレーニングビデオ：Recommendations アクティビティの作成（7:15） ![&#x200B; チュートリアルバッジ &#x200B;](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/27688)
