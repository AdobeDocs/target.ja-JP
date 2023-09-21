---
keywords: オーディエンス;オーディエンスの選択;オーディエンスの選択;セレクター
description: オーディエンスは、Adobeに入るサイト訪問者を決定します [!DNL Target] アクティビティ。
title: オーディエンスを選択する方法 [!DNL Target] A/B アクティビティ？
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: 676350453268e4ffc04df83dcda0525842ca8b07
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 70%

---

# オーディエンスの選択

オーディエンスは、訪問者が [!DNL Adobe Target] アクティビティ。

>[!NOTE]
>
>既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

1. Adobe Analytics の [!UICONTROL 対象ユーザ] ボックスで、 **[!UICONTROL 編集]** アイコン（縦の省略記号）をクリックし、 **[!UICONTROL オーディエンスを置換]**.

   ![「オーディエンスを置換」オプション](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/replace-audience.png)

   デフォルトでは、すべての訪問者がオーディエンスです。ただし、オーディエンスを変更することができます。オーディエンスは、オーディエンスライブラリから選択できます。また、アクティビティのみのオーディエンスを作成することもできます。オーディエンスライブラリには、[!DNL Target] の一部として事前にビルドされた一般的なオーディエンスを含め、以前に定義したオーディエンスが含まれています。

1. 目的のオーディエンスを選択または作成します。

   * ライブラリからオーディエンスを選択
   * [複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)
   * [新しいオーディエンスの作成](/help/main/c-target/c-audiences/create-audience.md#task_1D507519D3AD4390B507F188BD294DC1)
   * [アクティビティのみのオーディエンスの作成](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

   特定のオーディエンスのターゲティングを持たない A/B テストの場合、デフォルトを選択します。 [!UICONTROL すべての訪問者].

   オーディエンスを編集またはコピーするには、 [!UICONTROL オーディエンスを追加] ダイアログボックスに表示されます。

   オーディエンスのコピーは、既存のオーディエンスと同様のオーディエンスを作成したい場合に便利です。オーディエンスのコピーを作成して編集し、新しいオーディエンスとして保存できます。このホバー機能は、他のタイプのアクティビティでも利用できます。

   ![オーディエンスにマウスポインターを置く](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audience_picker_hover-new.png)

   オーディエンスの作成時に、場所（mbox）を選択して、その場所のパラメーターを指定できます。の下 [!UICONTROL カスタムパラメーター]、「 mbox 」を選択してから、目的のパラメーターを指定します。

   >[!NOTE]
   >
   >オーディエンスリストを開いたときに、インポートされたオーディエンスが 10 分以上経っている場合は、オーディエンスがバックグラウンドで自動的にインポートされます。

1. （条件付き）アクティビティに含める資格のある訪問者の割合を指定します。

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

### アクティビティワークフロー — ターゲティング(2:14) ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスのセットアップに関する情報が説明されています。

* オーディエンスのアクティビティへの割り当て
* トラフィックの増減調整
* トラフィック配分方法の選択
* 様々なエクスペリエンスへのトラフィック配分

>[!VIDEO](https://video.tv.adobe.com/v/17385)

詳しくは、[オーディエンス](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)を参照してください。
