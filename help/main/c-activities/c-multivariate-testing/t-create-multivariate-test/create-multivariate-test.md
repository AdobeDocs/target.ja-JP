---
keywords: Mvt;多変量分析テスト;多変量分析テスト作成;多変量分析テストの作成;mvt 作成;mvt 作成;mvt の方法;多変量分析テスト方法
description: ' [!DNL Adobe Target] の[!UICONTROL Visual Experience Composer] （VEC）を使用して[!UICONTROL Multivariate Test] （MVT）を作成する方法を説明します。'
title: '[!UICONTROL Multivariate Test]を作成するにはどうすればよいですか？'
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
TQID: https://experienceleague.adobe.com/gxrnY43A7OWsiW48Rlq1Orp7ZxBswdAPZEAbRQrCDZA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 737
ht-degree: 26%

---

# 多変量分析テストの作成

[!DNL Adobe Target]の[!UICONTROL Visual Experience Composer] （VEC）を使用すると、[!UICONTROL Multivariate Test]を簡単に作成でき、[!DNL Target]内のページの一部を変更できます。

[!DNL Target]のポイント&amp;クリック エディターを使用すると、任意の場所を選択して複数のオファーを追加できます。

[!UICONTROL Multivariate Test] （MVT）は、ページファースト レポートを受け取ります。 つまり、テストは特定の URL に対して実行され、そのページに対して設計されたエクスペリエンスが表示されます。

1. **[!UICONTROL Create Activity]**／**[!UICONTROL Multivariate Test]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] で使用できる様々なアクティビティタイプおよびその違いについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)を参照してください。 ニーズに最も適したアクティビティタイプを決定するのに役立つ情報については、[Target アクティビティタイプ](/help/main/c-activities/target-activities-guide.md)を参照してください。

1. （条件付き）配信タイプを選択します：[!UICONTROL Web]、[!UICONTROL Mobile]、[!UICONTROL Email]、または[!UICONTROL Other/API]。

