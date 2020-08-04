---
keywords: Targeting;success;conversion metric;page score metric;page views metric;revenue metrics;time on site metric;estimated value;advanced settings;success metrics;advanced settings
description: Adobe Targetでは、成功指標はアクティビティの成功を測定するために使用されるパラメーターです。 成功指標には、Target アクティビティの特定のエクスペリエンスやオファーの成功を判定できる、主要なビジネス測定が含まれます。
title: Adobe Targetの成功指標
uuid: 24e9ae0f-099b-430b-b2bb-03b405f88929
translation-type: tm+mt
source-git-commit: 4fd2de5600060d58759ffa54a771a45b263f115b
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 52%

---


# 成功指標{#success-metrics}

In [!DNL Adobe Target] success metrics are parameters used to measure the success of an activity. Success metrics include key business measures that enable you to determine the success of a given experience or offer in a [!DNL Target] activity.

例えば、新しいオファーが訪問者あたりの売上高を増加させたり、買い物かごに品目を追加したりするかどうかを判断できます。成功指標は、登録、注文または購入ファネルの問題を見つけるのに役立ちますが、単に訪問者やお客様のエンゲージメントにも役立ちます。

## 概要

では、成功指標 [!DNL Target]は、レポートと追跡の両方の目的に最適なオプションを使用して事前設定されています。

デフォルトでは、コンバージョンイベントは「カウントを[!UICONTROL 増分、アクティビティでユーザーを保持]」に設定されます。 コンバージョンは1回だけカウントされ、繰り返しコンバージョンはカウントされず、訪問者には常にアクティビティのコンテンツが表示されます。

Revenue metrics that are set to &quot;[!UICONTROL Increment count &amp; keep user in activity]&quot; log order details only for the first order made by the same visitor. All subsequent orders increase conversion count, but will not add revenue to RPV/AOV/Sales, and will not be included in the [!UICONTROL Order Details] report.

>[!NOTE]
>
>[Analyticsをレポートソースとして使用するアクティビティ(A4T)のデフォルトの動作は、「カウントを](/help/c-integrating-target-with-mac/a4t/a4t.md) 増分、アクティビティ内にユーザーを保持[!UICONTROL 」で、「参加者あたり]1回」です。

以下の成功指標を使用できます。

| 成功指標 | 測定アプローチ | 定義 |
|--- |--- |--- |
| コンバージョン | コンバージョンベース | コンバージョンとは、訪問者が定義したサイト上で、 <ul><li>ボタンをクリック</li><li>ページが表示された</li><li>調査の完了</li><li>購入</li></ul>コンバージョンは、訪問者ごとに1回、または訪問者がコンバージョンを完了するたびにカウントできます。 |
| 売上高 | コンバージョンベース | 訪問者によって生成された売上高。次のいずれかの売上高指標から選択できます。<ul><li>訪問者あたりの売上高（RPV）</li><li>平均注文額（AOV）</li><li>合計販売額</li><li>注文件数</li></ul> |
| ページビュー数 | エンゲージメントベース | 一意の訪問ごとに 1 回のコンバージョンとしてカウントします。 |
| カスタムスコア | エンゲージメントベース | Aggregated score based on the value assigned to pages visited on the site, from the point the visitor first sees the activity&#39;s first display [!DNL Target] request. |
| サイト滞在時間 | エンゲージメントベース | Time spent in the visit (in seconds) from the point the visitor sees the activity&#39;s first display [!DNL Target] request to the load of the final page with a request in the session. |

エンゲージメントベースの指標の場合は（コンバージョンベースおよび売上高ベースの指標とは異なり）、訪問者はそのセッションのカウントをインクリメントするために、訪問ごとにアクティビティを再評価する必要があります。関連付けられた指標は、再評価の後にインクリメントが開始され、各訪問者のセッションの終わりでインクリメントが停止します。30 分間無操作状態が続くと、そのセッションは終了します。したがって、テスト中にすぐに結果が表示されることはありません。 ただし、そのセッションの結果は、セッションの終了から数分以内にすべて利用できます。

## カスタム成功指標

カスタムの成功指標も作成できます。

成功指標を選択し、目的を達成するために訪問者がとるアクションを選択します。For example, choose a [!UICONTROL Conversion] metric, set it to be counted once per visitor, then set whether success is achieved when a visitor views a certain page (or set of pages), views a specific [!DNL Target] request, or clicks a specific link.

