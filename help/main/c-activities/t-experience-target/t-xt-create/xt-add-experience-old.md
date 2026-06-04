---
keywords: エクスペリエンスの作成;エクスペリエンス作成;優先度;オーディエンス;エクスペリエンス;Visual Experience Composer
description: ' [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）を使用して、[!UICONTROL Experience Targeting] （XT）アクティビティでページ上のエクスペリエンスを作成および編集する方法について説明します。'
title: '[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] アクティビティでエクスペリエンスを作成するにはどうすればよいですか？'
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 32%

---

# [!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （XT）アクティビティでのエクスペリエンスの作成

[!DNL Adobe Target]の[!UICONTROL Visual Experience Composer] （VEC）は、[!UICONTROL Experience Targeting] （XT）アクティビティでページ上のエクスペリエンスを編集するためのビジュアルインターフェイスを提供します。

1. 変更する要素を選択し、必要な変更を加えます。

   [ エクスペリエンスのターゲット設定] アクティビティ (/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)を作成すると、3つの部分からなるガイド付きワークフロー（[!UICONTROL &#x200B; エクスペリエンス &#x200B;]）の手順1では、デフォルトの[!UICONTROL &#x200B; エクスペリエンス A]と[!UICONTROL すべての訪問者] オーディエンスが表示されます。

   ![すべての訪問者オーディエンス](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   変更はすべて[!UICONTROL &#x200B; エクスペリエンス A]に適用されます。以下の手順では、**[!UICONTROL エクスペリエンスターゲティングを追加]**&#x200B;をクリックして、追加のエクスペリエンスを作成します。

   ページ上の要素にカーソルを合わせると、その要素がハイライト表示されます。 強調表示された要素は、Experience Composer を使用して変更できます。 エクスペリエンスを変更するために要素で実行可能なアクションのリストについては、[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

   >[!NOTE]
   >
   >デフォルトでは、バナーの回転など JavaScript を含む要素については、VEC で変更できません。 JavaScriptを無効にして、VECを使用してこれらの要素を変更できます。

1. 追加のエクスペリエンスを作成するには、**[!UICONTROL エクスペリエンスのターゲット設定を追加]**&#x200B;をクリックします。

   ![エクスペリエンスのターゲット設定を追加リンク](/help/main/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   「[!UICONTROL &#x200B; オーディエンスを追加]」ダイアログボックスが表示されます。 エクスペリエンスをオーディエンスにターゲットするには、エクスペリエンスを追加する前にオーディエンスを選択します。

   オーディエンスライブラリには、[!DNL Target] の一部として事前にビルドされた一般的なオーディエンスを含め、以前に定義したオーディエンスが含まれています。 ライブラリからオーディエンスを選択するか、[新しいオーディエンスを作成](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)します。

   既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。 詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

   オーディエンスを作成する際に、場所を選択し、その場所のパラメーターを指定できます。 [!UICONTROL &#x200B; カスタム &#x200B;] （[!UICONTROL &#x200B; オーディエンスを作成] > [!UICONTROL &#x200B; カスタム &#x200B;]）で、場所を選択し、目的のパラメーターを指定します。

   >[!NOTE]
   >
   >オーディエンスリストを開くと、オーディエンスは自動的にバックグラウンドで読み込まれ、読み込まれたオーディエンスは10分以上前の状態になります。

1. エクスペリエンスでターゲットとする1つ以上のオーディエンスを選択し、**[!UICONTROL 完了]**&#x200B;をクリックします。

   ![エクスペリエンス B](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   エクスペリエンス Bが上の図に表示され、このエクスペリエンスはUS Visitors オーディエンスをターゲットにしています。

1. 上記の手順1で説明したように、このエクスペリエンスのために変更する要素を選択し、必要な変更を加えます。

1. 必要に応じて、前述の手順を繰り返して、追加のターゲット設定されたエクスペリエンスを作成します。

1. エクスペリエンスのデザインが完了したら、**[!UICONTROL 次へ]**&#x200B;をクリックします。

   アクティビティ図が表示されます。

   ![XT ターゲティングの図](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >メインページ以外のソースから画像を配信できます（`akamai.net`でホストされ、`adobe.com`で配信された画像など）。 他の場所でホストされている画像は、フロー図に表示されているページのサムネールには表示されません。

1. （条件付き）エクスペリエンスのターゲット設定[!UICONTROL &#x200B; アクティビティの作成または編集中に、オーディエンスとエクスペリエンスのペアをドラッグ&amp;ドロップして、目的の順序で配置します。]

   訪問者は、上位のエクスペリエンスから順番に条件を満たしているかどうかが評価されます。

   ![エクスペリエンスの移動](/help/main/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL &#x200B; エクスペリエンスのターゲット設定]は、注文が重要であると仮定します。 訪問者が最初のオーディエンスとエクスペリエンスのペアに該当した場合、最初のエクスペリエンスが配信されます。

   例えば、[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] アクティビティの作成中に、注文が重要であることに気づいていなかったとします。 その場合、エクスペリエンス B または C の条件に該当すると思っていた訪問者が、エクスペリエンス A に該当することになっていることに後で気が付くことがあります。こうした問題が生じるのは、各オーディエンスが相互に排他的ではなく、適切な順番になっていないことが原因です。例えば、エクスペリエンス A が米国、エクスペリエンス B がサンフランシスコ、エクスペリエンス C がカリフォルニアになっているとします。 このシナリオでは、米国のすべてのユーザーが、サンフランシスコまたはカリフォルニア州の他の場所にいる場合でも、エクスペリエンス Aの対象となります。 オーディエンスとエクスペリエンスのペアを、アクティビティ全体を再作成することなく、最も制限の厳しい順から最も制限の少ない順（サンフランシスコ/カリフォルニア/米国）に並べ替えることができます。

   [!UICONTROL すべての訪問者]のオーディエンスがある場合は、そのオーディエンスが図の最初のオーディエンスでないことを確認してください。 「[!UICONTROL すべての訪問者]」をターゲットにしたエクスペリエンスは、[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] アクティビティの最後のエクスペリエンスとして使用して、他のエクスペリエンスに入っていない訪問者を「キャッチ」することができます。

## エクスペリエンスの名前の変更または編集

「[!UICONTROL &#x200B; エクスペリエンスのターゲット設定]」アクティビティのエクスペリエンスの「[!UICONTROL 編集]」アイコン（垂直省略記号）をクリックし、必要に応じて次のオプションから選択できます。

* [!UICONTROL 名前変更]
* [!UICONTROL Edit]

![名前の変更および編集オプション](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## エクスペリエンスを削除する

**[!UICONTROL エクスペリエンス]** ページ（3段階のガイド付きワークフローの最初のステップ）で、垂直省略記号> **[!UICONTROL 削除]**&#x200B;をクリックします。

![エクスペリエンスを削除](/help/main/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## エクスペリエンスの複製

エクスペリエンスを[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] アクティビティにコピーできるので、エクスペリエンス全体を再作成することなく、エクスペリエンスに微調整を加えることができます。

**[!UICONTROL エクスペリエンス]** ページ（3段階のガイド付きワークフローの最初のステップ）で、垂直省略記号> **[!UICONTROL 重複]**&#x200B;をクリックします。

![エクスペリエンスを複製](/help/main/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## トレーニングビデオ：

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### A/B テストから[!UICONTROL &#x200B; エクスペリエンスのターゲット設定]へ

このビデオでは、[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （XT）でA/B テストを次のレベルに引き上げる方法について説明します。

* [!UICONTROL &#x200B; エクスペリエンスのターゲット設定] アクティビティを設定するための3段階のガイド付きワークフローについて説明します
* それぞれの地域のオーディエンスに、位置情報にもとづくコンテンツを配信する方法を説明します
* 適確なコンテンツが適切なオーディエンスに配信されるように、エクスペリエンスを並べ替える方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/38305?captions=jpn)

### アクティビティ タイプ （9:03）

このビデオでは、[!DNL Target] で利用できるアクティビティのタイプについて説明しています。 [!UICONTROL &#x200B; エクスペリエンスのターゲット設定]については、5:15から説明します。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/30014?captions=jpn)

### [!UICONTROL Visual Experience Composer]の使用

このビデオでは、[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （VEC）オプションの使用に関する情報を説明します。

* ページのコンテンツの変更
* ページのレイアウトの変更

>[!VIDEO](https://video.tv.adobe.com/v/29948?captions=jpn)
