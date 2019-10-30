---
description: 'Recommendationsオファーを含むRecommendations、A/Bテストまたはエクスペリエンスターゲット設定(XT)アクティビティを作成したら、アクティビティを起動する前に、そのアクティビティをプレビューして結果が使用可能であることを確認します。 Target Recommendationsでは、レコメンデーションをプレビューする複数の方法が用意されています。 '
keywords: Recommendations；オファー；プレビュー；起動
seo-description: 'Adobe Target Recommendationsオファーを含むRecommendations、A/Bテストまたはエクスペリエンスターゲット設定(XT)アクティビティを作成したら、アクティビティを起動する前に、そのアクティビティをプレビューして結果が利用可能であることを確認します。 Target Recommendationsでは、レコメンデーションをプレビューする複数の方法が用意されています。 '
seo-title: 'Adobe Target Recommendationsオファーを含むRecommendations、A/Bテストまたはエクスペリエンスターゲット設定(XT)アクティビティを作成したら、アクティビティを起動する前に、そのアクティビティをプレビューして結果が利用可能であることを確認します。 Target Recommendationsでは、レコメンデーションをプレビューする複数の方法が用意されています。 '
solution: 'Target '
subtopic: Recommendations
title: Recommendationsアクティビティのプレビューと起動
title-outputclass: premium
topic: Premium
badge: Premium
translation-type: tm+mt
source-git-commit: c0603b5d18c3986e24313044baf3be0a67880bbf

---


# Recommendationsアクティビティのプレビューと起動

Recommendationsを含む [!UICONTROL Recommendations]、 [!UICONTROL A/B Test]、 [!UICONTROL Experience Targeting][](/help/c-recommendations/recommendations-as-an-offer.md)(XT)アクティビティを作成した後は、アクティビティを開始する前に結果が利用可能であることを確認するためのプレビューを行います。 [!DNL Target Recommendations] には、レコメンデーションをプレビューする複数の方法が用意されています。

## Recommendationsアルゴリズムのステータスの確認

アクティビティの作成後、アルゴリズム [!DNL Recommendations] を実行してレコメンデーションを生成します。 このアルゴリズムの実行には数時間かかる場合があります。

アルゴリズムの実行が完了したかどうかは、条件のステータスが表示さ [!UICONTROL れる] 「アクティビティの概要」図で確認できます。 The following illustration shows the status in the activity diagram on a [!DNL Recommendations] activity's [!UICONTROL Overview] page:

