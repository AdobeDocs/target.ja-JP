---
keywords: Recommendations；オファー；プレビュー；ローンチ；ステータス；条件；アルゴリズム
description: アクティビティを開始する前に、Adobe [!DNL Target] Recommendations アクティビティをプレビューして、結果が使用可能であることを確認する方法を説明します。
title: Recommendations アクティビティをプレビューして開始するにはどうすればよいですか？
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: ed400ad0ecf62a74283d2f24038bacab6a275461
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 15%

---

# Recommendations アクティビティのプレビューと起動

[Recommendations オファー ](/help/main/c-recommendations/recommendations-as-an-offer.md) を含む [!UICONTROL Recommendations]、[!UICONTROL A/B Test] または [!UICONTROL Experience Targeting] （XT）アクティビティを作成したら、アクティビティを開始する前に、推奨事項をプレビューして、結果が使用可能であることを確認します。 [!DNL Target Recommendations] では、お勧めをプレビューする方法が複数用意されています。

## Recommendations アルゴリズムのステータスの確認

アクティビティを作成した後、[!DNL Recommendations] はアルゴリズムを実行してレコメンデーションを生成します。 このアルゴリズムの実行には数時間かかる場合があります。

条件のステータスが一覧表示される [!UICONTROL Activity] の概要図で、アルゴリズムの実行が完了したかどうかを確認できます。 次の図は、[!DNL Recommendations] のアクティビティの [!UICONTROL Overview] ページのアクティビティ図のステータスを示しています。

![Recommendations アクティビティの概要ページ ](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview-new.png)

ステータス結果には、次の図が含まれます。

* [!UICONTROL Results Ready]: アルゴリズムから結果が返されたことを示します
* [!UICONTROL Results Not Ready]: アルゴリズムの実行が完了していないことを示します。
* [!UICONTROL Feed Failure]：カスタム条件フィードファイルを取得できなかったことを示します。

![ 結果ダイアログボックス ](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## アルゴリズムの実行にはどの程度の時間がかかりますか？

条件を含むアクティビティを保存すると、選択し [!DNL Target] コレクション、条件、デザイン、プロモーションに基づいてお勧めが計算されます。 この計算の実行には時間がかかり、選択したレコメンデーションロジック、データ範囲、カタログ内の項目数、顧客が生成した行動データの量、選択した行動データソースに基づいて、時間枠が異なります。

次のように、行動データソースは、処理時間に最も影響します。

### mbox

mbox が行動データソースとして選択される場合、一旦作成されると、条件は即座に実行されます。使用される行動データの量とカタログのサイズに応じて、アルゴリズムの実行には最大で 12 時間かかります。条件の設定を変更すると、通常、アルゴリズムが再実行されます。行った変更によっては、再実行が完了するまで以前に計算したレコメンデーションを使用できない場合や、大規模な変更の場合、再実行が完了するまでバックアップまたはデフォルトコンテンツのみを使用できる場合があります。 アルゴリズムが変更されない場合、選択されたデータ範囲に応じて 12 ～ 48 時間ごとに、[!DNL Target] によって自動的に再実行されます。

### [!DNL Adobe Analytics]

[!DNL Adobe Analytics] を行動データソースとして使用する条件を作成した場合は、選択されているレポートスイートとルックバックウィンドウが他の条件でも使用されているかどうかに応じて、条件が使用可能になる時間が異なります。

* **1 回限りのレポートスイート設定**：指定されたデータ範囲のルックバックウィンドウで最初にレポートスイートが使用されると、[!DNL Target Recommendations] は、選択されたレポートスイートの行動データを [!DNL Analytics] から完全にダウンロードするまで 2 ～ 7 日間かかる可能性があります。この期間は、[!DNL Analytics] システム負荷に依存します。
* **既に使用可能なレポートスイートを使用して新規または編集した条件**：新しい条件を作成したり既存の条件を編集したりする際、選択したレポートスイートが既に [!DNL Target Recommendations] で使用されていて、選択したデータ範囲以下のデータ範囲がある場合、データは直ちに使用でき、1 回限りの設定は不要です。 この場合、または選択されたレポートスイートまたはデータ範囲が変更されずにアルゴリズムの設定が編集されると、12 時間以内にアルゴリズムが実行または再実行されます。
* **進行中のアルゴリズム実行**：毎日の [!DNL Analytics] から [!DNL Target Recommendations] へのデータフロー。例えば、[!UICONTROL Viewed Affinity] のレコメンデーションでは、ユーザーが製品を閲覧すると、製品ビューのトラッキングコールがにリアルタイムに近い [!DNL Analytics] で渡されます。 [!DNL Analytics] データは翌日早く [!DNL Target] にプッシュされ、[!DNL Target] は 12 時間未満でアルゴリズムを実行します。

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] では、オフラインアルゴリズムの実行は必要なく、結果はすぐに得られます。 mbox データに基づく [!UICONTROL Top Viewed] および [!UICONTROL Top Sellers] アルゴリズムは、一般に、必要な計算が簡素化されているので、結果を非常に迅速に得られます。 これらは、デザインの変更をプレビューしたり、行動データが正しく収集されていることを確認したりする場合に適したオプションです。

## QA リンクを使用したRecommendationsのプレビュー

アルゴリズムで結果の準備が整ったら、[!DNL Adobe Target] の [QA リンク ](/help/main/c-activities/c-activity-qa/activity-qa.md) 機能を使用して、その結果をプレビューできます。 QA リンクは、[!UICONTROL Activity] の概要ページの「[!UICONTROL Activity Location]」セクションで使用できます。

