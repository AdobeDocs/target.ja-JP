---
keywords: レコメンデーション;オファー
description: A/B テスト（自動配分と自動ターゲットを含む）およびエクスペリエンスのターゲット設定（XT）アクティビティで、オファーとして Adobe レコメンデーションを使用する方法を説明します。
title: レコメンデーションを他のアクティビティタイプでオファーとして使用するにはどうすればよいですか。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
TQID: 'https://experienceleague.adobe.com/ZMOb5RdY6bES331INSM7VF-w4be-5Xmjqon0YvfuNG4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 17%
---
# オファーとしてのレコメンデーション {#recommendations-as-an-offer}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、[!UICONTROL A/B テスト ]および[!UICONTROL  エクスペリエンスのターゲット設定] （XT）アクティビティで、オファーとしてレコメンデーションを追加、編集、削除する方法について説明します。

>[!ENDSHADEBOX]

[!UICONTROL Recommendations] アクティビティに加えて、[!UICONTROL A/B テスト ] （[!UICONTROL 自動割り当て]および[!UICONTROL 自動ターゲット ]を含む）および[!UICONTROL  エクスペリエンスのターゲット設定] （XT）アクティビティにレコメンデーションを含めることができます。 これにより、次のことが可能になります。

* 同じアクティビティ内のレコメンデーションと非レコメンデーションのコンテンツをテストおよびターゲット設定します。
* 複数のレコメンデーションの順序を含め、ページ上のレコメンデーションの配置を試します。
* **[!UICONTROL 自動配分]**&#x200B;を使用して、最もパフォーマンスの高いレコメンデーションエクスペリエンスにトラフィックを自動的にプッシュします。
* **[!UICONTROL 自動ターゲット]**&#x200B;を使用して、プロファイルに基づいてカスタマイズされたレコメンデーション エクスペリエンスに訪問者を動的に割り当てます。

## レコメンデーションをオファーとして追加 {#add-recs-offer}

[!UICONTROL A/B テスト ]またはXT アクティビティで[!UICONTROL Visual Experience Composer] （VEC）を使用してエクスペリエンスを作成する際に、レコメンデーションがオファーとして追加されます。

1. VECの3段階のガイド付きワークフローを開始して、[A/B テスト ](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)または[ エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) （XT） アクティビティを作成します。

   >[!NOTE]
   >
   >A/B テストの場合、[自動割り当て](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) オプションは、トラフィックを最もパフォーマンスの高いレコメンデーションに自動的にプッシュし、[自動ターゲット ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) オプションは、訪問者のプロファイルに基づいて、カスタマイズされたレコメンデーション エクスペリエンスに訪問者を割り当てます。

1. [ エクスペリエンス ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)の作成中に、次のいずれかの方法でレコメンデーションをオファーとして追加します。

   * レコメンデーションを追加する要素をクリックし、**[!UICONTROL コンテンツを置換]**&#x200B;をクリックしてから、**[!UICONTROL レコメンデーション]**&#x200B;を選択します。

     ![見出しを選択したVisual Experience Composer。HTMLのオファーオプションとエクスペリエンスフラグメントオプションの横にある「おすすめ」オプションがメニューに強調表示されている](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

   * **[!UICONTROL コンポーネント]** パネルで、**[!UICONTROL 動的]**&#x200B;の下の&#x200B;**[!UICONTROL 推奨事項]**&#x200B;を選択し、ページ上の既存の要素にカーソルを合わせ、**[!UICONTROL 前に挿入]**&#x200B;または&#x200B;**[!UICONTROL 後に挿入]**&#x200B;をクリックして、その要素の前後に推奨事項を配置します。

1. **[!UICONTROL プロパティを表示]** メニューにアクセスし、**[!UICONTROL 推奨事項を選択]**&#x200B;をクリックします。

1. 目的の[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を選択し、**[!UICONTROL 次へ]**&#x200B;をクリックします。

1. 目的の[ デザイン ](/help/main/c-recommendations/c-design-overview/design-overview.md)を選択し、**[!UICONTROL 次へ]**&#x200B;をクリックします。

1. **[!UICONTROL オプション]** ダイアログボックスで、次の項目を指定します。

   * [コレクション](/help/main/c-recommendations/c-products/collections.md)を選択します。
   * 必要に応じて、[ フロントプロモーションとバックプロモーション ](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)のオプションを設定します。

1. 「**[!UICONTROL Save]**」をクリックします。

1. 3段階のガイド付きワークフローを使用して、[!UICONTROL A/B テスト ]またはXT アクティビティの設定を完了します。

## レコメンデーションオファーの編集 {#edit-recs-offer}

レコメンデーションオファーの基準、デザイン、コレクション、およびプロモーションは、オファーが追加された後、**[!UICONTROL Recommendation]** ペインから変更できます。

1. オファーをクリックして編集し、右側のペインメニューのオプションを参照します。

   ![条件、デザイン、コレクション名と、選択したオファーの「プロモーションを追加」ボタンが表示されたレコメンデーションペイン ](assets/create_reco_7.png)

1. 次のいずれかのオプションを選択します。

   * [条件を変更](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [デザインを変更](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [コレクションを変更](/help/main/c-recommendations/c-products/collections.md)
   * [プロモーションを変更](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. 編集を行います。

## レコメンデーションオファーの削除 {#delete-recs-offer}

不要になったレコメンデーションオファーは、**[!UICONTROL Recommendation]** ペインから削除できます。

削除するオファーをクリックし、**[!UICONTROL Recommendation]** ペインのbin アイコン（![Bin アイコン ](assets/Smock_Delete_18_N.svg)）をクリックします。

![bin アイコンがハイライト表示されたレコメンデーションペイン ](assets/create_reco_8.png)

## レコメンデーションオファーのステータスの表示 {#status}

レコメンデーションオファー（アルゴリズム）のステータスは、[!UICONTROL A/B テスト ]およびレコメンデーションオファーを含むXT アクティビティの&#x200B;**[!UICONTROL 概要]** ページの下部に表示されます。 ステータスは次のいずれかです。

* **[!UICONTROL 結果の準備完了]**
* **[!UICONTROL 結果の準備ができていません]**
* **[!UICONTROL フィード失敗]**

## トレーニングビデオ：オファーとしてのレコメンデーション![概要バッジ](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
