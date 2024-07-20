---
keywords: レポート；自動ターゲット；自動ターゲット；AT；レポート
description: Adobe Targetで自動ターゲット概要レポートを解釈する方法について説明します。 このレポートから自動セグメント レポートと重要な属性レポートに切り替えることができます。
title: 自動ターゲット概要レポートの使用方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 54%

---

# 自動ターゲット概要レポート

[!DNL Adobe Target] の [!UICONTROL Auto-Target Summary] レポートの解釈方法に関する情報です。

>[!NOTE]
>
>[!UICONTROL Auto-Target] は、[!DNL Target Premium] ソリューションの一部として利用できます。 [Target Premium ライセンス ](/help/main/c-intro/intro.md#premium) のない [!DNL Target Standard] には含まれていません。

[!UICONTROL Auto-Target Summary] のレポートを表示するには：

1. [!UICONTROL Activities] ページで、目的の [!UICONTROL Auto-Target] アクティビティをクリックします。

   アクティビティが多数ある場合は、[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Property]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type] および [!UICONTROL Activity Source] の各ドロップダウンリストからオプションを選択してリストをフィルタリングできます。

1. 「[!UICONTROL Reports]」タブをクリックしてから、目的のアイコンをクリックします。

   * テーブル表示
   * グラフ表示
   * 自動セグメント
   * 重要な属性

## テーブル表示

[!UICONTROL Auto-Target] アクティビティのレポートを表示した [!UICONTROL Table View] 合の一般的な概要レポートを次の図に示します。

![ 自動ターゲットテーブルビューレポート ](/help/main/c-reports/assets/at-table-view.png)

[!UICONTROL Auto-Target] レポートを解釈する際のヒントと考慮事項を次に示します。

* 表の様々な行は、アクティビティのパフォーマンスを理解するのに役立ちます。

   * レポートページ上の表の最初の 2 行には、コントロール（ランダムに提供されるエクスペリエンス）に配分された訪問者と、パーソナライゼーションアルゴリズムに配分された訪問者を比較する A/B テストの結果が表示されます。このデータを見れば、ランダムに提供されるコントロールと比較して、パーソナライゼーションアルゴリズムがどの程度のパフォーマンスを発揮しているかを把握できます。
   * その他の行には、エクスペリエンス単位の結果が表示されます。各エクスペリエンスで、ランダム提供のコントロールとしてそのエクスペリエンスが提供された訪問者の平均反応率と、パーソナライゼーションアルゴリズムを使用してエクスペリエンスが提供された訪問者の平均反応率を比較できます。

* レポートの各エクスペリエンスの横にある緑のチェックアイコンは、対象のエクスペリエンス用にパーソナライズされた機械学習モデルが作成されたことを意味します。時計アイコンは、トラフィックの量が不十分でモデルがまだ作成されていないことを意味します。

   * モデルはエクスペリエンスごとに構築されるので、緑のチェックアイコンが表示されているエクスペリエンスと、時計アイコンが表示されているエクスペリエンスが混在する場合もあります。
   * このケースでは、アクティビティのすべてのエクスペリエンスのモデル構築を高速化するために、まだモデルが構築されていないエクスペリエンスに追加トラフィックを送るようになっています。
   * パーソナライゼーションを開始するためには、モデルが構築されたエクスペリエンス（緑のチェックマーク）が少なくとも 2 つ必要です。

* エクスペリエンス A とエクスペリエンス B のコンバージョン率の比較は、[!UICONTROL Auto-Target] では適切な比較ではありません。 この機能の要点は、エクスペリエンス A がインテリジェントな方法で提供された場合に、ランダムで提供された場合よりもパフォーマンスが高まるのかどうかということです。マーケティング担当者は、個々のエクスペリエンスの上昇率を見るときに注意する必要があります。パーソナライゼーションアルゴリズムでは、個々のエクスペリエンス単位ではなく、アクティビティ全体での成功指標を重視して最適化をおこなうためです。
* 最も高い上昇率を示すエクスペリエンスは、母集団内で最も高い差別化要因を持つと考えることができます。これは、特定のエクスペリエンスを最も好むセグメントをアルゴリズムが見つけたということです。
* 表の様々な列には、訪問数、コンバージョン率、平均上昇率と信頼水準、信頼性が示されています。 詳しくは、[A/B テストでの統計計算 ](/help/main/c-reports/statistical-methodology/statistical-calculations.md) を参照してください。

## グラフ表示

[!UICONTROL Auto-Target] アクティビティのレポートを表示した [!UICONTROL Graph View] 合の一般的な概要レポートを次の図に示します。

![ 自動ターゲットグラフ表示レポート ](/help/main/c-reports/assets/at-graph-view.png)

次に示すように、2 つのドロップダウンリストを使用して、目的の指標、カウント方法などを選択できます。 詳しくは、[ レポート設定の概要 ](/help/main/c-reports/c-report-settings/report-settings.md) を参照してください。

![ 自動ターゲットグラフ表示レポート ](/help/main/c-reports/assets/at-graph-view-2.png)

## 自動セグメント

[!UICONTROL Automated Segments] アイコンをクリックします。 このレポートは、AP/AT アクティビティのオファー/エクスペリエンスに対する様々な訪問者の反応を示します。 このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。

![ 自動セグメントアイコン ](/help/main/c-reports/assets/icon-automated-sements.png)

詳しくは、[ 自動セグメントレポート ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) を参照してください。

## 重要な属性

[!UICONTROL Important Attributes] アイコンをクリックします。 このレポートでは、モデルがどのようにパーソナライズを決定するかについて、様々なアクティビティで様々な属性がより多く（または少なく）重要である様子を示します。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。

![ 重要な属性アイコン ](/help/main/c-reports/assets/icon-important-attributes.png)

詳しくは、[ 重要な属性レポート ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) を参照してください。