1. （条件付き）お客様が[Target Premium](/help/main/c-intro/intro.md#premium)のお客様の場合は、[&#x200B; ワークスペースを選択してください](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. [&#x200B; テストするページのURL &#x200B;](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0)を指定し、**[!UICONTROL Create]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >最初に、HTTPまたはHTTPSを含む完全なURLを使用します。

   ブラウザーで混合コンテンツを有効にするように求めるメッセージが表示された場合は、メッセージの指示に従います。 ブラウザーで混合コンテンツを有効にした後、再度手順 1 から開始します。

   [!UICONTROL Visual Experience Composer]が開きます。

1. アクティビティに名前を付けるには、「[!UICONTROL Untitled Activity]」の横にある&#x200B;**[!UICONTROL Edit]** アイコン（![編集アイコン &#x200B;](/help/main/assets/icons/Edit.svg)）をクリックし、アクティビティのわかりやすい名前を指定して、**[!UICONTROL Save]**&#x200B;をクリックします。

   アクティビティ名の先頭に次の文字を使用することはできません：

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

   アクティビティ名に次の文字シーケンスを含めることはできません。

   | 文字シーケンス | 説明 |
   |--- |--- |
   | ;= | セミコロン、次に等しい |
   | ;+ | セミコロン、プラス |
   | ;- | セミコロン、マイナス |
   | ;@ | セミコロン、記号 |
   | ,= | コンマ、次に等しい |
   | ,+ | コンマ、プラス |
   | ,- | コンマ、マイナス |
   | ,@ | コンマ、記号 |
   | `[`&quot; | 角括弧を開く、二重引用符 |
   | &quot;`]` | 二重引用符、角括弧を閉じる |

1. [それぞれの場所でオファーを作成します](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6)。

   以下の種類のオファーを追加できます。

   * HTML
   * 画像
   * テキスト

1. **[!UICONTROL Preview]**&#x200B;をクリックして[体験をプレビュー](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md)します。

1. **[!UICONTROL Show Experiences]** アイコン（![&#x200B; エクスペリエンスを表示アイコン &#x200B;](/help/main/assets/icons/WebPages.svg)）をクリックすると、左側のフレームにすべてのエクスペリエンスのリストが表示されます。

1. リスト内の特定のエクスペリエンスをクリックして、そのエクスペリエンスを表示します。

1. （条件付き）アクティビティから1つ以上のエクスペリエンスを除外するには、**[!UICONTROL Manage Content]** アイコン （![&#x200B; エクスペリエンスの管理アイコン &#x200B;](/help/main/assets/icons/Experience.svg)）をクリックして、[!UICONTROL Manage Experiences] ダイアログボックスを表示します。

1. （条件付き） [!UICONTROL Manage Experiences] ダイアログボックスで、除外するエクスペリエンスの横にある&#x200B;**[!UICONTROL More Actions]** アイコン （![その他のアクション アイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、**[!UICONTROL Exclude]**&#x200B;をクリックします。

   矛盾するバリエーションを表示するエクスペリエンスや、デザイン的にバランスのとれていないエクスペリエンスなどを除外します。

1. （条件付き）複数のエクスペリエンスを除外するには、目的のエクスペリエンスのチェックボックスを選択し、**[!UICONTROL Exclude]**&#x200B;をクリックします。

1. [トラフィック見積もりを使用](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)して、テスト計画の実行可能性をテストします。

1. 「**[!UICONTROL Next]**」をクリックして、[!UICONTROL Targeting] ページに進みます。

   他の[!DNL Target] アクティビティタイプを使用している場合、**ターゲティング**&#x200B;手順は見慣れています。 ここで、オーディエンスを選択し、各エクスペリエンスを表示する訪問者の割合を指定できます。

   フロー図では、オーディエンスとそのトラフィック率の割り当て、トラフィック配分方法の選択、アクティビティの各エクスペリエンスのトラフィック配分の指定の手順を順を追って説明します。

1. （条件付き）アクティビティの別のオーディエンスを選択するには、**[!UICONTROL All Visitors]** コントロールをクリックします。

   [!UICONTROL All Visitors] オーディエンスがデフォルトとして設定されています。 別のオーディエンスを選択すると、その名前が一番左のコントロールに表示されます。

   右側のフレームが表示され、オーディエンスを追加または削除し、アクティビティの訪問者パーセンテージを割り当てることができます。

   1. オーディエンスを変更するには、右側のフレームの&#x200B;**[!UICONTROL Replace]アイコン** （![置換アイコン &#x200B;](/help/main/assets/icons/Retweet.svg)）をクリックします。
   1. [!UICONTROL Add Audience] ダイアログボックスで、[目的のオーディエンス &#x200B;](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)を選択し、**[!UICONTROL Assign Audience]**&#x200B;をクリックします。

      「**オーディエンスを結合**」をクリックして、[複数のオーディエンスを結合するオーディエンスを作成できます](/help/main/c-target/combining-multiple-audiences.md)。

      まだ[!UICONTROL Audience Library]にない新しいオーディエンスを作成する必要がある場合は、**オーディエンスの作成**&#x200B;をクリックします。 [create-audience ワークフロー](/help/main/c-target/c-audiences/audiences.md)中に、次のオプションから選択できます。

      * **[!UICONTROL Audience Library]**: [!UICONTROL Audience Library]に保存されたオンデマンドオーディエンスを作成し、他のアクティビティで再利用できます。
      * **[!UICONTROL This activity only]**: [!UICONTROL Audience Library]に保存されず、現在のアクティビティでのみ使用できる[&#x200B; アクティビティ固有のオーディエンス &#x200B;](/help/main/c-target/creating-activity-only-audience.md)を作成します。

   1. 右側のフレームで「**[!UICONTROL Visitor Percentage]**」をクリックし、アクティビティに参加する適格な訪問者の割合を選択します。

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. [&#x200B; テストの概要](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7)を確認し、必要な変更を加えたら、**[!UICONTROL Next]**&#x200B;をクリックします。

1. [テストの目標と設定を指定](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)します。

1. 「**[!UICONTROL Save and Close]**」をクリックしてアクティビティを作成します。

## トレーニングビデオ：多変量テストの作成（9:25） ![&#x200B; チュートリアルバッジ &#x200B;](/help/main/assets/tutorial.png)

このビデオでは、[!DNL Target] 3段階のガイド付きワークフローを使用して、多変量テストを計画および作成する方法を説明します。

* 多変量分析テストの定義と設計
* 多変量分析テストの作成

>[!VIDEO](https://video.tv.adobe.com/v/29957?captions=jpn)
