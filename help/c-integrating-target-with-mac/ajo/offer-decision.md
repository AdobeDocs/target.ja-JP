---
keywords: Visual Experience Composer オプション；Experience Composer オプション；エクスペリエンスオプション；オファーの決定；offer decisioning;ajo;Journey Optimizer
description: で作成したオファーの決定を追加する方法を説明します。 [!DNL Adobe Journey Optimizer] を「 」アクティビティに追加します。
title: オファーの決定の使用方法
feature: Visual Experience Composer (VEC)
exl-id: cec46d5c-bb5e-4cc9-8785-370f158d3f8e
source-git-commit: 1f36666836218718cfac5af2acdc6102d2413e76
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 0%

---

# オファーの決定を使用

用途 [!DNL Adobe Target] と [!DNL Adobe Journey Optimizer] web およびモバイルでの訪問者に対し、次に最適なオファーを決定して配信するためのオファーの決定。

で作成したオファーの決定を追加 [!DNL Adobe Journey Optimizer] から [!DNL Target] アクティビティ（手動） [!UICONTROL A/B テスト] または [!UICONTROL エクスペリエンスのターゲット設定]) を [!UICONTROL Visual Experience Composer] (VEC) または [!UICONTROL フォームベースのコンポーザー] を使用して、パーソナライズされたオファーをインバウンドチャネルで訪問者にテストし配信する [!DNL Target].

>[!NOTE]
>
>このトピックで説明するオファー判定機能は、2022 年 1 月 13 日にリリースされ、 [!DNL Target Standard/Premium] 22.1.1 リリースです。

詳しくは、 [!DNL Adobe Journey Optimizer]を参照してください。 [Journey Optimizerの概要](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) 内 *Journey Optimizer* ドキュメント。

オファーの決定について詳しくは、 [決定管理について](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html) 内 *[!DNL Journey Optimizer]ドキュメント*.

## 前提条件

でオファーの決定を使用するには [!DNL Target]に値を入力するには、以下が必要です。

* [!DNL Adobe Target Standard] または [!DNL Adobe Target Premium] を使用して実装 [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md).

   この機能は、 [!DNL Target] at.js またはその他の [!DNL Target] SDK.

* [!DNL Adobe Journey Optimizer Ultimate] (AJ0 +Offer decisioning) または [!DNL Adobe Experience Platform] そして [!UICONTROL offer decisioning] アプリケーションサービスアドオン。

## 使用例

次に、 [!DNL Target]/[!DNL Adobe Journey Optimizer] のオファー決定を使用する統合 [!DNL Target] アクティビティ：

### スポーツマーチャンダイジング

スポーツリーグのマーケターは、（デスクトップとモバイル Web サイトの両方で）ホームページのコンテンツをパーソナライズする必要がある。 複数のディメンションに基づいてコンテンツをパーソナライズし、関連するフランチャイズ商品を購入するオファーを提示する必要がある場合。 興味の対象：

* 訪問者のお気に入りのチーム
* 最近のアスリート/プレイヤーのアクティビティ（チームの動き、契約の更新、怪我など）

例えば、次の各地域にパーソナライズされたエクスペリエンスを配信するとします。Dortmund、Frankfurt、Bochum と、これらのチームの暗黙で明示的なファンであるユーザー向けのツールです。 指標として、商品サイトへの訪問回数とクリック数を確認します。

次の項目をデザインする： [!UICONTROL A/B テスト] アクティビティ (50/50分割 ) は、デフォルトエクスペリエンスとパーソナライズされたエクスペリエンス（各地域およびチーム向けのオファーを含むオファー決定を含む）の間でおこなわれます。 このアクティビティを使用して、パーソナライズされたエクスペリエンスとコントロールのコンバージョンおよび上昇率を判断します。

### ゲームストリーミングプラットフォーム

ゲーム組織のマーケターは、様々な地域のデスクトップおよびモバイルユーザー向けのゲームストリーミングプラットフォーム用にパーソナライズされたオファーを提供したいと考えています。ドイツ、フランス、メキシコ、ブラジル。 訪問者がこれらの地域の 1 つからデスクトップまたはモバイル Web サイトにアクセスする場合、ローカル言語でのゲームストリーミング用のオファーと、ローカル通貨に対応する価格を提供する必要があります。

In [!DNL Adobe Journey Optimizer]を使用すると、ターゲットとする各地域に対してパーソナライズされたホームページのヒーローオファーを作成し、さらにデフォルトのホームページのヒーローを含むフォールバックオファーを作成できます。 その後、これらのオファーとその実施要件ルールを組み込んだオファーの決定を作成できます。 次に、 [!DNL Target]を使用する場合、 [!DNL Experience Targeting] (XT) アクティビティを作成してオファーの決定をデスクトップまたはモバイル Web サイトに挿入し、パーソナライズされたエクスペリエンスを訪問者に提供します。

## オファーの決定を使用するエクスペリエンスを作成します。

