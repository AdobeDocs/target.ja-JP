---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Adobe TargetRecommendationsのインクルージョンルールを使用して、フィルターする1つ以上の静的値を手動で入力します。
title: Adobe TargetRecommendationsのインクルージョンルールで静的値でフィルター
feature: criteria
translation-type: tm+mt
source-git-commit: 60b71c426b61bb16a23976da9a03926f8e73cf6c
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 49%

---


# ![PREMIUM](/help/assets/premium.png) Static Filter

のインクルージョンルールを使用してフィルタリングする1つ以上の静的値を手動で入力 [!DNL Adobe Target] し [!DNL Recommendations]ます。

例えば、「G」または「PG」のMotion Picture Association(MPA)の評価を持つコンテンツのみをレコメンデーションします。

>[!NOTE]
>
>Target 17.6.1 リリース（2017 年 6 月）以前におけるインクルージョンルールの設定方法に慣れている場合は、一部のオプションや演算子が変わっていることに気付くかもしれません。選択したオプションに適用できる演算子のみが表示されるようになり、いくつかの演算子は、よりわかりやすく一貫性のある名前に変更されています（「一致」が「次に等しい」になるなど）。このリリース以前に作成された既存の除外ルールは、新しい方式に自動的に移行されているので、手動で再設定をおこなう必要はありません。

## GまたはPGと評価されたコンテンツを推奨

静的値を持つインクルージョンルールを作成し、MPAの定格が「G」または「PG」のみのコンテンツをレコメンデーションする場合（「R」および「NC17」コンテンツを除外する場合）は、次の2つのフィルタリングルールを作成できます。以下に示すように、「movie-rating equals g-rated」と「movie-rating equal pg-rated」。

![映画評価の例](/help/c-recommendations/c-algorithms/assets/movies.png)

インクルージョンルールは必要に応じて無制限に作成できます。インクルージョンルールは AND 演算子で結合します。品目がレコメンデーションに含まれるためには、すべてのルールを満たす必要があります。