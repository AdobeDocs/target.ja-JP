---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Adobe TargetRecommendationsのインクルージョンルールを使用して、フィルターする1つ以上の静的値を手動で入力します。
title: Adobe TargetRecommendationsのインクルージョンルールで静的値でフィルター
feature: criteria
translation-type: tm+mt
source-git-commit: c814215476ef6e40f4f175fe3f9dbb2c26b966eb
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 73%

---


# ![PREMIUM](/help/assets/premium.png) Static Filter

のインクルージョンルールを使用してフィルタリングする1つ以上の静的値を手動で入力 [!DNL Adobe Target] し [!DNL Recommendations]ます。

例えば、MPAA レーティングが「G」または「PG」のコンテンツのみをレコメンデーションできます。

>[!NOTE]
>
>Target 17.6.1 リリース（2017 年 6 月）以前におけるインクルージョンルールの設定方法に慣れている場合は、一部のオプションや演算子が変わっていることに気付くかもしれません。選択したオプションに適用できる演算子のみが表示されるようになり、いくつかの演算子は、よりわかりやすく一貫性のある名前に変更されています（「一致」が「次に等しい」になるなど）。このリリース以前に作成された既存の除外ルールは、新しい方式に自動的に移行されているので、手動で再設定をおこなう必要はありません。

インクルージョンルールは必要に応じて無制限に作成できます。インクルージョンルールは AND 演算子で結合します。品目がレコメンデーションに含まれるためには、すべてのルールを満たす必要があります。