1. 手動の編集中または作成中 [!UICONTROL A/B テスト] または [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ [!UICONTROL Visual Experience Composer] (VEC)、ページ要素をクリックして [オプションメニュー](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   ![Visual Experience Composer のオプションメニュー](assets/options-menu1.png)

   >[!NOTE]
   >
   >また、 [!UICONTROL オファーの決定] 内 [[!UICONTROL フォームベースの Experience Composer]](/help/c-experiences/form-experience-composer.md).

1. クリック **[!UICONTROL 前に挿入]**, **[!UICONTROL 後ろに挿入]**&#x200B;または **[!UICONTROL コンテンツを置換]**&#x200B;を選択し、「 **[!UICONTROL オファーの決定]**.

   この [!UICONTROL オファーの決定] オプションは、編集または作成時に使用できます [手動 [!UICONTROL A/B テスト]](/help/c-activities/t-test-ab/test-ab.md#types) または [[!UICONTROL エクスペリエンスのターゲット設定]](/help/c-activities/t-experience-target/experience-target.md) (XT) アクティビティのみ。 このオプションは、他のアクティビティタイプでは使用できません。 メニューで使用できるオプションは、選択した要素によって異なります。

   ![Visual Experience Composer のオプションメニュー](assets/options-menu.png)

1. 内 **[!UICONTROL オファーの決定を追加]** ダイアログボックスで、目的のサンドボックスと配置を選択します。

   A [サンドボックス](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/overview.html){target=_blank} [!DNL Adobe Experience Platform] では、インスタンスを仮想環境に分割できます。 例えば、実稼動環境とステージング環境があるとします。 A [配置](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/create-components/creating-placements.html){target=_blank} [!DNL Adobe Journey Optimizer] を使用すれば、適切なオファーコンテンツを適切な場所に表示できます。

   ![オファーの決定を追加ダイアログボックスのサンドボックスドロップダウンリストとプレースメントドロップダウンリスト](/help/c-integrating-target-with-mac/ajo/assets/sandbox-placement.png)

1. 目的のオファーの決定を選択し、「 **[!UICONTROL 作成]**.

   ![オファーの決定を追加ダイアログボックスで選択されたオファーの決定](assets/offer-decision.png)

   Web サイトが VEC に表示され、ここで、新しく作成されたオファーの決定を [!UICONTROL 変更] ウィンドウの右側に表示されます。 変更の上にマウスポインターを置いて、 [!UICONTROL プレビュー] アイコンを使用して、オファーの決定を確認します。

   ![プレビューアイコン](assets/preview-icon.png)

   オファーに含まれる様々なオファーを調べるには、 [!UICONTROL オファープレビュー] ダイアログボックスに、フォールバックオファーが含まれます。 フォールバックオファーは、訪問者がコレクション内のパーソナライズされたオファーの対象でない場合に表示されるデフォルトオファーです。

   ![オファーのプレビュー](assets/offer-preview.png)

1. アクティビティの作成を完了するには、 [!UICONTROL ターゲット設定] および [!UICONTROL 目標と設定] 3 ステップのガイドによるワークフローの手順

   >[!IMPORTANT]
   >
   >次の手順で [!DNL Target] アクティビティをパーソナライズする場合は、現在のアクティビティの開始日/終了日が、 [!DNL Adobe Journey Optimizer]. この [!DNL Target] 開始日/終了日が、オファーの決定の開始日/終了日の範囲外 ( デフォルトは [!DNL Target] 訪問者にコンテンツが表示されます。

   ![オファーの決定の警告メッセージ](/help/c-integrating-target-with-mac/ajo/assets/offer-decision-warning.png)

## メモと制限事項

オファーの決定を扱う際は、次の注意事項と制限事項を考慮してください。

* offer decisioningの統合は、で機能します。 [!DNL Target] に基づく実装 [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md). この機能は、 [!DNL Target] at.js またはその他の [!DNL Target] SDK.

* Target とAdobe Journey Optimizerの統合では、 [手動 [!UICONTROL A/B テスト]](/help/c-activities/t-test-ab/test-ab.md#types) および [[!UICONTROL エクスペリエンスのターゲット設定]](/help/c-activities/t-experience-target/experience-target.md) (XT) アクティビティのみ。 この機能は、他のアクティビティタイプでは使用できません。

* text/html コンテンツタイプのオファーは、deliveryURL コンテンツ配信をサポートしていません。 deliveryURL は、フォームベースの Experience Composer を通じてのみサポートされます。この場合、クライアントはコンテンツを明示的に取得し、構成します。

* [!DNL Target] レポートには、オファーの決定レベルのレポートは含まれません。

* 視覚化 [QA リンク](/help/c-activities/c-activity-qa/activity-qa.md) 対象 [!DNL Target] オファーの決定を含むエクスペリエンスは、 [!DNL Adobe Journey Optimizer] を設定する必要があります。