![Recommendationsアクティビティの概要ページ](/help/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

次の図は、 [!UICONTROL A/B testまたはXTアクティビティの概要ページのス] テータスを示して [!UICONTROL います] 。

![A/Bテストの概要ページ](/help/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

次に示すように、ステータスの結果は次のとおりです。

* [!UICONTROL Results Ready]:アルゴリズムが結果を返したことを示します
* [!UICONTROL Results Not Ready]:アルゴリズムの実行が完了していないことを示します。
* [!UICONTROL フィードの失敗]:カスタム条件のフィードファイルを取得できなかったことを示します。

![結果ダイアログボックス](/help/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## アルゴリズムの実行にはどのくらい時間がかかりますか。

条件を含むアクティビティを保存した後、選択し [!DNL Target] たコレクション、条件、デザインおよびプロモーションに基づいてレコメンデーションが計算されます。 この計算の実行には、しばらく時間がかかり、その期間は、選択したレコメンデーションロジック、データ範囲、カタログの項目数、お客様によって生成された行動データの量および選択された行動データソースによって異なります。

次のように、行動データソースは、処理時間に最も影響します。

### mbox

mbox が行動データソースとして選択される場合、一旦作成されると、条件は即座に実行されます。使用される行動データの量とカタログのサイズに応じて、アルゴリズムの実行には最大で 12 時間かかります。条件の設定を変更すると、通常、アルゴリズムが再実行されます。変更内容によっては、以前に計算されたレコメンデーションは、再実行が完了するまで使用できない場合や、大きな変更を行う場合は、再実行が完了するまでバックアップまたはデフォルトコンテンツのみを使用できます。 アルゴリズムが変更されない場合、選択されたデータ範囲に応じて 12 ～ 48 時間ごとに、[!DNL Target] によって自動的に再実行されます。

### Adobe Analytics

[!DNL Adobe Analytics] を行動データソースとして使用する条件を作成した場合は、選択されているレポートスイートとルックバックウィンドウが他の条件でも使用されているかどうかに応じて、条件が使用可能になる時間が異なります。

* **1 回限りのレポートスイート設定**：指定されたデータ範囲のルックバックウィンドウで最初にレポートスイートが使用されると、[!DNL Target Recommendations] は、選択されたレポートスイートの行動データを [!DNL Analytics] から完全にダウンロードするまで 2 ～ 7 日間かかる可能性があります。この期間は、[!DNL Analytics] システム負荷に依存します。
* **既に利用可能なレポートスイートを使用して新しい条件または編集した条件**:新しい条件を作成する場合や既存の条件を編集する場合、選択したレポートスイートが既に使用されていて、選択したデータ範囲と同じかそれ未満のデータ範囲を持つ場合は、そのデータがすぐに使用可能になり、一時的な設定は不要です。 [!DNL Target Recommendations]この場合、または選択されたレポートスイートまたはデータ範囲が変更されずにアルゴリズムの設定が編集されると、12 時間以内にアルゴリズムが実行または再実行されます。
* **進行中のアルゴリズム実行**：毎日の [!DNL Analytics] から [!DNL Target Recommendations] へのデータフロー。例えば、[!UICONTROL 表示の親和性]レコメンデーションの場合、ユーザーが製品を表示すると、製品表示トラッキングコールがほぼリアルタイムで [!DNL Analytics] に渡されます。The [!DNL Analytics] data is pushed to [!DNL Target] early the next day and [!DNL Target] runs the algorithm in fewer than 12 hours.

>[!NOTE]
>
>[!UICONTROL 最近表示した品目は] 、オフラインアルゴリズムを実行する必要がなく、結果をすぐに使用できます。 [!UICONTROL mboxデータに基づく最多閲覧] (Top Viewed  )アルゴリズムとトップセラーアルゴリズムは、通常、必要な計算がシンプルになるので、非常に迅速に結果を生み出します。 デザインの変更をプレビューしたり、行動データが正しく収集されていることを確認したりする場合に、これらのオプションが役立ちます。

## QAリンクを使用したRecommendationsのプレビュー

アルゴリズムの結果の準備が整ったら、の [QAリンク機能を使用して結果をプレビューできま](/help/c-activities/c-activity-qa/activity-qa.md)[!DNL Adobe Target]す。 QAリンクは、アクティビティの概要ペ [!UICONTROL ージの「アクティビティQA] 」セクションで利用できます。

![アクティビティ QA リンク](/help/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>デフォルトでは、 [!DNL Target] QAリンクに必要なオーディエンスに自動的に追加されます。 この設定をオフにし、アクティビティにターゲットルールが含まれる場合、ユーザープロファイルは、recommendationsを含むエクスペリエンスを表示するには、これらのターゲットルールを満たす必要があります。

QAリンクを使用すると、ページ上でレコメンデーションをプレビューできます。

![特集製品](/help/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>Target QAモードは「固定」で、cookieに保存されます。 QAモードを終了しない場合は、サイト全体でQA結果が表示され続けます。 QAモードを終了するには、ブックマークレットを [使用しま](/help/c-activities/c-activity-qa/activity-qa-bookmark.md)す。

>[!NOTE]
>
>QAモードの間は、サイトを閲覧しても、プロファイルの「最近表示した品目 [!UICONTROL 」や「最近購入した品目」には影響しません]。この動作は、生産行動データの意図しない汚染を避けるために設計上行われます。 最近表示した品目またはユーザ [!UICONTROL ーベースのレコメンデーション条件の結果をプレビューするには] 、まずQAモード以外でサイトを参照し、次に同じセッションを使用してQAモードリンクを開きます。

## CSVダウンロードを使用したレコメンデーションのプレビュー

場合によっては、レコメンデーションする特定の品目を監査する必要があります。 これは、「これを閲覧した人」、「他に閲覧した人」などのアルゴリズムを使用する場合に特に便利です。ユーザーが現在閲覧している品目に応じて、様々な品目セットがレコメンデーションされ、カタログに何千、何百万もの品目が含まれる場合があります。 

結果は、アクティビティ内の少なくとも1つのアルゴ [!UICONTROL リズムに対して] 「Results Ready」ステータスが表示されるまで、ダウンロードできません。

プレビュー用に結果をダウンロードするには、アクティビティの概要ページの右上隅にあるメニューアイコンをクリックし、「データをダウンロード」をク **[!UICONTROL リックしま]**&#x200B;す。

![ダウンロードデータオプション](/help/c-recommendations/t-create-recs-activity/assets/download-data.png)

CSVファイルがダウンロードされます。 開いて、レコメンデーション品目を表示します。

![推奨品目のCSVファイル](/help/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

左から右にレコメンデーション品目のリストが表示されます。この場合は、最も頻繁に閲覧されます。 レコメンデーションは環境ごとに分けられます。この場合、レコメンデーションを持つのは実稼働環境のみです。 このアルゴリズムでは、キー値に基づく制限は適用されていないので、アスタリスク(*)の付いた行にはレコメンデーションの完全なセットが含まれます。 キー値に基づく他のアルゴリズムタイプ( [!UICONTROL People Who View This、Viewed That])の場合、キー値（「This」項目）が一番左の列に、レコメンデーション品目（「That」項目）がRecommendation_X列に左から右に表示されます。

>[!NOTE]
>
>ユーザーベースのレコメンデーションアルゴリズムを含むアクティビティで [!UICONTROL は、結果のダウンロードを使用] できません。 「最近表示した品目」レコメンデーションロジックを使用した条件で [!UICONTROL は、結果のダウンロードを使用] できません。

## Recommendationsアクティビティのアクティブ化

「アクティビティ [!UICONTROL の概要] 」タブで、ステータスの横にあるドロップダウン矢印をクリックし、「アクティブ化」を選択 **[!UICONTROL します]**。

![Activateオプション](/help/c-recommendations/t-create-recs-activity/assets/activate.png)

ステータスが「アクティブ化中」にな [!UICONTROL ります]。

![アクティブ化中](/help/c-recommendations/t-create-recs-activity/assets/activating.png)

数秒から数分後に、ステータスが [!UICONTROL Liveに切り替わります]。

![ライブ](/help/c-recommendations/t-create-recs-activity/assets/live.png)

同じドロップダウンリストを使用して、アクティビティを非アクティブ化またはアーカイブすることもできます。

## Recommendationsの設定変更時の中断の回避

ライブア [!DNL Recommendations] クティビティのコレクション、条件、プロモーションまたはデザイン設定を変更すると、アルゴリズムの結果が無効になり、アルゴリズムのステータスが「結果の準備ができていませ [!UICONTROL ん]」に変更。

ライブアクティビティの中断を避けるため、ライブアクティビティを変更する際は、次の方法を使用することをお勧めします。

1. 変更するアクティビティと条件を複製します。
1. 複製されたアクティビティと条件に変更を加え、アルゴリズムが結果を生成するのを待ちます。
1. 新しく変更されたアクティビティをプレビューし、結果が希望どおりになることを確認します。
1. 新しいアクティビティをアクティブ化します。
1. 古いアクティビティを非アクティブ化します。

同じアクティビティで履歴レポートの結果を保持する必要がある場合は、代替アプローチが可能で、レコメンデーションの可用性が一時的に停止する可能性があります。

1. 変更するアクティビティと条件を複製します。
1. 複製されたアクティビティと条件に変更を加え、アルゴリズムが結果を生成するのを待ちます。
1. 新しく変更されたアクティビティをプレビューし、結果が希望どおりになることを確認します。
1. 既存のアクティビティを一時停止し、設定/条件を新しい条件に置き換えます。
1. 既存のアクティビティをプレビューし、結果が希望どおりになることを確認します。
1. アクティビティを再度アクティブ化します。
