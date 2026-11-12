---
keywords: Mvt;多変量分析テスト;多変量分析テスト作成;多変量分析テストの作成;mvt 作成;mvt 作成;mvt の方法;多変量分析テスト方法
description: '[!DNL Adobe Target]の[!UICONTROL Visual Experience Composer] （VEC）を使用して、[!UICONTROL 多変量テスト &#x200B;] （MVT）を作成する方法を説明します。'
title: '[!UICONTROL 多変量テスト &#x200B;]を作成するにはどうすればよいですか？'
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
TQID: 'https://experienceleague.adobe.com/gxrnY43A7OWsiW48Rlq1Orp7ZxBswdAPZEAbRQrCDZA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aad553690f1f399177214c94a2276d038f46d9cb
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 16%
---
# 多変量分析テストの作成 {#create-mvt}

>[!BEGINSHADEBOX]

**このページ：** **[!UICONTROL Visual Experience Composer]** （VEC）で&#x200B;**[!UICONTROL 多変量テスト]** （MVT）を作成する方法を説明します。 アクティビティの作成、エクスペリエンスの構築とレビュー、ターゲティングの設定、目標と設定の設定をおこないます。

>[!ENDSHADEBOX]

[!DNL Adobe Target]の&#x200B;**[!UICONTROL Visual Experience Composer]** （VEC）を使用すると、**[!UICONTROL 多変量テスト]**&#x200B;を簡単に作成し、[!DNL Target]内のページの一部を変更できます。

[!DNL Target]のポイント&amp;クリック エディターを使用すると、任意の場所を選択して複数のオファーを追加できます。

**[!UICONTROL 多変量テスト]** （MVT）は、ページファースト レポートを受け取ります。 つまり、テストは特定の URL に対して実行され、そのページに対して設計されたエクスペリエンスが表示されます。

次の手順に従って、**[!UICONTROL 多変量テスト]** （MVT）を作成します。

