---
keywords: visual experience composer オプション；experience composer オプション；エクスペリエンスオプション；オファー決定；offer decisioning;ajo;journey optimizer
description: で作成したオファーの決定をアクティビティ  [!DNL Adobe Journey Optimizer]  追加する方法を説明します。
title: オファーの決定の使用方法
feature: Integrations
exl-id: cec46d5c-bb5e-4cc9-8785-370f158d3f8e
source-git-commit: d31c9a6f47ea73342cfb638600f351ade4be7013
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 0%

---

# オファーの決定を使用

[!DNL Adobe Journey Optimizer] オファー決定と [!DNL Adobe Target] を使用すると、web やモバイルでの訪問者に最適な次善のオファーを決定し配信できます。

[!UICONTROL Visual Experience Composer] （VEC）または [!UICONTROL Form-Based Composer] のいずれかを使用して、[!DNL Adobe Journey Optimizer] で作成したオファーの決定を [!DNL Target] アクティビティ（手動 [!UICONTROL A/B Test] または [!UICONTROL Experience Targeting]）に追加し、[!DNL Target] を活用したインバウンドチャネルで、パーソナライズされたオファーをテストして訪問者に配信します。

オファーと [!DNL Adobe Journey Optimizer] ファーの決定について詳しくは、*[!DNL Journey Optimizer]* ドキュメントの次のトピックを参照してください。

* [Journey Optimizerの概要 ](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html)

* [ 意思決定管理について ](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html)

## 前提条件

[!DNL Target] でオファーの決定を使用するには、以下が必要です。

* [!DNL Adobe Target Standard] または [!DNL Adobe Target Premium] は、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} を使用して実装されています。

  この機能は、at.js または他の [!DNL Target] SDK で [!DNL Target] を実装する場合は使用できません。

* [!DNL Adobe Journey Optimizer Ultimate] （AJO + Offer Decisioning）または [!DNL Adobe Experience Platform] および [!UICONTROL Offer Decisioning] application service アドオン。

## サンプルユースケース

以下は、[!DNL Target]/[!DNL Adobe Journey Optimizer] 統合を使用して [!DNL Target] のアクティビティでオファーの決定を使用する方法の使用例です。

### スポーツマーチャンダイジング

スポーツリーグのマーケターとして、ホームページ（デスクトップとモバイルの両方の web サイト）のコンテンツをパーソナライズする必要があります。 複数のディメンションに基づいてコンテンツをパーソナライズし、関連するフランチャイズ商品を購入するためのオファーを提示する場合。 関心のある分野：

* 訪問者のお気に入りのチーム
* 最近のアスリート/選手の活動（例、チームの動き、契約書の更新、けがなど）

例えば、ドルトムント、フランクフルト、ボフムの各リージョンと、これらのチームの暗黙的かつ明示的なファンであるユーザーに対して、パーソナライズされたエクスペリエンスを提供する場合。 指標として、商品サイトの訪問およびクリック数を調べます。

デフォルトのエクスペリエンスとパーソナライズされたエクスペリエンス（各地域およびチームのオファーを含むオファー決定を含む）の間の [!UICONTROL A/B Test] ーディエンスアクティビティ（50 分の 1 分割）をデザインする場合。 このアクティビティを使用して、パーソナライズされたエクスペリエンスとコントロールのコンバージョンおよび上昇率を決定します。

### ゲームストリーミングプラットフォーム

ゲーム組織のマーケターとして、ドイツ、フランス、メキシコ、ブラジルなど、様々な地域のデスクトップユーザーやモバイルユーザーに対してゲームストリーミングプラットフォームのパーソナライズされたオファーを提供します。 訪問者がこれらのいずれかの地域からデスクトップまたはモバイル web サイトにアクセスする場合、ゲームストリーミングのオファーを現地言語と現地通貨の対応価格で配信する必要があります。

ま [!DNL Adobe Journey Optimizer]、ターゲットとする地域ごとにパーソナライズされたホームページヒーローオファーと、デフォルトのホームページヒーローを使用したフォールバックオファーを作成できます。 その後、これらのオファーと実施要件ルールを組み込んだオファー決定を作成できます。 次に、[!DNL Target] で [!DNL Experience Targeting] （XT）アクティビティを作成し、デスクトップまたはモバイル web サイトにそのオファーの決定を挿入して、パーソナライズされたエクスペリエンスを訪問者に提供します。

## オファーの決定を使用するエクスペリエンスを作成します。

