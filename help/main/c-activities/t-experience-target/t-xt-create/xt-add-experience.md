---
keywords: エクスペリエンスの作成;エクスペリエンス作成;優先度;オーディエンス;エクスペリエンス;Visual Experience Composer
description: の使用方法を学ぶ [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) を使用して、 [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ
title: でエクスペリエンスを作成する方法 [!UICONTROL エクスペリエンスのターゲット設定] 活動？
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 0dfdd995c00961ed2aed91ec03406e8493292af7
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 39%

---

# でのエクスペリエンスの作成 [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ

The [!UICONTROL Visual Experience Composer] (VEC) [!DNL Adobe Target] は、ページ上のエクスペリエンスを編集するための視覚的なインターフェイスを提供します ( [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ

1. 変更する要素を選択し、必要な変更を行います。

   While [作成 [!UICONTROL エクスペリエンスのターゲット設定] アクティビティ](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)、3 ステップのガイドによるワークフロー ([!UICONTROL エクスペリエンス]) はデフォルトを表示します [!UICONTROL エクスペリエンス A] と [!UICONTROL すべての訪問者] オーディエンス。

   ![すべての訪問者オーディエンス](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   今おこなった変更が適用される対象 [!UICONTROL エクスペリエンス A]. 以下の手順で、 **[!UICONTROL エクスペリエンスのターゲット設定を追加]** をクリックして、追加のエクスペリエンスを作成します。

   ページ上の要素の上にマウスポインターを置くと、その要素がハイライト表示されます。 強調表示された要素は、Experience Composer を使用して変更できます。エクスペリエンスを変更するために要素で実行可能なアクションのリストについては、[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

   >[!NOTE]
   >
   >デフォルトでは、バナーの回転など JavaScript を含む要素については、VEC で変更できません。VEC を使用して JavaScript を無効にし、これらの要素を変更できます。

1. 追加のエクスペリエンスを作成するには、「**[!UICONTROL エクスペリエンスのターゲットを追加]**」をクリックします。

   ![エクスペリエンスのターゲットを追加リンク](/help/main/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   The [!UICONTROL オーディエンスを追加] ダイアログボックスが表示されます。 オーディエンスに対してエクスペリエンスをターゲット設定するには、エクスペリエンスを追加する前にオーディエンスを選択します。

   オーディエンスライブラリには、[!DNL Target] の一部として事前にビルドされた一般的なオーディエンスを含め、以前に定義したオーディエンスが含まれています。ライブラリからオーディエンスを選択するか、[新しいオーディエンスを作成](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)します。

   既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

   オーディエンスを作成する際に、場所を選択して、その場所のパラメーターを指定できます。 の下 [!UICONTROL カスタム] ([!UICONTROL オーディエンスを作成] > [!UICONTROL カスタム]) をクリックし、場所を選択して、目的のパラメーターを指定します。

   >[!NOTE]
   >
   >オーディエンスリストを開いたとき、インポートされたオーディエンスが 10 分以上経っている場合、オーディエンスはバックグラウンドで自動的にインポートされます。

1. エクスペリエンスでターゲットとする 1 つ以上のオーディエンスを選択して、「**[!UICONTROL 完了]**」をクリックします。

   ![エクスペリエンス B](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   エクスペリエンス B が前の図に表示され、このエクスペリエンスが米国の訪問者オーディエンスをターゲットに設定されました。

1. 上記の手順 1 に従って、このエクスペリエンス用に変更する要素を選択し、必要な変更を行います。

1. 必要に応じて、前述の手順を繰り返して、追加のターゲット設定されたエクスペリエンスを作成します。

1. エクスペリエンスのデザインが終了したら、「**[!UICONTROL 次へ]**」をクリックします。

   アクティビティ図が表示されます。

   ![XT ターゲット設定の図](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >メインページ以外のソースから画像を配信できます ( 例えば、 `akamai.net` および配信済み `adobe.com`) をクリックします。 他の場所でホストされている画像は、フロー図のページのサムネールには表示されません。

1. （条件付き）作成または編集時に、オーディエンスとエクスペリエンスのペアをドラッグ&amp;ドロップします [!UICONTROL エクスペリエンスのターゲット設定] 「 」アクティビティを使用して、ペアの順序を変更します。

   訪問者は、上位のエクスペリエンスから順番に条件を満たしているかどうかが評価されます。

   ![エクスペリエンスの移動](/help/main/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL エクスペリエンスのターゲット設定では、この順番が重要です。]訪問者が最初のオーディエンスとエクスペリエンスのペアに該当する場合、最初のエクスペリエンスが配信されます。

   例えば、 [!UICONTROL エクスペリエンスのターゲット設定] アクティビティ。 その場合、エクスペリエンス B または C の条件に該当すると思っていた訪問者が、エクスペリエンス A に該当することになっていることに後で気が付くことがあります。こうした問題が生じるのは、各オーディエンスが相互に排他的ではなく、適切な順番になっていないことが原因です。例えば、エクスペリエンス A が米国、エクスペリエンス B がサンフランシスコ、エクスペリエンス C がカリフォルニアになっているとします。このシナリオでは、米国のすべてのユーザーは、サンフランシスコやカリフォルニアの他の場所にいる場合でも、エクスペリエンス A の資格を得ます。 オーディエンスとエクスペリエンスのペアは、アクティビティ全体を再作成することなく、最も制限が厳しいものから最も制限が厳しいもの（サンフランシスコ/カリフォルニア/米国）に並べ替えることができます。

   [!UICONTROL すべての訪問者]オーディエンスがある場合、この図で最初のオーディエンスでないことを確認します。「 」をターゲットとするエクスペリエンス[!UICONTROL すべての訪問者]」は、 [!UICONTROL エクスペリエンスのターゲット設定] アクティビティを使用して、他のエクスペリエンスに当てはまらない訪問者を「キャッチ」することができます。

## エクスペリエンスの名前の変更または編集

次の項目をクリックします。 [!UICONTROL 編集] 内のエクスペリエンスのアイコン（縦並びの省略記号） [!UICONTROL エクスペリエンスのターゲット設定] 必要に応じて、「 」アクティビティを選択し、次のオプションから選択します。

* [!UICONTROL 名前変更]
* [!UICONTROL 編集]

![名前の変更および編集オプション](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## エクスペリエンスを削除する

次の日： **[!UICONTROL エクスペリエンス]** ページ（3 ステップのガイドによるワークフローの最初の手順）で、縦の省略記号/ **[!UICONTROL 削除]**.

![エクスペリエンスを削除](/help/main/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## エクスペリエンスの複製

エクスペリエンスを [!UICONTROL エクスペリエンスのターゲット設定] アクティビティを使用すると、エクスペリエンス全体を再作成する必要なく、アクティビティに小さな変更を加えることができます。

次の日： **[!UICONTROL エクスペリエンス]** ページ（3 ステップのガイドによるワークフローの最初の手順）で、縦の省略記号/ **[!UICONTROL 複製]**.

![エクスペリエンスを複製](/help/main/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## トレーニングビデオ：

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### A/B テストから [!UICONTROL エクスペリエンスのターゲット設定]

このビデオでは、A/B テストを次のレベルに進める方法を説明します。 [!UICONTROL エクスペリエンスのターゲット設定] (XT)。

* 3 ステップのガイドによるワークフローを説明し、 [!UICONTROL エクスペリエンスのターゲット設定] アクティビティ
* 様々な地域のオーディエンスに場所固有のコンテンツを配信する方法について説明する
* 適確なコンテンツが適切なオーディエンスに配信されるように、エクスペリエンスを並べ替える方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### アクティビティタイプ（9:03）

このビデオでは、[!DNL Target] で利用できるアクティビティタイプについて説明しています。[!UICONTROL エクスペリエンスのターゲット設定に関する説明は、5:15 から始まります。]

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### の使用 [!UICONTROL Visual Experience Composer]

このビデオでは、 [!UICONTROL エクスペリエンスのターゲット設定] (VEC) オプション。

* ページのコンテンツの変更
* ページのレイアウトの変更

>[!VIDEO](https://video.tv.adobe.com/v/17399)
