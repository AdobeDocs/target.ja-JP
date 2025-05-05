---
keywords: Recommendations;オファー
description: A/B テスト（自動配分と自動ターゲットを含む）およびエクスペリエンスのターゲット設定（XT）アクティビティで、オファーとして Adobe Recommendations を使用する方法を説明します。
title: Recommendations を他のアクティビティタイプでオファーとして使用するにはどうすればよいですか。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 3821d868f45b85d2f6f0e204f9828544b759067b
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 50%

---

# オファーとしての Recommendations 

[!UICONTROL A/B Test] （[!UICONTROL Auto-Allocate] と [!UICONTROL Auto-Target] を含む）アクティビティおよび [!UICONTROL Experience Targeting] （XT）アクティビティにレコメンデーションを含めることができるようになりました。

この機能により、次のようなことがおこなえるようになります。

* 同じアクティビティ内の Recommendations と非 Recommendations のコンテンツをテストおよびターゲット設定します。
* 複数のレコメンデーションの順序を含め、ページ上のレコメンデーションの配置を簡単に試すことができます。
* [!UICONTROL Auto-Allocate] を使用して、最もパフォーマンスの高いレコメンデーションエクスペリエンスにトラフィックを自動的にプッシュします。
* [!UICONTROL Auto-Target] を使用し、プロファイルに基づいて、カスタマイズされた Recommendations エクスペリエンスへと訪問者を動的に割り当てます。

開始するには、[!UICONTROL Visual Experience Composer] を使用して [!UICONTROL A/B Test] アクティビティまたは [!UICONTROL Experience Targeting] アクティビティを作成し、[!UICONTROL Recommend] アクションを使用してエクスペリエンスにレコメンデーションを追加します。

## Recommendations をオファーとして A/B テストまたは XT アクティビティに追加する

1. [A/B テスト](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)または[エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)（XT）アクティビティを作成するには、Visual Experience Composer（VEC）を使用して 3 ステップのガイドによるワークフローを開始します。

   >[!NOTE]
   >
   >A/B テストの場合、パフォーマンスが最も高い Recommendations にトラフィックを自動的にプッシュする[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)オプション、または訪問者をプロファイルに基づいて詳細にカスタマイズされた Recommendations エクスペリエンスに動的に割り当てる[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) オプションを選択できます。

1. [ エクスペリエンス ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) の作成中に、レコメンデーションをオファーとして追加する要素をクリックし、「**[!UICONTROL Replace Content]**」（![ コンテンツを置換アイコン ](/help/main/assets/icons/Switch.svg)）をクリックして、「**[!UICONTROL Recommendation]**」を選択します。

   ![Recommendations をオファーとして挿入](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. 右側の [!UICONTROL Recommendation] パネルで「**[!UICONTROL Select a Recommendation]**」をクリックして、「[!UICONTROL Select Criteria]」ダイアログボックスを表示します。

1. 「**[!UICONTROL Create Criteria]**」をクリックするか、既存の条件を選択します。

1. （オプション） **[!UICONTROL Filter]** アイコン（![ フィルターアイコン ](/help/main/assets/icons/Filter.svg)）をクリックして次のオプションから選択し、ページタイプ別の一般的なレコメンデーション条件を表示します。

   * 買い物かごページ
   * カテゴリページ
   * ホームページ
   * ランディングページ
   * 製品紹介ページ
   * 検索結果ページ
   * 「ありがとうございます」ページ
   * その他

1. 「**[!UICONTROL Create Criteria]**」をクリックするか、既存の [ 条件 ](/help/main/c-recommendations/c-algorithms/algorithms.md) を選択し、「**[!UICONTROL Next]**」をクリックして [!UICONTROL Select Design] 定ダイアログボックスを表示します。

1. 「**[!UICONTROL Create Design]**」をクリックするか、既存の [ デザイン ](/help/main/c-recommendations/c-design-overview/design-overview.md) を選択して、「**[!UICONTROL &#x200B; Next]**」をクリックします。

1. [!UICONTROL Options] ダイアログボックスで、次の設定を行います。

   * [コレクション](/help/main/c-recommendations/c-products/collections.md)を選択します。
   * 必要に応じて、[プロモーション - 前とプロモーション - 後](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)オプションを設定します。

1. **[!UICONTROL Save]** をクリックします。
1. 3 ステップのガイドによるワークフローを使用して、A/B テストまたは XT アクティビティの設定を完了します。

## Recommendations オファーの設定の編集

1. [!UICONTROL Recommendation] パネルで、[!UICONTROL Criteria Name]、[!UICONTROL Design Name]、[!UICONTROL Collection Name] の横にある **[!UICONTROL Edit]** アイコン ![ 編集アイコン ](/help/main/assets/icons/Edit.svg)）をクリックして、要素を変更します。

## Recommendations オファーの削除

1. [!UICONTROL Recommendation] パネルの上部にある **[!UICONTROL Delete]** アイコン ![ 削除アイコン ](/help/main/assets/icons/Delete.svg)）をクリックします。

### Recommendations オファーのステータスの表示 {#status}

Recommendations オファー（アルゴリズム）ステータスは、A/B テストと、Recommendations オファーを含む XT アクティビティについて、アクティビティの [!UICONTROL Overview] ページの下部に表示されます。

* 結果の準備ができました
* 結果の準備ができていません
* フィードエラー
