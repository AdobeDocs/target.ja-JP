---
keywords: インクルージョンルール；インクルージョン条件；レコメンデーション；プロモーション；動的フィルタリング；静的；静的フィルター
description: Adobe [!DNL Target] Recommendationsのインクルージョンルールを使用して、1つ以上の静的な値を手動で入力し、フィルタリングする方法を説明します。
title: Recommendationsアクティビティで静的値でフィルタリングする方法を教えてください。
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 46%

---

# ![](/help/assets/premium.png) 保険料フィルタ

[!DNL Adobe Target] [!DNL Recommendations]のインクルージョンルールを使用して、フィルターする1つ以上の静的値を手動で入力します。

例えば、「G」または「PG」のMotion Picture Association(MPA)の評価を持つコンテンツのみをレコメンデーションします。

インクルージョンルールは必要に応じて無制限に作成できます。インクルージョンルールは AND 演算子で結合します。品目がレコメンデーションに含まれるためには、すべてのルールを満たす必要があります。

>[!NOTE]
>
>Target 17.6.1 リリース（2017 年 6 月）以前におけるインクルージョンルールの設定方法に慣れている場合は、一部のオプションや演算子が変わっていることに気付くかもしれません。選択したオプションに適用できる演算子のみが表示されるようになり、いくつかの演算子は、よりわかりやすく一貫性のある名前に変更されています（「一致」が「次に等しい」になるなど）。このリリース以前に作成された既存の除外ルールは、新しい方式に自動的に移行されているので、手動で再設定をおこなう必要はありません。

## GまたはPGと評価されたコンテンツを推奨

MPAの定格が「G」または「PG」のみのコンテンツを推奨する静的値を持つインクルージョンルールを作成するには（「R」および「NC17」コンテンツを除く）、次に示すように、「movie-rating equals-rated」および「movie-rating equal pg-rated」フィルタを作成します。

![映画評価の例](/help/c-recommendations/c-algorithms/assets/movies.png)
