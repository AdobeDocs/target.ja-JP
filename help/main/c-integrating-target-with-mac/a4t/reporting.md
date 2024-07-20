---
keywords: analytics for target;a4t；レポートソースとしての analytics;analytics
description: Analytics for  [!DNL Target]  （A4T）の使用方法について説明します。 A4T では、Analytics 指標およびオーディエンスセグメントを使用するアクティビティの  [!DNL Target] Analytics レポートにアクセスできます。
title: A4T でのレポートの使用方法
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 39%

---

# A4T レポート

[!DNL Adobe Analytics] を [!DNL Adobe Target] のレポートソース（A4T）として使用すると、[!DNL Target] アクティビティの [!DNL Analytics] レポートにアクセスできます。

アクティビティのレポートは、[!DNL Analytics] と [!DNL Target] の両方で表示できます。

[!DNL Analytics] for [!DNL Target] を使用したレポートのベストプラクティスについては、[ このAdobe Spark Pageを参照 ](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) してください。

## 概要 {#section_035A62D65608423285D8A5A54731E2C5}

[!DNL Analytics] レポートと [!DNL Target] レポートはどちらも、サイトへの訪問者ではなく、エントリ（テストに参加したユーザー）を測定します。

訪問者がページ上でアクティビティのコンテンツを表示す [!DNL Target] たびに、訪問者が表示したアクティビティやエクスペリエンスを含め、[!DNL Analytics] へのサーバー間直接呼び出しを行います。 変換 [!DNL Target] 行われるたびに [!DNL Analytics] も呼び出します。 [!DNL Analytics] では、コンバージョンを「アクティビティコンバージョン」という名前の特定の新しい [!DNL Analytics] イベントとして追加します。このイベントは、[!DNL Analytics] で収集された他のデータと共に追跡されます。

[!UICONTROL Select] 操作を使用し、*エントリ* を並べ替えると、選択した期間にエントリを受け取ったエクスペリエンスのみがレポートに表示されます。

>[!NOTE]
>
>[!DNL Target] を使用したレポートの待ち時間は 4 分です。 A4T を利用したアクティビティの場合、[!DNL Target] レポートと [!DNL Analytics] レポートの両方で、アクティビティが最初に保存されてから最大 24 時間かかり、レポートデータをエクスペリエンス別に分類できるようになることがあります。 最初の 24 時間に収集されたデータも正確であり、適切なエクスペリエンスに割り当てられます。

## Analytics のレポート {#analytics}

ま [!DNL Analytics]、A4T 統合が有効になった後で、いくつかのディメンションと指標が使用可能になります。

### ディメンション

* [!UICONTROL Analytics for Target] – 統合を通じて渡される親 ID。 このディメンションの形式は `Activity ID:Experience ID:3rd ID` です。 以下のディメンションは、このディメンションの分類です。
* [!UICONTROL Target Activities]
* [!UICONTROL Target Experiences]
* [!UICONTROL Target Activity]／[!UICONTROL Experience]
* [!UICONTROL 3rd ID] – 無視できます。

### 指標

* [!UICONTROL Activity Impressions] - [!DNL Target] レポートの [!UICONTROL Entrants] 番号に一致します。
* [!UICONTROL Activity Conversions] - [!DNL Target] レポートの [!UICONTROL Custom Conversions] 番号に一致します。

ま [!DNL Analysis Workspace]、[!UICONTROL Analytics for Target] パネルを使用して、上昇率と信頼性で [!DNL Target] アクティビティとエクスペリエンスを分析します。 詳しくは、『 [Analytics ツールガイド *の ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=ja)Analytics for Target （A4T）パネル* を参照してください。

>[!IMPORTANT]
>
>[!DNL Analytics] の [!UICONTROL Target Activities] レポートにアクティビティが一覧表示されるのではなく「未指定」と表示される場合は、プロビジョニングされたアカウントを更新する必要があります。 カスタマーケアに連絡して、この問題を解決してください。

詳細と例については、Adobe Experience Leagueが提供する [Analytics &amp; Target：分析のベストプラクティス ](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) チュートリアルをご覧ください。

## [!DNL Target] のレポート {#section_C0D1F17F88374B6690BF904D7B83B42E}

[!DNL Analytics] がレポートソースとして使用されている場合、[!DNL Target] のレポートには、[!DNL Analytics] から収集されたデータが表示されます。 このレポートは、他の [!DNL Target] レポートとは多少異なります。

* [!UICONTROL Audiences] リストには、[!DNL Analytics] レポートスイートで使用可能なオーディエンスが表示されます。
* [!UICONTROL Metric] のリストには、[!DNL Analytics] で使用可能なすべての指標が表示されます。

  カスタム指標や [!DNL Analytics] に組み込まれている計算指標を含む、すべての指標を使用できます。

  増加する数値は、望ましくない増加の場合でも、肯定的なものとしてレポートに表示されます。 例えば、バウンス率を低く抑えたい場合であっても、最も高いバウンス率を持つものが勝者として表示されます。このような指標の取り扱いには注意が必要です。ポートに基づいて判断を行う場合には、数値が低下した方が好ましいのか、上昇した方が好ましいのかを確認してください。

アクティビティの開始後、またはテストが完了した後でも、[!DNL Target] のレポートに指標やオーディエンスを適用できます。 測定する内容を事前に正確に知っておく必要はありません。

クリックすると、完全な [!DNL Analytics] レポートがアクティビティレポートページから直接表示されます。

## アクティビティの作成 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

