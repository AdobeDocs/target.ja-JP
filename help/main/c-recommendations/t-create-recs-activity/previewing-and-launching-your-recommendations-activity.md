---
keywords: Recommendations；オファー；プレビュー；ローンチ；ステータス；条件；アルゴリズム
description: Adobeのプレビュー方法 [!DNL Target] Recommendationsアクティビティを使用して、アクティビティを開始する前に結果が使用可能であることを確認します。
title: Recommendationsアクティビティのプレビューと開始方法を教えてください。
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: 6e15b9b10e6a40c8efec06c45442b0f9894e648e
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 16%

---

# Recommendations アクティビティのプレビューと起動

次の [!UICONTROL Recommendations], [!UICONTROL A/B Test]または [!UICONTROL Experience Targeting] (XT) 次を含むアクティビティ： [Recommendationsオファー](/help/main/c-recommendations/recommendations-as-an-offer.md)を使用する場合、アクティビティを開始する前に、レコメンデーションをプレビューして、結果が使用可能であることを確認する必要があります。 [!DNL Target Recommendations] では、レコメンデーションを複数の方法でプレビューできます。

## Recommendationsアルゴリズムのステータスの確認

アクティビティの作成後、 [!DNL Recommendations] は、レコメンデーションを生成するためのアルゴリズムを実行します。 このアルゴリズムの実行には数時間かかる場合があります。

アルゴリズムの実行が [!UICONTROL Activity] 概要図。条件のステータスが表示されます。 次の図に、 [!DNL Recommendations] アクティビティの [!UICONTROL Overview] ページ：

