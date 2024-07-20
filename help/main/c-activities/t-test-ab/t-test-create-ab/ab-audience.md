---
keywords: オーディエンス;オーディエンスの選択;オーディエンスの選択;セレクター
description: オーディエンスは、どのサイト訪問者にAdobeアクティビティ  [!DNL Target]  入力するかを決定します。
title: A [!DNL Target] A/B アクティビティでオーディエンスを選択するにはどうすればよいですか？
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: 676350453268e4ffc04df83dcda0525842ca8b07
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 66%

---

# オーディエンスの選択

オーディエンスは、[!DNL Adobe Target] アクティビティに入力するサイト訪問者を決定します。

>[!NOTE]
>
>既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

1. [!UICONTROL Audience] のボックスで、**[!UICONTROL Edit]** アイコン（縦並びの省略記号）をクリックし、「**[!UICONTROL Replace Audience]**」をクリックします。

   ![「オーディエンスを置換」オプション](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/replace-audience.png)

   デフォルトでは、すべての訪問者がオーディエンスです。ただし、オーディエンスを変更することができます。オーディエンスは、オーディエンスライブラリから選択できます。また、アクティビティのみのオーディエンスを作成することもできます。オーディエンスライブラリには、[!DNL Target] の一部として事前に作成された一般的なオーディエンスなど、以前に定義されたオーディエンスが含まれています。

1. 目的のオーディエンスを選択または作成します。

   * ライブラリからオーディエンスを選択
   * [複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)
   * [新しいオーディエンスの作成](/help/main/c-target/c-audiences/create-audience.md#task_1D507519D3AD4390B507F188BD294DC1)
   * [ アクティビティのみのオーディエンスの作成 ](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)。

   特定のオーディエンスのターゲティングを使用しない A/B テストの場合は、デフォルトの [!UICONTROL All Visitors] を選択します。

   次に示すように、[!UICONTROL Add Audience] ールダイアログボックスで目的のオーディエンスにカーソルを合わせて、オーディエンスを編集またはコピーすることもできます。

   オーディエンスのコピーは、既存のオーディエンスと同様のオーディエンスを作成したい場合に便利です。オーディエンスのコピーを作成して編集し、新しいオーディエンスとして保存できます。このホバー機能は、他のタイプのアクティビティでも利用できます。

   ![オーディエンスにマウスポインターを置く](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audience_picker_hover-new.png)

   オーディエンスの作成時に、場所（mbox）を選択して、その場所のパラメーターを指定できます。「[!UICONTROL Custom Parameters]」で mbox を選択し、必要なパラメーターを指定します。

   >[!NOTE]
   >
   >オーディエンスリストを開いたときに、インポートされたオーディエンスが 10 分以上経っている場合は、オーディエンスがバックグラウンドで自動的にインポートされます。

1. （条件付き）アクティビティに含める選定訪問者の割合を指定します。

   例えば、すべての訪問者の 50％を含めることを選択できます。

   ![オーディエンスの割合](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   また、Target で[自動的にトラフィックを割り当てる](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)こともできます。

## トレーニングビデオ

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### Adobe Target での オーディエンス の使用(6:21) ![概要バッジ](/help/main/assets/overview.png)

このビデオでは、[!DNL Target Standard/Premium] におけるオーディエンスの使用方法を説明します。

* 用語「オーディエンス」の説明
* 最適化のためにオーディエンスを使用する 2 つの方法の説明
* オーディエンスリストでのオーディエンスの検索
* アクティビティのオーディエンスへのターゲット設定
* アクティビティの受動的なレポート用でのオーディエンスの使用

>[!VIDEO](https://video.tv.adobe.com/v/17398)

### アクティビティワークフロー – ターゲティング（2:14） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスのセットアップに関する情報が説明されています。

* オーディエンスのアクティビティへの割り当て
* トラフィックの増減調整
* トラフィック配分方法の選択
* 様々なエクスペリエンスへのトラフィック配分

>[!VIDEO](https://video.tv.adobe.com/v/17385)

詳しくは、[オーディエンス](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)を参照してください。
