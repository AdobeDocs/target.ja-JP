---
keywords: エクスペリエンスの作成;エクスペリエンス作成;優先度;オーディエンス;エクスペリエンス;Visual Experience Composer
description: ' [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）を使用して、[!UICONTROL Experience Targeting] （XT）アクティビティでページのエクスペリエンスを作成および編集する方法を説明します。'
title: '[!UICONTROL Experience Targeting] アクティビティでエクスペリエンスを作成するにはどうすればよいですか？'
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 35%

---

# [!UICONTROL Experience Targeting] （XT）アクティビティでのエクスペリエンスの作成

[!UICONTROL Visual Experience Composer] の [!DNL Adobe Target] （VEC）は、[!UICONTROL Experience Targeting] （XT）アクティビティでページ上のエクスペリエンスを編集するための視覚的なインターフェイスを提供します。

1. 変更する要素を選択し、必要な変更を行います。

   [[!UICONTROL Experience Targeting] アクティビティの作成 ](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) 中、3 つのパートから成るガイド付きワークフロー（[!UICONTROL Experiences]）のステップ 1 では、[!UICONTROL Experience A] オーディエンスを持つデフォルトの [!UICONTROL All Visitors] が表示されます。

   ![すべての訪問者オーディエンス](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   すべての変更が [!UICONTROL Experience A] に適用されます。 次の手順で、「**[!UICONTROL Add Experience Targeting]**」をクリックして、追加のエクスペリエンスを作成します。

   ページ上の要素にポインタを合わせると、その要素がハイライト表示される。 強調表示された要素は、Experience Composer を使用して変更できます。エクスペリエンスを変更するために要素で実行可能なアクションのリストについては、[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

   >[!NOTE]
   >
   >デフォルトでは、バナーの回転など JavaScript を含む要素については、VEC で変更できません。JavaScriptを無効にして、VEC を使用してこれらの要素を変更できます。

1. 追加のエクスペリエンスを作成するには、「**[!UICONTROL Add Experience Targeting]**」をクリックします。

   ![エクスペリエンスのターゲットを追加リンク](/help/main/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   [!UICONTROL Add Audience] ダイアログボックスが表示されます。 エクスペリエンスをオーディエンスにターゲットするには、エクスペリエンスを追加する前に、オーディエンスを選択します。

   オーディエンスライブラリには、[!DNL Target] の一部として事前にビルドされた一般的なオーディエンスを含め、以前に定義したオーディエンスが含まれています。ライブラリからオーディエンスを選択するか、[新しいオーディエンスを作成](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)します。

   既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

   オーディエンスを作成する際に、場所を選択し、その場所のパラメーターを指定できます。 [!UICONTROL Custom] （[!UICONTROL Create Audience]/[!UICONTROL Custom]）で場所を選択し、必要なパラメーターを指定します。

   >[!NOTE]
   >
   >オーディエンスは、オーディエンスリストを開いたときにバックグラウンドで自動的に読み込まれ、読み込まれたオーディエンスが 10 分以上前のものです。

1. エクスペリエンスのターゲットとするオーディエンスを 1 つ以上選択し、「**[!UICONTROL Done]**」をクリックします。

   ![エクスペリエンス B](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   エクスペリエンス B が前の図に表示され、このエクスペリエンスは米国の訪問者オーディエンスをターゲットにしています。

1. このエクスペリエンスで変更する要素を選択し、上記の手順 1 で説明したように必要な変更を行います。

1. 必要に応じて、前述の手順を繰り返して、追加のターゲット設定されたエクスペリエンスを作成します。

1. エクスペリエンスのデザインが完了したら、「**[!UICONTROL Next]**」をクリックします。

   アクティビティ図が表示されます。

   ![XT ターゲット設定の図](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >メインページ以外のソース（`akamai.net` でホストされ、`adobe.com` で配信される画像など）から画像を配信できます。 他の場所でホストされている画像は、フロー図に表示されるページのサムネールには表示されません。

1. （条件付き）アクティビティを作成または編集する際に、オーディエンスとエクスペリエンスのペア [!UICONTROL Experience Targeting] ドラッグ&amp;ドロップして、ペアを目的の順序に配置します。

   訪問者は、上位のエクスペリエンスから順番に条件を満たしているかどうかが評価されます。

   ![エクスペリエンスの移動](/help/main/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL Experience Targeting] は順序が問題であると想定します。 訪問者が最初のオーディエンスとエクスペリエンスのペアに当てはまる場合は、最初のエクスペリエンスが配信されます。

   例えば、[!UICONTROL Experience Targeting] アクティビティの作成時に、注文が重要であることを認識していなかったとします。 その場合、エクスペリエンス B または C の条件に該当すると思っていた訪問者が、エクスペリエンス A に該当することになっていることに後で気が付くことがあります。こうした問題が生じるのは、各オーディエンスが相互に排他的ではなく、適切な順番になっていないことが原因です。例えば、エクスペリエンス A が米国、エクスペリエンス B がサンフランシスコ、エクスペリエンス C がカリフォルニアになっているとします。このシナリオでは、米国のすべてのユーザーは、サンフランシスコやカリフォルニア州の他の場所にいる場合でも、エクスペリエンス A の対象となります。 アクティビティ全体を再作成せずに、オーディエンスとエクスペリエンスのペアを最も制限が高い状態から最も制限が少ない状態（サンフランシスコ/カリフォルニア/米国）に並べ替えることができます。

   [!UICONTROL All Visitors] オーディエンスがある場合は、それが図の最初のオーディエンスでないことを確認します。 「[!UICONTROL All Visitors]」をターゲットにしたエクスペリエンスを [!UICONTROL Experience Targeting] アクティビティの最後のエクスペリエンスとして使用すると、他のエクスペリエンスに分類されていない訪問者を「キャッチ」できます。

## エクスペリエンスの名前の変更または編集

[!UICONTROL Edit] アクティビティのエクスペリエンスで [!UICONTROL Experience Targeting] アイコン（縦並びの省略記号）をクリックし、必要に応じて次のオプションから選択できます。

* [!UICONTROL Rename]
* [!UICONTROL Edit]

![名前の変更および編集オプション](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## エクスペリエンスを削除する

**[!UICONTROL Experiences]** ページ（3 ステップのガイドによるワークフローの最初のステップ）で、縦並びの省略記号/**[!UICONTROL Delete]** をクリックします。

![エクスペリエンスを削除](/help/main/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## エクスペリエンスの複製

[!UICONTROL Experience Targeting] アクティビティのエクスペリエンスをコピーすると、エクスペリエンス全体を再作成しなくても、エクスペリエンスに小さな変更を加えることができます。

**[!UICONTROL Experiences]** ページ（3 ステップのガイドによるワークフローの最初のステップ）で、縦並びの省略記号/**[!UICONTROL Duplicate]** をクリックします。

![エクスペリエンスを複製](/help/main/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## トレーニングビデオ：

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### A/B テストから [!UICONTROL Experience Targeting] へ

このビデオでは、[!UICONTROL Experience Targeting] （XT）で A/B テストを次のレベルに進める方法を説明します。

* [!UICONTROL Experience Targeting] アクティビティを設定するための 3 ステップのガイド付きワークフローの説明
* 様々な地域のオーディエンスに場所固有のコンテンツを配信する方法を説明します
* 適確なコンテンツが適切なオーディエンスに配信されるように、エクスペリエンスを並べ替える方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### アクティビティタイプ （9:03）

このビデオでは、[!DNL Target] で利用できるアクティビティタイプについて説明しています。[!UICONTROL Experience Targeting] については 5:15 から説明します。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### [!UICONTROL Visual Experience Composer] の使用

このビデオでは、[!UICONTROL Experience Targeting] （VEC）オプションの使用について説明します。

* ページのコンテンツの変更
* ページのレイアウトの変更

>[!VIDEO](https://video.tv.adobe.com/v/17399)
