---
keywords: Recommendations;offer;preview;launch
description: 'Adobe TargetRecommendationsのオファーを含むRecommendations、A/Bテストまたはエクスペリエンスターゲット設定(XT)アクティビティを作成したら、アクティビティを起動する前に、そのをプレビューして、確実な結果が得られるようにします。 ターゲットRecommendationsは、レコメンデーションをプレビューする複数の方法をオファーしています。 '
title: 'Adobe TargetRecommendationsのオファーを含むRecommendations、A/Bテストまたはエクスペリエンスターゲット設定(XT)アクティビティを作成したら、アクティビティを起動する前に、そのをプレビューして、確実な結果が得られるようにします。 ターゲットRecommendationsは、レコメンデーションをプレビューする複数の方法をオファーしています。 '
feature: null
subtopic: Recommendations
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 19%

---


# Recommendationsアクティビティのプレビューと起動

[!UICONTROL Recommendationsオファーを含む]Recommendations [!UICONTROL 、]A/B Test [!UICONTROL 、または] エクスペリエンスターゲット設定 [](/help/c-recommendations/recommendations-as-an-offer.md)(XT)アクティビティを作成したら、アクティビティを起動する前に結果が確実に得られるようにレコメンデーションをプレビューします。 [!DNL Target Recommendations] オファーは、レコメンデーションをプレビューする複数の方法を使用します。

## Recommendationsアルゴリズムの状態の確認

アクティビティの作成後、アルゴリズムを [!DNL Recommendations] 実行してレコメンデーションを生成します。 このアルゴリズムの実行には数時間かかる場合があります。

条件のステータスが表示される [!UICONTROL アクティビティ] 概要図で、アルゴリズムの実行が終了したかどうかを確認できます。 The following illustration shows the status in the activity diagram on a [!DNL Recommendations] activity&#39;s [!UICONTROL Overview] page:

