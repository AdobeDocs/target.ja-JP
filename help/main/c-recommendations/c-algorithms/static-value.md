---
keywords: インクルージョンルール;インクルージョン条件;レコメンデーション;プロモーション;動的;動的フィルター;静的;静的フィルター
description: Adobe [!DNL Target]の推奨事項の包含ルールを使用して、1つ以上の静的値を手動で入力してフィルタリングする方法について説明します。
title: 静的フィルター
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
TQID: 'https://experienceleague.adobe.com/-HTJO4YFi0-isyA-5LbVUaEPu7YX1WFgPy-OexMSXFY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 22%
---
# 静的フィルター {#static-filter}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、[!DNL Adobe Target Recommendations]の包含ルールに1つ以上の静的値を手動で入力して、推奨事項をフィルタリングする方法について説明します。

>[!ENDSHADEBOX]

**[!UICONTROL 静的フィルター]**&#x200B;は、レコメンデーションの項目を、手動で入力された静的値に一致する項目に制限します。 任意の数のインクルージョンルールを作成できます。 包含ルールはAND演算子と結合されるため、レコメンデーションに含める項目に対してすべてのルールを満たす必要があります。 包含ルールに関する一般的な情報については、[動的および静的な包含ルールを使用する](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)を参照してください。

## G または PG レーティングのコンテンツのレコメンデーション

「G」または「PG」の評価がMPA （Motion Picture Association）のコンテンツのみを推奨するには、「R」および「NC17」のコンテンツを除く）、演算子「movie-rating equals any of」を使用して1つのフィルタリングルールを作成し、「g-rated」および「pg-rated」の値を入力します。
