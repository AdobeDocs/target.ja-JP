---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Adobe TargetRecommendationsのインクルージョンルールを使用して、フィルターする1つ以上の静的値を手動で入力します。
title: Adobe TargetRecommendationsのインクルージョンルールで静的値でフィルター
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 75%

---


# ![PREMIUM](/help/assets/premium.png) Static Filter

Adobe TargetRecommendationsのインクルージョンルールを使用して、フィルターする1つ以上の静的値を手動で入力します。

例えば、MPAA レーティングが「G」または「PG」のコンテンツのみをレコメンデーションできます。

使用可能な演算子：

* equals
* 次と等しくない
* 次を含む
* 次を含まない
* 次の語句で始まる
* 次の語句で終わる
* 値が存在する
* 値が存在しない
* 次よりも大きいか等しい
* 次よりも小さいか等しい

>[!NOTE]
>
>Target 17.6.1 リリース（2017 年 6 月）以前におけるインクルージョンルールの設定方法に慣れている場合は、一部のオプションや演算子が変わっていることに気付くかもしれません。選択したオプションに適用できる演算子のみが表示されるようになり、いくつかの演算子は、よりわかりやすく一貫性のある名前に変更されています（「一致」が「次に等しい」になるなど）。このリリース以前に作成された既存の除外ルールは、新しい方式に自動的に移行されているので、手動で再設定をおこなう必要はありません。

インクルージョンルールは必要に応じて無制限に作成できます。インクルージョンルールは AND 演算子で結合します。品目がレコメンデーションに含まれるためには、すべてのルールを満たす必要があります。