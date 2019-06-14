---
description: Visual Experience Composer（VEC）は、ページ上のエクスペリエンスを編集するための視覚的なインターフェイスを備えています。
keywords: エクスペリエンスの作成;エクスペリエンス作成;優先度;オーディエンス;エクスペリエンス;Visual Experience Composer
seo-description: Adobe Target Visual Experience Composer（VEC）は、ページ上のエクスペリエンスを編集するための視覚的なインターフェイスを備えています。
seo-title: エクスペリエンスを作成
solution: 'Target '
title: エクスペリエンスを作成
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 5eb79fcd0407e0da841048bcd0a1b64393490fcf

---


# エクスペリエンスの作成{#create-experience}

Visual Experience Composer（VEC）は、エクスペリエンスターゲット設定（XT）アクティビティでページ上のエクスペリエンスを編集するための視覚的なインターフェイスです。

1. 変更する要素を選択し、必要な変更をおこないます。

   XTアクティビティ [](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)の作成時に、3つのガイドによるワークフロー（エクスペリエンス）の1つに、デフォルト [!UICONTROL のエクスペリエンスA] が [!UICONTROL すべての訪問者] のオーディエンスと共に表示されます。

   ![すべての訪問者オーディエンス](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   変更内容は、エクスペリエンスAに適用されます。次の手順で、「エクスペリエンスのターゲット設定 [!UICONTROL ] を追加」をクリックして、エクスペリエンスを追加します。

   ページ上の要素にマウスカーソルを重ねると、その要素が強調表示されます。ハイライトされている要素は、VECを使用して変更できます。エクスペリエンスを変更するために要素上で実行できるアクションのリストについては [、Visual Experience Composerのオプション](/help/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

   Target Classic（旧称 Test&amp;Target）を使用してページに mbox を作成していた場合は、mbox 名を表示する要素として mbox が表示され、他の要素と同様に修正することができます。

1. エクスペリエンスを追加するには、「エクスペリエンスのターゲット設定 **[!A」をクリック]** します。

   ![エクスペリエンスターゲット設定のリンクの追加](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   オーディエンス [!UICONTROL を選択] ダイアログボックスが表示されます。オーディエンスにエクスペリエンスをターゲット設定するには、エクスペリエンスを追加する前にオーディエンスを選択する必要があります。

   オーディエンスライブラリには、Target の一部として事前設計された一般的なオーディエンスを含め、以前に定義したオーディエンスが含まれています。ライブラリからオーディエンスを選択するか、または[新しいオーディエンスを作成](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)します。すべての参加者に同じエクスペリエンスを表示する場合は、「すべての訪問者数」を選択します。

   >[!NOTE]
   >
   >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

   オーディエンスの作成時に、場所（mbox）を選択して、その場所のパラメーターを指定できます。「カスタムパラメーター」から mbox を選択し、必要なパラメーターを指定します。

   >[!NOTE]
   >
   >オーディエンスリストを開いたときに、インポートされたオーディエンスが 10 分以上経っている場合は、オーディエンスがバックグラウンドで自動的にインポートされます。

1. エクスペリエンスをターゲットにする1つまたは複数のオーディエンスを選択し、 **[!UICONTROL 「完了]**」をクリックします。

   ![エクスペリエンス B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   エクスペリエンスBが前の図に表示され、このエクスペリエンスが米国の訪問者のオーディエンスをターゲットにしていることがわかります。

1. このエクスペリエンスに変更する要素を選択し、上記の手順1で説明した変更を行います。

1. 上記の手順を繰り返して、必要に応じてターゲット設定したエクスペリエンスを追加します。

1. エクスペリエンスの設計が終了したら、「 **[!UICONTROL 次へ」]** をクリックします。

   アクティビティ図が表示されます。

   ![XTターゲティング図](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

1. （オプション） XTアクティビティを作成または編集中にオーディエンス/エクスペリエンスのペアをドラッグ&amp;ドロップして、ペアを目的の順序で並べ替えます。

   訪問者は、上から下に順にエクスペリエンスの評価を行います。

   ![エクスペリエンスの移動](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   エクスペリエンスのターゲット設定では、この順番が重要です。訪問者が最初のオーディエンス／エクスペリエンスのペアに該当する場合は、その最初のエクスペリエンスが配信されます。

   例えば、順番が重要であることを知らずに、XT アクティビティを作成したとします。その場合、エクスペリエンス B または C の条件に該当すると思っていた訪問者が、エクスペリエンス A に該当することになっていることに後で気が付くことがあります。こうした問題が生じるのは、各オーディエンスが相互に排他的ではなく、適切な順番になっていないことが原因です。例えば、エクスペリエンス A が米国、エクスペリエンス B がサンフランシスコ、エクスペリエンス C がカリフォルニアになっているとします。この例では、米国のユーザーは、サンフランシスコ在住でもカリフォルニアの他の地域在住でも、すべてエクスペリエンス A に該当することになります。オーディエンス／エクスペリエンスのペアは、アクティビティ全体を作り直さなくても、条件が狭い方から順に並べ替えることができます（この例では、サンフランシスコ &gt; カリフォルニア &gt; 米国）。

## エクスペリエンスの名前変更または編集

XTアクティビティのエクスペリエンス上の [!UICONTROL 編集] アイコン（3つの垂直の楕円）をクリックし、必要に応じて次のオプションから選択できます。

* 名前変更
* 編集

![名前変更および編集オプション](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## エクスペリエンスの削除

**[!UICONTROL エクスペリエンス]** ページ（3ステップガイドのワークフローの最初の手順）で、3つの垂直方向の楕円/ **[!UICONTROL 削除をクリック]** します。

![エクスペリエンスの削除](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## エクスペリエンスの複製

エクスペリエンスのターゲット設定（XT）アクティビティでエクスペリエンスをコピーできるようになり、ゼロからエクスペリエンスを再作成しなくても、エクスペリエンスにマイナーな変更を加えられるようになりました。

**[!UICONTROL エクスペリエンス]** ページ（3 ステップのガイドによるワークフローの最初の手順）で、縦並びの省略記号／**[!UICONTROL 複製]** をクリックします。

![エクスペリエンスの複製](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## トレーニングビデオ：Visual Experience Composer の使用

このビデオでは、Visual Experience Composer のオプションの使用に関する情報を提供しています。

* ページのコンテンツの変更
* ページのレイアウトの変更

>[!VIDEO](https://video.tv.adobe.com/v/17399?captions=jpn)