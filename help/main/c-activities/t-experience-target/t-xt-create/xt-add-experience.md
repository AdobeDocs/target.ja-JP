---
keywords: エクスペリエンスの作成;エクスペリエンス作成;優先度;オーディエンス;エクスペリエンス;Visual Experience Composer
description: ' [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）を使用して、[!UICONTROL Experience Targeting] （XT）アクティビティでページ上のエクスペリエンスを作成および編集する方法を説明します。'
title: '[!UICONTROL Experience Targeting] アクティビティでエクスペリエンスを作成するにはどうすればよいですか？'
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
TQID: https://experienceleague.adobe.com/neRp-1hK4qnksT5dJA-A3HD-ShbbpuL2bjkB4He8qPQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 902
ht-degree: 23%

---

# [!UICONTROL Experience Targeting] （XT） アクティビティでのエクスペリエンスの作成

[!DNL Adobe Target]の[!UICONTROL Visual Experience Composer] （VEC）は、[!UICONTROL Experience Targeting] （XT）アクティビティでページ上のエクスペリエンスを編集するための視覚的なインターフェイスを提供します。

1. 変更する要素を選択し、必要な変更を加えます。

   [が[!UICONTROL Experience Targeting] アクティビティ &#x200B;](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)を作成している間、3つの部分からなるガイド付きワークフロー（[!UICONTROL Experiences]）の手順1では、デフォルトの[!UICONTROL Experience A]が[!UICONTROL All Visitors] オーディエンスで表示されます。

   ![すべての訪問者オーディエンス](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors-new.png)

   変更はすべて[!UICONTROL Experience A]に適用されます。 次の手順では、**[!UICONTROL Add Experience Targeting]**&#x200B;をクリックして追加のエクスペリエンスを作成します。

   ページ上の要素にカーソルを合わせると、その要素がハイライト表示されます。 強調表示された要素は、Experience Composer を使用して変更できます。 エクスペリエンスを変更するために要素で実行可能なアクションのリストについては、[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

   >[!NOTE]
   >
   >デフォルトでは、バナーの回転など JavaScript を含む要素については、VEC で変更できません。 JavaScriptを無効にして、VECを使用してこれらの要素を変更できます。

1. 追加のエクスペリエンスを作成するには、**[!UICONTROL Add]** （![&#x200B; ボタンを追加](/help/main/assets/icons/Add.svg)）をクリックします。

   [!UICONTROL Add Audience] ダイアログボックスが表示されます。 エクスペリエンスをオーディエンスにターゲットするには、エクスペリエンスを追加する前にオーディエンスを選択します。

   オーディエンスライブラリには、[!DNL Target] の一部として事前にビルドされた一般的なオーディエンスを含め、以前に定義したオーディエンスが含まれています。 ライブラリからオーディエンスを選択するか、[新しいオーディエンスを作成](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)します。

   既存のオーディエンスを選択するだけでなく、複数のオーディエンスを組み合わせて、新しいオーディエンスを作成するのではなく、オンデマンドで組み合わせたオーディエンスを作成できます。 詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

   オーディエンスを作成する際に、場所を選択し、その場所のパラメーターを指定できます。 [!UICONTROL Custom] （[!UICONTROL Create Audience] > [!UICONTROL Custom]）で、場所を選択し、目的のパラメーターを指定します。

   >[!NOTE]
   >
   >オーディエンスリストを開くと、オーディエンスは自動的にバックグラウンドで読み込まれ、読み込まれたオーディエンスは10分以上前の状態になります。

1. エクスペリエンスでターゲットにする1つ以上のオーディエンスを選択し、**[!UICONTROL Assign Audience]**&#x200B;をクリックします。

   前の図にエクスペリエンス Bが表示され、このエクスペリエンスは適切なオーディエンスを対象としています。

1. 上記の手順1で説明したように、このエクスペリエンスのために変更する要素を選択し、必要な変更を加えます。

1. 必要に応じて、前述の手順を繰り返して、追加のターゲット設定されたエクスペリエンスを作成します。

1. エクスペリエンスのデザインが完了したら、**[!UICONTROL Next]**&#x200B;をクリックします。

   アクティビティ図が表示されます。

   ![XT ターゲティングの図](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-refresh.png)

   >[!NOTE]
   >
   >メインページ以外のソースから画像を配信できます（`akamai.net`でホストされ、`adobe.com`で配信された画像など）。 他の場所でホストされている画像は、フロー図に表示されているページのサムネールには表示されません。

1. （条件付き） [!UICONTROL Experience Targeting] アクティビティの作成または編集中に、オーディエンスとエクスペリエンスのペアをドラッグ&amp;ドロップして、ペアを目的の順序で配置します。

   並べ替えアイコン（![並べ替えアイコン &#x200B;](/help/main/assets/icons/Reorder.svg)）をクリックして、[!UICONTROL Experiences]列を右側に表示し、必要に応じてエクスペリエンスを並べ替えます。

   訪問者は、上位のエクスペリエンスから順番に条件を満たしているかどうかが評価されます。

   [!UICONTROL Experience Targeting]は、注文が重要であると仮定します。 訪問者が最初のオーディエンスとエクスペリエンスのペアに該当した場合、最初のエクスペリエンスが配信されます。

   例えば、[!UICONTROL Experience Targeting] アクティビティの作成中に注文が重要であることに気づいていなかったとします。 後でテストを行うと、エクスペリエンス BまたはCの対象とすべきと思われる訪問者が、エクスペリエンス Aの対象であることがわかります。この状況は、オーディエンスが相互に排他的ではなく、適切な順序ではないことが原因である可能性があります（例えば、エクスペリエンス A =米国、エクスペリエンス B = サンフランシスコ、エクスペリエンス C = カリフォルニアなど）。 このシナリオでは、米国のすべてのユーザーが、サンフランシスコまたはカリフォルニア州の他の場所にいる場合でも、エクスペリエンス Aの対象となります。 オーディエンスとエクスペリエンスのペアを、アクティビティ全体を再作成することなく、最も制限の厳しい順から最も制限の少ない順（サンフランシスコ/カリフォルニア/米国）に並べ替えることができます。

   [!UICONTROL All Visitors]人のオーディエンスがある場合は、そのオーディエンスが図の最初のオーディエンスでないことを確認します。 「[!UICONTROL All Visitors]」をターゲットにしたエクスペリエンスは、[!UICONTROL Experience Targeting] アクティビティの最後のエクスペリエンスとして使用して、他のエクスペリエンスに落ちていない訪問者を「キャッチ」することができます。

## エクスペリエンスの名前を変更、編集、複製、または削除

[!UICONTROL Experience Targeting] アクティビティの図でエクスペリエンスをクリックすると、右側に[!UICONTROL Experiences]列が表示されます。

![名前の変更および編集オプション](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-refresh.png)

必要に応じて、次のオプションから選択します。

* **[!UICONTROL Rename]**: [!UICONTROL Name] フィールドに目的の名前を入力します。
* **[!UICONTROL Edit]**：編集アイコン（![編集アイコン &#x200B;](/help/main/assets/icons/Edit.svg)）をクリックし、必要な変更を加えます。
* **[!UICONTROL Duplicate]**: [!UICONTROL Experience Targeting] アクティビティ内のエクスペリエンスをコピーして、エクスペリエンス全体を再作成しなくても、アクティビティにマイナーな変更を加えることができます。 [!UICONTROL Duplicate] アイコン（![&#x200B; アイコンを複製](/help/main/assets/icons/Duplicate.svg)）をクリックし、必要に応じてエクスペリエンスを編集します。
* **[!UICONTROL Delete]**: [!UICONTROL Delete] アイコン （![削除アイコン &#x200B;](/help/main/assets/icons/Delete.svg)）をクリックし、削除を確認します。

## トレーニングビデオ：

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### A/B テストから[!UICONTROL Experience Targeting]へ

このビデオでは、[!UICONTROL Experience Targeting] （XT）を使用してA/B テストを次のレベルに引き上げる方法について説明します。

* [!UICONTROL Experience Targeting] アクティビティを設定するための3段階のガイド付きワークフローについて説明します
* それぞれの地域のオーディエンスに、位置情報にもとづくコンテンツを配信する方法を説明します
* 適確なコンテンツが適切なオーディエンスに配信されるように、エクスペリエンスを並べ替える方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### アクティビティ タイプ （9:03）

このビデオでは、[!DNL Target] で利用できるアクティビティのタイプについて説明しています。 [!UICONTROL Experience Targeting]は5:15から議論されています。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### [!UICONTROL Visual Experience Composer]の使用

このビデオでは、[!UICONTROL Experience Targeting] （VEC）オプションの使用に関する情報を説明します。

* ページのコンテンツの変更
* ページのレイアウトの変更

>[!VIDEO](https://video.tv.adobe.com/v/17399)
