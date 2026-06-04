---
keywords: インクルージョンルール;インクルージョン条件;レコメンデーション;プロモーション;動的;動的フィルター;静的;静的フィルター
description: Adobe  [!DNL Target] レコメンデーションのインクルージョンルールを使用して、1 つ以上の静的値を手動で入力し、フィルタリングする方法を説明します。
title: レコメンデーションのアクティビティで静的値を使用してフィルタリングする方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
TQID: https://experienceleague.adobe.com/-HTJO4YFi0-isyA-5LbVUaEPu7YX1WFgPy-OexMSXFY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 248
ht-degree: 75%

---

# [!UICONTROL 静的フィルター]

[!DNL Adobe Target Recommendations]の包含ルールを使用してフィルターを実行するには、1つ以上の静的値を手動で入力してください。

例えば、Motion Picture Association（MPA）のレーティングが「G」または「PG」のコンテンツのみをレコメンデーションできます。

インクルージョンルールは必要に応じて無制限に作成できます。 インクルージョンルールは AND 演算子で結合します。 品目がレコメンデーションに含まれるためには、すべてのルールを満たす必要があります。

>[!NOTE]
>
>Target 17.6.1 リリース（2017 年 6 月）以前におけるインクルージョンルールの設定方法に慣れている場合は、一部のオプションや演算子が変わっていることに気付くかもしれません。 選択したオプションに適用できる演算子のみが表示されるようになり、いくつかの演算子は、よりわかりやすく一貫性のある名前に変更されています（「一致」が「次に等しい」になるなど）。 このリリース以前に作成された既存の除外ルールは、新しい方式に自動的に移行されているので、 手動で再設定を行う必要はありません。

## G または PG レーティングのコンテンツのレコメンデーション

MPA評価が「G」または「PG」のみのコンテンツを推奨する静的な値を含む包含ルールを作成するには（「R」および「NC17」のコンテンツを除く）、次のフィルタールールを作成できます。「movie-rating equals any of g-rated」および「movie-rating equals any of pg-rated」。
