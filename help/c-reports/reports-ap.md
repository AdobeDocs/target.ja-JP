---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: Automated Personalizationサマリレポートの使用方法
title: Automated Personalization 概要レポート
feature: Reports
translation-type: tm+mt
source-git-commit: a34c6830b0e30017ae54ef1bf47407d390935d29
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 42%

---


# ![Premium](/help/assets/premium.png) Automated Personalization 概要レポート

[!DNL Adobe Target]の[!UICONTROL Automated Personalization]アクティビティのユーザーは、特殊なレポートを利用できます。

>[!NOTE]
>
>[!UICONTROL Automated Personalization] は、[!DNL Target Premium] ソリューションの一部として利用できます。[ターゲットプレミアムライセンス](/help/c-intro/intro.md#premium)がない場合、[!DNL Target Standard]には含まれません。

1. 「**[!UICONTROL アクティビティ]**」をクリックし、リストで目的の [!UICONTROL Automated Personalization] アクティビティをクリックし、「**[!UICONTROL レポート」タブをクリックします。]**

   多くのアクティビティがある場合、[!UICONTROL タイプ]ドロップダウンリストから [!UICONTROL Automated Personalization] を選択することで、リストをフィルターできます。

1. （オプション）**[!UICONTROL ダウンロード]**&#x200B;アイコンをクリックし、概要ビュー（例えば、コントロールとターゲットのトラフィックの比較）を利用可能なすべての成功指標による分類としてダウンロードします。

[!UICONTROL Automated Personalization] では次のレポートを利用できます。

* アクティビティレベル
* オファーレベル
* 自動セグメント
* 重要な属性

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

## よくある質問

### アクティビティレベルレポートとオファーレベルレポートの間にデータの違いはありますか。

**[!UICONTROL アクティビティ] レベルレポート**: [!UICONTROL アクティビティレベルの] レポートで記録される訪問は、コントロールのエクスペリエンスへの訪問回数と「ターゲット」トラフィック。ターゲットトラフィックには、調査用のトラフィックとパーソナライズされたトラフィックの組み合わせが含まれます。

**オファーレベルレポート**:  オファーレベルレポートで記録されたインプレッションは、各オファーのインプレッション数をキャプチャします。したがって、複数の場所を持つアクティビティでは、すべてのレポートグループで[!UICONTROL オファーレベル]レポートに記録される訪問の合計数は、[!UICONTROL アクティビティレベル]レポートのコントロールまたはターゲットトラフィックの記録数の倍になります。 デフォルトコンテンツが使用可能な場所で発生したデフォルトコンテンツのインプレッションは、「デフォルトコンテンツ」オファーグループに記録されます。 レポートグループに割り当てられていないオファーのインプレッションは、「グループ解除」オファーグループに記録されます。

>[!NOTE]

[!UICONTROL オファーレベル]レポートに記録されたインプレッション数は、[!UICONTROL アクティビティレベル]レポートに記録された訪問数の正確な倍数ではない可能性があります。 これは、インターネット上でのレポートデータトラフィックの取り込みに発生する小さな相違が原因です（一般的な相違率は5%未満）。 したがって、アクティビティがアクティブ化された後にアクティビティで使用可能な場所の数が変更された場合、インプレッションの数は正確な倍数になりません。
