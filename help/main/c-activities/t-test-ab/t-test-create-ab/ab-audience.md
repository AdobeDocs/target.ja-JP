---
keywords: オーディエンス;オーディエンスの選択;オーディエンスの選択;セレクター
description: オーディエンス条件に基づいて、Adobe [!DNL Target]  アクティビティに参加するサイト訪問者を定義します。
title: A [!DNL Target] A/B アクティビティでオーディエンスを選択するにはどうすればよいですか？
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
TQID: https://experienceleague.adobe.com/7W8BrRxk4mKlYlgGb-GSOuc0kRMRWBvSochz9STYrTs
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 531
ht-degree: 11%

---

# オーディエンスの選択

オーディエンスは、どの適格な訪問者を[!DNL Adobe Target] アクティビティに入力するかを決定します。

アクティビティを作成する[の際の3つの部分で構成されるガイド付きワークフローの[!UICONTROL Targeting] ステップでは、オーディエンスとそのトラフィック率の割り当て、トラフィック割り当て方法の選択、アクティビティ内の各エクスペリエンスのトラフィック割り当ての指定の手順を示すフロー図が表示されます。](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)

![A/B テストのターゲティング手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

フロー図のすべてのオプションについて詳しくは、[A/B テストアクティビティの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)を参照してください。

## アクティビティのオーディエンスの選択

1. アクティビティの別のオーディエンスを選択するには、**[!UICONTROL All Visitors]** コントロールをクリックします。

   [!UICONTROL All Visitors] オーディエンスがデフォルトとして設定されています。 別のオーディエンスを選択すると、その名前が一番左のコントロールに表示されます。

   特定のオーディエンスターゲティングを使用しないA/B テストの場合は、デフォルトの[!UICONTROL All Visitors]を選択します。

   右側のフレームが表示され、オーディエンスを追加または削除し、アクティビティの訪問者パーセンテージを割り当てることができます。

1. オーディエンスを変更するには、右側のフレームの&#x200B;**[!UICONTROL Replace]アイコン** （![置換アイコン &#x200B;](/help/main/assets/icons/Retweet.svg)）をクリックします。

1. [!UICONTROL Add Audience] ダイアログボックスで、[目的のオーディエンス &#x200B;](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)を選択し、**[!UICONTROL Assign Audience]**&#x200B;をクリックします。

   デフォルトでは、すべての訪問者がオーディエンスです。 ただし、オーディエンスを変更することができます。 オーディエンスは[!UICONTROL Audience Library]から選択されるか、アクティビティのみのオーディエンスを作成できます。 [!UICONTROL Audience Library]には、[!DNL Target]の一部として事前に構築された一般的なオーディエンスなど、以前に定義されたオーディエンスが含まれています。

1. （条件付き）複数のオーディエンスを組み合わせるオーディエンスを作成するには、**オーディエンスを組み合わせる**&#x200B;から[をクリックします](/help/main/c-target/combining-multiple-audiences.md)。

1. （条件付き）まだ[!UICONTROL Audience Library]にない新しいオーディエンスを作成するには、**オーディエンスの作成**&#x200B;をクリックし、オーディエンスを定義してから&#x200B;**[!UICONTROL Done]**&#x200B;をクリックします。

   [create-audience ワークフロー](/help/main/c-target/c-audiences/audiences.md)中に、次のオプションから選択できます。

   * **[!UICONTROL Audience Library]**: [!UICONTROL Audience Library]に保存されたオンデマンドオーディエンスを作成し、他のアクティビティで再利用できます。
   * **[!UICONTROL This activity only]**: [!UICONTROL Audience Library]に保存されず、現在のアクティビティでのみ使用できる[&#x200B; アクティビティ固有のオーディエンス &#x200B;](/help/main/c-target/creating-activity-only-audience.md)を作成します。

1. 右側のペインで「**[!UICONTROL Visitor Percentage]**」をクリックし、アクティビティに含める対象となる訪問者の割合を指定します。

1. オーディエンスに問題がなければ、**[!UICONTROL Next]**&#x200B;をクリックして、3段階のガイド付きワークフローの3番目のステップに移動します。

>[!NOTE]
>
>[!UICONTROL Audience] リストを開くと、オーディエンスは自動的にバックグラウンドで読み込まれ、読み込まれたオーディエンスが10分以上経過しています。

## オーディエンス情報の表示

1. [!UICONTROL Add Audiences] ダイアログボックスで、オーディエンスの横にある&#x200B;**[!UICONTROL Information]** アイコン （![情報アイコン &#x200B;](/help/main/assets/icons/InfoOutline.svg)）をクリックして、そのオーディエンスのソースと属性を含む詳細を表示します。

1. 「**[!UICONTROL View Full Details]**」をクリックして、オーディエンスに関する詳細を表示します。 詳細には、オーディエンスの属性、オーディエンスの説明、ワークスペース、タイプ、ソース、およびこのオーディエンスを参照するアクティビティのリストが含まれます。 アクティビティ名、ステータス、ワークスペース、オーディエンスが最後に変更された日時や変更者など、各オーディエンスに関する情報を確認できます。

## オーディエンスの編集またはコピー

オーディエンスを編集またはコピーするには、[!UICONTROL Add Audience] ダイアログボックスで、目的のオーディエンスの横にある[!UICONTROL More Actions] アイコン（![詳細アクション アイコン &#x200B;](/help/main/assets/icons/More.svg)）をクリックし、[!UICONTROL Edit]または[!UICONTROL Copy]をクリックします。

オーディエンスのコピーは、既存のオーディエンスと同様のオーディエンスを作成したい場合に便利です。 オーディエンスのコピーを作成して編集し、新しいオーディエンスとして保存できます。