If enabled, the [!UICONTROL Estimated Value of one conversion] field (not available for the [!UICONTROL Page Score] metrics) provides a value for your goal, but not for other metrics. この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。For all revenue metrics ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales], and [!UICONTROL Orders]), the estimate uses [!UICONTROL Revenue per Visitor]. データタイプは通貨です。詳しくは、「[売上高情報の予測](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。

アクティビティに対して選択した成功指標は、そのアクティビティのレポートを表示するときに、レポート設定で利用できます。

Some metrics, such as [!UICONTROL Custom Scoring] and [!UICONTROL Revenue Per Visitor], require a customized implementation that passes in information such as order totals and order IDs.

## 詳細設定 {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

詳細設定を使用して、成功の測定方法を管理します。インプレッションごとや訪問者ごとに指標をカウントする、アクティビティにユーザーを保持するか、ユーザーの再入場を許可しないかを選択する、などのオプションがあります。

「 [!UICONTROL 詳細設定] 」オプションにアクセスするには、 **[!UICONTROL 垂直楕円]** / **[!UICONTROL 詳細設定をクリックします]**。

![詳細設定メニュー](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>[!DNL Adobe Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。The [!UICONTROL Advanced Settings] option will not be available. For more information, see [Adobe Analytics as the reporting source for Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md).

また、詳細設定を使用して、訪問者が別の指標を先に達成した場合に 1 つの指標のみを増分する、従属成功指標を作成できます。

![依存関係を追加](/help/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

例えば、テストコンバージョンが、訪問者がオファーをクリックした場合、または、コンバートする前に特定のページに到達する場合にのみ有効になることがあります。

従属成功指標は、A/B テスト、自動パーソナライゼーション、エクスペリエンスターゲット設定、多変量分析テストアクティビティでサポートされます。Recommendations アクティビティは、現在、従属成功指標をサポートしていません。

>[!NOTE]
>
>従属成功指標は次の場合にはコンバートされません。
>
>* 循環依存（指標 1 が指標 2 に依存し、指標 2 が指標 1 に依存する）を作成した場合、どちらの指標もコンバートできません。
>* 自動パーソナライゼーションアクティビティではユーザーが作業をおこなう必要はなく、コンバージョン指標に到達するとアクティビティが再開されます。そのため、そのコンバージョン指標に依存する指標はコンバートされません。


ユーザーが目標指標に到達した後の動作について指定するには、詳細設定を使用します。次の表に、使用可能なオプションを示します。

| ユーザーがこの目標指標に達した後 | オプション |
|--- |--- |
| [!UICONTROL カウントを増分、アクティビティでユーザーを保持] | カウントの増分方法を指定します。<ul><li>参加者ごとに 1 回（デフォルト）</li><li>すべてのインプレッション（ページの更新を除く）</li><li>すべてのインプレッション</li></ul> |
| [!UICONTROL カウントを増分、ユーザーをリリース、再入場を許可] | 訪問者がアクティビティに再度入ったときに表示されるエクスペリエンスを選択します。<ul><li>同じエクスペリエンス（デフォルト）</li><li>ランダムエクスペリエンス</li><li>未表示のエクスペリエンス</li></ul> |
| [!UICONTROL カウントを増分、ユーザーをリリース、再入場を許可しない] | アクティビティのコンテンツの代わりにユーザーに表示する内容を指定します。<ul><li>同じエクスペリエンス（トラッキングなし）（デフォルト）</li><li>デフォルト／他のアクティビティのコンテンツ</li></ul> |

>[!NOTE]
>
>「カウントを [!UICONTROL 増分] 」オプション（前述）のいずれかに指標を設定した場合、指標のカウントは、参加者ごとに、訪問者レベルでのみ正しく1回増加します。 指標のカウントは、訪問レベルで新しいセッションごとに訪問ごとに1回増加します。

## トレーニングビデオ： アクティビティ指標

このビデオでは、アクティビティの指標の使用方法を示します。

* 「目標」指標の理解
* コンバージョン、収益、エンゲージメントの指標の理解と構築
* クリック追跡指標の構築

>[!VIDEO](https://video.tv.adobe.com/v/17380)