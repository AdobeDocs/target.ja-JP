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
source-wordcount: '419'
ht-degree: 52%

---

# オファーとしてのレコメンデーション

[!UICONTROL A/B Test] （[!UICONTROL Auto-Allocate]と[!UICONTROL Auto-Target]を含む）および[!UICONTROL Experience Targeting] （XT）アクティビティ内にレコメンデーションを含めることができるようになりました。

この機能により、次のようなことがおこなえるようになります。

* 同じアクティビティ内のレコメンデーションと非レコメンデーションのコンテンツをテストおよびターゲット設定します。
* 複数のレコメンデーションの順序など、ページ上のレコメンデーションの配置を簡単に試すことができます。
* [!UICONTROL Auto-Allocate] を使用して、トラフィックをパフォーマンスの高いレコメンデーションエクスペリエンスに自動的にプッシュします。
* [!UICONTROL Auto-Target]を使用して、プロファイルに基づいて、カスタマイズされたレコメンデーション エクスペリエンスに訪問者を動的に割り当てます。

開始するには、[!UICONTROL A/B Test]を使用して[!UICONTROL Experience Targeting]または[!UICONTROL Visual Experience Composer] アクティビティを作成し、[!UICONTROL Recommend] アクションを使用してエクスペリエンスに推奨事項を追加します。

## Recommendations をオファーとして A/B テストまたは XT アクティビティに追加する

1. [A/B テスト](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)または[エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)（XT）アクティビティを作成するには、Visual Experience Composer（VEC）を使用して 3 ステップのガイドによるワークフローを開始します。

   >[!NOTE]
   >
   >A/B テストの場合、パフォーマンスが最も高いレコメンデーションにトラフィックを自動的にプッシュする[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)オプション、または訪問者をプロファイルに基づいて詳細にカスタマイズされたレコメンデーションエクスペリエンスに動的に割り当てる[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)オプションを選択できます。

1. [ エクスペリエンス ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を作成する際に、オファーとしてレコメンデーションを追加する要素をクリックし、**[!UICONTROL Replace Content]** （![ コンテンツアイコンを置換](/help/main/assets/icons/Switch.svg)）をクリックしてから、**[!UICONTROL Recommendation]**&#x200B;を選択します。

   ![Recommendations をオファーとして挿入](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. 右側の[!UICONTROL Recommendation] パネルから、**[!UICONTROL Select a Recommendation]**&#x200B;をクリックして[!UICONTROL Select Criteria] ダイアログボックスを表示します。

1. **[!UICONTROL Create Criteria]**&#x200B;をクリックするか、既存の条件を選択してください。

1. （オプション） **[!UICONTROL Filter]** アイコン （![ フィルターアイコン ](/help/main/assets/icons/Filter.svg)）をクリックして、次のオプションから選択し、ページのタイプ別に一般的なレコメンデーション条件を表示します。

   * 買い物かごページ
   * カテゴリページ
   * ホームページ
   * ランディングページ
   * 製品ページ
   * 検索結果ページ
   * 「ありがとうございます」ページ
   * その他

1. **[!UICONTROL Create Criteria]**&#x200B;をクリックするか、既存の[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を選択してから、**[!UICONTROL Next]**&#x200B;をクリックして[!UICONTROL Select Design] ダイアログボックスを表示します。

1. **[!UICONTROL Create Design]**&#x200B;をクリックするか、既存の[ デザイン ](/help/main/c-recommendations/c-design-overview/design-overview.md)を選択してから、**[!UICONTROL  Next]**&#x200B;をクリックします。

1. [!UICONTROL Options] ダイアログボックスで、次の項目を指定します。

   * [コレクション](/help/main/c-recommendations/c-products/collections.md)を選択します。
   * 必要に応じて、[プロモーション - 前とプロモーション - 後](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)オプションを設定します。

1. **[!UICONTROL Save]** をクリックします。
1. 3 ステップのガイドによるワークフローを使用して、A/B テストまたは XT アクティビティの設定を完了します。

## レコメンデーションオファーの設定の編集

1. [!UICONTROL Recommendation] パネルで、**[!UICONTROL Edit]**、![、または](/help/main/assets/icons/Edit.svg)の横にある[!UICONTROL Criteria Name] アイコン（[!UICONTROL Design Name]編集アイコン [!UICONTROL Collection Name]）をクリックして、要素を変更します。

## レコメンデーションオファーの削除

1. **[!UICONTROL Delete]** パネルの上部にある![ アイコン（](/help/main/assets/icons/Delete.svg)削除アイコン [!UICONTROL Recommendation]）をクリックします。

### レコメンデーションオファーのステータスの表示 {#status}

Recommendations オファー（アルゴリズム）のステータスは、A/B テストおよびRecommendations オファーを含むXT アクティビティのアクティビティの[!UICONTROL Overview] ページの下部に表示されます。

* 結果の準備ができました
* 結果の準備ができていません
* フィードエラー
