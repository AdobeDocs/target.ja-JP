---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Adobe TargetRecommendationsのインクルージョンルールを使用して、フィルターする1つ以上の静的値を手動で入力します。
title: Adobe TargetRecommendationsのインクルージョンルールで静的値でフィルター
feature: criteria
translation-type: tm+mt
source-git-commit: f8311dbc91b74977a11dc9b97a70465ab4493b93
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 48%

---


# ![PREMIUM](/help/assets/premium.png) Static Filter

のインクルージョンルールを使用してフィルタリングする1つ以上の静的値を手動で入力 [!DNL Adobe Target] し [!DNL Recommendations]ます。

例えば、「G」または「PG」のMotion Picture Association(MPA)の評価を持つコンテンツのみをレコメンデーションします。

インクルージョンルールは必要に応じて無制限に作成できます。インクルージョンルールは AND 演算子で結合します。品目がレコメンデーションに含まれるためには、すべてのルールを満たす必要があります。

>[!NOTE]
>
>Target 17.6.1 リリース（2017 年 6 月）以前におけるインクルージョンルールの設定方法に慣れている場合は、一部のオプションや演算子が変わっていることに気付くかもしれません。選択したオプションに適用できる演算子のみが表示されるようになり、いくつかの演算子は、よりわかりやすく一貫性のある名前に変更されています（「一致」が「次に等しい」になるなど）。このリリース以前に作成された既存の除外ルールは、新しい方式に自動的に移行されているので、手動で再設定をおこなう必要はありません。

## GまたはPGと評価されたコンテンツを推奨

MPAの定格が「G」または「PG」のみのコンテンツを推奨する静的値を持つインクルージョンルールを作成するには（「R」および「NC17」コンテンツを除く）、次に示すように、「movie-rating equals-rated」および「movie-rating equal pg-rated」フィルタを作成します。

![映画評価の例](/help/c-recommendations/c-algorithms/assets/movies.png)

