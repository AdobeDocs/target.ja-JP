---
keywords: レポート；自動ターゲット；自動ターゲット；AT；レポート
description: Adobe Targetの自動ターゲティング概要レポートの解釈方法について説明します。 このレポートから自動セグメントと重要属性レポートに切り替えることができます。
title: 自動ターゲットサマリーレポートの使用方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
TQID: https://experienceleague.adobe.com/de9ST0undYRSL-BMmwEhvbU7PsfHgYieNAWY-qsQ-Z8
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 666
ht-degree: 38%

---

# [!UICONTROL 自動ターゲット概要レポート]

[!DNL Adobe Target]の[!UICONTROL 自動ターゲットサマリー] レポートの解釈方法に関する情報。

>[!NOTE]
>
>[!UICONTROL 自動ターゲット &#x200B;]は、[!DNL Target Premium] ソリューションの一部として利用できます。 [Target Premium ライセンス &#x200B;](/help/main/c-intro/intro.md#premium)を持たない[!DNL Target Standard]には含まれていません。

[!UICONTROL 自動ターゲットサマリー] レポートを表示するには：

1. [!UICONTROL &#x200B; アクティビティ &#x200B;] ページで、目的の[!UICONTROL 自動ターゲット &#x200B;] アクティビティをクリックします。

   アクティビティが多い場合は、フィルター（![&#x200B; フィルターアイコン &#x200B;](/help/main/assets/icons/Filter.svg)）アイコンをクリックして、[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL 指標タイプ &#x200B;]、[!UICONTROL Activity Source] ドロップダウンリストからオプションを選択して、リストをフィルタリングします。

1. 「**[!UICONTROL レポート]**」タブをクリックし、目的のアイコンをクリックします。

   * **[!UICONTROL テーブルビュー]** （![&#x200B; テーブルビューアイコン &#x200B;](/help/main/assets/icons/Table.svg)）
   * **[!UICONTROL グラフ表示]** （![&#x200B; グラフ表示アイコン &#x200B;](/help/main/assets/icons/GraphTrend.svg)）
   * **[!UICONTROL セグメントの自動化]** （![&#x200B; セグメントの自動化レポート &#x200B;](/help/main/assets/icons/AutomatedSegment.svg)）
   * [!UICONTROL 重要な属性]** （![重要な属性アイコン &#x200B;](/help/main/assets/icons/ViewList.svg)）

## テーブル表示

[!UICONTROL 自動ターゲット &#x200B;] レポートを解釈する際のヒントと考慮事項：

* テーブルの様々な行は、アクティビティのパフォーマンスを把握するのに役立ちます。

   * レポートページのテーブルの上位2行には、コントロールに割り当てられた訪問者（ランダムに提供されたエクスペリエンス）とパーソナライゼーションアルゴリズムに割り当てられた訪問者の間のA/B テストの結果が表示されます。 この情報を使用して、パーソナライゼーションアルゴリズムがランダムに提供されたコントロールと比較してどのように実行されたかを測定できます。
   * その他の行には、エクスペリエンス単位の結果が表示されます。 各エクスペリエンスで、ランダム提供のコントロールとしてそのエクスペリエンスが提供された訪問者の平均反応率と、パーソナライゼーションアルゴリズムを使用してエクスペリエンスが提供された訪問者の平均反応率を比較できます。

* レポートの各エクスペリエンスの横にある緑のチェックアイコンは、対象のエクスペリエンス用にパーソナライズされた機械学習モデルが作成されたことを意味します。 時計アイコンは、トラフィックの量が不十分でモデルがまだ作成されていないことを意味します。

   * モデルはエクスペリエンスごとに構築されるので、緑のチェックアイコンが表示されているエクスペリエンスと、時計アイコンが表示されているエクスペリエンスが混在する場合もあります。
   * このケースでは、アクティビティのすべてのエクスペリエンスのモデル構築を高速化するために、まだモデルが構築されていないエクスペリエンスに追加トラフィックを送るようになっています。
   * パーソナライゼーションを開始するには、構築されたモデル（緑のチェックマーク）で少なくとも2つのエクスペリエンスが必要です。

* エクスペリエンス Aとエクスペリエンス Bのコンバージョン率を比較することは、[!UICONTROL 自動ターゲット &#x200B;]では正しい比較ではありません。 この機能の要点は、エクスペリエンス A がインテリジェントな方法で提供された場合に、ランダムで提供された場合よりもパフォーマンスが高まるのかどうかということです。 マーケティング担当者は、個々のエクスペリエンスの上昇率を見るときに注意する必要があります。パーソナライゼーションアルゴリズムでは、個々のエクスペリエンス単位ではなく、アクティビティ全体での成功指標を重視して最適化をおこなうためです。
* 最も高い上昇率を示すエクスペリエンスは、母集団内で最も高い差別化要因を持つと考えることができます。 つまり、アルゴリズムにより、その特定の体験を最も気に入るセグメントが見つかりました。
* 表の様々な列には、訪問数、コンバージョン率、平均上昇率と信頼性レベル、および信頼性が表示されます。 詳しくは、[A/B テストでの統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)を参照してください。

## グラフ表示

2つのドロップダウンリストを使用して、目的の指標、カウント方法などを選択します。 詳細については、[&#x200B; レポート設定の概要](/help/main/c-reports/c-report-settings/report-settings.md)を参照してください。

## 自動セグメント

このレポートは、AP/AT アクティビティのオファー/エクスペリエンスに対して、異なる訪問者がどのように反応するかを示します。 このレポートでは、[!DNL Target]個のパーソナライゼーションモデルによって定義されたさまざまな自動セグメントが、アクティビティ内のオファー/エクスペリエンスに対してどのように応答したかを示します。

詳しくは、[自動セグメント レポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)を参照してください。

## 重要な属性

このレポートでは、異なるアクティビティにおいて、モデルがパーソナライズする方法において、異なる属性がどのように重要か（または重要でないか）を示しています。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。

詳しくは、[重要な属性レポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)を参照してください。
