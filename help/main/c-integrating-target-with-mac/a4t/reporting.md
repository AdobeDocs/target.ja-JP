---
keywords: analytics for target;A4T；レポートソースとしての analytics;analytics
description: Analytics を使用して [!DNL Target] (A4T)。 A4T は、 [!DNL Target] アクティビティを使用している必要があります。
title: A4T でレポートを使用する方法を教えてください。
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 29%

---

# A4T レポート

使用 [!DNL Adobe Analytics] レポートソースとして [!DNL Adobe Target] (A4T) を使用すると、 [!DNL Analytics] レポート [!DNL Target] アクティビティ。

アクティビティのレポートは、 [!DNL Analytics] および [!DNL Target].

レポートのベストプラクティスで [!DNL Analytics] 対象 [!DNL Target], [このAdobe Spark Pageを訪問](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## 概要 {#section_035A62D65608423285D8A5A54731E2C5}

両方 [!DNL Analytics] および [!DNL Target] レポートは、サイトへの訪問者ではなく、参加者（テストに参加した人）を測定します。

訪問者がページ上でアクティビティのコンテンツを見るたびに、 [!DNL Target] は、 [!DNL Analytics]（訪問者が閲覧したアクティビティやエクスペリエンスを含む） [!DNL Target] 呼び出し [!DNL Analytics] 変換がおこなわれたときに必ず。 [!DNL Analytics] は、特定の新しい [!DNL Analytics] イベント名「アクティビティコンバージョン」。 [!DNL Analytics].

次の場合に [!UICONTROL 選択] 操作が使用され、 *参加者*&#x200B;に設定されている場合、選択した期間に参加者を受け取ったエクスペリエンスのみがレポートに表示されます。

>[!NOTE]
>
>を活用したレポート [!DNL Target] 待ち時間は 4 分です。 A4T を活用したアクティビティの場合、 [!DNL Target] および [!DNL Analytics] レポートの場合は、アクティビティが最初に保存されてから、エクスペリエンス別にレポートデータを分類できるようになるまでに、最大 24 時間かかる場合があります。 最初の 24 時間に収集されたデータも正確であり、適切なエクスペリエンスに割り当てられます。

## Analytics のレポート {#analytics}

In [!DNL Analytics]に値を指定する場合、A4T 統合を有効にした後で、いくつかのディメンションと指標を使用できるようになります。

### ディメンション

* [!UICONTROL Analytics for Target]  — 統合経由で渡される親 ID。 このディメンションの形式は、 `Activity ID:Experience ID:3rd ID`. 以下のディメンションは、このディメンションの分類です。
* [!UICONTROL ターゲットアクティビティ]
* [!UICONTROL ターゲットエクスペリエンス]
* [!UICONTROL Target アクティビティ] > [!UICONTROL エクスペリエンス]
* [!UICONTROL 3 番目の ID]  — 無視可能

### 指標

* [!UICONTROL アクティビティのインプレッション] - [!UICONTROL 参加者] 数 [!DNL Target] レポート。
* [!UICONTROL アクティビティコンバージョン] - [!UICONTROL カスタムコンバージョン] 数 [!DNL Target] レポート。

In [!DNL Analysis Workspace]、 [!UICONTROL Analytics for Target] パネルを使用して [!DNL Target] 上昇率と信頼性を備えたアクティビティとエクスペリエンス。 詳しくは、 [Analytics for Target(A4T) パネル](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=ja) 内 *Analytics ツールガイド*.

>[!IMPORTANT]
>
>次に、 [!UICONTROL Target アクティビティ] レポート [!DNL Analytics] では、アクティビティのリストの代わりに「未指定」がリストされます。プロビジョニング済みのアカウントの更新が必要です。 カスタマーケアに連絡して、この問題を解決してください。

詳細と例については、 [Analytics &amp; Target:分析のベストプラクティス](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) Adobe Experience Leagueが提供するチュートリアル。

## のレポート [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

条件 [!DNL Analytics] はレポートソースとして使用され、レポートは [!DNL Target] 収集したデータを示す [!DNL Analytics]. この報告は他の報告とは少し異なる [!DNL Target] レポート：

* この [!UICONTROL オーディエンス] リストには、 [!DNL Analytics] レポートスイートを使用します。
* この [!UICONTROL 指標] リストには、使用可能なすべての指標が表示されます [!DNL Analytics].

   組み込みのカスタム指標や計算指標を含め、すべての指標を使用できます [!DNL Analytics].

   増加した数値は、増加が望ましくない場合でも、肯定的な数値としてレポートに表示されます。 例えば、バウンス率を低く抑えたい場合であっても、最も高いバウンス率を持つものが勝者として表示されます。このような指標の取り扱いには注意が必要です。ポートに基づいて判断をおこなう場合には、数値が低下した方が好ましいのか、上昇した方が好ましいのかを確認してください。

指標またはオーディエンスを [!DNL Target] アクティビティの開始後、またはテストが完了した後でも、 測定する内容を事前に正確に知っておく必要はありません。

クリックして完全な [!DNL Analytics] レポートを直接アクティビティレポートページから開きます。

## アクティビティの作成 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

アクティビティを作成する場合は、[!UICONTROL 設定]ページでアクティビティの目標を指定する必要があります。この目標は、レポートのデフォルトの指標となり、指標セレクターで常に先頭に表示されます。通常の Target アクティビティとは異なり、レポート用のセグメントを自由に選択できません。を使用したテスト [!DNL Analytics] uses [!DNL Adobe Analytics] セグメントではなく [!DNL Target] オーディエンス。

## Analytics for Adobe Target(A4T) でのオフライン計算の実行 {#section_33A97A691F3A45D497DAF57A844388F0}

A4T でオフライン計算を実行することはできますが、[!DNL Analytics] でのデータエクスポートを含む手順が必要になります。

詳しくは、[Analytics for Target（A4T）でのオフライン計算の実行](/help/main/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)を参照してください。