![Recommendationsアクティビティの概要ページ](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

以下の図は、 [!UICONTROL A/B Test] または XT アクティビティの [!UICONTROL Overview] ページ：

![A/B テストの概要ページ](/help/main/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

ステータスの結果には次のものが含まれます（下図を参照）。

* [!UICONTROL Results Ready]：アルゴリズムが返した結果を示します
* [!UICONTROL Results Not Ready]：アルゴリズムの実行が完了していないことを示します。
* [!UICONTROL Feed Failure]：カスタム条件フィードファイルを取得できなかったことを示します。

![[ 結果 ] ダイアログボックス](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## アルゴリズムの実行にはどのくらいの時間がかかりますか？

条件を含むアクティビティを保存した後、 [!DNL Target] 選択したコレクション、条件、デザイン、プロモーションに基づいてレコメンデーションを計算します。 この計算の実行には時間がかかり、時間枠は、選択したレコメンデーションロジック、データ範囲、カタログ内の項目数、顧客が生成した行動データの量、選択した行動データソースに基づいて異なります。

次のように、行動データソースは、処理時間に最も影響します。

### mbox

mbox が行動データソースとして選択される場合、一旦作成されると、条件は即座に実行されます。使用される行動データの量とカタログのサイズに応じて、アルゴリズムの実行には最大で 12 時間かかります。条件の設定を変更すると、通常、アルゴリズムが再実行されます。おこなわれた変更によっては、再実行が完了するまで、以前に計算されたレコメンデーションは使用できない場合や、大きな変更の場合は、再実行が完了するまで、バックアップまたはデフォルトコンテンツのみが使用できます。 アルゴリズムが変更されない場合、選択されたデータ範囲に応じて 12 ～ 48 時間ごとに、[!DNL Target] によって自動的に再実行されます。

### Adobe Analytics

[!DNL Adobe Analytics] を行動データソースとして使用する条件を作成した場合は、選択されているレポートスイートとルックバックウィンドウが他の条件でも使用されているかどうかに応じて、条件が使用可能になる時間が異なります。

* **1 回限りのレポートスイート設定**：指定されたデータ範囲のルックバックウィンドウで最初にレポートスイートが使用されると、[!DNL Target Recommendations] は、選択されたレポートスイートの行動データを [!DNL Analytics] から完全にダウンロードするまで 2 ～ 7 日間かかる可能性があります。この期間は、[!DNL Analytics] システム負荷に依存します。
* **既に利用可能なレポートスイートを使用して新しい条件または編集した条件**：新しい条件の作成時、または既存の条件の編集時に、選択されたレポートスイートが既に [!DNL Target Recommendations]で指定したデータ範囲よりも小さいか等しい場合、データは直ちに使用可能になり、1 回限りのセットアップは不要です。 この場合、または選択されたレポートスイートまたはデータ範囲が変更されずにアルゴリズムの設定が編集されると、12 時間以内にアルゴリズムが実行または再実行されます。
* **進行中のアルゴリズム実行**：毎日の [!DNL Analytics] から [!DNL Target Recommendations] へのデータフロー。例えば、 [!UICONTROL Viewed Affinity] レコメンデーションでは、ユーザーが製品を表示する際に、製品表示トラッキングコールが [!DNL Analytics] リアルタイムに近い The [!DNL Analytics] データが次にプッシュされる： [!DNL Target] 翌日早々に [!DNL Target] は 12 時間以内にアルゴリズムを実行します。

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] では、オフラインアルゴリズムの実行が不要で、結果をすぐに使用できます。 [!UICONTROL Top Viewed] および [!UICONTROL Top Sellers] mbox データに基づくアルゴリズムは、通常、必要な計算が単純なので、非常に迅速に結果を生成します。 これらは、デザインの変更をプレビューしたり、行動データが正しく収集されていることを確認したりする場合に適したオプションです。

## QA リンクを使用したRecommendationsのプレビュー

アルゴリズムの結果の準備が整ったら、 [QA リンク](/help/main/c-activities/c-activity-qa/activity-qa.md) 機能 [!DNL Adobe Target]. QA リンクは [!UICONTROL Activity QA] アクティビティの概要ページの「 」セクションで、以下の操作をおこないます。

![アクティビティ QA リンク](/help/main/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>デフォルトでは、 [!DNL Target] により、QA リンクの必要なオーディエンスに自動的に追加されます。 この設定をオフにし、アクティビティにターゲットルールが設定されている場合、レコメンデーションを含むエクスペリエンスを表示するには、ユーザープロファイルがこれらのターゲットルールを満たしている必要があります。

QA リンクを使用すると、ページ上のレコメンデーションをプレビューできます。

![主な製品](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* Target QA モードは「固定」で、Cookie に保存されます。 QA モードを終了しないと、サイト全体で QA 結果が表示され続けます。 QA モードを終了するには、 [ブックマークレット](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md).
>
>* QA モードの場合、サイトの閲覧はプロファイルの [!UICONTROL Recently Viewed Items] または [!UICONTROL Recently Purchased Items]. この動作は、生産行動データの意図しない汚染を防ぐために設計によって行われます。 次の結果をプレビューするには： [!UICONTROL Recently Viewed Items] または [!UICONTROL User-Based Recommendations] 条件を選択し、まず QA モード以外でサイトを参照し、次に同じセッションを使用して QA モードのリンクを開きます。

## CSV ダウンロードを使用したレコメンデーションのプレビュー

場合によっては、レコメンデーションされる特定の品目を監査する必要があります。 これは、のようなアルゴリズムを使用する場合に特に役立ちます。 [!UICONTROL People Who Viewed This, Viewed That]：ユーザーが現在表示している品目に応じて異なる品目セットがレコメンデーションされ、カタログに数千または数百万の異なる品目が含まれる場合があります。

結果は、 [!UICONTROL Results Ready] ステータスは、アクティビティ内の 1 つ以上のアルゴリズムに対して表示されます。

プレビュー用の結果をダウンロードするには、アクティビティの概要ページの右上隅にあるメニューアイコンをクリックし、 **[!UICONTROL Download data]**.

![データオプションをダウンロード](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

CSV ファイルがダウンロードされます。 それを開いて、レコメンデーションされた品目を確認します。

![推奨品目の CSV ファイル](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

左から右に、レコメンデーションされた品目のリストが表示されます。この場合は、最も頻繁に表示されます。 レコメンデーションは環境別に分けられます。この場合、実稼動環境にのみレコメンデーションが含まれます。

アスタリスク (*) が行の最初の値である場合は、 [バックアップ項目](/help/main/c-recommendations/c-algorithms/backup-recs.md). アルゴリズムの推奨品目（条件）でデザインのすべてのスロットを埋めることができない場合は、バックアップ品目が表示されます。

キー値に基づく他のアルゴリズムタイプの場合： [!UICONTROL People Who Viewed This, Viewed That]の場合、キー値（「この」項目）は最左の列に、レコメンデーション項目（「その」項目）は Recommendation_X 列に左から右にリストされます。

>[!NOTE]
>
>結果のダウンロードは、 [!UICONTROL User-Based Recommendations] アルゴリズム。 結果のダウンロードは、 [!UICONTROL Recently-Viewed Items] レコメンデーションロジック。

## Recommendationsアクティビティのアクティブ化

次から： [!UICONTROL Activity Overview] 」タブで、ステータスの横にあるドロップダウン矢印をクリックし、「 **[!UICONTROL Activate]**.

![「有効化」オプション](/help/main/c-recommendations/t-create-recs-activity/assets/activate.png)

ステータスが [!UICONTROL Activating]:

![有効化中](/help/main/c-recommendations/t-create-recs-activity/assets/activating.png)

数秒から数分後に、ステータスがに切り替わります。 [!UICONTROL Live]:

![ライブ](/help/main/c-recommendations/t-create-recs-activity/assets/live.png)

また、同じドロップダウンリストを使用して、アクティビティのアクティベートを解除したり、アーカイブしたりすることもできます。

## Recommendations設定の変更時の中断の回避

変更中 [!DNL Recommendations] ライブアクティビティのコレクション、条件、プロモーションまたはデザイン設定が原因で、アルゴリズムの結果が無効になり、アルゴリズムのステータスが「 [!UICONTROL Results Not Ready].

ライブアクティビティを中断しないように、ライブアクティビティを変更する際は次の方法を取ることをお勧めします。

1. 元のアクティビティ（アクティビティ 1）と変更する条件を複製して、新しいアクティビティ（アクティビティ 2）を作成します。
1. 重複したアクティビティ（アクティビティ 2）と条件を変更し、アルゴリズムが結果を生成するのを待ちます。
1. 変更された新しいアクティビティ（アクティビティ 2）をプレビューし、結果が必要に応じて表示されることを確認します。
1. 新しいアクティビティをアクティブ化します（アクティビティ 2）。
1. 元のアクティビティを非アクティブ化します（アクティビティ 1）。

同じアクティビティで履歴レポートの結果を保持する必要がある場合は、別のアプローチが可能です。その結果、レコメンデーションの可用性が一時的に中断される可能性があります。

1. 元のアクティビティ（アクティビティ 1）と変更する条件を複製して、新しいアクティビティ（アクティビティ 2）を作成します。
1. 重複したアクティビティ（アクティビティ 2）と条件を変更し、アルゴリズムが結果を生成するのを待ちます。
1. 変更された新しいアクティビティ（アクティビティ 2）をプレビューし、結果が必要に応じて表示されることを確認します。
1. 変更された新しいアクティビティ（アクティビティ 2）を一時停止し、設定/条件を元のアクティビティ（アクティビティ 1）と入れ替えます。
1. 元のアクティビティ（アクティビティ 1）をプレビューし、結果が必要に応じて表示されることを確認します。
1. 元のアクティビティを再アクティブ化します（アクティビティ 1）。
