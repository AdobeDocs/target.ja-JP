---
keywords: レポート、ダウンロードレポート、csv、success metrics、注文の詳細
description: Adobe [!DNL Target]  アクティビティからCVS形式でデータをダウンロードして、Excel、Access、またはその他のデータ分析プログラムにすばやく読み込む方法について説明します。
title: CSV ファイルにレポートデータをダウンロードするにはどうすればよいですか？
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
TQID: https://experienceleague.adobe.com/-1FEosKnw-h8hRoK-VTO9VZsi5vIghnMnZp-fUUXo2U
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 653
ht-degree: 34%

---

# CSV ファイル内のデータのダウンロード

[!DNL Excel]、[!DNL Access]またはその他のデータ分析プログラムにすばやく読み込むために、.csv形式でデータをダウンロードします。

CSV ファイル内のデータをダウンロードするには：

1. をクリック **[!UICONTROL Activities]** し、リストから目的のアクティビティをクリックします。

   アクティビティが多い場合は、フィルター（![&#x200B; フィルターアイコン &#x200B;](/help/main/assets/icons/Filter.svg)）アイコンをクリックして、[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]、および[!UICONTROL Activity Source] ドロップダウンリストからオプションを選択してリストをフィルタリングします。

1. 「**[!UICONTROL Reports]**」タブをクリックします。
1. **[!UICONTROL Download]** （![&#x200B; ダウンロードアイコン &#x200B;](/help/main/assets/icons/Download.svg)）アイコンをクリックし、Excelやその他のツールで分析用にダウンロードするレポートタイプを選択します。

   * [!UICONTROL Export Reports to CSV]
   * [!UICONTROL Export Order Details to CSV]

## [!UICONTROL Export Report to CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

[!UICONTROL Success Metrics] レポートには、成功指標に関する情報と、[!DNL Target] UIで使用できない次の指標が表示されます。

* コンバージョンまでの平均時間数。平均的な訪問者がコンバージョンポイントに到達するまでにかかった時間を確認できます。
* 合計売上高（2 乗）。オフラインの統計的な信頼性の計算に使用します。

データは、アクティビティの最後まで保存されます。

>[!NOTE]
>
>CSV レポートには生データのみが含まれ、A/B テストに使用された、訪問者一人あたりの売上高、上昇率、信頼性などの計算指標は含まれていません。 これらの計算指標を計算するには、[!DNL Target] [信頼計算ツールを完了](/help/main/assets/complete_confidence_calculator.xlsx) Excel ファイルをダウンロードしてアクティビティの値を入力するか、A/Bn テストで[統計計算を確認します](/help/main/c-reports/statistical-methodology/statistical-calculations.md)。

## [!UICONTROL Export Order Details to CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

[!UICONTROL Order Details] レポートには、次のような注文に関する情報が表示されます。

* 注文日時
* 注文金額（発注 mbox を挿入した場合）

  [!UICONTROL Order Details] レポートは、注文がある場合にのみ機能します。

* 注文フラグ（重複注文または極端な注文）

  注文は、平均注文額から+/- 3標準偏差を超える場合、エクストリームフラグが付けられます。 この計算は、データの最後の月（計算が行われた時点まで）を使用します。 アクティビティが 1 時間実施された場合、または 15 件の注文を受けるまでのいずれか早い方のタイミングで、アクティビティの極端な注文が除外されます。 詳しくは、「[極端な注文の除外](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)」を参照してください。

* 製品 ID

  製品IDの合計長をコンマで連結した場合、255文字を超えないようにするか、IDがレポートに正しく表示されません。 例えば、注文に含める製品の ID が「aa, bb」である場合、長さの合計は「aa,bb」 = 5 になります。

* エクスペリエンス

  [!UICONTROL A/B Test]、[!UICONTROL Experience Targeting] （XT）および[!UICONTROL Multivariate Test] （MVT）アクティビティの[!UICONTROL Order Details] レポートでは、[!UICONTROL Experience]列にエクスペリエンス `localId`が含まれています。 これは、オファートークン `$campaign.recipe.id` からの出力値です。

  [!UICONTROL Automated Personalization] （AP） アクティビティの[!UICONTROL Experience]列がありません。 現在の[!UICONTROL Algorithm Name]列は、[!DNL Target]の他の場所で示されているように、「Control」と「Targeted」の用語に置き換えられました。

  [!UICONTROL Recommendations]件のアクティビティに影響はありませんでした。

>[!NOTE]
>
>* 注文レポートのデータには、デフォルト環境（ホストグループ）の 4 週間分のデータと、デフォルト以外のすべての環境の 2 週間分のデータが含まれます。
>* 「[!UICONTROL Increment count and keep the user in the activity]」に設定された収益指標は、同じ訪問者が最初に行った注文の詳細のみを記録します。 後続のすべての注文はコンバージョン数を増加させますが、RPV/AOV/Salesに収益を追加することはなく、[!UICONTROL Order Details] レポートには含まれません。

## ベストプラクティス

* 注文レコードを記録するには、`orderTotal` パラメーターを渡す必要があります。
* `ProductPurchasedId` mbox パラメーターで渡された値は、[!UICONTROL Order Details] レポートに一覧表示されます。
* ベストプラクティスは、`orderID`と`orderTotal`を含めることです。 両方を追加すると、重複する注文を自動的に無視することができます。

## 注意事項 {#section_49B9590904A645B18E694B4EFFFC1DEF}

次の情報は、[!UICONTROL Download] オプションに適用されます。

* [!UICONTROL A/B Test]、[!UICONTROL Automated Personalization]、[!UICONTROL Experience Targeting]および[!UICONTROL Multivariate]のアクティビティの両方のレポートをダウンロードできます。 [!UICONTROL Recommendations] アクティビティの[!UICONTROL Success Metrics] レポートをダウンロードできません。
* [!UICONTROL Download] オプションは、[!DNL Target] バージョン 15.7.1 （2015年7月）より前に作成された[!UICONTROL A/B Test]および[!UICONTROL Experience Targeting] アクティビティでは使用できません。
* 関連データのないエクスペリエンスは、ダウンロードしたレポートに記録されません。
* [!DNL Target] レポート UIで適用されたオーディエンスは、ダウンロードレポートに引き継ぎません。
* アクティビティユーザーが.複数の指標を使用している場合、csv ファイル形式でダウンロード用に生成されたレポートに一貫性がありません。 ダウンロード可能なレポートは、レポート設定のみに基づいて生成され、使用される他の指標と同じ値を考慮します。 信頼できる唯一の情報源は常に [!DNL Target] UIに表示されるレポートです。
