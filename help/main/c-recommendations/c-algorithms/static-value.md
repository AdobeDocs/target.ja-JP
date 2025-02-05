---
keywords: インクルージョンルール;インクルージョン条件;レコメンデーション;プロモーション;動的;動的フィルター;静的;静的フィルター
description: Adobe  [!DNL Target]  Recommendations のインクルージョンルールを使用して、1 つ以上の静的値を手動で入力し、フィルタリングする方法を説明します。
title: Recommendations のアクティビティで静的値を使用してフィルタリングする方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 76%

---

# [!UICONTROL Static Filter]

[!DNL Adobe Target Recommendations] のインクルージョンルールを使用して、1 つ以上の静的値を手動で入力し、フィルタリングします。

例えば、Motion Picture Association（MPA）のレーティングが「G」または「PG」のコンテンツのみをレコメンデーションできます。

インクルージョンルールは必要に応じて無制限に作成できます。インクルージョンルールは AND 演算子で結合します。品目がレコメンデーションに含まれるためには、すべてのルールを満たす必要があります。

>[!NOTE]
>
>Target 17.6.1 リリース（2017 年 6 月）以前におけるインクルージョンルールの設定方法に慣れている場合は、一部のオプションや演算子が変わっていることに気付くかもしれません。選択したオプションに適用できる演算子のみが表示されるようになり、いくつかの演算子は、よりわかりやすく一貫性のある名前に変更されています（「一致」が「次に等しい」になるなど）。このリリース以前に作成された既存の除外ルールは、新しい方式に自動的に移行されているので、手動で再設定を行う必要はありません。

## G または PG レーティングのコンテンツのレコメンデーション

MPA のレーティングが「G」または「PG」のみのコンテンツ（「R」および「NC17」のコンテンツを除外）をレコメンデーションするために、静的な値を含むインクルージョンルールを作成するには、「映画のレーティングが g レートのいずれかと等しい」および「映画のレーティングが pg レートのいずれかと等しい」というフィルタリングルールを作成します。
