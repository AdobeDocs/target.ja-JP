---
keywords: Mvt;多変量分析テスト;多変量分析テスト作成;多変量分析テストの作成;mvt 作成;mvt 作成;mvt の方法;多変量分析テスト方法
description: ターゲット対応のページで、Adobe TargetのVisual Experience Composer(VEC)を使用して多変量分析テスト(MVT)を作成する方法を説明します。
title: 多変量分析テストの作成方法
feature: 多変量分析テスト
translation-type: tm+mt
source-git-commit: e87786f2df104d66d97cacd83921875dacd78afe
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 87%

---


# 多変量分析テストの作成{#create-a-multivariate-test}

[!DNL Adobe Target] の [!DNL Target]Visual Experience Composer[!UICONTROL （VEC）を使用すると、Target に対応したページで適切なテストを作成し、] 内でページの一部を変更する作業が簡単におこなえます。

[!DNL Target]ポイント&amp;クリックエディターを使用すると、任意の場所を選択し、複数のオファーを追加できます。

[!UICONTROL 多変量分析テスト]（MVT）では、ページ本位のレポートが生成されます。つまり、テストは特定の URL に対して実行され、そのページに対して設計されたエクスペリエンスが表示されます。

1. **[!UICONTROL アクティビティを作成]**／**[!UICONTROL 多変量分析テスト]**&#x200B;をクリックします。

   ![多変量分析テストを作成](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、Target アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。例えば、[!UICONTROL 自動パーソナライゼーション]は、[Target Premium 機能](/help/c-intro/intro.md#premium)です。
   >
   >[!DNL Target] で使用できる様々なアクティビティタイプおよびその違いについて詳しくは、[アクティビティ](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)を参照してください。ニーズに最も適したアクティビティタイプを決定するのに役立つ情報については、[Target アクティビティタイプ](/help/c-activities/target-activities-guide.md)を参照してください。

1. 必要に応じて、「**[!UICONTROL ビジュアル (デフォルト)]**」を選択します。

   ![多変量分析テストアクティビティを作成ダイアログボックス](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-mvt-dialog.png)

   >[!NOTE]
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。
   >
   >前述の図の「[!UICONTROL ワークスペースを選択]」オプションは、[Target Premium](/help/c-intro/intro.md) の機能です。このオプションが表示されない場合、お客様の組織は Target Standard ライセンスを所有しています。

1. （条件付き）Target Premium のお客様の場合、[ワークスペースを選択](/help/administrating-target/c-user-management/property-channel/property-channel.md)します。

1. テストするページの [URL を指定](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0)し、「**[!UICONTROL 次へ]**」をクリックします。

   >[!NOTE]
   >
   >先頭に HTTP または HTTPS を含め、完全な URL を使用します。

   ブラウザーで混合コンテンツを有効にするように求めるメッセージが表示された場合は、メッセージの指示に従います。ブラウザーで混合コンテンツを有効にした後、再度手順 1 から開始します。

   Visual Experience Composer が開きます。

1. アクティビティ名を入力します。

   ![アクティビティ名フィールド](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

   アクティビティ名の先頭に次の文字を使用することはできません。

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

1. [それぞれの場所でオファーを作成します](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6)。

   ![テキスト / HTML を編集ダイアログボックス](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   以下の種類のオファーを追加できます。

   * HTML
   * 画像
   * テキスト

1. 「**[!UICONTROL プレビュー]**」をクリックして、[エクスペリエンスをプレビュー ](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md)します。

   ![エクスペリエンスをプレビュー](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   各エクスペリエンスを表示し、テストに組み込まないエクスペリエンスを除外できます。1 つ以上のエクスペリエンスを除外するには、目的のチェックボックスをオンにしてから、「**[!UICONTROL 除外]**」をクリックします。

   ![エクスペリエンスを除外](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [トラフィック見積もりを使用](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)して、テスト計画の実行可能性をテストします。

   ![トラフィックインジケーター](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   以下の図は、アクティビティに十分なトラフィックがないことを示しています。

   ![](assets/estimator.png)

   以下の図は、アクティビティに十分なトラフィックがないことを示しています。

   ![](assets/estimator2.png)

1. 「**[!UICONTROL 次へ]**」をクリックして、[!UICONTROL ターゲット]ページに進みます。

1. アクティビティに参加する資格のある訪問者のオーディエンスおよび割合を選択します。

   ![MVT アクティビティのターゲット設定ページ](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

   >[!NOTE]
   >
   >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

1. [テスト概要を確認](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7)して、必要な変更をおこない、「**[!UICONTROL 次へ]**」をクリックします。

1. [テストの目標と設定を指定](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)します。

1. 「**[!UICONTROL 保存して閉じる]**」をクリックして、アクティビティを作成します。

## トレーニングビデオ：多変量分析テストの作成(9:25)![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオでは、Target の 3 ステップのガイドによるワークフローを使用して、多変量分析テストを計画し、作成する方法についてデモをおこないます。

* 多変量分析テストの定義と設計
* 多変量分析テストの作成

>[!VIDEO](https://video.tv.adobe.com/v/17395)
