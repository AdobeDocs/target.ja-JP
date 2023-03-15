---
keywords: レポート；自動ターゲット；自動ターゲット；AT；レポート
description: Adobe Targetでの自動ターゲットの概要レポートの解釈方法を説明します。 このレポートから、自動セグメントレポートと重要な属性レポートに切り替えることができます。
title: 自動ターゲット概要レポートの使用方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 52%

---

# 自動ターゲット概要レポート

の解釈方法に関する情報 [!UICONTROL 自動ターゲットの概要] レポート [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL 自動ターゲット] は、この [!DNL Target Premium] ソリューションの一部として使用できます。次に含まれません： [!DNL Target Standard] 無しに [Target Premium ライセンス](/help/main/c-intro/intro.md#premium).

次の手順で [!UICONTROL 自動ターゲットの概要] レポート：

1. 次の [!UICONTROL アクティビティ] ページで、目的の [!UICONTROL 自動ターゲット] アクティビティ。

   多数のアクティビティがある場合、 [!UICONTROL タイプ], [!UICONTROL ステータス], [!UICONTROL プロパティ], [!UICONTROL レポートソース], [!UICONTROL Experience Composer], [!UICONTROL 指標タイプ]、および [!UICONTROL アクティビティソース] 」ドロップダウンリストを使用します。

1. 次をクリック： [!UICONTROL レポート] 」タブをクリックし、目的のアイコンをクリックします。

   * テーブル表示
   * グラフ表示
   * 自動セグメント
   * 重要な属性

## テーブル表示

次の図に、典型的なサマリレポートがどのように表示されるかを示します [!UICONTROL テーブル表示] 表示時 [!UICONTROL 自動ターゲット] アクティビティのレポート：

![自動ターゲットのテーブル表示レポート](/help/main/c-reports/assets/at-table-view.png)

お客様が [!UICONTROL 自動ターゲット] レポート：

* テーブルの様々な行は、アクティビティのパフォーマンスを理解するのに役立ちます。

   * レポートページ上の表の最初の 2 行には、コントロール（ランダムに提供されるエクスペリエンス）に配分された訪問者と、パーソナライゼーションアルゴリズムに配分された訪問者を比較する A/B テストの結果が表示されます。このデータを見れば、ランダムに提供されるコントロールと比較して、パーソナライゼーションアルゴリズムがどの程度のパフォーマンスを発揮しているかを把握できます。
   * その他の行には、エクスペリエンス単位の結果が表示されます。各エクスペリエンスで、ランダム提供のコントロールとしてそのエクスペリエンスが提供された訪問者の平均反応率と、パーソナライゼーションアルゴリズムを使用してエクスペリエンスが提供された訪問者の平均反応率を比較できます。

* レポートの各エクスペリエンスの横にある緑のチェックアイコンは、対象のエクスペリエンス用にパーソナライズされた機械学習モデルが作成されたことを意味します。時計アイコンは、トラフィックの量が不十分でモデルがまだ作成されていないことを意味します。

   * モデルはエクスペリエンスごとに構築されるので、緑のチェックアイコンが表示されているエクスペリエンスと、時計アイコンが表示されているエクスペリエンスが混在する場合もあります。
   * このケースでは、アクティビティのすべてのエクスペリエンスのモデル構築を高速化するために、まだモデルが構築されていないエクスペリエンスに追加トラフィックを送るようになっています。
   * パーソナライゼーションを開始するためには、モデルが構築されたエクスペリエンス（緑のチェックマーク）が少なくとも 2 つ必要です。

* エクスペリエンス A とエクスペリエンス B のコンバージョン率の比較は、 [!UICONTROL 自動ターゲット]. この機能の要点は、エクスペリエンス A がインテリジェントな方法で提供された場合に、ランダムで提供された場合よりもパフォーマンスが高まるのかどうかということです。マーケティング担当者は、個々のエクスペリエンスの上昇率を見るときに注意する必要があります。パーソナライゼーションアルゴリズムでは、個々のエクスペリエンス単位ではなく、アクティビティ全体での成功指標を重視して最適化をおこなうためです。
* 最も高い上昇率を示すエクスペリエンスは、母集団内で最も高い差別化要因を持つと考えることができます。これは、特定のエクスペリエンスを最も好むセグメントをアルゴリズムが見つけたということです。
* 表の様々な列に、訪問数、コンバージョン率、平均上昇率および信頼水準、信頼性が表示されます。 詳しくは、 [A/B テストの統計指標](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## グラフ表示

次の図に、典型的なサマリレポートがどのように表示されるかを示します [!UICONTROL グラフ表示] 表示時 [!UICONTROL 自動ターゲット] アクティビティのレポート：

![自動ターゲットのグラフ表示レポート](/help/main/c-reports/assets/at-graph-view.png)

以下に示すように、2 つのドロップダウンリストを使用して、目的の指標、カウント手法などを選択できます。 詳しくは、 [レポート設定の概要](/help/main/c-reports/c-report-settings/report-settings.md) 詳しくは、以下を参照してください。

![自動ターゲットのグラフ表示レポート](/help/main/c-reports/assets/at-graph-view-2.png)

## 自動セグメント

次をクリック： [!UICONTROL 自動セグメント] アイコン このレポートは、AP/AT アクティビティでのオファーやエクスペリエンスに対する異なる訪問者の反応を示します。 このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。

![自動セグメントアイコン](/help/main/c-reports/assets/icon-automated-sements.png)

詳しくは、 [自動セグメントレポート](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## 重要な属性

次をクリック： [!UICONTROL 重要な属性] アイコン このレポートは、異なるアクティビティにおいて、モデルによるパーソナライゼーションの決定にとって異なる属性が重要である（あるいはそれほど重要でない）方法を示します。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。

![重要な属性アイコン](/help/main/c-reports/assets/icon-important-attributes.png)

詳しくは、 [重要な属性レポート](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).