>[!NOTE]
>
>デフォルトでは、[!DNL Target] は QA リンクに必要なオーディエンスに自動的に追加します。 この設定がオフになっていて、アクティビティにターゲティングルールがある場合、レコメンデーションを含むエクスペリエンスを表示するには、ユーザープロファイルがこれらのターゲティングルールを満たす必要があります。

QA リンクを使用すると、ページ上でレコメンデーションをプレビューできます。

![ 特集商品 ](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* ターゲット QA モードは「スティッキー」で、cookie に保存されます。 QA モードを終了しない場合は、サイト全体で QA 結果が引き続き表示されます。 QA モードを終了するには、[ ブックマークレット ](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md) を使用します。
>
>* QA モードの場合、サイトを閲覧してもプロファイルの [!UICONTROL Recently Viewed Items] や [!UICONTROL Recently Purchased Items] には影響しません。 この動作は、生産行動データの意図しない汚染を避けるために設計によって行われます。 [!UICONTROL Recently Viewed Items] または [!UICONTROL User-Based Recommendations] の条件の結果をプレビューするには、QA モード以外のサイトを参照してから、同じセッションを使用して QA モードのリンクを開きます。

## CSV ダウンロードを使用したレコメンデーションのプレビュー

場合によっては、推奨される特定の項目を監査する必要があります。 これは、[!UICONTROL People Who Viewed This, Viewed That] などのアルゴリズムを使用する場合に特に便利です。現在表示している項目に応じて異なる項目セットを推奨し、カタログに数千または数百万の異なる項目を含める場合があります。

アクティビティ内の 1 つ以上のアルゴリズムで [!UICONTROL Results Ready] ステータスが表示されるまで、結果をダウンロードできません。

プレビュー用に結果をダウンロードするには、アクティビティの概要ページの右上隅にあるメニューアイコンをクリックし、「**[!UICONTROL Download data]**」をクリックします。

![ 「データをダウンロード」オプション ](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

CSV ファイルがダウンロードされます。 これを開いて、推奨される項目を確認します。

![ 推奨項目の CSV ファイル ](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

左から右へは、推奨される項目のリストです。この場合、最も頻繁に閲覧される項目となります。 レコメンデーションは環境によって区切られています。この場合、実稼動環境にのみレコメンデーションがあります。

アスタリスク（*）が行の最初の値の場合は、[ バックアップ項目 ](/help/main/c-recommendations/c-algorithms/backup-recs.md) を示します。 設計内のすべてのスロットがアルゴリズムの推奨項目（条件）によって満たすことができない場合、バックアップ項目が表示されます。

[!UICONTROL People Who Viewed This, Viewed That] などのキー値に基づくその他のアルゴリズムタイプの場合、キー値（「This」項目）は左端の列に表示され、推奨項目（「That」項目）は Recommendation_X 列に左から右に表示されます。

>[!NOTE]
>
>[!UICONTROL User-Based Recommendations] しいアルゴリズムを含むアクティビティでは、結果のダウンロードは使用できません。 [!UICONTROL Recently-Viewed Items] レコメンデーションロジックを使用した条件では、結果のダウンロードは使用できません。

## Recommendations アクティビティのアクティベート

「[!UICONTROL Activity Overview]」タブで、「ステータス」ドロップダウン矢印をクリックし、「**[!UICONTROL Activate]**」を選択します。

[!UICONTROL Recommendations] アクティビティが現在「[!UICONTROL Inactive]」状態の場合、ドロップダウンリストには「[!UICONTROL Inactive]」というラベルが付きます。

数秒から数分後に、ステータスが [!UICONTROL Live] に切り替わります。

同じドロップダウンリストを使用して、アクティビティをディアクティベートまたはアーカイブすることもできます。

## Recommendations設定変更時の混乱を避ける

ライブアクティビティ内 [!DNL Recommendations] コレクション、条件、プロモーション、または設計設定を変更すると、アルゴリズム結果が無効になり、アルゴリズムのステータスが「[!UICONTROL Results Not Ready]」に変更される場合があります。

ライブアクティビティが中断されないようにするには、ライブアクティビティを変更する際に、次のアプローチを採用することをお勧めします。

1. 元のアクティビティ（アクティビティ 1）と、変更する条件を複製して、新しいアクティビティ（アクティビティ 2）を作成します。
1. 重複したアクティビティ（アクティビティ 2）と条件に変更を加え、アルゴリズムが結果を生成するまで待ちます。
1. 新しく変更されたアクティビティ（アクティビティ 2）をプレビューし、結果が必要に応じて得られることを確認します。
1. 新しいアクティビティ（アクティビティ 2）をアクティブ化します。
1. 元のアクティビティ（アクティビティ 1）を非アクティブ化します。

過去のレポート結果を同じアクティビティで保持する必要がある場合は、別の方法を選択することもできます。その場合、レコメンデーションの可用性が一時的に中断される可能性があります。

1. 元のアクティビティ（アクティビティ 1）と、変更する条件を複製して、新しいアクティビティ（アクティビティ 2）を作成します。
1. 重複したアクティビティ（アクティビティ 2）と条件に変更を加え、アルゴリズムが結果を生成するまで待ちます。
1. 新しく変更されたアクティビティ（アクティビティ 2）をプレビューし、結果が必要に応じて得られることを確認します。
1. 新しく変更されたアクティビティ（アクティビティ 2）を一時停止し、設定/条件を元のアクティビティ（アクティビティ 1）に入れ替えます。
1. 元のアクティビティ（アクティビティ 1）をプレビューし、結果が必要に応じて得られることを確認します。
1. 元のアクティビティ（アクティビティ 1）を再アクティブ化します。
