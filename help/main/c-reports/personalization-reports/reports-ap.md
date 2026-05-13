---
keywords: ターゲティング；AP レポート；自動パーソナライゼーションレポート；アクティビティレベルレポート；オファーレベルレポート；オファー詳細レポート；faq
description: Adobe TargetでAutomated Personalization概要レポートを解釈する方法について説明します。 このレポートから自動セグメントと重要属性レポートに切り替えることができます。
title: Automated Personalization概要レポートの使用方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
TQID: https://experienceleague.adobe.com/Gj9Jo0NHnSxGE4BpvFbd0SudYjbkP4yrV3GFHWHNPjw
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 653
ht-degree: 16%

---

# Automated Personalization 概要レポート

専用サマリーレポートは、[!DNL Adobe Target]の[!UICONTROL Automated Personalization] アクティビティのユーザーが利用できます。

>[!NOTE]
>
>[!UICONTROL Automated Personalization]は[!DNL Target Premium] ソリューションの一部として利用できます。 [Target Premium ライセンス &#x200B;](/help/main/c-intro/intro.md#premium)を持たない[!DNL Target Standard]には含まれていません。

1. **[!UICONTROL Activities]**&#x200B;をクリックし、リストから目的の[!UICONTROL Automated Personalization] アクティビティをクリックしてから、**[!UICONTROL Reports]** タブをクリックします。

   アクティビティが多い場合は、フィルター（![&#x200B; フィルターアイコン &#x200B;](/help/main/assets/icons/Filter.svg)）アイコンをクリックして、[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]、および[!UICONTROL Activity Source] ドロップダウンリストからオプションを選択してリストをフィルタリングします。

1. （オプション） **[!UICONTROL Download]** （![&#x200B; ダウンロードアイコン &#x200B;](/help/main/assets/icons/Download.svg)）アイコンをクリックして、利用可能なすべての成功指標で分類された概要ビュー（コントロールとターゲットトラフィックの比較など）をダウンロードします。

[!UICONTROL Automated Personalization]は次のレポートを提供します：

* アクティビティレベル
* オファーレベル
* 自動セグメント
* 重要な属性

## アクティビティレベルレポート {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL Activity Level] レポートは、[!UICONTROL Automated Personalization] アルゴリズムを使用した集計パフォーマンスと、ランダムに提供されたコンテンツ （コントロール）を比較します。

上昇率、信頼性、トレンド、期間などを含む、A/B テストの結果を解釈する標準ルールは、依然として適用されます。 結果の解釈について詳しくは、[A/Bn テストでの統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)を参照してください。

## オファーレベルレポート {#section_CAA6409879E349C6906E2BE8156D87A1}

ランダム フォレスト エクスペリエンスの[!UICONTROL Offer Level] レポートは、アルゴリズムで適用された各オファーのパフォーマンスと、同じランダムに提供されたオファー（Control）を比較します。 そのため、このビューでオファーを相互に比較しないでください。

エクスペリエンスアルゴリズム （ランダムフォレストまたはコントロール）をクリックして、[!UICONTROL Offer Level] レポートを表示します。

>[!NOTE]
>
>時計のアイコンは、アルゴリズムモデルがまだ構築中であることを示しています。 チェックマークアイコンは、基本アルゴリズムが確立されたことを示します。

オファーは[&#x200B; レポートグループ &#x200B;](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)内に表示でき、これらのレポートグループは折りたたんで展開できます。 テーブルの&#x200B;**[!UICONTROL Control]**&#x200B;または&#x200B;**[!UICONTROL Targeted]**&#x200B;をクリックすると、オファーではなくレポートグループによってロールアップ情報が表示されます。

## 自動セグメント

[!UICONTROL Automated Segments] アイコンをクリックします。 このレポートは、AP/AT アクティビティのオファー/エクスペリエンスに対して、異なる訪問者がどのように反応するかを示します。 このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。

詳しくは、[自動セグメントレポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)を参照してください。

## 重要な属性

[!UICONTROL Important Attributes] アイコンをクリックします。 このレポートでは、異なるアクティビティにおいて、モデルがパーソナライズする方法において、異なる属性がどのように重要か（または重要でないか）を示しています。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。

詳しくは、[重要な属性レポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)を参照してください。

## よくある質問

### アクティビティレベルとオファーレベルのレポートでデータに違いがあるのはなぜですか？

**[!UICONTROL Activity Level]レポート**: [!UICONTROL Activity Level] レポートに記録された訪問回数は、コントロールエクスペリエンスへの訪問回数と「ターゲット設定」トラフィックの訪問回数をキャプチャします。 ターゲットトラフィックには、探索トラフィックとパーソナライズされたトラフィックの組み合わせが含まれます。

**オファーレベルレポート**: [!UICONTROL Offer Level] レポートに記録されたインプレッション数は、各オファーのインプレッション数を取得します。 したがって、複数の場所を持つアクティビティでは、すべてのレポートグループで[!UICONTROL Offer Level] レポートに記録された合計訪問数は、[!UICONTROL Activity Level] レポートのControlまたはターゲットトラフィックに記録された訪問数とアクティビティの合計訪問数の倍数に等しくなります。 デフォルトコンテンツが使用可能なオプションであった場所で発生したデフォルトコンテンツのインプレッションは、「デフォルトコンテンツ」オファーグループに記録されます。 レポートグループに割り当て解除されたオファーのインプレッションは、「グループ化されていない」オファーグループに記録されます。

>[!NOTE]
>
>[!UICONTROL Offer Level] レポートに記録されたインプレッション数は、[!UICONTROL Activity Level] レポートに記録された訪問数の正確な整数倍ではない可能性があります。 これは、インターネット経由のレポートデータトラフィックのキャプチャで発生する軽微な不一致が原因です（一般的な不一致の割合は5%未満）。 したがって、アクティビティがアクティブ化された後にアクティビティで利用可能な場所の数が変更された場合、インプレッションの数は正確な倍数にはなりません。
