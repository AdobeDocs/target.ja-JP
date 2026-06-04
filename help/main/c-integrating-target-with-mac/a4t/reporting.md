---
keywords: analytics for target;a4t；レポートソースとしてのanalytics;analytics
description: Analytics for [!DNL Target]  （A4T）の使用方法を説明します。 A4Tは、Analytics指標とオーディエンスセグメントを使用する [!DNL Target]  アクティビティのAnalytics レポートへのアクセスを提供します。
title: A4Tでレポートを使用するにはどうすればよいですか？
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
TQID: https://experienceleague.adobe.com/oYF9-9IHLmdxfWV-k3FLYd26rkXgOE9CddNTldF9TSY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1316
ht-degree: 41%

---

# A4T レポート

[!DNL Adobe Analytics]を[!DNL Adobe Target] （A4T）のレポートソースとして使用すると、[!DNL Target] アクティビティの[!DNL Analytics]件のレポートにアクセスできます。

[!DNL Analytics]と[!DNL Target]の両方でアクティビティのレポートを表示できます。

[!DNL Target]の[!DNL Analytics]を使用してベストプラクティスを報告するには、[このAdobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)にアクセスしてください。

## 概要 {#section_035A62D65608423285D8A5A54731E2C5}

[!DNL Analytics]と[!DNL Target]の両方のレポートは、サイトへの訪問者ではなく、参加者（テストに参加した人）を測定します。

訪問者がページ上のアクティビティコンテンツを見るたびに、[!DNL Target]は、訪問者が見たアクティビティとエクスペリエンスを含め、[!DNL Analytics]に直接サーバー間呼び出しを行います。 [!DNL Target]は、変換が行われるたびに[!DNL Analytics]も呼び出します。 [!DNL Analytics]は、コンバージョンを「アクティビティのコンバージョン」という名前の特定の新しい[!DNL Analytics] イベントとして追加します。このイベントは、[!DNL Analytics]によって収集された他のデータと共に追跡されます。

[!UICONTROL Select]操作を使用し、*参加者*&#x200B;に並べ替えると、選択した期間に参加者を受け取ったエクスペリエンスのみがレポートに表示されます。

>[!NOTE]
>
>[!DNL Target]によるレポートの待ち時間は4分です。 A4Tによるアクティビティの場合、[!DNL Target]と[!DNL Analytics]の両方のレポートで、アクティビティが最初に保存されてからエクスペリエンスで分類されるまで、最大24時間かかることがあります。 最初の 24 時間に収集されたデータも正確であり、適切なエクスペリエンスに割り当てられます。

## Analytics のレポート {#analytics}

[!DNL Analytics]では、A4T統合が有効になった後に、いくつかのディメンションと指標が使用できるようになります。

### ディメンション

