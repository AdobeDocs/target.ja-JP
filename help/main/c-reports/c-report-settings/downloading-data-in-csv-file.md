---
keywords: レポート、ダウンロードレポート、csv、success metrics、注文の詳細
description: Adobeからデータをダウンロードする方法 [!DNL Target] アクティビティを CVS 形式で使用して、Excel、Access、またはその他のデータ分析プログラムにすばやくインポートできます。
title: レポートデータを CSV ファイルでダウンロードする方法を教えてください。
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: fc1dcc2b6de1248c35191c1ecd7b36aeb891fd3f
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 54%

---

# CSV ファイル内のデータのダウンロード

.csv 形式のデータをダウンロードして、Excel、Access またはその他のデータ分析プログラムにすばやくインポートできます。

CSV ファイル内のデータをダウンロードするには：

1. 「**[!UICONTROL アクティビティ]**」をクリックし、リストから目的のアクティビティをクリックします。

   多数のアクティビティが表示される場合は、[!UICONTROL 種類]、[!UICONTROL ステータス]、[!UICONTROL レポートソース]、[!UICONTROL Experience Composer]、[!UICONTROL 指標のタイプ]、[!UICONTROL アクティビティソース]のドロップダウンリストからオプションを選択して、リストにフィルターを適用できます。

1. 「**[!UICONTROL レポート]**」タブをクリックします。
1. **[!UICONTROL ダウンロード]**&#x200B;アイコンをクリックして、Excel や他のツールでの分析用にダウンロードするレポートのタイプを選択します。

   * [!UICONTROL レポートを CSV に書き出す]
   * [!UICONTROL 注文の詳細を CSV に書き出す]

   ![ダウンロードオプション](/help/main/c-reports/assets/download-options.png)

## [!UICONTROL レポートを CSV に書き出す] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

この [!UICONTROL 成功指標] レポートには、成功指標および [!DNL Target] UI:

* コンバージョンまでの平均時間数。平均的な訪問者がコンバージョンポイントに到達するまでにかかった時間を確認できます。
* 合計売上高（2 乗）。オフラインの統計的な信頼性の計算に使用します。

データは、アクティビティの最後まで保存されます。

>[!NOTE]
>
>CSV レポートには、生データのみが含まれ、A/B テストで使用される訪問者あたりの売上高、上昇率、信頼性などの計算指標は含まれません。 これらの計算指標を計算するには、 [!DNL Target] [Complete Confidence Calculator](/help/main/assets/complete_confidence_calculator.xlsx) アクティビティの値を入力または確認する Excel ファイル [A/Bn テストの統計指標](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## [!UICONTROL 注文の詳細を CSV に書き出す] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

この [!UICONTROL 注文の詳細] レポートには、次の情報を含む注文に関する情報が表示されます。

* 注文日時
* 注文金額（発注 mbox を挿入した場合）

   この [!UICONTROL 注文の詳細] レポートは、注文がある場合にのみ機能します。

* 注文フラグ（重複注文または極端な注文）

   標準偏差が平均注文額から+/- 3 以上離れている場合、注文は極端としてフラグ付けされます。 この計算では、最後の月のデータが使用されます（計算がおこなわれた時点まで）。 アクティビティが 1 時間実施された場合、または 15 件の注文を受けるまでのいずれか早い方のタイミングで、アクティビティの極端な注文が除外されます。詳しくは、「[極端な注文の除外](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)」を参照してください。

* 製品 ID

   製品 ID をコンマで連結した場合、合計の長さは 255 文字を超えないでください。そうしないと、ID がレポートに正しく表示されません。 例えば、注文に含める製品の ID が「aa, bb」である場合、長さの合計は「aa,bb」 = 5 になります。

* エクスペリエンス

   [!UICONTROL A/B テスト]、[!UICONTROL エクスペリエンスターゲット設定]（XT）、[!UICONTROL 多変量分析テスト]（MVT）の各アクティビティの[!UICONTROL 注文の詳細]レポートでは、[!UICONTROL エクスペリエンス]列にエクスペリエンス `localId` が含まれています。これは、オファートークン `$campaign.recipe.id` からの出力値です。

   [!UICONTROL 自動パーソナライゼーション]（AP）アクティビティについては、[!UICONTROL エクスペリエンス]列はありません。[!UICONTROL  の別の場所で見られるように、現在の]アルゴリズム名[!DNL Target]列は、「コントロール」と「ターゲット」の用語に置き換えられています。

   [!UICONTROL Recommendations] アクティビティに対する影響はありませんでした。

>[!NOTE]
>
>* 注文レポートのデータには、デフォルト環境（ホストグループ）の 4 週間分のデータと、デフォルト以外のすべての環境の 2 週間分のデータが含まれます。
>* 売上高指標が「[!UICONTROL カウントを増分、アクティビティでユーザーを保持]」同じ訪問者が最初に行った注文の詳細のみをログに記録します。 それ以降のすべての注文は、コンバージョン数を増加しますが、RPV/AOV/Sales に売上高を追加しないので、 [!UICONTROL 注文の詳細] レポート。


## ベストプラクティス

* 注文レコードを記録するには、 `orderTotal` パラメーターを渡す必要があります。
* `ProductPurchasedId` mbox パラメーター経由で渡された値は、注文の詳細レポートに表示されます。
* ベストプラクティスは、 `orderID` および `orderTotal`. 両方を追加すると、重複する注文を自動的に無視することができます。

## 注意事項 {#section_49B9590904A645B18E694B4EFFFC1DEF}

次の情報は、 [!UICONTROL ダウンロード] オプション：

* 両方のレポートを [!UICONTROL A/B テスト], [!UICONTROL Automated Personalization], [!UICONTROL エクスペリエンスのターゲット設定]、および [!UICONTROL 多変量分析] アクティビティ。 をダウンロードできません [!UICONTROL 成功指標] 報告する [!UICONTROL Recommendations] アクティビティ。
* この [!UICONTROL ダウンロード] オプションは次の場合に使用できません： [!UICONTROL A/B テスト] および [!UICONTROL エクスペリエンスのターゲット設定] 以前に作成されたアクティビティ [!DNL Target] バージョン 15.7.1（2015 年 7 月）
* 関連データのないエクスペリエンスは、ダウンロードしたレポートに記録されません。
* オーディエンスを適用 [!DNL Target] レポート UI は、ダウンロードレポートに引き継がれません。
* アクティビティユーザーが.複数の指標を使用している場合、csv ファイル形式でダウンロード用に生成されたレポートに一貫性がありません。ダウンロード可能なレポートは、レポート設定に基づいてのみ生成され、他の指標で使用される場合と同じ値を考慮します。信頼できる唯一の情報源は常に [!DNL Target] UIに表示されるレポートです。
