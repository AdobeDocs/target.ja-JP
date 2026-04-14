---
keywords: レコメンデーション；オファー；プレビュー；ローンチ；ステータス；条件；アルゴリズム
description: Adobe [!DNL Target] Recommendations アクティビティをプレビューして、アクティビティを開始する前に結果が使用可能であることを確認する方法を説明します。
title: Recommendations アクティビティをプレビューして起動するにはどうすればよいですか？
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: f6034e83564a9a386e21e4e57279c66cc3c94537
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 15%

---

# レコメンデーションアクティビティのプレビューと起動

[!UICONTROL Recommendations]Recommendations オファー[!UICONTROL A/B Test]を含む[!UICONTROL Experience Targeting]、[または](/help/main/c-recommendations/recommendations-as-an-offer.md) （XT）アクティビティを作成した後、アクティビティを起動する前に結果が利用可能であることを確認するために、レコメンデーションをプレビューする必要があります。 [!DNL Target Recommendations]では、レコメンデーションをプレビューする複数の方法が用意されています。

## Recommendations アルゴリズムのステータスの確認

アクティビティの作成後、[!DNL Recommendations]はアルゴリズムを実行してレコメンデーションを生成します。 このアルゴリズムを実行するには数時間かかる場合があります。

アルゴリズムの実行が完了したかどうかを、[!UICONTROL Activity]概要ダイアグラムで確認できます。このダイアグラムには、基準ステータスが一覧表示されます。 次の図は、[!DNL Recommendations] アクティビティの[!UICONTROL Overview] ページのアクティビティ ダイアグラムのステータスを示しています。

