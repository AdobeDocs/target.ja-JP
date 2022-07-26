---
keywords: エクスペリエンスの作成;エクスペリエンス作成;優先度;オーディエンス;エクスペリエンス;Visual Experience Composer
description: Adobe [!DNL Target] Visual Experience Composer(VEC) を使用して、エクスペリエンスターゲット設定 (XT) アクティビティのページ上でエクスペリエンスを作成および編集できます。
title: エクスペリエンスターゲット設定アクティビティでエクスペリエンスを作成する方法を教えてください。
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 87%

---

# エクスペリエンスターゲット設定 (XT) アクティビティでのエクスペリエンスの作成

この [!UICONTROL Visual Experience Composer] (VEC) [!DNL Adobe Target] は、 [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ

1. 変更する要素を選択し、必要な変更をおこないます。

   [XT アクティビティを作成する](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)際に、3 ステップのガイドによるワークフローの手順 1（[!UICONTROL エクスペリエンス]）で、[!UICONTROL すべての訪問者]オーディエンスを含むデフォルトの[!UICONTROL エクスペリエンス A] が表示されます。

   ![すべての訪問者オーディエンス](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   今おこなった変更は、エクスペリエンス A に適用されます。以下の手順では、「**[!UICONTROL エクスペリエンスのターゲットを追加]**」をクリックして、追加のエクスペリエンスを作成します。

   ページ上の要素にマウスポインターを置くと、その要素が強調表示されます。強調表示された要素は、Experience Composer を使用して変更できます。エクスペリエンスを変更するために要素で実行可能なアクションのリストについては、[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

   以下を作成した場合、 [!DNL Target] 次を使用してページでリクエスト [!DNL Target Classic]、 [!DNL Target] リクエストは、リクエスト名を示す要素として表示され、他の要素と同様に変更できます。

   >[!NOTE]
   >
   >デフォルトでは、バナーの回転など JavaScript を含む要素については、VEC で変更できません。このような要素を VEC を使用して変更するには、JavaScript を無効にします。

1. 追加のエクスペリエンスを作成するには、「**[!UICONTROL エクスペリエンスのターゲットを追加]**」をクリックします。

   ![エクスペリエンスのターゲットを追加リンク](/help/main/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   [!UICONTROL オーディエンスを選択]ダイアログボックスが表示されます。オーディエンスに対してエクスペリエンスをターゲット設定するには、エクスペリエンスを追加する前にオーディエンスを選択する必要があります。

   オーディエンスライブラリには、[!DNL Target] の一部として事前にビルドされた一般的なオーディエンスを含め、以前に定義したオーディエンスが含まれています。ライブラリからオーディエンスを選択するか、[新しいオーディエンスを作成](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)します。

   >[!NOTE]
   >
   >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

   オーディエンスを作成する際に、場所を選択して、その場所のパラメーターを指定できます。 の下 [!UICONTROL カスタム] (Create Audience/Add Rule/Custom)、場所を選択し、目的のパラメーターを指定します。

   >[!NOTE]
   >
   >オーディエンスリストを開いたときに、インポートされたオーディエンスが 10 分以上経っている場合は、オーディエンスがバックグラウンドで自動的にインポートされます。

1. エクスペリエンスでターゲットとする 1 つ以上のオーディエンスを選択して、「**[!UICONTROL 完了]**」をクリックします。

   ![エクスペリエンス B](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   前述の図にエクスペリエンス B が表示され、このエクスペリエンスが米国の訪問者オーディエンスをターゲットとしていることがわかります。

1. 前述の手順 1 で説明したように、このエクスペリエンス用に変更する要素を選択し、必要な変更をおこないます。

1. 必要に応じて、前述の手順を繰り返して、追加のターゲット設定されたエクスペリエンスを作成します。

1. エクスペリエンスのデザインが終了したら、「**[!UICONTROL 次へ]**」をクリックします。

   アクティビティ図が表示されます。

   ![XT ターゲット設定の図](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >メインページ以外のソースから画像を提供する場合（例えば、`akamai.net` 上でホストされている画像を `adobe.com` で提供する場合）、フロー図内のページのサムネールには画像が表示されません。

1. （条件付き）XT アクティビティの作成または編集時に、オーディエンス／エクスペリエンスのペアをドラッグ＆ドロップして順番を変更します。

   訪問者は、上位のエクスペリエンスから順番に条件を満たしているかどうかが評価されます。

   ![エクスペリエンスの移動](/help/main/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL エクスペリエンスのターゲット設定では、この順番が重要です。]訪問者が最初のオーディエンス／エクスペリエンスのペアに該当する場合は、その最初のエクスペリエンスが配信されます。

   例えば、順番が重要であることを知らずに、XT アクティビティを作成したとします。その場合、エクスペリエンス B または C の条件に該当すると思っていた訪問者が、エクスペリエンス A に該当することになっていることに後で気が付くことがあります。こうした問題が生じるのは、各オーディエンスが相互に排他的ではなく、適切な順番になっていないことが原因です。例えば、エクスペリエンス A が米国、エクスペリエンス B がサンフランシスコ、エクスペリエンス C がカリフォルニアになっているとします。この例では、米国のユーザーは、サンフランシスコ在住でもカリフォルニアの他の地域在住でも、すべてエクスペリエンス A に該当することになります。オーディエンス／エクスペリエンスのペアは、アクティビティ全体を作り直さなくても、条件が狭い方から順に並べ替えることができます（この例では、サンフランシスコ > カリフォルニア > 米国）。

   [!UICONTROL すべての訪問者]オーディエンスがある場合、この図で最初のオーディエンスでないことを確認します。ターゲット設定アクティビティで最後のエクスペリエンスとして「すべての訪問者」をターゲットに設定しているエクスペリエンスを使用すると、他のどのエクスペリエンスにも該当しない訪問者を「捕捉」することができます。

## エクスペリエンスの名前の変更または編集

必要に応じて、XT アクティビティのエクスペリエンスの[!UICONTROL 編集]アイコン（縦並びの省略記号）をクリックして、以下のオプションから選択できます。

* 名前変更
* 編集

![名前の変更および編集オプション](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## エクスペリエンスを削除する

**[!UICONTROL エクスペリエンス]**&#x200B;ページ（3 ステップのガイドによるワークフローの最初の手順）で、縦並びの省略記号／**[!UICONTROL 削除]**&#x200B;をクリックします。

![エクスペリエンスを削除](/help/main/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## エクスペリエンスの複製

XT アクティビティでエクスペリエンスをコピーできるようになり、ゼロからエクスペリエンスを再作成しなくても、エクスペリエンスにマイナーな変更を加えられるようになりました。

**[!UICONTROL エクスペリエンス]**&#x200B;ページ（3 ステップのガイドによるワークフローの最初の手順）で、縦並びの省略記号／**[!UICONTROL 複製]**&#x200B;をクリックします。

![エクスペリエンスを複製](/help/main/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## トレーニングビデオ：

以下のビデオは、この記事で説明する概念についてさらに詳しく説明しています。

### A/B テストからエクスペリエンスのターゲット設定へ

このビデオでは、エクスペリエンスのターゲット設定（XT）で A/B テストを次の段階に進める方法について説明します。

* XT アクティビティを設定するための、3 つの手順から成るガイド付きのワークフローを説明します。
* 場所に特有のコンテンツを様々な地域のオーディエンスに配信する方法を説明します。
* 適確なコンテンツが適切なオーディエンスに配信されるように、エクスペリエンスを並べ替える方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### アクティビティのタイプ（9:03）

このビデオでは、Target Standard／Premium で利用できるアクティビティのタイプについて説明しています。エクスペリエンスのターゲット設定に関する説明は、5:15 から始まります。

* [!DNL Adobe Target] に含まれるアクティビティのタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプに適用される 3 ステップのガイドによるワークフローについての説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Visual Experience Composer の使用

このビデオでは、Visual Experience Composer のオプションの使用に関する情報を提供しています。

* ページのコンテンツの変更
* ページのレイアウトの変更

>[!VIDEO](https://video.tv.adobe.com/v/17399)
