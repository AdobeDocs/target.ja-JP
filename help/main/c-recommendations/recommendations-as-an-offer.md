---
keywords: Recommendations;オファー
description: A/B テスト（自動配分と自動ターゲットを含む）およびエクスペリエンスのターゲット設定（XT）アクティビティで、オファーとして Adobe Recommendations を使用する方法を説明します。
title: Recommendations を他のアクティビティタイプでオファーとして使用するにはどうすればよいですか。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
source-git-commit: f848c79cb95009b5810a1707d04e548a57220e12
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 64%

---

#  オファーとしての Recommendations 

[!UICONTROL A/B Test] （[!UICONTROL Auto-Allocate] と [!UICONTROL Auto-Target] を含む）アクティビティおよび [!UICONTROL Experience Targeting] （XT）アクティビティにレコメンデーションを含めることができるようになりました。

この機能により、次のようなことがおこなえるようになります。

* 同じアクティビティ内の Recommendations と非 Recommendations のコンテンツをテストおよびターゲット設定します。
* 複数の Recommendations の順序など、Recommendations のページ配置を簡単に試行します。
* [!UICONTROL Auto-Allocate] を使用して、最もパフォーマンスの高いレコメンデーションエクスペリエンスにトラフィックを自動的にプッシュします。
* [!UICONTROL Auto-Target] を使用し、プロファイルに基づいて、カスタマイズされた Recommendations エクスペリエンスへと訪問者を動的に割り当てます。

開始するには、[!UICONTROL Visual Experience Composer] を使用して [!UICONTROL A/B Test] アクティビティまたは [!UICONTROL Experience Targeting] アクティビティを作成し、[!UICONTROL Insert Before]、[!UICONTROL Insert After] または [!UICONTROL Replace With] アクションを使用してエクスペリエンスにレコメンデーションを追加します。

## Recommendations をオファーとして A/B テストまたは XT アクティビティに追加する

1. [A/B テスト](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)または[エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)（XT）アクティビティを作成するには、Visual Experience Composer（VEC）を使用して 3 ステップのガイドによるワークフローを開始します。

   >[!NOTE]
   >
   >A/B テストの場合、パフォーマンスが最も高い Recommendations にトラフィックを自動的にプッシュする[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)オプション、または訪問者をプロファイルに基づいて詳細にカスタマイズされた Recommendations エクスペリエンスに動的に割り当てる[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) オプションを選択できます。

1. [ エクスペリエンス ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) の作成中に、レコメンデーションをオファーとして追加する要素をクリックし、「**[!UICONTROL Replace Content]**」をクリックして「**[!UICONTROL Recommendation]**」を選択します。

   ![Recommendations をオファーとして挿入](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. ページタイプ別の一般的な Recommendations 条件を表示するには、次のオプションから選択します。

   * 買い物かごページ
   * カテゴリページ
   * ホームページ
   * ランディングページ
   * 製品紹介ページ
   * 検索結果ページ
   * 「ありがとうございます」ページ
   * その他

1. 目的の [ 条件 ](/help/main/c-recommendations/c-algorithms/algorithms.md) を選択し、「[!UICONTROL Next]」をクリックします。
1. 目的の [ デザイン ](/help/main/c-recommendations/c-design-overview/design-overview.md) を選択し、「[!UICONTROL Next]」をクリックします。
1. [!UICONTROL Options] ダイアログボックスで、次の設定を行います。

   * [コレクション](/help/main/c-recommendations/c-products/collections.md)を選択します。
   * 必要に応じて、[プロモーション - 前とプロモーション - 後](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)オプションを設定します。

1. [!UICONTROL Save] をクリックします。
1. 3 ステップのガイドによるワークフローを使用して、A/B テストまたは XT アクティビティの設定を完了します。

## Recommendations オファーの設定の編集

オファーの設定を編集するには、次の 2 つの方法があります。

* [!UICONTROL Edit] メニューの使用
* [!UICONTROL Modifications] パネルの使用

### 編集メニューを使用した Recommendations オファーの編集

1. 編集するオファーをクリックし、「**[!UICONTROL Edit]**」をクリックします。

   ![Recommendations オファーの編集](/help/main/c-recommendations/assets/recs-offer-edit.png)

1. 次のオプションから選択します。

   * [条件を変更](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [デザインを変更](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [コレクションを変更](/help/main/c-recommendations/c-products/collections.md)
   * [プロモーションを変更](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. 編集をおこないます。

### 変更パネルを使用した Recommendations オファーの編集

1. [!UICONTROL Modifications] アイコン **（`</>`）** をクリックして [ 変更 ](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) ペインを表示します。
1. 目的のアクションの上にマウスポインターを置いて、「**[!UICONTROL Edit]**」アイコンをクリックします。

   ![変更パネル](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. 編集をおこないます。

## Recommendations オファーの削除

Recommendations オファーを削除するには、次の 2 つの方法があります。

* [!UICONTROL Edit] メニューの使用
* [!UICONTROL Modifications] パネルの使用

### 編集メニューを使用した Recommendations オファーの削除

1. 削除するオファーをクリックし、「削 **[!UICONTROL Layout > Remove]**」をクリックします。

   ![削除](/help/main/c-recommendations/assets/recs-offer-remove.png)

### 変更パネルを使用した Recommendations オファーの削除

1. [!UICONTROL Modifications] アイコン **（&lt;/>）** をクリックして [ 変更 ](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) ペインを表示します。
1. 目的のアクションの上にマウスポインターを置いて、「[!UICONTROL Delete]」アイコンをクリックします。

   ![削除アイコン](/help/main/c-recommendations/assets/recs-offer-delete.png)

### Recommendations オファーのステータスの表示 {#status}

Recommendations オファーの（アルゴリズム）ステータスは、Recommendations オファーを含む A/B テストおよび XT アクティビティの [!UICONTROL Overview] ページの下部に表示されます。

* 結果の準備ができました
* 結果の準備ができていません
* フィードエラー

![Recommendations オファーステータス](/help/main/c-recommendations/assets/recs-offer-status.png)

## トレーニングビデオ：オファーとしての Recommendations![概要バッジ](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