1. [アクティビティの作成](#create-activity)
1. [エクスペリエンスの構築とレビュー](#build-experiences)
1. [ターゲティングの設定](#set-targeting)
1. [目標と設定の設定](#configure-goals-and-settings)

## アクティビティの作成 {#create-activity}

アクティビティタイプと配信タイプを選択し、テストするページを指定して、アクティビティに名前を付けます。

1. 「**[!UICONTROL アクティビティを作成]**」 > 「**[!UICONTROL 多変量テスト]**」をクリックします。

   [!DNL Target] で使用できる様々なアクティビティタイプおよびその違いについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)を参照してください。 ニーズに最も適したアクティビティタイプを決定するのに役立つ情報については、[Target アクティビティタイプ](/help/main/c-activities/target-activities-guide.md)を参照してください。

   ![](../../assets/create-mvt-1.png)

1. 配信タイプを選択します：**[!UICONTROL Web]**、**[!UICONTROL Mobile]**、**[!UICONTROL Email]**、または&#x200B;**[!UICONTROL Other/API]**。

1. （条件付き）お客様が[Target Premium](/help/main/c-intro/intro.md#premium)のお客様の場合は、[&#x200B; ワークスペースを選択してください](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. [&#x200B; テストするページのURL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#ab-activity-url)を指定します。 最初に、HTTPまたはHTTPSを含む完全なURLを使用します。

1. 次に、**[!UICONTROL 作成]**&#x200B;をクリックします。 **[!UICONTROL Visual Experience Composer]**&#x200B;が開きます。

1. アクティビティに名前を付けるには、**[!UICONTROL 編集]** アイコン （![編集アイコン &#x200B;](/help/main/assets/icons/Edit.svg)）をクリックし、アクティビティのわかりやすい名前を指定して、**[!UICONTROL 保存]**&#x200B;をクリックします。

   {{activity-name-rules}}

   ![](../../assets/create-mvt-2.png)

## エクスペリエンスの構築とレビュー {#build-experiences}

各場所にオファーを追加し、結果のエクスペリエンスをプレビューして、テストプランが実現可能であることを確認します。

1. [それぞれの場所でオファーを作成します](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6)。

   以下の種類のオファーを追加できます。

   * HTML
   * 画像
   * テキスト

1. **[!UICONTROL プレビュー]**&#x200B;をクリックして[体験をプレビュー](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md)します。

1. 「**[!UICONTROL エクスペリエンスを表示]**」アイコン（![&#x200B; エクスペリエンスアイコン &#x200B;](/help/main/assets/icons/WebPages.svg)）をクリックして、左側のフレーム内のすべてのエクスペリエンスのリストを表示し、リスト内の特定のエクスペリエンスをクリックしてそのエクスペリエンスを表示します。

1. [トラフィック見積もりを使用](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)して、テスト計画の実行可能性をテストします。

### エクスペリエンスを除外（オプション） {#exclude-experiences}

矛盾するバリエーションを表示するエクスペリエンスや、デザイン的にバランスのとれていないエクスペリエンスなどを除外します。

1. **[!UICONTROL コンテンツの管理]** アイコン （![&#x200B; エクスペリエンスの管理アイコン &#x200B;](/help/main/assets/icons/Experience.svg)）をクリックして、**[!UICONTROL エクスペリエンスの管理]** ダイアログボックスを表示します。

1. 1つのエクスペリエンスを除外するには、そのエクスペリエンスの横にある&#x200B;**[!UICONTROL その他のアクション]** アイコン （![その他のアクション アイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、**[!UICONTROL 除外]**&#x200B;をクリックします。

1. 複数のエクスペリエンスを除外するには、目的のエクスペリエンスのチェックボックスを選択し、**[!UICONTROL 除外]**&#x200B;をクリックします。

## ターゲティングの設定 {#set-targeting}

テストに参加する訪問者を選択し、テストの概要を確認します。

1. 「**[!UICONTROL 次へ]**」をクリックして、**[!UICONTROL ターゲティング]** ページにアクセスします。

   フロー図では、オーディエンスとそのトラフィック率の割り当て、トラフィック配分方法の選択、アクティビティの各エクスペリエンスのトラフィック配分の指定の手順を順を追って説明します。

1. （条件付き）アクティビティの別のオーディエンスを選択するには、**[!UICONTROL すべての訪問者]** コントロールをクリックします。

   **[!UICONTROL すべての訪問者]** オーディエンスがデフォルトとして設定されます。 別のオーディエンスを選択すると、その名前が一番左のコントロールに表示されます。 例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

   +++ 別のオーディエンスを選択する手順

   右側のフレームが表示され、オーディエンスを追加または削除し、アクティビティの訪問者パーセンテージを割り当てることができます。

   1. オーディエンスを変更するには、右側のフレームの&#x200B;**[!UICONTROL 置換]** アイコン（![置換アイコン &#x200B;](/help/main/assets/icons/Retweet.svg)）をクリックします。
   1. **[!UICONTROL オーディエンスを追加]** ダイアログボックスで、[目的のオーディエンス &#x200B;](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)を選択し、**[!UICONTROL オーディエンスを割り当て]**&#x200B;をクリックします。

      複数のオーディエンスを組み合わせたオーディエンスを作成するには、**[!UICONTROL オーディエンスを組み合わせる]**&#x200B;をクリックします。 詳しくは、[複数のオーディエンスを組み合わせる](/help/main/c-target/combining-multiple-audiences.md)を参照してください。

      まだ&#x200B;**[!UICONTROL オーディエンスライブラリ]**&#x200B;にない新しいオーディエンスを作成するには、**[!UICONTROL オーディエンスの作成]**&#x200B;をクリックします。 [create-audience ワークフロー](/help/main/c-target/c-audiences/audiences.md)で、次のいずれかのオプションを選択します。

      * **[!UICONTROL オーディエンスライブラリ]**: **[!UICONTROL オーディエンスライブラリ]**&#x200B;に保存され、他のアクティビティで再利用できるオンデマンドオーディエンスを作成します。
      * **[!UICONTROL このアクティビティのみ]**: **[!UICONTROL オーディエンスライブラリ]**&#x200B;に保存されていない[&#x200B; アクティビティ固有のオーディエンス &#x200B;](/help/main/c-target/creating-activity-only-audience.md)を作成し、現在のアクティビティでのみ使用できます。

   1. 右側のフレームで「**[!UICONTROL 訪問者の割合]**」をクリックし、アクティビティに参加する対象となる訪問者の割合を選択します。

   +++

1. [&#x200B; テストの概要](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7)を確認し、必要な変更を加えたら、**[!UICONTROL 次へ]**&#x200B;をクリックします。

## 目標と設定の設定 {#configure-goals-and-settings}

**[!UICONTROL 目標と設定]** ページで、[!DNL Target]にテストの測定方法を指示します。 使用可能な設定は、レポートソースとして[!DNL Target]または[!DNL Analytics]を使用するかどうかに応じて異なります。

1. ページのセクションを確認し、必要なものを設定します。 「[目標と設定」ページで設定した内容](#goals-settings-overview)を参照してください。


   | セクション | 設定するもの |
   |---|---|
   | **[!UICONTROL アクティビティの設定]** | オプションの目的、**[!UICONTROL 優先度]** （複数のアクティビティが場所とオーディエンスを共有する場合に使用）、および&#x200B;**[!UICONTROL 期間]** （開始日と終了日）です。 |
   | **[!UICONTROL レポート設定]** | レポートソース、目標指標（例：**[!UICONTROL コンバージョン]**&#x200B;指標）、追加指標、レポート用オーディエンス。 目標指標の詳細設定も、ここで使用できます。 |
   | **[!UICONTROL その他のメタデータ]** | 自分または他のチームメンバーに役立つアクティビティに関するメモ。 |

1. 「**[!UICONTROL 保存して閉じる]**」をクリックして、アクティビティを作成します。

各オプションについて詳しくは、[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#ab-goals-and-settings)を参照してください。

## トレーニングビデオ：多変量テストの作成（9:25） ![&#x200B; チュートリアルバッジ &#x200B;](/help/main/assets/tutorial.png)

このビデオでは、[!DNL Target] 3段階のガイド付きワークフローを使用して、多変量テストを計画および作成する方法を説明します。

* 多変量分析テストの定義と設計
* 多変量分析テストの作成

>[!VIDEO](https://video.tv.adobe.com/v/29957?captions=jpn)
