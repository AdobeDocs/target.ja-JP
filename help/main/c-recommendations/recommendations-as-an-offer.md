---
keywords: Recommendations;オファー
description: A/B テスト（自動配分と自動ターゲットを含む）およびエクスペリエンスのターゲット設定（XT）アクティビティで、オファーとして Adobe Recommendations を使用する方法を説明します。
title: Recommendations を他のアクティビティタイプでオファーとして使用するにはどうすればよいですか。
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: ht
source-wordcount: '556'
ht-degree: 100%

---

# ![PREMIUM](/help/main/assets/premium.png) オファーとしての Recommendations

[!UICONTROL A/B テスト]（[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット]を含む）および[!UICONTROL エクスペリエンスのターゲット設定]（XT）アクティビティに Recommendations を含めることができるようになりました。

この機能により、次のようなことがおこなえるようになります。

* 同じアクティビティ内の Recommendations と非 Recommendations のコンテンツをテストおよびターゲット設定します。
* 複数の Recommendations の順序など、Recommendations のページ配置を簡単に試行します。
* [!UICONTROL 自動配分]を使用して、パフォーマンスが最も高い Recommendations エクスペリエンスにトラフィックを自動的にプッシュします。
* [!UICONTROL 自動ターゲット]を使用して、訪問者をプロファイルに基づいて詳細にカスタマイズされた Recommendations エクスペリエンスに動的に割り当てます。

開始するには、 [!UICONTROL A/B テスト]または [!UICONTROL エクスペリエンスのターゲット設定]アクティビティを [!UICONTROL Visual Experience Composer] を使用して作成し、[!UICONTROL 前に挿入]、[!UICONTROL 後ろに挿入]、または [!UICONTROL 次で置換]アクションを使用して Recommendations をエクスペリエンスに追加します。

## Recommendations をオファーとして A/B テストまたは XT アクティビティに追加する

1. [A/B テスト](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)または[エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)（XT）アクティビティを作成するには、Visual Experience Composer（VEC）を使用して 3 ステップのガイドによるワークフローを開始します。

   >[!NOTE]
   >
   >A/B テストの場合、パフォーマンスが最も高い Recommendations にトラフィックを自動的にプッシュする[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)オプション、または訪問者をプロファイルに基づいて詳細にカスタマイズされた Recommendations エクスペリエンスに動的に割り当てる[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) オプションを選択できます。

1. [エクスペリエンス](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)の作成中に、Recommendations をオファーとして追加する要素をクリックして、**[!UICONTROL 前に挿入]**、**[!UICONTROL 後ろに挿入]**、または&#x200B;**[!UICONTROL 次で置換]**&#x200B;アクションを選択してから、[!UICONTROL Recommendation] を選択します。

   次の図に、[!UICONTROL 後ろに挿入／Recommendation] オプションを示します。

   ![Recommendations をオファーとして挿入](/help/main/c-recommendations/assets/replace-after-recommendations.png)

1. ページタイプ別の一般的な Recommendations 条件を表示するには、次のオプションから選択します。

   * 買い物かごページ
   * カテゴリページ
   * ホームページ
   * ランディングページ
   * 製品紹介ページ
   * 検索結果ページ
   * 「ありがとうございます」ページ
   * その他

1. 希望する[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を選択してから、「[!UICONTROL 次へ]」をクリックします。
1. 希望する[デザイン](/help/main/c-recommendations/c-design-overview/design-overview.md)を選択してから、「[!UICONTROL 次へ]」をクリックします。
1. [!UICONTROL オプション]ダイアログボックスで、以下を指定します。

   * [コレクション](/help/main/c-recommendations/c-products/collections.md)を選択します。
   * 必要に応じて、[プロモーション - 前とプロモーション - 後](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)オプションを設定します。

1. 「[!UICONTROL 保存]」をクリックします。
1. 3 ステップのガイドによるワークフローを使用して、A/B テストまたは XT アクティビティの設定を完了します。

## Recommendations オファーの設定の編集

オファーの設定を編集するには、次の 2 つの方法があります。

* [!UICONTROL 編集]メニューの使用
* [!UICONTROL 変更]パネルの使用

### 編集メニューを使用した Recommendations オファーの編集

1. 編集するオファーをクリックし、「**[!UICONTROL 編集]**」をクリックします。

   ![Recommendations オファーの編集](/help/main/c-recommendations/assets/recs-offer-edit.png)

1. 次のオプションから選択します。

   * [条件を変更](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [デザインを変更](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [コレクションを変更](/help/main/c-recommendations/c-products/collections.md)
   * [プロモーションを変更](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. 編集をおこないます。

### 変更パネルを使用した Recommendations オファーの編集

1. [!UICONTROL 変更]アイコン **（`</>`）** をクリックして、[変更](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)パネルを表示します。
1. 目的のアクションの上にマウスポインターを置いて、**[!UICONTROL 編集]**&#x200B;アイコンをクリックします。

   ![変更パネル](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. 編集をおこないます。

## Recommendations オファーの削除

Recommendations オファーを削除するには、次の 2 つの方法があります。

* [!UICONTROL 編集]メニューの使用
* [!UICONTROL 変更]パネルの使用

### 編集メニューを使用した Recommendations オファーの削除

1. 削除するオファーをクリックし、**[!UICONTROL レイアウト／削除]**&#x200B;をクリックします。

   ![削除](/help/main/c-recommendations/assets/recs-offer-remove.png)

### 変更パネルを使用した Recommendations オファーの削除

1. [!UICONTROL 変更]アイコン&#x200B;**（&lt;/>）**&#x200B;をクリックして、[変更](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)パネルを表示します。
1. 目的のアクションの上にマウスポインターを置いて、[!UICONTROL 削除]アイコンをクリックします。

   ![削除アイコン](/help/main/c-recommendations/assets/recs-offer-delete.png)

### Recommendations オファーのステータスの表示 {#status}

Recommendations オファーの（アルゴリズム）ステータスは、Recommendations オファーを含む A/B テストおよび XT アクティビティの[!UICONTROL 概要]ページの下部に表示されます。

* 結果の準備ができました
* 結果の準備ができていません
* フィードエラー

![Recommendations オファーステータス](/help/main/c-recommendations/assets/recs-offer-status.png)

## トレーニングビデオ：オファーとしての Recommendations![概要バッジ](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