1. [!UICONTROL Visual Experience Composer] （VEC）で手動の [!UICONTROL A/B Test] または [!UICONTROL Experience Targeting] （XT）アクティビティを編集または作成する際に、ページ要素をクリックして [ オプションメニュー ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) を表示します。

   ![Visual Experience Composer のオプションメニュー ](assets/options-menu1.png)

   >[!NOTE]
   >
   >また、[[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md) で [!UICONTROL Offer Decisions] を使用するエクスペリエンスを作成することもできます。

1. 「**[!UICONTROL Replace Content]**」をクリックし、「**[!UICONTROL Offer Decision]**」をクリックします。

   [!UICONTROL Offer Decision] オプションは、[ 手動 [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) または [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) （XT） アクティビティの編集または作成時にのみ使用できます。 このオプションは、他のアクティビティタイプでは使用できません。 メニューで使用できるオプションは、選択した要素によって異なります。

   ![Visual Experience Composer のオプションメニュー ](assets/options-menu.png)

1. VEC の右側の **[!UICONTROL Add Offer Decision]** パネルで、目的のサンドボックスを選択し、「オファーの決定。プレースメントを選択」をクリックします。

   [!DNL Adobe Experience Platform] の [ サンドボックス ](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/overview.html){target=_blank} を使用すると、インスタンスを仮想環境に分割できます。 例えば、実稼動環境とステージング環境が存在する場合があります。 [!DNL Adobe Journey Optimizer] の [ プレースメント ](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/create-components/creating-placements.html){target=_blank} は、適切なオファーコンテンツを適切な場所に確実に表示するのに役立ちます。

   ![ オファーの決定を追加ダイアログボックスの「サンドボックス」ドロップダウンリストと「プレースメント」ドロップダウンリスト ](/help/main/c-integrating-target-with-mac/ajo/assets/sandbox-placement.png)

1. 目的のオファーのプレースメントとオファーの決定を選択し、「**[!UICONTROL Add]**」をクリックします。

   ![ オファーの決定を選択ダイアログボックス ](/help/main/c-integrating-target-with-mac/ajo/assets/select-offer-decision.png)

   Web サイトが VEC に表示され、新しく作成したオファーの決定を [!UICONTROL Modifications] のパネルで確認できます。 [!UICONTROL Offer Decision] ントロールパネルの下部にある「[!UICONTROL Offer Preview]」の下の「オファー」をクリックすると、オファーの決定を調べることができます。

   <!--You can examine the various offers contained in the offer by clicking the appropriate icon at the bottom of the [!UICONTROL Offer Preview] dialog box, including the fallback offer. A fallback offer is the default offer displayed when a visitor is not eligible for any of the personalized offers in the collection.-->

   ![ オファーのプレビュー ](assets/offer-preview2.png)

1. 3 つのパートから成るガイド付きワークフローの [!UICONTROL Targeting] と [!UICONTROL Goals & Settings] のステップを完了して、アクティビティの作成を完了します。

   >[!IMPORTANT]
   >
   >[!DNL Target] のアクティビティを確実にパーソナライズするには、現在のアクティビティの開始日/終了日が、オファーの決定の [!DNL Adobe Journey Optimizer] の開始日/終了日と同期していることを確認します。 [!DNL Target] の開始日/終了日がオファーの決定の開始日/終了日の範囲外にある場合、デフォルトの [!DNL Target] コンテンツが訪問者に表示されます。

## メモと制限事項

オファーの決定を扱う際は次の点に注意してください。

* Offer Decisioning 統合は、[Adobe Experience Platform web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} に基づく [!DNL Target] 実装で機能します。 この機能は、at.js または他の [!DNL Target] SDK で [!DNL Target] を実装する場合は使用できません。

* [!DNL Target]/[!DNL Adobe Journey Optimizer] 統合では、[ 手動 [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) および [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) （XT）アクティビティのみをサポートしています。 この機能は、他のアクティビティタイプでは使用できません。

* アクティビティでオファーの決定を使用している場合は、[[!UICONTROL Analytics as the reporting source]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用できません。 アクティビティでオファーの決定を使用する場合は、アクティビティの設定時に [!UICONTROL Goals and Settings] ページでレポートソースとして「[!DNL Target]」を選択します。

* text/html コンテンツタイプのオファーでは、deliveryURL コンテンツ配信をサポートしていません。 deliveryURL は、クライアントがコンテンツの明示的な取得と構成を担当する場合にのみ ](/help/main/c-experiences/form-experience-composer.md) フォームベースの Experience Composer[ を通じてサポートされます。

* [!DNL Target] レポートは、オファーの決定レベルのレポートを提供しません。

* オファーの決定を含んだ [!DNL Target] ーザーエクスペリエンスの [QA リンク ](/help/main/c-activities/c-activity-qa/activity-qa.md) を視覚化すると、それらのオファーの決定に対する [!DNL Adobe Journey Optimizer] のフリークエンシーキャップ設定に影響します。
