---
keywords: Mvt;多変量分析テスト;多変量分析テスト作成;多変量分析テストの作成;mvt 作成;mvt 作成;mvt の方法;多変量分析テスト方法
description: '[!UICONTROL Visual Experience Composer] （VEC）を使用して [!UICONTROL Multivariate Test] （MVT）を作成  [!DNL Adobe Target]  る方法を説明します。'
title: '[!UICONTROL Multivariate Test] の作成方法'
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
source-git-commit: be118753eed999ce24d547c90ac9d195cce7e9e9
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 26%

---

# 多変量分析テストの作成

[!DNL Adobe Target] の [!UICONTROL Visual Experience Composer] （VEC）を使用すると、[!UICONTROL Multivariate Test] ージの作成や、[!DNL Target] 内のページの一部の変更が簡単にできます。

[!DNL Target] のポイントアンドクリックエディターを使用すると、任意の場所を選択し、複数のオファーを追加できます。

[!UICONTROL Multivariate Test] （MVT）は、ページ先頭のレポートを取得します。 つまり、テストは特定の URL に対して実行され、そのページに対して設計されたエクスペリエンスが表示されます。

1. **[!UICONTROL Create Activity]**／**[!UICONTROL Multivariate Test]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] で使用できる様々なアクティビティタイプおよびその違いについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)を参照してください。ニーズに最も適したアクティビティタイプを決定するのに役立つ情報については、[Target アクティビティタイプ](/help/main/c-activities/target-activities-guide.md)を参照してください。

1. （条件付き）配信タイプ（[!UICONTROL Web]、[!UICONTROL Mobile]、[!UICONTROL Email]、[!UICONTROL Other/API]）を選択します。

1. （条件付き） [Target Premium](/help/main/c-intro/intro.md#premium) のお客様は、[ ワークスペースを選択 ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) してください。

1. テストするページの [URL を指定 ](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) し、「**[!UICONTROL Create]**」をクリックします。

   >[!NOTE]
   >
   >最初に HTTP や HTTPS を含む完全な URL を使用します。

   ブラウザーで混合コンテンツを有効にするように求めるメッセージが表示された場合は、メッセージの指示に従います。ブラウザーで混合コンテンツを有効にした後、再度手順 1 から開始します。

   [!UICONTROL Visual Experience Composer] が開きます。

1. &#x200B;
   1. **[!UICONTROL Rename]** アイコン（名前を変更アイコン ![ をクリックし ](/help/main/assets/icons/MoreSmallListVert.svg) 「名前を **[!UICONTROL Rename]** 更」をクリックしてアクティビティの名前を指定し、「名前を変更」をクリックし **[!UICONTROL Save]** す。

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

   以下の種類のオファーを追加できます。

   * HTML
   * 画像
   * テキスト

1. 「**[!UICONTROL Preview]**」をクリックして [ エクスペリエンスをプレビュー ](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md) します。

1. **[!UICONTROL Show Experiences]** アイコン（![ エクスペリエンスを表示アイコン ](/help/main/assets/icons/WebPages.svg)）をクリックして、左側のフレームにすべてのエクスペリエンスのリストを表示します。

1. リスト内の特定のエクスペリエンスをクリックすると、そのエクスペリエンスが表示されます。

1. （条件付き） 1 つ以上のエクスペリエンスをアクティビティから除外するには、エクスペリ **[!UICONTROL Manage Content]** ンス アイコン（![ エクスペリエンスを管理アイコン ](/help/main/assets/icons/Experience.svg)）をクリックして、[!UICONTROL Manage Experiences] ダイアログボックスを表示します。

1. （条件付き） [!UICONTROL Manage Experiences] ダイアログボックスで、除外するエクスペリエンスの横にある **[!UICONTROL More Actions]** アイコン ![ その他のアクションアイコン ](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、「**[!UICONTROL Exclude]**」をクリックします。

   矛盾するバリエーションを表示するエクスペリエンスや、デザイン的にバランスのとれていないエクスペリエンスなどを除外します。

1. （条件付き）複数のエクスペリエンスを除外するには、目的のエクスペリエンスのチェックボックスを選択して、「**[!UICONTROL Exclude]**」をクリックします。

1. [トラフィック見積もりを使用](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)して、テスト計画の実行可能性をテストします。

1. 「**[!UICONTROL Next]**」をクリックして、[!UICONTROL Targeting] のページに進みます。

   **ターゲティング** ステップは、他の [!DNL Target] アクティビティタイプを使用したことがある場合によく見られます。 ここでは、オーディエンスを選択し、各エクスペリエンスを表示する訪問者の割合を指定できます。

   フロー図は、オーディエンスとそのトラフィックの割合を割り当て、トラフィックの割り当て方法を選択し、アクティビティ内の各エクスペリエンスのトラフィックの割り当てを指定する手順を示しています。

1. （条件付き）アクティビティに別のオーディエンスを選択するには、**[!UICONTROL All Visitors]** のコントロールをクリックします。

   [!UICONTROL All Visitors] オーディエンスがデフォルトとして設定されます。 別のオーディエンスを選択すると、その名前が一番左のコントロールに表示されます。

   右側のフレームが表示されます。ここでは、オーディエンスを追加または削除したり、アクティビティの訪問者の割合を割り当てたりできます。

   1. オーディエンスを変更するには **右側のフレームで**&#x200B;[!UICONTROL Replace] アイコン（![ 置換アイコン ](/help/main/assets/icons/Retweet.svg)）をクリックします。
   1. [!UICONTROL Add Audience] のダイアログボックスで [ 目的のオーディエンスを選択 ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) し、「**[!UICONTROL Assign Audience]**」をクリックします。

      **オーディエンスを組み合わせる** をクリックして、[ 複数のオーディエンスを組み合わせたオーディエンスを作成 ](/help/main/c-target/combining-multiple-audiences.md) できます。

      [!UICONTROL Audience Library] ージにない新しいオーディエンスを作成する必要がある場合は、「**オーディエンスを作成**」をクリックします。 [ オーディエンスを作成ワークフロー ](/help/main/c-target/c-audiences/audiences.md) 中に、次のいずれかのオプションを選択できます。

      * **[!UICONTROL Audience Library]**:[!UICONTROL Audience Library] ーザーに保存され、他のアクティビティで再利用できるオンデマンドオーディエンスを作成します。
      * **[!UICONTROL This activity only]**:[!UICONTROL Audience Library] ーザーに保存されず、現在のアクティビティでのみ使用できる [ アクティビティ固有のオーディエンス ](/help/main/c-target/creating-activity-only-audience.md) を作成します。

   1. 右側のフレームで「**[!UICONTROL Visitor Percentage]**」をクリックし、アクティビティにエントリする選定訪問者の割合を選択します。

   例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. [ テストの概要を確認し ](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7) 必要な変更を加えて、「**[!UICONTROL Next]**」をクリックします。

1. [テストの目標と設定を指定](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)します。

1. 「**[!UICONTROL Save and Close]**」をクリックして、アクティビティを作成します。

## トレーニングビデオ：多変量分析テストの作成（9:25） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、[!DNL Target] の 3 ステップのガイド付きワークフローを使用して多変量分析テストを計画および作成する方法を説明します。

* 多変量分析テストの定義と設計
* 多変量分析テストの作成

>[!VIDEO](https://video.tv.adobe.com/v/17395)