* [!UICONTROL Analytics for Target] – 統合を通じて渡される親ID。 このディメンションの形式は`Activity ID:Experience ID:3rd ID`です。 以下のディメンションは、このディメンションの分類です。
* [!UICONTROL &#x200B; ターゲットアクティビティ &#x200B;]
* [!UICONTROL &#x200B; ターゲットエクスペリエンス &#x200B;]
* [!UICONTROL &#x200B; ターゲットアクティビティ &#x200B;] > [!UICONTROL &#x200B; エクスペリエンス &#x200B;]
* [!UICONTROL 3rd ID] – 無視できます

### 指標

* [!UICONTROL &#x200B; アクティビティのインプレッション &#x200B;] - [!DNL Target] レポートの[!UICONTROL 参加者]の数値と一致します。
* [!UICONTROL &#x200B; アクティビティ コンバージョン &#x200B;] - [!DNL Target] レポートの[!UICONTROL &#x200B; カスタム コンバージョン &#x200B;]番号と一致します。

[!DNL Analysis Workspace]では、[!UICONTROL Analytics for Target] パネルを使用して、上昇率と信頼性を持って[!DNL Target]のアクティビティとエクスペリエンスを分析します。 詳しくは、*分析ツールガイド*&#x200B;の「[Analytics for Target （A4T） Panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=ja)」を参照してください。

>[!IMPORTANT]
>
>[!DNL Analytics]の[!UICONTROL &#x200B; ターゲットアクティビティ &#x200B;] レポートに、アクティビティを一覧表示する代わりに「未指定」が一覧表示されている場合、プロビジョニングされたアカウントに更新が必要です。 カスタマーケアに連絡して、この問題を解決してください。

詳細な情報と例については、Adobe Experience Leagueが提供する[AnalyticsとTarget：分析のベストプラクティス &#x200B;](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)のチュートリアルを開いてください。

## [!DNL Target]のレポート {#section_C0D1F17F88374B6690BF904D7B83B42E}

[!DNL Analytics]がレポートソースとして使用されている場合、[!DNL Target]のレポートには[!DNL Analytics]から収集されたデータが表示されます。 このレポートは、他の[!DNL Target]件のレポートとは多少異なります。

* [!UICONTROL &#x200B; オーディエンス &#x200B;]のリストには、[!DNL Analytics] レポートスイートで使用できるオーディエンスが表示されます。
* [!UICONTROL 指標] リストには、[!DNL Analytics]を通じて使用可能なすべての指標が表示されます。

  [!DNL Analytics]に組み込まれているカスタム指標または計算指標を含め、すべての指標を利用できます。

  増加した数値は、増加が望ましくない場合でも、レポートにプラスとして表示されます。 例えば、バウンス率を低く抑えたい場合であっても、最も高いバウンス率を持つものが勝者として表示されます。 このような指標の取り扱いには注意が必要です。ポートに基づいて判断を行う場合には、数値が低下した方が好ましいのか、上昇した方が好ましいのかを確認してください。

アクティビティが開始された後、またはテストが完了した後でも、[!DNL Target]に指標またはオーディエンスをレポートに適用できます。 測定する内容を事前に正確に知っておく必要はありません。

クリックすると、アクティビティレポートページから直接[!DNL Analytics] レポート全体が表示されます。

## アクティビティの作成 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

アクティビティを作成する場合は、[!UICONTROL 設定]ページでアクティビティの目標を指定する必要があります。 この目標は、レポートのデフォルトの指標となり、指標セレクターで常に先頭に表示されます。 通常の Target アクティビティとは異なり、レポート用のセグメントを自由に選択できません。 [!DNL Analytics]を使用したテストでは、[!DNL Target]人のオーディエンスではなく[!DNL Adobe Analytics]人のセグメントを使用します。

## Analytics for Adobe Target（A4T）のオフライン計算の実行 {#section_B34BD016C8274C97AC9564F426B9607E}

A4Tの信頼区間と信頼区間のオフライン計算は、[!DNL Target] [信頼計算ツール &#x200B;](/help/main/assets/complete_confidence_calculator.xlsx) Excel ファイルを使用して実行できますが、[!DNL Analytics]でのデータの書き出しには手順が必要です。

A4Tの場合、（バイナリ指標ではなく）連続変数に[Welchのt-test](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank}計算を使用します。 Analytics では、訪問者は常に追跡され、実行されたすべてのアクションがカウントされます。 したがって、訪問者が複数回買い物をした場合や成功指標を複数回訪問した場合、これらの追加のヒット数もカウントされます。 この場合、指標は連続型変数になります。 ウェルチのt検定の計算を行うには、分散を計算するために「二乗和」が必要であり、これはt統計量の分母で使用されます。 [A/Bn テストの統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)では、使用される数式の詳細が説明されます。 正方形の合計は[!DNL Analytics]から取得できます。 平方和のデータを取得するには、サンプルの期間を対象に、最適化する指標で訪問者レベルのエクスポートを実行する必要があります。

例えば、訪問者一人あたりのページビュー数を最適化する場合、指定された時間枠、数日間（数千のデータポイントが必要な場合のみ）に、訪問者一人あたりのページビュー数のサンプルを書き出します。 そのうえでそれぞれの値を 2 乗し、その総和を算出します（ここでは演算の順番が非常に重要です）。 この「平方和」の値は、Complete Confidence Calculator で使用されます。 これらの値には、このスプレッドシートの「売上高」セクションを使用します。

**[!DNL Analytics] のデータエクスポート機能を使用してこれをおこなう手順は次のとおりです。**

1. [!DNL Adobe Analytics]にログインします。
1. **[!UICONTROL ツール]**／**[!UICONTROL Data Warehouse]** をクリックします。
1. 「**[!UICONTROL Data Warehouse リクエスト]**」タブで、各フィールドに記入します。

   各フィールドについて詳しくは、[Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=ja) の「Data Warehouse の説明」を参照してください。

   | フィールド | 手順 |
   |--- |--- |
   | リクエスト名 | リクエストの名前を指定します。 |
   | レポート日 | 期間と精度を指定します。<br>最初のリクエストでは 1 時間以内または 1 日以内のデータを選択することをお勧めします。  Data Warehouse のファイルは、リクエストする期間が長いほど処理に時間がかかります。そのため、最初は短い期間のデータをリクエストして、ファイルが想定どおりの結果を返すかどうかを確認することをお勧めします。 その後リクエストマネージャーに移動してリクエストを複製し、2 回目はより長い期間のデータをリクエストします。 また、粒度を「なし」以外に切り替えると、ファイルサイズが大幅に増加します。<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | 選択可能なセグメント | 必要に応じてセグメントを適用します。 |
   | 分類 | 目的のディメンションを選択します。標準は標準（OOTB）ですが、カスタムにはeVarとpropが含まれます。 「Experience Cloud訪問者ID」ではなく、訪問者ID レベルの情報が必要な場合は、「訪問者ID」を使用することをお勧めします。<ul><li>訪問者 ID は、Analytics で使用される最終的な ID で、 AID（既存の顧客）か MID（新規の顧客、または Experience Cloud 訪問者 ID サービスが開始されてから Cookie が消去された顧客）になります。</li><li>Experience Cloud 訪問者 ID が設定されるのは、新規の顧客、または Experience Cloud 訪問者 ID サービスが開始されてから Cookie が消去された顧客のみです。</li></ul> |
   | 指標 | 目的の指標を選択します。 「標準」は OOTB で、「カスタム」にはカスタムイベントが含まれます。 |
   | レポートプレビュー | レポートのスケジュールを設定する前に設定を確認します。<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | 配信の予定 | ファイルを配信する電子メールアドレスを入力し、ファイルに名前を付けて、[!UICONTROL すぐに送信]を選択します。<br>注意：ファイルは、[!UICONTROL 詳細配信オプション &#x200B;]<br>![配信スケジュール &#x200B;](/help/main/c-reports/assets/datawarehouse3.png)の下でFTP経由で配信できます。 |

1. 「**[!UICONTROL このレポートのリクエスト]**」をクリックします。

   ファイルの配信には、リクエストしたデータの量に応じて最大で 72 時間かかります。 リクエストの進捗状況は、[!UICONTROL ツール]／[!UICONTROL Data Warehouse]／[!UICONTROL リクエストマネージャー]をクリックすることでいつでもチェックできます。

   過去にリクエストしたデータを再リクエストする場合は、必要に応じて[!UICONTROL &#x200B; リクエストマネージャー]から古いリクエストを複製できます。

[!DNL Data Warehouse] について詳しくは、[!DNL Analytics] のヘルプドキュメントの以下のリンクを参照してください。

* [Data Warehouse リクエストを作成](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html?lang=ja)
* [Data Warehouseのベストプラクティス](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html?lang=ja)
