---
keywords: analytics for target;A4T;レポートソースとしての analytics
description: Analyticsをターゲットに使用する方法(A4T)について説明します。 A4Tは、Analytics指標とオーディエンスセグメントを使用するターゲットアクティビティのAnalyticsレポートへのアクセスを提供します。
title: A4Tでレポートを使用する方法
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 32%

---


# A4T レポート{#a-t-reporting}

[!DNL Analytics]を[!DNL Target] (A4T)のレポートソースとして使用すると、[!DNL Target]アクティビティの[!DNL Analytics]レポートにアクセスできます。

アクティビティの表示レポートは、[!DNL Analytics]と[!DNL Target]の両方で作成できます。

[!DNL Analytics]を[!DNL Target]に使用するレポートのベストプラクティスについては、[このAdobe Sparkのページ](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)を参照してください。

## 概要 {#section_035A62D65608423285D8A5A54731E2C5}

[!DNL Analytics]と[!DNL Target]の両方のレポートは、サイトへの訪問者ではなく、参加者（テストに参加した人）を測定します。

訪問者がページ上のアクティビティコンテンツを見るたびに、[!DNL Target]は、訪問者がどのアクティビティとエクスペリエンスを見たかを含む、[!DNL Analytics]への直接のサーバー間呼び出しを行います。 [!DNL Target] また、コンバージョンがおこなわれ [!DNL Analytics] た場合は必ずが呼び出されます。[!DNL Analytics] によって、「アクティビティコンバージョン」という名前の特定の新しい [!DNL Analytics] イベントとしてコンバージョンが追加されます。この [!DNL Analytics]は、によって収集された他のデータと共に追跡されます。

[!UICONTROL 「]を選択」操作を使用し、*参加者*&#x200B;で並べ替えると、選択した期間に参加者を獲得したエクスペリエンスのみがレポートに表示されます。

>[!NOTE]
>
>[!DNL Target]が生成するレポートには、4分の遅延があります。 A4Tで動作するアクティビティの場合、[!DNL Target]と[!DNL Analytics]の両方のレポートで、アクティビティが最初に保存されてから、エクスペリエンス別にレポートデータを分類できるようになるまでに、最大24時間かかる場合があります。 最初の 24 時間に収集されたデータも正確であり、適切なエクスペリエンスに割り当てられます。

## Analytics のレポート {#analytics}

[!DNL Analytics]には、A4T統合を有効にした後に使用できるディメンションと指標がいくつかあります。

### ディメンション

* [!UICONTROL ターゲットの分析]  — 統合を介して渡される親ID。このディメンションの形式は`Activity ID:Experience ID:3rd ID`です。 次のディメンションは、このディメンションの分類です。
* [!UICONTROL ターゲットアクティビティ]
* [!UICONTROL ターゲットエクスペリエンス]
* [!UICONTROL ターゲットアクティビティ] / [!UICONTROL エクスペリエンス]
* [!UICONTROL 3番目のID]  — 無視可能

### 指標

* [!UICONTROL アクティビティのインプレッション] -  レポートの [!DNL Target] 参加者数に一致します。
* [!UICONTROL アクティビティコンバージョン] - [!UICONTROL レポート内の] カスタムコンバージョン [!DNL Target] 数に一致します。

[!DNL Analysis Workspace]で、[!UICONTROL ターゲットの分析]パネルを使用して、[!DNL Target]のアクティビティーとエクスペリエンスを上昇率と信頼性の高いもので分析します。 詳しくは、*Analyticsツールガイド*&#x200B;の[ターゲット用のAnalytics(A4T)パネル](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html)を参照してください。

>[!IMPORTANT]
>
>[!UICONTROL ターゲットアクティビティ]が、アクティビティのリストを表示する代わりに[!DNL Analytics]リストーで「未指定」と報告する場合は、プロビジョニングされたアカウントの更新が必要です。 カスタマーケアに連絡して、この問題を解決してください。

詳細な情報と例については、[Analytics &amp;ターゲットを開きます。Adobe Experience Leagueが提供する分析](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)のベストプラクティスのチュートリアル。

## Target のレポート {#section_C0D1F17F88374B6690BF904D7B83B42E}

[!DNL Analytics]をレポートソースとして使用すると、[!DNL Target]のレポートには、[!DNL Analytics]から収集されたデータが表示されます。 このレポートは他の[!DNL Target]レポートと少し異なります。

* [!UICONTROL オーディエンス]リストは、[!DNL Analytics]レポートスイートで使用できるオーディエンスを表示します。
* [!UICONTROL 指標]リストは、[!DNL Analytics]を通じて使用できるすべての指標を表示します。

   カスタム指標や計算指標など、[!DNL Analytics]に組み込まれている指標はすべて使用できます。

   このレポートでは、実際には数値の上昇が好ましくない状況であっても、数値の上昇が肯定的な現象として表示されることに注意してください。例えば、バウンス率を低く抑えたい場合であっても、最も高いバウンス率を持つものが勝者として表示されます。このような指標の取り扱いには注意が必要です。ポートに基づいて判断をおこなう場合には、数値が低下した方が好ましいのか、上昇した方が好ましいのかを確認してください。

指標やオーディエンスは、アクティビティ開始後、またはテストが完了した後でも、[!DNL Target]のレポートに適用できます。 測定する内容を事前に正確に知っておく必要はありません。

[!DNL Analytics]のフルレポートをアクティビティレポートページから直接表示するには、をクリックします。

## アクティビティの作成 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

アクティビティを作成する場合は、[!UICONTROL 設定]ページでアクティビティの目標を指定する必要があります。この目標は、レポートのデフォルトの指標となり、指標セレクターで常に先頭に表示されます。通常の Target アクティビティとは異なり、レポート用のセグメントを自由に選択できません。[!DNL Analytics]を使用したテストでは、[!DNL Target]オーディエンスではなく[!DNL Adobe Analytics]セグメントが使用されます。

## ターゲット用のAnalytics(A4T) {#section_33A97A691F3A45D497DAF57A844388F0}に対するオフライン計算の実行

A4T でオフライン計算を実行することはできますが、[!DNL Analytics] でのデータエクスポートを含む手順が必要になります。

詳しくは、[Analytics for Target（A4T）でのオフライン計算の実行](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)を参照してください。
