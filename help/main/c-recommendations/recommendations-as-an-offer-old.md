---
keywords: レコメンデーション;オファー
description: A/B テスト（自動配分と自動ターゲットを含む）およびエクスペリエンスのターゲット設定（XT）アクティビティで、オファーとして Adobe レコメンデーションを使用する方法を説明します。
title: レコメンデーションを他のアクティビティタイプでオファーとして使用するにはどうすればよいですか。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: f6034e83564a9a386e21e4e57279c66cc3c94537
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 46%

---

# オファーとしてのレコメンデーション

[!UICONTROL A/B テスト &#x200B;] （[!UICONTROL 自動割り当て]および[!UICONTROL 自動ターゲット &#x200B;]を含む）および[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （XT）アクティビティ内に推奨事項を含めることができるようになりました。

この機能により、次のようなことがおこなえるようになります。

* 同じアクティビティ内のレコメンデーションと非レコメンデーションのコンテンツをテストおよびターゲット設定します。
* 複数のレコメンデーションの順序など、ページ上のレコメンデーションの配置を簡単に試すことができます。
* [!UICONTROL 自動配分]を使用して、最もパフォーマンスの高いレコメンデーションエクスペリエンスにトラフィックを自動的にプッシュします。
* [!UICONTROL 自動ターゲット &#x200B;]を使用して、プロファイルに基づいてカスタマイズされたレコメンデーションエクスペリエンスに訪問者を動的に割り当てます。

開始するには、[!UICONTROL Visual Experience Composer]を使用して[!UICONTROL A/B テスト &#x200B;]または[!UICONTROL Experience Targeting] アクティビティを作成し、[!UICONTROL おすすめ] アクションを使用してエクスペリエンスに推奨事項を追加します。

## Recommendations をオファーとして A/B テストまたは XT アクティビティに追加する

1. [A/B テスト](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)または[エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)（XT）アクティビティを作成するには、Visual Experience Composer（VEC）を使用して 3 ステップのガイドによるワークフローを開始します。

   >[!NOTE]
   >
   >A/B テストの場合、パフォーマンスが最も高いレコメンデーションにトラフィックを自動的にプッシュする[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)オプション、または訪問者をプロファイルに基づいて詳細にカスタマイズされたレコメンデーションエクスペリエンスに動的に割り当てる[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)オプションを選択できます。

1. [&#x200B; エクスペリエンス &#x200B;](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を作成する際に、レコメンデーションをオファーとして追加する要素をクリックし、**[!UICONTROL コンテンツの置換]** （![&#x200B; コンテンツの置換アイコン &#x200B;](/help/main/assets/icons/Switch.svg)）をクリックしてから、**[!UICONTROL Recommendation]**&#x200B;を選択します。

   ![Recommendations をオファーとして挿入](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. 右側の[!UICONTROL Recommendation] パネルから、**[!UICONTROL Recommendation]**&#x200B;を選択をクリックして、[!UICONTROL 条件を選択] ダイアログボックスを表示します。

1. **[!UICONTROL 条件を作成]**&#x200B;をクリックするか、既存の条件を選択します。

1. （オプション） **[!UICONTROL フィルター]** アイコン （![&#x200B; フィルターアイコン &#x200B;](/help/main/assets/icons/Filter.svg)）をクリックして、次のオプションから選択し、ページタイプ別の一般的なレコメンデーション条件を表示します。

   * 買い物かごページ
   * カテゴリページ
   * ホームページ
   * ランディングページ
   * 製品ページ
   * 検索結果ページ
   * 「ありがとうございます」ページ
   * その他

1. **[!UICONTROL 条件を作成]**&#x200B;をクリックするか、既存の[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を選択してから、**[!UICONTROL 次へ]**&#x200B;をクリックして[!UICONTROL &#x200B; デザインを選択] ダイアログボックスを表示します。

1. **[!UICONTROL デザインを作成]**&#x200B;をクリックするか、既存の[&#x200B; デザイン &#x200B;](/help/main/c-recommendations/c-design-overview/design-overview.md)を選択してから、**[!UICONTROL 次へ]**&#x200B;をクリックします。

1. [!UICONTROL &#x200B; オプション &#x200B;] ダイアログボックスで、次の項目を指定します。

   * [コレクション](/help/main/c-recommendations/c-products/collections.md)を選択します。
   * 必要に応じて、[プロモーション - 前とプロモーション - 後](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)オプションを設定します。

1. 「**[!UICONTROL 保存]**」をクリックします。
1. 3 ステップのガイドによるワークフローを使用して、A/B テストまたは XT アクティビティの設定を完了します。

## レコメンデーションオファーの設定の編集

1. [!UICONTROL Recommendation] レールから、[!UICONTROL 条件名]、[!UICONTROL &#x200B; デザイン名]、[!UICONTROL &#x200B; コレクション名]の横にある&#x200B;**[!UICONTROL 編集]** アイコン （![編集アイコン &#x200B;](/help/main/assets/icons/Edit.svg)）をクリックして、要素を変更します。

## レコメンデーションオファーの削除

1. [!UICONTROL Recommendation] パネルの上部にある&#x200B;**[!UICONTROL 削除]** アイコン （![削除アイコン &#x200B;](/help/main/assets/icons/Delete.svg)）をクリックします。

### レコメンデーションオファーのステータスの表示 {#status}

Recommendations オファー（アルゴリズム）のステータスは、A/B テストおよびRecommendations オファーを含むXT アクティビティのアクティビティの[!UICONTROL 概要] ページの下部に表示されます。

* 結果の準備ができました
* 結果の準備ができていません
* フィードエラー
