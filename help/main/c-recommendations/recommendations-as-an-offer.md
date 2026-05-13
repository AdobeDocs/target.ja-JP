---
keywords: レコメンデーション;オファー
description: A/B テスト（自動配分と自動ターゲットを含む）およびエクスペリエンスのターゲット設定（XT）アクティビティで、オファーとして Adobe レコメンデーションを使用する方法を説明します。
title: レコメンデーションを他のアクティビティタイプでオファーとして使用するにはどうすればよいですか。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
TQID: https://experienceleague.adobe.com/ZMOb5RdY6bES331INSM7VF-w4be-5Xmjqon0YvfuNG4
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 525
ht-degree: 69%

---

# オファーとしてのレコメンデーション

[!UICONTROL A/B Test]（[!UICONTROL Auto-Allocate] と [!UICONTROL Auto-Target] を含む）アクティビティおよび [!UICONTROL Experience Targeting]（XT）アクティビティにレコメンデーションを含めることができるようになりました。

この機能により、次のようなことがおこなえるようになります。

* 同じアクティビティ内のレコメンデーションと非レコメンデーションのコンテンツをテストおよびターゲット設定します。
* 複数のレコメンデーションの順序など、レコメンデーションのページ配置を簡単に試行します。
* [!UICONTROL Auto-Allocate] を使用して、トラフィックをパフォーマンスの高いレコメンデーションエクスペリエンスに自動的にプッシュします。
* [!UICONTROL Auto-Target]を使用して、プロファイルに基づいて、カスタマイズされたレコメンデーション エクスペリエンスに訪問者を動的に割り当てます。

開始するには、[!UICONTROL Visual Experience Composer]を使用して[!UICONTROL A/B Test]または[!UICONTROL Experience Targeting] アクティビティを作成し、[!UICONTROL Insert Before]、[!UICONTROL Insert After]または[!UICONTROL Replace With] アクションを使用して、エクスペリエンスに推奨事項を追加します。

## Recommendations をオファーとして A/B テストまたは XT アクティビティに追加する

1. [A/B テスト](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)または[エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)（XT）アクティビティを作成するには、Visual Experience Composer（VEC）を使用して 3 ステップのガイドによるワークフローを開始します。

   >[!NOTE]
   >
   >A/B テストの場合、パフォーマンスが最も高いレコメンデーションにトラフィックを自動的にプッシュする[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)オプション、または訪問者をプロファイルに基づいて詳細にカスタマイズされたレコメンデーションエクスペリエンスに動的に割り当てる[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)オプションを選択できます。

1. [&#x200B; エクスペリエンス &#x200B;](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を作成する際に、オファーとしてレコメンデーションを追加する要素をクリックし、**[!UICONTROL Replace Content]**&#x200B;をクリックしてから、**[!UICONTROL Recommendation]**&#x200B;を選択します。

   ![Recommendations をオファーとして挿入](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. ページタイプ別の一般的なレコメンデーション条件を表示するには、次のオプションから選択します。

   * 買い物かごページ
   * カテゴリページ
   * ホームページ
   * ランディングページ
   * 製品ページ
   * 検索結果ページ
   * 「ありがとうございます」ページ
   * その他

1. 目的の[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を選択し、[!UICONTROL Next]をクリックします。
1. 目的の[&#x200B; デザイン &#x200B;](/help/main/c-recommendations/c-design-overview/design-overview.md)を選択し、[!UICONTROL Next]をクリックします。
1. [!UICONTROL Options] ダイアログボックスで、次の項目を指定します。

   * [コレクション](/help/main/c-recommendations/c-products/collections.md)を選択します。
   * 必要に応じて、[プロモーション - 前とプロモーション - 後](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)オプションを設定します。

1. [!UICONTROL Save] をクリックします。
1. 3 ステップのガイドによるワークフローを使用して、A/B テストまたは XT アクティビティの設定を完了します。

## レコメンデーションオファーの設定の編集

オファーの設定を編集するには、次の 2 つの方法があります。

* [!UICONTROL Edit] メニューの使用
* [!UICONTROL Modifications] パネルの使用

### 編集メニューを使用したレコメンデーションオファーの編集

1. 編集するオファーをクリックし、**[!UICONTROL Edit]**&#x200B;をクリックします。

   ![レコメンデーションオファーの編集](/help/main/c-recommendations/assets/recs-offer-edit.png)

1. 次のオプションから選択します。

   * [条件を変更](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [デザインを変更](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [コレクションを変更](/help/main/c-recommendations/c-products/collections.md)
   * [プロモーションを変更](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. 編集をおこないます。

### 変更パネルを使用したレコメンデーションオファーの編集

1. [!UICONTROL Modifications] アイコン **（`</>`）**&#x200B;をクリックして、[変更](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) ペインを表示します。
1. 目的のアクションにカーソルを合わせて、**[!UICONTROL Edit]** アイコンをクリックします。

   ![変更パネル](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. 編集をおこないます。

## レコメンデーションオファーの削除

レコメンデーションオファーを削除するには、次の 2 つの方法があります。

* [!UICONTROL Edit] メニューの使用
* [!UICONTROL Modifications] パネルの使用

### 編集メニューを使用したレコメンデーションオファーの削除

1. 削除するオファーをクリックし、**[!UICONTROL Layout > Remove]**&#x200B;をクリックします。

   ![削除](/help/main/c-recommendations/assets/recs-offer-remove.png)

### 変更パネルを使用したレコメンデーションオファーの削除

1. [!UICONTROL Modifications] アイコン **（&lt;/>）**&#x200B;をクリックして、[変更](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) ペインを表示します。
1. 目的のアクションにカーソルを合わせて、[!UICONTROL Delete] アイコンをクリックします。

   ![削除アイコン](/help/main/c-recommendations/assets/recs-offer-delete.png)

### レコメンデーションオファーのステータスの表示 {#status}

Recommendations オファー（アルゴリズム）のステータスは、Recommendations オファーを含むA/B テストおよびXT アクティビティの[!UICONTROL Overview] ページの下部に表示されます。

* 結果の準備ができました
* 結果の準備ができていません
* フィードエラー

![レコメンデーションオファーステータス](/help/main/c-recommendations/assets/recs-offer-status.png)

## トレーニングビデオ：オファーとしてのレコメンデーション![概要バッジ](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