アクティビティの作成時に、[!UICONTROL Settings] ページ上のアクティビティの目標を指定する必要があります。 この目標は、レポートのデフォルトの指標となり、指標セレクターで常に先頭に表示されます。通常の Target アクティビティとは異なり、レポート用のセグメントを自由に選択できません。[!DNL Analytics] を使用したテストでは、オーディエンスの [!DNL Target] ではなく [!DNL Adobe Analytics] セグメントを使用します。

## Analytics for Adobe Target （A4T）のオフライン計算の実行 {#section_B34BD016C8274C97AC9564F426B9607E}

[!DNL Target] の [Complete Confidence Calculator](/help/main/assets/complete_confidence_calculator.xlsx) Excel ファイルを使用して、A4T の信頼性と信頼区間に対してオフライン計算を実行できますが、[!DNL Analytics] でのデータの書き出しに関する手順が必要です。

A4T では、（バイナリ指標ではなく）連続変数に対して [Welch の t 検定 ](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} 計算を使用します。 Analytics では、訪問者は常に追跡され、実行されたすべてのアクションがカウントされます。したがって、訪問者が複数回買い物をした場合や成功指標を複数回訪問した場合、これらの追加のヒット数もカウントされます。この場合、指標は連続型変数になります。ウェルチの t 検定の計算を行うには、分散を計算するために「平方和」が必要であり、t 統計の分母で使用されます。 [A/Bn テストでの統計計算 ](/help/main/c-reports/statistical-methodology/statistical-calculations.md) では、使用される数式の詳細について説明しています。 平方和は、[!DNL Analytics] から取得することができます。 平方和のデータを取得するには、サンプルの期間を対象に、最適化する指標で訪問者レベルのエクスポートを実行する必要があります。

例えば、訪問者あたりのページビュー数を最適化する場合は、特定の時間枠、例えば数日（2、3 日で必要なデータポイントは数千）にわたって、訪問者ごとにページビューの合計数のサンプルを書き出します。 そのうえでそれぞれの値を 2 乗し、その総和を算出します（ここでは演算の順番が非常に重要です）。この「平方和」の値は、Complete Confidence Calculator で使用されます。これらの値には、このスプレッドシートの「売上高」セクションを使用します。

**[!DNL Analytics] のデータエクスポート機能を使用してこれをおこなう手順は次のとおりです。**

1. [!DNL Adobe Analytics]にログインします。
1. **[!UICONTROL Tools]**／**[!UICONTROL Data Warehouse]**&#x200B;をクリックします。
1. 「**[!UICONTROL Data Warehouse Request]**」タブで、フィールドに入力します。

   各フィールドについて詳しくは、[Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html) の「Data Warehouse の説明」を参照してください。

   | フィールド | 手順 |
   |--- |--- |
   | リクエスト名 | リクエストの名前を指定します。 |
   | レポート日 | 期間と精度を指定します。<br>最初のリクエストでは 1 時間以内または 1 日以内のデータを選択することをお勧めします。Data Warehouse のファイルは、リクエストする期間が長いほど処理に時間がかかります。そのため、最初は短い期間のデータをリクエストして、ファイルが想定どおりの結果を返すかどうかを確認することをお勧めします。その後リクエストマネージャーに移動してリクエストを複製し、2 回目はより長い期間のデータをリクエストします。また、精度を「なし」以外に切り替えると、ファイルサイズが大幅に増加します。<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | 選択可能なセグメント | 必要に応じてセグメントを適用します。 |
   | 分類 | 目的のディメンションを選択します。「標準」は標準（OOTB）であり、「カスタム」には eVar および prop が含まれています。 「Experience Cloud訪問者 ID」ではなく、訪問者 ID レベルの情報が必要な場合は、「訪問者 ID」を使用することをお勧めします。<ul><li>訪問者 ID は、Analytics で使用される最終的な ID で、AID（既存の顧客）か MID（新規の顧客、または Experience Cloud 訪問者 ID サービスが開始されてから Cookie が消去された顧客）になります。</li><li>Experience Cloud 訪問者 ID が設定されるのは、新規の顧客、または Experience Cloud 訪問者 ID サービスが開始されてから Cookie が消去された顧客のみです。</li></ul> |
   | 指標 | 目的の指標を選択します。「標準」は OOTB で、「カスタム」にはカスタムイベントが含まれます。 |
   | レポートプレビュー | レポートのスケジュールを設定する前に設定を確認します。<br>![Data Warehouse2](/help/main/c-reports/assets/datawarehouse2.png) |
   | 配信の予定 | ファイルの配信先のメールアドレスを入力し、ファイルに名前を付けて、「[!UICONTROL Send Immediately]」を選択します。<br> メモ：ファイルは、FTP の [!UICONTROL Advanced Delivery Options]<br>![ スケジュール配信 ](/help/main/c-reports/assets/datawarehouse3.png) で配信できます。 |

1. **[!UICONTROL Request this Report]** をクリックします。

   ファイルの配信には、リクエストしたデータの量に応じて最大で 72 時間かかります。[!UICONTROL Tools]/[!UICONTROL Data Warehouse]/[!UICONTROL Request Manager] をクリックすると、いつでもリクエストの進行状況を確認できます。

   過去にリクエストしたデータを再度要求する場合は、必要に応じて [!UICONTROL Request Manager] から古いリクエストを複製できます。

[!DNL Data Warehouse] について詳しくは、[!DNL Analytics] のヘルプドキュメントの以下のリンクを参照してください。

* [Data Warehouseリクエストの作成 ](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [Data Warehouseのベストプラクティス ](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)
