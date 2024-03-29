---
keywords: ターゲット設定、AP レポート、自動パーソナライゼーションレポート、アクティビティレベルレポート、オファーレベルレポート、オファー詳細レポート、faq
description: Adobe TargetでのAutomated Personalization Summary レポートの解釈方法を説明します。 このレポートから、自動セグメントレポートと重要な属性レポートに切り替えることができます。
title: Automated Personalization Summary レポートの使用方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 32%

---

# Automated Personalization 概要レポート

のユーザーは、特殊なサマリレポートを使用できます。 [!UICONTROL Automated Personalization] アクティビティ [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Automated Personalization] は、[!DNL Target Premium] ソリューションの一部として利用できます。次に含まれません： [!DNL Target Standard] 無しに [Target Premium ライセンス](/help/main/c-intro/intro.md#premium).

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

![アクティビティレベルレポート](/help/main/c-reports/assets/box_plot_ap.png)

上昇率、信頼性、トレンド、期間などを含む、A/B テストの結果を解釈する標準ルールは、依然として適用されます。結果の解釈について詳しくは、 [A/Bn テストでの統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## オファーレベルレポート {#section_CAA6409879E349C6906E2BE8156D87A1}

ランダムフォレストエクスペリエンスの[!UICONTROL オファーレベル]レポートは、各アルゴリズムが適用されたオファーのパフォーマンスをランダムに提供された同じオファー（コントロール）と比較します。そのため、このビューでオファーを相互に比較しないでください。

エクスペリエンスアルゴリズム（ランダムフォレストまたはコントロール）をクリックして、 [!UICONTROL オファーレベル] レポート。

![Adobe Targetのオファーレベルレポート](/help/main/c-reports/assets/ap_OfferLevelRpt.png)

>[!NOTE]
>
>時計アイコンは、アルゴリズムモデルが構築中であることを示します。 チェックマークアイコンは、ベースアルゴリズムが確立されたことを示します。

オファーは、 [レポートグループ](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)また、これらのレポートグループは、折りたたんだり展開したりできます。 クリック **[!UICONTROL 制御]** または **[!UICONTROL ターゲット]** を参照して、オファーではなく、レポートグループ別にロールアップ情報を表示します。

## 自動セグメント

次をクリック： [!UICONTROL 自動セグメント] アイコン このレポートは、AP/AT アクティビティでのオファーやエクスペリエンスに対する異なる訪問者の反応を示します。 このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。

![自動セグメントアイコン](/help/main/c-reports/assets/icon-automated-sements-ap.png)

詳しくは、 [自動セグメントレポート](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## 重要な属性

次をクリック： [!UICONTROL 重要な属性] アイコン このレポートは、異なるアクティビティにおいて、モデルによるパーソナライゼーションの決定にとって異なる属性が重要である（あるいはそれほど重要でない）方法を示します。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。

![重要な属性アイコン](/help/main/c-reports/assets/icon-important-attributes-ap.png)

詳しくは、 [重要な属性レポート](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## よくある質問

### アクティビティレベルレポートとオファーレベルレポートにデータの違いがあるのはなぜですか？

**[!UICONTROL アクティビティレベル] レポート**:次に記録された訪問： [!UICONTROL アクティビティレベル] レポートは、コントロールエクスペリエンスへの訪問数と「ターゲット」トラフィック。 ターゲットトラフィックには、調査用トラフィックとパーソナライズされたトラフィックの組み合わせが含まれます。

**オファーレベルレポート**:に記録されたインプレッション [!UICONTROL オファーレベル] レポートは、各オファーのインプレッション数を取り込みます。 したがって、複数の場所があるアクティビティでは、 [!UICONTROL オファーレベル] すべてのレポートグループのレポートは、 [!UICONTROL アクティビティレベル] レポートに、アクティビティ内の合計場所数が表示されます。 デフォルトコンテンツが利用可能なオプションであった場所で発生するデフォルトコンテンツのインプレッションは、「デフォルトコンテンツ」オファーグループに記録されます。 レポートグループに割り当てられていないオファーのインプレッションは、「グループ化解除」オファーグループに記録されます。

>[!NOTE]
>
>に記録されたインプレッション数 [!UICONTROL オファーレベル] レポートは、 [!UICONTROL アクティビティレベル] レポート。 これは、インターネットを介したレポートデータトラフィックの取得で生じる軽微な相違が原因です（一般的な相違率は 5%未満です）。 したがって、アクティビティがアクティブ化された後に、アクティビティで使用可能な場所の数が変更された場合、インプレッションの数は正確に複数にはなりません。
