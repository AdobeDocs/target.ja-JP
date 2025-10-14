---
keywords: レポート；自動ターゲット；自動ターゲット；AT；レポート
description: Adobe Targetで自動ターゲット概要レポートを解釈する方法について説明します。 このレポートから自動セグメント レポートと重要な属性レポートに切り替えることができます。
title: 自動ターゲット概要レポートの使用方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 39%

---

# [!UICONTROL Auto-Target Summary report]

[!UICONTROL Auto-Target Summary] の [!DNL Adobe Target] レポートの解釈方法に関する情報です。

>[!NOTE]
>
>[!UICONTROL Auto-Target] は、[!DNL Target Premium] ソリューションの一部として利用できます。 [!DNL Target Standard]Target Premium ライセンス [&#x200B; のない &#x200B;](/help/main/c-intro/intro.md#premium) には含まれていません。

[!UICONTROL Auto-Target Summary] のレポートを表示するには：

1. [!UICONTROL Activities] ページで、目的の [!UICONTROL Auto-Target] アクティビティをクリックします。

   アクティビティが多数ある場合は、フィルター（![&#x200B; フィルターアイコン &#x200B;](/help/main/assets/icons/Filter.svg)）アイコンをクリックし、「[!UICONTROL Type]」、「[!UICONTROL Status]」、「[!UICONTROL Reporting Source]」、「[!UICONTROL Experience Composer]」、「[!UICONTROL Metrics Type]」、「[!UICONTROL Activity Source]」の各ドロップダウンリストからオプションを選択してリストをフィルタリングします。

1. 「**[!UICONTROL Reports]**」タブをクリックしてから、目的のアイコンをクリックします。

   * **[!UICONTROL Table View]** （![&#x200B; テーブル表示アイコン &#x200B;](/help/main/assets/icons/Table.svg)）
   * **[!UICONTROL Graph View]** （![&#x200B; グラフ表示アイコン &#x200B;](/help/main/assets/icons/GraphTrend.svg)）
   * **[!UICONTROL Automated Segments]** （![&#x200B; 自動セグメントレポート &#x200B;](/help/main/assets/icons/AutomatedSegment.svg)）
   * [!UICONTROL Important Attributes]** （![&#x200B; 重要な属性アイコン &#x200B;](/help/main/assets/icons/ViewList.svg)）

## テーブル表示

[!UICONTROL Auto-Target] レポートを解釈する際のヒントと考慮事項を次に示します。

* 表の様々な行は、アクティビティのパフォーマンスを理解するのに役立ちます。

   * レポートページ上の表の上位 2 行には、コントロールに割り当てられた訪問者（ランダムに提供されたエクスペリエンス）とパーソナライゼーションアルゴリズムに割り当てられた訪問者の間の A/B テスト結果が表示されます。 この情報を使用すると、ランダムに提供されるコントロールと比較して、パーソナライゼーションアルゴリズムの実行方法を測定できます。
   * その他の行には、エクスペリエンス単位の結果が表示されます。各エクスペリエンスで、ランダム提供のコントロールとしてそのエクスペリエンスが提供された訪問者の平均反応率と、パーソナライゼーションアルゴリズムを使用してエクスペリエンスが提供された訪問者の平均反応率を比較できます。

* レポートの各エクスペリエンスの横にある緑のチェックアイコンは、対象のエクスペリエンス用にパーソナライズされた機械学習モデルが作成されたことを意味します。時計アイコンは、トラフィックの量が不十分でモデルがまだ作成されていないことを意味します。

   * モデルはエクスペリエンスごとに構築されるので、緑のチェックアイコンが表示されているエクスペリエンスと、時計アイコンが表示されているエクスペリエンスが混在する場合もあります。
   * このケースでは、アクティビティのすべてのエクスペリエンスのモデル構築を高速化するために、まだモデルが構築されていないエクスペリエンスに追加トラフィックを送るようになっています。
   * パーソナライゼーションを開始するには、構築されたモデル（緑色のチェックマーク）を持つエクスペリエンスが少なくとも 2 つ必要です。

* エクスペリエンス A とエクスペリエンス B のコンバージョン率の比較は、[!UICONTROL Auto-Target] では適切な比較ではありません。 この機能の要点は、エクスペリエンス A がインテリジェントな方法で提供された場合に、ランダムで提供された場合よりもパフォーマンスが高まるのかどうかということです。マーケティング担当者は、個々のエクスペリエンスの上昇率を見るときに注意する必要があります。パーソナライゼーションアルゴリズムでは、個々のエクスペリエンス単位ではなく、アクティビティ全体での成功指標を重視して最適化をおこなうためです。
* 最も高い上昇率を示すエクスペリエンスは、母集団内で最も高い差別化要因を持つと考えることができます。つまり、アルゴリズムは、その特定のエクスペリエンスが最も好きなセグメントを見つけました。
* 表の様々な列には、訪問数、コンバージョン率、平均上昇率と信頼水準、信頼性が示されています。 詳しくは、[A/B テストでの統計計算 &#x200B;](/help/main/c-reports/statistical-methodology/statistical-calculations.md) を参照してください。

## グラフ表示

2 つのドロップダウンリストを使用して、目的の指標、カウント方法などを選択します。 詳しくは、[&#x200B; レポート設定の概要 &#x200B;](/help/main/c-reports/c-report-settings/report-settings.md) を参照してください。

## 自動セグメント

このレポートは、AP/AT アクティビティのオファー/エクスペリエンスに対する様々な訪問者の反応を示します。 このレポートでは、[!DNL Target] パーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー/エクスペリエンスにどのように応答したかを示します。

詳しくは、[&#x200B; 自動セグメントレポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) を参照してください。

## 重要な属性

このレポートでは、モデルがどのようにパーソナライズを決定するかについて、様々なアクティビティで様々な属性がより多く（または少なく）重要である様子を示します。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。

詳しくは、[&#x200B; 重要な属性レポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) を参照してください。
