---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: Adobe TargetのAutomated Personalizationアクティビティのユーザーは、専門レポートを利用できます。
title: Automated Personalization 概要レポート
feature: reports
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 70%

---


# ![Premium](/help/assets/premium.png) Automated Personalization 概要レポート{#automated-personalization-summary-reports}

[!DNL Adobe Target]の[!UICONTROL Automated Personalization]アクティビティのユーザーは、特殊なレポートを利用できます。

>[!NOTE]
>
>[!UICONTROL Automated Personalization] は、[!DNL Target Premium] ソリューションの一部として利用できます。[ターゲットプレミアムライセンス](/help/c-intro/intro.md#premium)がない場合、[!DNL Target Standard]には含まれません。

1. 「**[!UICONTROL アクティビティ]**」をクリックし、リストで目的の [!UICONTROL Automated Personalization] アクティビティをクリックし、「**[!UICONTROL レポート」タブをクリックします。]**

   多くのアクティビティがある場合、[!UICONTROL タイプ]ドロップダウンリストから [!UICONTROL Automated Personalization] を選択することで、リストをフィルターできます。

1. （オプション）[!UICONTROL ダウンロード]アイコンをクリックし、概要ビュー（例えば、コントロールとターゲットのトラフィックの比較）を利用可能なすべての成功指標による分類としてダウンロードします。

[!UICONTROL Automated Personalization] では次のレポートを利用できます。

## アクティビティレベルレポート {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL アクティビティレベル]レポートは、[!UICONTROL Automated Personalization] アルゴリズムを使用した場合と、コンテンツがランダムに提供された場合（コントロール）の集計パフォーマンスを比較します。

![アクティビティレベルレポート](/help/c-reports/assets/box_plot_ap.png)

上昇率、信頼性、トレンド、期間などを含む、A/B テストの結果を解釈する標準ルールは、依然として適用されます。結果の解釈について詳しくは、[コンバージョン率について](/help/c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844)を参照してください。

## オファーレベルレポート {#section_CAA6409879E349C6906E2BE8156D87A1}

ランダムフォレストエクスペリエンスの[!UICONTROL オファーレベル]レポートは、各アルゴリズムが適用されたオファーのパフォーマンスをランダムに提供された同じオファー（コントロール）と比較します。そのため、このビューでオファーを相互に比較しないでください。

エクスペリエンスアルゴリズム（ランダムフォレストまたはコントロール）をクリックして、[!UICONTROL オファーレベル]レポートを表示します。

![](assets/ap_OfferLevelRpt.png)

オファーは、レポートグループ内に表示できます。これらのレポートグループは、折りたたみと展開が可能です。ドロップダウンリストの「[!UICONTROL レポートグループ]」を選択して、オファー別ではなく、レポートグループ別にロールアップ情報を表示します。

>[!NOTE]
>
>時計アイコンは、アルゴリズムモデルが構築中であることを示します。チェックマークアイコンは、ベースアルゴリズムが確立されたことを示します。

## 自動セグメント

[!UICONTROL 自動セグメント]アイコンをクリックします。 このレポートは、AP/ATアクティビティのオファー/エクスペリエンスに対する訪問者の反応が異なる様子を示します。 このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。

![自動セグメントアイコン](/help/c-reports/assets/icon-automated-sements-ap.png)

詳しくは、[自動セグメントレポート](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)を参照してください。

## 重要な属性

[!UICONTROL 重要な属性]アイコンをクリックします。 このレポートは、異なるアクティビティで、モデルがどのようにパーソナライズを決定するかに関して、異なる属性がどの程度重要か（あるいはそれほど重要か）を示します。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。

![重要な属性アイコン](/help/c-reports/assets/icon-important-attributes-ap.png)

詳しくは、[重要な属性レポート](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)を参照してください。