![Recommendationsアクティビティ概要ページ](/help/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

次の図は、 [!UICONTROL A/B Test] （A/Bテスト）またはXTアクティビティの [!UICONTROL 概要] ページのステータスを示しています。

![A/Bテストの概要ページ](/help/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

ステータスの結果には、次のように表示されます。

* [!UICONTROL Results Ready]:アルゴリズムが結果を返したことを示します
* [!UICONTROL Results Not Ready]:アルゴリズムの実行が完了していないことを示します。
* [!UICONTROL フィードエラー]:カスタム条件のフィードファイルを取得できなかったことを示します。

![結果ダイアログボックス](/help/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## アルゴリズムの実行に要する時間はどのくらいか

条件を含むアクティビティを保存すると、選択したコレクション、条件、デザインおよびプロモーションに基づいてレコメンデーションが [!DNL Target] 計算されます。 この計算の実行には、しばらく時間がかかり、その期間は、選択したレコメンデーションロジック、データ範囲、カタログの項目数、お客様によって生成された行動データの量および選択された行動データソースによって異なります。

次のように、行動データソースは、処理時間に最も影響します。

### mbox

mbox が行動データソースとして選択される場合、一旦作成されると、条件は即座に実行されます。使用される行動データの量とカタログのサイズに応じて、アルゴリズムの実行には最大で 12 時間かかります。条件の設定を変更すると、通常、アルゴリズムが再実行されます。変更によっては、前に計算されたレコメンデーションは、再実行が完了するか、大きな変更を行う場合は、再実行が完了するまでバックアップまたはデフォルトコンテンツのみが使用可能になる場合があります。 アルゴリズムが変更されない場合、選択されたデータ範囲に応じて 12 ～ 48 時間ごとに、[!DNL Target] によって自動的に再実行されます。

### Adobe Analytics

[!DNL Adobe Analytics] を行動データソースとして使用する条件を作成した場合は、選択されているレポートスイートとルックバックウィンドウが他の条件でも使用されているかどうかに応じて、条件が使用可能になる時間が異なります。

* **1 回限りのレポートスイート設定**：指定されたデータ範囲のルックバックウィンドウで最初にレポートスイートが使用されると、[!DNL Target Recommendations] は、選択されたレポートスイートの行動データを [!DNL Analytics] から完全にダウンロードするまで 2 ～ 7 日間かかる可能性があります。この期間は、[!DNL Analytics] システム負荷に依存します。
* **既に利用可能なレポートスイートを使用して新しい条件または編集した条件**:新しい条件を作成する場合や既存の条件を編集する場合、選択したレポートスイートが既に使用されていて、選択したデータ範囲と同じかそれ以下のデータ範囲がある場合、そのデータはすぐに使用可能になり、一時的な設定は不要です。 [!DNL Target Recommendations]この場合、または選択されたレポートスイートまたはデータ範囲が変更されずにアルゴリズムの設定が編集されると、12 時間以内にアルゴリズムが実行または再実行されます。
* **進行中のアルゴリズム実行**：毎日の [!DNL Analytics] から [!DNL Target Recommendations] へのデータフロー。例えば、[!UICONTROL 表示の親和性]レコメンデーションの場合、ユーザーが製品を表示すると、製品表示トラッキングコールがほぼリアルタイムで [!DNL Analytics] に渡されます。The [!DNL Analytics] data is pushed to [!DNL Target] early the next day and [!DNL Target] runs the algorithm in fewer than 12 hours.

>[!NOTE]
>
>[!UICONTROL 最近表示した項目] ：オフラインアルゴリズムの実行は不要で、結果を即座に使用できます。 [!UICONTROL mboxデータに基づく最多閲覧] （トップ）アルゴリズムおよび [!UICONTROL トップセラー] （トップセラー）アルゴリズムは、通常、必要な計算が単純なので、非常に迅速に結果を生み出します。 これらは、デザインの変更をプレビューしたり、行動データが正しく収集されていることを確認する場合に便利です。

## プレビューRecommendationsへのQAリンクの使用

アルゴリズムの結果の準備が整ったら、の [QAリンク](/help/c-activities/c-activity-qa/activity-qa.md) 機能を使用して、これらの結果をプレビューでき [!DNL Adobe Target]ます。 QAリンクは、アクティビティの概要ページの「 [!UICONTROL アクティビティQA] 」セクションで利用できます。

![アクティビティ QA リンク](/help/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>デフォルトでは、はQAリンクに必要なオーディエンスにユーザーを [!DNL Target] 自動的に追加します。 この設定をオフにして、アクティビティにターゲットルールがある場合、レコメンデーションを含むエクスペリエンスを表示するには、ユーザープロファイルがこれらのターゲットルールを満たす必要があります。

QAリンクを使用すると、ページ上のレコメンデーションをプレビューできます。

![特集製品](/help/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>ターゲットQAモードは「固定」で、cookieに保存されます。 QAモードを終了しない場合は、サイト全体でQA結果が表示され続けます。 QAモードを終了するには、 [ブックマークレットを使用し](/help/c-activities/c-activity-qa/activity-qa-bookmark.md)ます。

>[!NOTE]
>
>QAモードの場合、サイトを閲覧しても、プロファイルの [!UICONTROL 最近表示した項目] 、 [!UICONTROL または最近購入した項目には影響しません]」。この動作は、意図しない生産行動データの汚染を防ぐために設計上発生します。 [!UICONTROL 最近表示した項目] 、または [!UICONTROL ユーザーベースのRecommendations] 条件から結果をプレビューするには、まずQAモード以外のサイトを参照し、同じセッションを使用してQAモードのリンクを開きます。

## CSVダウンロードを使用したプレビューレコメンデーション

場合によっては、レコメンデーションする特定の項目を監査する必要があります。 これは特に、「これを閲覧した 人」、「これを閲覧した」などのアルゴリズムを使用する場合に便利です。ユーザーが現在閲覧している品目に応じて異なる品目セットがレコメンデーションされ、カタログに何千、何百万もの品目が含まれる場合があります。

結果は、アクティビティ内の少なくとも1つのアルゴリズムに対して [!UICONTROL 結果準備完了] (Results Ready)のステータスが表示されるまで、ダウンロードできません。

プレビューの結果をダウンロードするには、アクティビティの概要ページの右上隅にあるメニューアイコンをクリックし、「データを **[!UICONTROL ダウンロード]**」をクリックします。

![データのダウンロードオプション](/help/c-recommendations/t-create-recs-activity/assets/download-data.png)

CSVファイルがダウンロードされます。 それを開いて、レコメンデーションする品目を確認します。

![推奨品目のCSVファイル](/help/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

左から右へとレコメンデーション品目のリストを示します。この場合は、最も頻繁に閲覧されます。 レコメンデーションは環境で区切られます。この場合、実稼動環境にのみレコメンデーションが含まれます。 このアルゴリズムでは、キー値に基づく制限は適用していないので、アスタリスク(*)の付いた行にはレコメンデーションの完全なセットが含まれています。 「これを閲覧した [!UICONTROL 人が他に閲覧したもの」など、キー値に基づく他のアルゴリズムタイプの場合]、キー値（「この」項目など）が一番左の列に、レコメンデーション品目（「その」項目）がRecommendation_X列の左から右に表示されます。

>[!NOTE]
>
>結果のダウンロードは、 [!UICONTROL ユーザーベースのRecommendations] アルゴリズムを含むアクティビティでは使用できません。 結果のダウンロードは、「 [!UICONTROL 最近表示された品目] 」レコメンデーションロジックを使用する条件では利用できません。

## Recommendationsアクティビティのアクティブ化

「 [!UICONTROL アクティビティの概要] 」タブで、ステータスの横にあるドロップダウン矢印をクリックし、「 **[!UICONTROL アクティブ化]**」を選択します。

![Activateオプション](/help/c-recommendations/t-create-recs-activity/assets/activate.png)

ステータスが「 [!UICONTROL アクティブ化中]」になります。

![アクティブ化中](/help/c-recommendations/t-create-recs-activity/assets/activating.png)

数秒から数分後、ステータスが [!UICONTROL ライブに切り替わります]。

![ライブ](/help/c-recommendations/t-create-recs-activity/assets/live.png)

同じドロップダウンリストを使用して、アクティビティを非アクティブ化したり、アーカイブしたりすることもできます。

## Recommendations設定の変更時の通信障害の回避

ライブアクティビティで [!DNL Recommendations] コレクション、条件、プロモーションまたはデザインの設定を変更すると、アルゴリズムの結果が無効になり、アルゴリズムのステータスが「 [!UICONTROL Results Not Ready]」に変わる可能性があります。

ライブアクティビティを中断させないように、ライブアクティビティを変更する場合は、次の方法を使用することをお勧めします。

1. 変更するアクティビティと条件を重複します。
1. 複製されたアクティビティと条件に変更を加え、アルゴリズムの結果生成を待ちます。
1. 新しく変更されたアクティビティをプレビューし、必要に応じて結果が得られることを確認します。
1. 新しいアクティビティをアクティブ化します。
1. 古いアクティビティを非アクティブ化します。

過去のレポート結果を同じアクティビティに維持する必要がある場合は、別の方法を使用することも可能です。これにより、レコメンデーションの可用性が一時的に停止する可能性があります。

1. 変更するアクティビティと条件を重複します。
1. 複製されたアクティビティと条件に変更を加え、アルゴリズムの結果生成を待ちます。
1. 新しく変更されたアクティビティをプレビューし、必要に応じて結果が得られることを確認します。
1. 既存のアクティビティを一時停止し、設定/条件を新しい条件に置き換えます。
1. 既存のアクティビティをプレビューし、必要に応じて結果が得られることを確認します。
1. アクティビティを再度アクティブにします。
