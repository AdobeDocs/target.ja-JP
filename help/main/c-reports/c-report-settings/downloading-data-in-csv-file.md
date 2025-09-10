---
keywords: レポート、ダウンロードレポート、csv、success metrics、注文の詳細
description: Adobe アクティビティのデータを CVS フォーマットでダウンロードして  [!DNL Target] Excel、Access、またはその他のデータ分析プログラムに素早くインポートする方法を説明します。
title: レポートデータを CSV ファイルでダウンロードするにはどうすればよいですか？
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: 26b0c5455e82014dab92c925ecc88bddb3947d2f
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 34%

---

# CSV ファイル内のデータのダウンロード

データを.csv 形式でダウンロードして、[!DNL Excel]、[!DNL Access] またはその他のデータ分析プログラムに素早く読み込むことができます。

CSV ファイル内のデータをダウンロードするには：

1. をクリック **[!UICONTROL Activities]** し、リストから目的のアクティビティをクリックします。

   アクティビティが多数ある場合は、フィルター（![ フィルターアイコン ](/help/main/assets/icons/Filter.svg)）アイコンをクリックし、「[!UICONTROL Type]」、「[!UICONTROL Status]」、「[!UICONTROL Reporting Source]」、「[!UICONTROL Experience Composer]」、「[!UICONTROL Metrics Type]」、「[!UICONTROL Activity Source]」の各ドロップダウンリストからオプションを選択してリストをフィルタリングします。

1. 「**[!UICONTROL Reports]**」タブをクリックします。
1. **[!UICONTROL Download]** （ダウンロードアイコン ![ アイコンをクリックし ](/help/main/assets/icons/Download.svg) から、ダウンロードするレポートタイプを選択して、Excel や他のツールで分析します。

   * [!UICONTROL Export Reports to CSV]
   * [!UICONTROL Export Order Details to CSV]

## [!UICONTROL Export Report to CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

[!UICONTROL Success Metrics] レポートには、成功指標に関する情報と、[!DNL Target] UI では使用できない次の指標が表示されます。

* コンバージョンまでの平均時間数。平均的な訪問者がコンバージョンポイントに到達するまでにかかった時間を確認できます。
* 合計売上高（2 乗）。オフラインの統計的な信頼性の計算に使用します。

データは、アクティビティの最後まで保存されます。

>[!NOTE]
>
>CSV レポートには、生データのみが含まれ、訪問者あたりの売上高、上昇率、A/B テストに使用された信頼性などの計算指標は含まれていません。 これらの計算指標を計算するには、[!DNL Target] [Complete Confidence Calculator](/help/main/assets/complete_confidence_calculator.xlsx) Excel ファイルをダウンロードしてアクティビティの値を入力するか、[A/Bn テストでの統計計算 ](/help/main/c-reports/statistical-methodology/statistical-calculations.md) を確認します。

## [!UICONTROL Export Order Details to CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

[!UICONTROL Order Details] のレポートには、次のような注文に関する情報が表示されます。

* 注文日時
* 注文金額（発注 mbox を挿入した場合）

  [!UICONTROL Order Details] レポートは、注文がある場合にのみ機能します。

* 注文フラグ（重複注文または極端な注文）

  注文が平均注文額から+/- 3 標準偏差を超える場合、注文は極端としてフラグ付けされます。 この計算では、（計算が行われた時点までの）最後の月のデータが使用されます。 アクティビティが 1 時間実施された場合、または 15 件の注文を受けるまでのいずれか早い方のタイミングで、アクティビティの極端な注文が除外されます。詳しくは、「[極端な注文の除外](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)」を参照してください。

* 製品 ID

  製品 ID の長さの合計がコンマで連結されており、255 文字を超えないようにするか、ID がレポートに正しく表示されません。 例えば、注文に含める製品の ID が「aa, bb」である場合、長さの合計は「aa,bb」 = 5 になります。

* エクスペリエンス

  [!UICONTROL Order Details]、[!UICONTROL A/B Test] （XT）および [!UICONTROL Experience Targeting] （MVT）アクティビティの [!UICONTROL Multivariate Test] レポートの [!UICONTROL Experience] 列にはエクスペリエンス `localId` が含まれます。 これは、オファートークン `$campaign.recipe.id` からの出力値です。

  [!UICONTROL Experience] （AP）アクティビティについては、[!UICONTROL Automated Personalization] 列はありません。 [!UICONTROL Algorithm Name] の他の場所で示されているように、現在の [!DNL Target] 列は「コントロール」と「ターゲット」の用語に置き換えられています。

  [!UICONTROL Recommendations] のアクティビティへの影響はありませんでした。

>[!NOTE]
>
>* 注文レポートのデータには、デフォルト環境（ホストグループ）の 4 週間分のデータと、デフォルト以外のすべての環境の 2 週間分のデータが含まれます。
>* 「[!UICONTROL Increment count and keep the user in the activity]」に設定されている売上高指標では、同じ訪問者による最初の注文についてのみ注文の詳細が記録されます。 以降の注文については、コンバージョン数は加算されますが、RPV/AOV/販売額に売上高が加算されることはなく、[!UICONTROL Order Details] レポートにも含まれません。

## ベストプラクティス

* 注文レコードを記録するには、`orderTotal` パラメーターを渡す必要があります。
* `ProductPurchasedId` mbox パラメーターを介して渡された値は、[!UICONTROL Order Details] レポートにリストされます。
* ベストプラクティスは、`orderID` と `orderTotal` を含めることです。 両方を追加すると、重複する注文を自動的に無視することができます。

## 注意事項 {#section_49B9590904A645B18E694B4EFFFC1DEF}

次の情報は、[!UICONTROL Download] オプションに適用されます。

* [!UICONTROL A/B Test]、[!UICONTROL Automated Personalization]、[!UICONTROL Experience Targeting] および [!UICONTROL Multivariate] アクティビティの両方のレポートをダウンロードできます。 [!UICONTROL Success Metrics] のアクティビティの [!UICONTROL Recommendations] レポートはダウンロードできません。
* [!UICONTROL Download] オプションは、[!UICONTROL A/B Test] バージョン 15.7.1 （2015 年 7 月）より前に作成された [!UICONTROL Experience Targeting] および [!DNL Target] アクティビティでは使用できません。
* 関連データのないエクスペリエンスは、ダウンロードしたレポートに記録されません。
* [!DNL Target] レポート UI で適用されたオーディエンスは、ダウンロードレポートに引き継がれません。
* アクティビティユーザーが.複数の指標を使用している場合、csv ファイル形式でダウンロード用に生成されたレポートに一貫性がありません。ダウンロード可能なレポートは、レポート設定に基づいてのみ生成され、他の指標で使用される場合と同じ値を考慮します。 信頼できる唯一の情報源は常に [!DNL Target] UIに表示されるレポートです。