![Recommendations アクティビティの概要ページ &#x200B;](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview-new.png)

ステータスの結果には、次の図が含まれます。

* [!UICONTROL Results Ready]: アルゴリズムが結果を返したことを示します
* [!UICONTROL Results Not Ready]: アルゴリズムの実行が完了していないことを示します。
* [!UICONTROL Feed Failure]: カスタム条件フィード ファイルを取得できなかったことを示します。

![結果ダイアログボックス &#x200B;](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## アルゴリズムの実行にどのくらいの時間がかかるか？

条件を含むアクティビティを保存すると、[!DNL Target]は、選択したコレクション、条件、デザイン、およびプロモーションに基づいて推奨事項を計算します。 この計算には時間がかかり、選択したレコメンデーションロジック、データ範囲、カタログ内の項目数、顧客が生成した行動データの量、選択した行動データソースにもとづいて時間枠が異なります。

次のように、行動データソースは、処理時間に最も影響します。

### mbox

mbox が行動データソースとして選択される場合、一旦作成されると、条件は即座に実行されます。使用される行動データの量とカタログのサイズに応じて、アルゴリズムの実行には最大で 12 時間かかります。条件の設定を変更すると、通常、アルゴリズムが再実行されます。変更に応じて、以前に計算された推奨事項は、再実行が完了するまで利用できない場合があります。また、より大きな変更の場合は、再実行が完了するまでバックアップまたはデフォルトのコンテンツのみが利用できる場合があります。 アルゴリズムが変更されない場合、選択されたデータ範囲に応じて 12 ～ 48 時間ごとに、[!DNL Target] によって自動的に再実行されます。

### [!DNL Adobe Analytics]

[!DNL Adobe Analytics] を行動データソースとして使用する条件を作成した場合は、選択されているレポートスイートとルックバックウィンドウが他の条件でも使用されているかどうかに応じて、条件が使用可能になる時間が異なります。

* **1 回限りのレポートスイート設定**：指定されたデータ範囲のルックバックウィンドウで最初にレポートスイートが使用されると、[!DNL Target Recommendations] は、選択されたレポートスイートの行動データを [!DNL Analytics] から完全にダウンロードするまで 2 ～ 7 日間かかる可能性があります。この期間は、[!DNL Analytics] システム負荷に依存します。
* **既に利用可能なレポートスイートを使用して新しい条件または編集された条件**：新しい条件を作成するか、既存の条件を編集する際に、選択したレポートスイートが既に[!DNL Target Recommendations]で使用されていて、選択したデータ範囲と同じかそれ以下のデータ範囲がある場合、データはすぐに使用でき、1回限りの設定は必要ありません。 この場合、または選択されたレポートスイートまたはデータ範囲が変更されずにアルゴリズムの設定が編集されると、12 時間以内にアルゴリズムが実行または再実行されます。
* **進行中のアルゴリズム実行**：毎日の [!DNL Analytics] から [!DNL Target Recommendations] へのデータフロー。例えば、[!UICONTROL Viewed Affinity]のレコメンデーションでは、ユーザーが製品を閲覧すると、リアルタイムに近い[!DNL Analytics]に製品ビューのトラッキング呼び出しが渡されます。 [!DNL Analytics] データは翌日早く[!DNL Target]にプッシュされ、[!DNL Target]はアルゴリズムを12時間未満で実行します。

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items]はオフライン アルゴリズムを実行する必要がなく、結果はすぐに利用できます。 mbox データに基づく[!UICONTROL Top Viewed]および[!UICONTROL Top Sellers] アルゴリズムは、一般的に、計算が簡単であるため、非常に迅速に結果を生成します。 これは、デザインの変更をプレビューする場合や、行動データが正しく収集されていることを確認する場合に適したオプションです。

## QA リンクを使用したレコメンデーションのプレビュー

アルゴリズムが結果を準備したら、[の](/help/main/c-activities/c-activity-qa/activity-qa.md)QA リンク [!DNL Adobe Target]機能を使用して、それらの結果をプレビューできます。 QA リンクは、[!UICONTROL Activity Location]概要ページの[!UICONTROL Activity] セクションで利用できます。

>[!NOTE]
>
>デフォルトでは、[!DNL Target]は自動的にQA リンクに必要なオーディエンスにユーザーを追加します。 この設定がオフになっていて、アクティビティにターゲティングルールがある場合、ユーザープロファイルは、レコメンデーションを含むエクスペリエンスを表示するためにこれらのターゲティングルールを満たす必要があります。

QA リンクを使用すると、ページ上のレコメンデーションをプレビューできます。

![注目の製品](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* ターゲット QA モードは「スティッキー」で、Cookieに保存されます。 QA モードを終了しない場合は、サイト全体でQAの結果が引き続き表示されます。 QA モードを終了するには、[bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md)を使用します。
>
>* QA モードでは、サイトを参照しても、プロファイルの[!UICONTROL Recently Viewed Items]または[!UICONTROL Recently Purchased Items]には影響しません。 この動作は、生産行動データの意図しない汚染を避けるために、設計によって行われます。 [!UICONTROL Recently Viewed Items]または[!UICONTROL User-Based Recommendations]条件の結果をプレビューするには、まずQA モード以外のサイトを参照してから、同じセッションを使用してQA モードリンクを開きます。

## CSV ダウンロードを使用したレコメンデーションのプレビュー

場合によっては、推奨される特定の項目を監査することもできます。 これは、[!UICONTROL People Who Viewed This, Viewed That]のようなアルゴリズムを使用する場合に特に役立ちます。このアルゴリズムでは、ユーザーが現在表示している項目に応じて異なる項目セットが推奨され、カタログに数千または数百万の異なる項目が含まれる場合があります。

アクティビティ内の少なくとも1つのアルゴリズムに[!UICONTROL Results Ready] ステータスが表示されるまで、結果をダウンロードできません。

プレビューの結果をダウンロードするには、アクティビティの概要ページの右上隅にあるメニューアイコンをクリックし、**[!UICONTROL Download data]**&#x200B;をクリックします。

![&#x200B; データオプションのダウンロード &#x200B;](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

CSV ファイルがダウンロードされます。 このタブを開くと、推奨項目が表示されます。

![おすすめアイテムのCSV ファイル &#x200B;](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

左から右へ推奨アイテムのリストです。この場合、最も頻繁に閲覧されます。 レコメンデーションは環境で区切られます。この場合、実稼動環境のみがレコメンデーションを持ちます。

アスタリスク （*）が行の最初の値である場合、[&#x200B; バックアップ項目](/help/main/c-recommendations/c-algorithms/backup-recs.md)を示します。 設計のすべてのスロットをアルゴリズムの推奨項目（条件）で埋めることができない場合は、バックアップ項目が表示されます。

[!UICONTROL People Who Viewed This, Viewed That]などのキー値に基づくその他のアルゴリズムタイプの場合、キー値（「この」項目）が一番左の列に表示され、推奨項目（「その」項目）がRecommendation_X列に左から右に表示されます。

>[!NOTE]
>
>結果のダウンロードは、[!UICONTROL User-Based Recommendations] アルゴリズムを含むアクティビティでは使用できません。 結果のダウンロードは、[!UICONTROL Recently-Viewed Items]のレコメンデーションロジックを使用する条件では利用できません。

## Recommendations アクティビティのアクティブ化

「[!UICONTROL Activity Overview]」タブで、「ステータス」ドロップダウン矢印をクリックし、「**[!UICONTROL Activate]**」を選択します。

[!UICONTROL Recommendations] アクティビティが現在[!UICONTROL Inactive]状態にある場合、ドロップダウンリストには[!UICONTROL Inactive]というラベルが付けられます。

数秒から数分後、ステータスが[!UICONTROL Live]に切り替わります。

同じドロップダウンリストを使用して、アクティビティを非アクティブ化またはアーカイブすることもできます。

## Recommendations設定を変更する際の中断の回避

ライブアクティビティで[!DNL Recommendations]個のコレクション、条件、プロモーション、デザイン設定を変更すると、アルゴリズムの結果が無効になり、アルゴリズムのステータスが[!UICONTROL Results Not Ready]に変更される場合があります。

ライブアクティビティの中断を回避するには、ライブアクティビティを変更する際に次の方法を使用することをお勧めします。

1. 元のアクティビティ（アクティビティ 1）と変更する基準を複製して、新しいアクティビティ（アクティビティ 2）を作成します。
1. 複製されたアクティビティ（アクティビティ 2）と基準に変更を加え、アルゴリズムが結果を生成するのを待ちます。
1. 新しい変更されたアクティビティ（アクティビティ 2）をプレビューし、結果が必要に応じて表示されることを確認します。
1. 新しいアクティビティ（アクティビティ 2）をアクティブ化します。
1. 元のアクティビティ（アクティビティ 1）を非アクティブにします。

過去のレポート結果を同じアクティビティで保持する必要がある場合は、別のアプローチが可能になり、レコメンデーションの可用性が一時的に中断される可能性があります。

1. 元のアクティビティ（アクティビティ 1）と変更する基準を複製して、新しいアクティビティ（アクティビティ 2）を作成します。
1. 複製されたアクティビティ（アクティビティ 2）と基準に変更を加え、アルゴリズムが結果を生成するのを待ちます。
1. 新しい変更されたアクティビティ（アクティビティ 2）をプレビューし、結果が必要に応じて表示されることを確認します。
1. 新しい変更されたアクティビティ（アクティビティ 2）を一時停止し、設定/基準を元のアクティビティ（アクティビティ 1）に切り替えます。
1. 元のアクティビティ（アクティビティ 1）をプレビューし、結果が必要なものであることを確認します。
1. 元のアクティビティ（アクティビティ 1）を再アクティブ化します。
