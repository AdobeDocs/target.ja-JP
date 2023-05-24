---
keywords: analytics for target;A4T；レポートソースとしての analytics;analytics
description: Analytics を使用して [!DNL Target] (A4T)。 A4T は、 [!DNL Target] アクティビティを使用している必要があります。
title: A4T でレポートを使用する方法を教えてください。
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1310'
ht-degree: 45%

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

   増加した数値は、増加が望ましくない場合でも、肯定的な数値としてレポートに表示されます。 例えば、バウンス率を低く抑えたい場合であっても、最も高いバウンス率を持つものが勝者として表示されます。このような指標の取り扱いには注意が必要です。ポートに基づいて判断を行う場合には、数値が低下した方が好ましいのか、上昇した方が好ましいのかを確認してください。

指標またはオーディエンスを [!DNL Target] アクティビティの開始後、またはテストが完了した後でも、 測定する内容を事前に正確に知っておく必要はありません。

クリックして完全な [!DNL Analytics] レポートを直接アクティビティレポートページから開きます。

## アクティビティの作成 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

アクティビティを作成する場合は、[!UICONTROL 設定]ページでアクティビティの目標を指定する必要があります。この目標は、レポートのデフォルトの指標となり、指標セレクターで常に先頭に表示されます。通常の Target アクティビティとは異なり、レポート用のセグメントを自由に選択できません。を使用したテスト [!DNL Analytics] uses [!DNL Adobe Analytics] セグメントではなく [!DNL Target] オーディエンス。

## Analytics for Adobe Target(A4T) でのオフライン計算の実行 {#section_B34BD016C8274C97AC9564F426B9607E}

A4T でオフライン計算を実行し、信頼区間と信頼区間を [!DNL Target] [Complete Confidence Calculator](/help/main/assets/complete_confidence_calculator.xlsx) Excel ファイルに関する情報は含まれていますが、 [!DNL Analytics].

A4T の場合、 [ウェルチ t 検定](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} バイナリ指標ではなく、連続変数の計算を行います。 Analytics では、訪問者は常に追跡され、実行されたすべてのアクションがカウントされます。したがって、訪問者が複数回買い物をした場合や成功指標を複数回訪問した場合、これらの追加のヒット数もカウントされます。この場合、指標は連続型変数になります。ウェルチの t 検定計算を実行するには、t 統計の分母に使用される平方偏差を計算するために、「平方和」が必要です。 [A/Bn テストの統計指標](/help/main/c-reports/statistical-methodology/statistical-calculations.md) では、使用する数式の詳細について説明します。 平方和は、 [!DNL Analytics]. 平方和のデータを取得するには、サンプルの期間を対象に、最適化する指標で訪問者レベルのエクスポートを実行する必要があります。

例えば、訪問者ごとのページビュー数に最適化する場合、指定した期間（おそらく数日）の訪問者ごとの合計ページビュー数のサンプルを書き出します（必要なデータポイントは数千個です）。 そのうえでそれぞれの値を 2 乗し、その総和を算出します（ここでは演算の順番が非常に重要です）。この「平方和」の値は、Complete Confidence Calculator で使用されます。これらの値には、このスプレッドシートの「売上高」セクションを使用します。

**[!DNL Analytics] のデータエクスポート機能を使用してこれをおこなう手順は次のとおりです。**

1. [!DNL Adobe Analytics]にログインします。
1. **[!UICONTROL ツール]**／**[!UICONTROL Data Warehouse]** をクリックします。
1. 「**[!UICONTROL Data Warehouse リクエスト]**」タブで、各フィールドに記入します。

   各フィールドについて詳しくは、[Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html) の「Data Warehouse の説明」を参照してください。

   | フィールド | 手順 |
   |--- |--- |
   | リクエスト名 | リクエストの名前を指定します。 |
   | レポート日 | 期間と精度を指定します。<br>最初のリクエストでは 1 時間以内または 1 日以内のデータを選択することをお勧めします。Data Warehouse のファイルは、リクエストする期間が長いほど処理に時間がかかります。そのため、最初は短い期間のデータをリクエストして、ファイルが想定どおりの結果を返すかどうかを確認することをお勧めします。その後リクエストマネージャーに移動してリクエストを複製し、2 回目はより長い期間のデータをリクエストします。また、精度を「なし」以外に切り替えると、ファイルサイズが大幅に増加します。<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | 選択可能なセグメント | 必要に応じてセグメントを適用します。 |
   | 分類 | 目的のディメンションを選択します。「標準」はあらかじめ用意されている（OOTB）ディメンションで、「カスタム」には eVar と prop が含まれます。訪問者 ID レベルの情報が必要な場合は、「訪問者 ID」ではなく、「Experience CloudID」を使用することをお勧めします。<ul><li>訪問者 ID は、Analytics で使用される最終的な ID で、AID（既存の顧客）か MID（新規の顧客、または Experience Cloud 訪問者 ID サービスが開始されてから Cookie が消去された顧客）になります。</li><li>Experience Cloud 訪問者 ID が設定されるのは、新規の顧客、または Experience Cloud 訪問者 ID サービスが開始されてから Cookie が消去された顧客のみです。</li></ul> |
   | 指標 | 目的の指標を選択します。「標準」は OOTB で、「カスタム」にはカスタムイベントが含まれます。 |
   | レポートプレビュー | レポートのスケジュールを設定する前に設定を確認します。<br>![Data Warehouse2](/help/main/c-reports/assets/datawarehouse2.png) |
   | 配信の予定 | ファイルを送信する相手のメールアドレスを入力し、ファイルに名前を付けてから、「[!UICONTROL すぐに送信]」を選択します。<br>注意: このファイルは、[!UICONTROL 詳細配信オプション]<br>![の下のFTP経由で配信できます。配信の予定](/help/main/c-reports/assets/datawarehouse3.png) |

1. 「**[!UICONTROL このレポートをリクエスト]**」をクリックします。

   ファイルの配信には、リクエストしたデータの量に応じて最大で 72 時間かかります。リクエストの進捗状況は、[!UICONTROL ツール]／[!UICONTROL Data Warehouse]／[!UICONTROL リクエストマネージャー]をクリックすることでいつでもチェックできます。

   過去にリクエストしたデータを再リクエストする場合は、 [!UICONTROL リクエストマネージャー] 必要に応じて。

[!DNL Data Warehouse] について詳しくは、[!DNL Analytics] のヘルプドキュメントの以下のリンクを参照してください。

* [Data Warehouse リクエストの作成](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [Data Warehouseのベストプラクティス](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)
