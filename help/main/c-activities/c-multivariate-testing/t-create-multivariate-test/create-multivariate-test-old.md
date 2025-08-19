---
keywords: Mvt;多変量分析テスト;多変量分析テスト作成;多変量分析テストの作成;mvt 作成;mvt 作成;mvt の方法;多変量分析テスト方法
description: '[!UICONTROL Visual Experience Composer] （VEC）を使用して  [!DNL Adobe Target]  （MVT）を作成 [!UICONTROL Multivariate Test] る方法を説明します。'
title: '[!UICONTROL Multivariate Test] の作成方法'
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 56%

---

# 多変量分析テストの作成

[!UICONTROL Visual Experience Composer] の [!DNL Adobe Target] （VEC）を使用すると、[!UICONTROL Multivariate Test] ージの作成や、[!DNL Target] 内のページの一部の変更が簡単にできます。

[!DNL Target] のポイントアンドクリックエディターを使用すると、任意の場所を選択し、複数のオファーを追加できます。

[!UICONTROL Multivariate Test] （MVT）は、ページ先頭のレポートを取得します。 つまり、テストは特定の URL に対して実行され、そのページに対して設計されたエクスペリエンスが表示されます。

1. **[!UICONTROL Create Activity]**／**[!UICONTROL Multivariate Test]**&#x200B;をクリックします。

   ![多変量分析テストを作成](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >[!DNL Target] で使用できる様々なアクティビティタイプおよびその違いについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)を参照してください。ニーズに最も適したアクティビティタイプを決定するのに役立つ情報については、[Target アクティビティタイプ](/help/main/c-activities/target-activities-guide.md)を参照してください。

1. （条件付き）配信タイプ（[!UICONTROL Web]、[!UICONTROL Mobile]、[!UICONTROL Email]、[!UICONTROL Other/API]）を選択します。

1. （条件付き） [Target Premium](/help/main/c-intro/intro.md#premium) のお客様は、[ ワークスペースを選択 ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) してください。

1. テストするページの [URL を指定 ](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) し、「**[!UICONTROL Next]**」をクリックします。

   >[!NOTE]
   >
   >最初に HTTP や HTTPS を含む完全な URL を使用します。

   ブラウザーで混合コンテンツを有効にするように求めるメッセージが表示された場合は、メッセージの指示に従います。ブラウザーで混合コンテンツを有効にした後、再度手順 1 から開始します。

   [!UICONTROL Visual Experience Composer] が開きます。

1. アクティビティ名を入力します。

   ![アクティビティ名フィールド](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

   アクティビティ名は、次の文字で始めることはできません：

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

   アクティビティ名には、次の文字シーケンスを含めることはできません：

   | 文字シーケンス | 説明 |
   |--- |--- |
   | ;= | セミコロン、次と等しい |
   | ;+ | セミコロン、プラス |
   | ;- | セミコロン マイナス |
   | ;@ | セミコロン、アットサイン |
   | ,= | コンマ、次と等しい |
   | ,+ | コンマ、プラス |
   | ,- | コンマ，マイナス |
   | ,@ | コンマ、アットサイン |
   | `[`&quot; | 左角括弧、二重引用符 |
   | &quot;`]` | 二重引用符、閉じ角括弧 |

1. [それぞれの場所でオファーを作成します](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6)。

   ![テキスト / HTML を編集ダイアログボックス](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   以下の種類のオファーを追加できます。

   * HTML
   * 画像
   * テキスト

1. 「**[!UICONTROL Preview]**」をクリックして [ エクスペリエンスをプレビュー ](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md) します。

   ![エクスペリエンスをプレビュー](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   各エクスペリエンスを表示し、テストに組み込まないエクスペリエンスを除外できます。1 つ以上のエクスペリエンスを除外するには、対象のチェックボックスを選択して、「**[!UICONTROL Exclude]** 除」をクリックします。

   ![エクスペリエンスを除外](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [トラフィック見積もりを使用](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)して、テスト計画の実行可能性をテストします。

   ![トラフィックインジケーター](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   以下の図は、アクティビティに十分なトラフィックがないことを示しています。

   ![ 推定画像 ](assets/estimator.png)

   以下の図は、アクティビティに十分なトラフィックがないことを示しています。

   ![estimator2 画像 ](assets/estimator2.png)

1. 「**[!UICONTROL Next]**」をクリックして、[!UICONTROL Targeting] のページに進みます。

1. アクティビティに参加する資格のある訪問者のオーディエンスおよび割合を選択します。

   ![MVT アクティビティのターゲット設定ページ](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

   >[!NOTE]
   >
   >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

1. [ テストの概要を確認し ](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7) 必要な変更を加えて、「**[!UICONTROL Next]**」をクリックします。

1. [テストの目標と設定を指定](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)します。

1. 「**[!UICONTROL Save and Close]**」をクリックして、アクティビティを作成します。

## トレーニングビデオ：多変量分析テストの作成（9:25） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、[!DNL Target] の 3 ステップのガイド付きワークフローを使用して多変量分析テストを計画および作成する方法を説明します。

* 多変量分析テストの定義と設計
* 多変量分析テストの作成

>[!VIDEO](https://video.tv.adobe.com/v/17395)
