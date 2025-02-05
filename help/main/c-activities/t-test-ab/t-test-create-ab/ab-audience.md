---
keywords: オーディエンス;オーディエンスの選択;オーディエンスの選択;セレクター
description: オーディエンス条件に基づいて、どのサイト訪問者がAdobe [!DNL Target]  アクティビティに参加するかを定義します。
title: A [!DNL Target] A/B アクティビティでオーディエンスを選択するにはどうすればよいですか？
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: f6845756f9d4220214b0d9131cd5f27db2ae94a9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 8%

---

# オーディエンスの選択

オーディエンスは、[!DNL Adobe Target] アクティビティに入力される選定訪問者を決定します。

[ アクティビティを作成 ](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) 時の 3 つの部分から成るガイド付きワークフローの [!UICONTROL Targeting] の手順には、オーディエンスとそのトラフィックの割合を割り当てる手順、トラフィックの割り当て方法を選択する手順、アクティビティ内の各エクスペリエンスのトラフィックの割り当てを指定する手順を示すフロー図が表示されます。

![A/B テストのターゲット設定手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

フロー図のすべてのオプションについて詳しくは、「[A/B テストアクティビティの作成 ](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)」を参照してください。

## アクティビティのオーディエンスの選択

1. アクティビティの別のオーディエンスを選択するには、**[!UICONTROL All Visitors]** のコントロールをクリックします。

   [!UICONTROL All Visitors] オーディエンスがデフォルトとして設定されます。 別のオーディエンスを選択すると、その名前が一番左のコントロールに表示されます。

   特定のオーディエンスのターゲティングを使用しない A/B テストの場合は、デフォルトの [!UICONTROL All Visitors] を選択します。

   右側のフレームが表示されます。ここでは、オーディエンスを追加または削除したり、アクティビティの訪問者の割合を割り当てたりできます。

1. オーディエンスを変更するには **右側のフレームで**[!UICONTROL Replace] アイコン（![ 置換アイコン ](/help/main/assets/icons/Retweet.svg)）をクリックします。

1. [!UICONTROL Add Audience] のダイアログボックスで [ 目的のオーディエンスを選択 ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) し、「**[!UICONTROL Assign Audience]**」をクリックします。

   デフォルトでは、すべての訪問者がオーディエンスです。ただし、オーディエンスを変更することができます。オーディエンスは [!UICONTROL Audience Library] ージから選択するか、アクティビティのみのオーディエンスを作成できます。 [!UICONTROL Audience Library] には、[!DNL Target] の一部として事前に作成された一般的なオーディエンスなど、以前に定義されたオーディエンスが含まれています。

1. （条件付き） **オーディエンスを組み合わせる** をクリックして [ 複数のオーディエンスを組み合わせたオーディエンスを作成 ](/help/main/c-target/combining-multiple-audiences.md) します。

1. （条件付き）オーディエンスにまだ含まれていない新しいオーディ [!UICONTROL Audience Library] ンスを作成するには、**オーディエンスを作成** をクリックし、オーディエンスを定義して、「**[!UICONTROL Done]**」をクリックします。

   [ オーディエンスを作成ワークフロー ](/help/main/c-target/c-audiences/audiences.md) の間に、次のオプションから選択できます。

   * **[!UICONTROL Audience Library]**:[!UICONTROL Audience Library] ーザーに保存され、他のアクティビティで再利用できるオンデマンドオーディエンスを作成します。
   * **[!UICONTROL This activity only]**:[!UICONTROL Audience Library] ーザーに保存されず、現在のアクティビティでのみ使用できる [ アクティビティ固有のオーディエンス ](/help/main/c-target/creating-activity-only-audience.md) を作成します。

1. 右側のパネルで「**[!UICONTROL Visitor Percentage]**」をクリックし、条件を満たす訪問者をアクティビティに含める割合を指定します。

1. オーディエンスに満足したら、「**[!UICONTROL Next]**」をクリックして、3 ステップのガイドによるワークフローの 3 ステップ目に移動します。

>[!NOTE]
>
>オーディエンスは、オーディエンスリストを開いたときにバックグラウンドで自動的に読み込まれ、読み込まれたオーディ [!UICONTROL Audience] ンスが 10 分以上前になっている。

## オーディエンスの情報の表示

1. [!UICONTROL Add Audiences] ダイアログボックスで、オーディエンスの横にある **[!UICONTROL Information]** アイコン（![ 情報アイコン ](/help/main/assets/icons/InfoOutline.svg)）をクリックすると、ソースや属性など、そのオーディエンスに関する詳細が表示されます。

1. 「**[!UICONTROL View Full Details]**」をクリックすると、オーディエンスに関する追加の詳細が表示されます。 詳細には、オーディエンスの属性、オーディエンスの説明、ワークスペース、タイプ、ソースおよび、このオーディエンスを参照するアクティビティのリストが含まれます。 アクティビティの名前、ステータス、ワークスペース、オーディエンスの最終変更日時や変更者など、各オーディエンスに関する情報を確認できます。

## オーディエンスの編集またはコピー

オーディエンスを編集またはコピーするには、[!UICONTROL Add Audience] ダイアログボックスで、目的のオーディエンスの横にある [!UICONTROL More Actions] のアイコン ![ その他のアクションアイコン ](/help/main/assets/icons/More.svg)）をクリックし、「[!UICONTROL Edit]」または「[!UICONTROL Copy]」をクリックします。

オーディエンスのコピーは、既存のオーディエンスと同様のオーディエンスを作成したい場合に便利です。オーディエンスのコピーを作成し、編集を加えてから、新しいオーディエンスとして保存できます。
