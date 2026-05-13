---
keywords: レコメンデーション；レコメンデーションアクティビティ；基準；アルゴリズム；レコメンデーションキー；カスタムキー；業界縦組み；小売；e コマース；リードジェネレーション；b2b；金融サービス；メディア；公開
description: Adobe [!DNL Target] [!DNL Recommendations]で条件を使用する方法について説明します。
title: ' [!DNL Target] Recommendationsで条件を使用するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
TQID: https://experienceleague.adobe.com/Wo7I3piBQ7zwYF7kqRphDeWjcBCpyvIvTkwKK0t0f9U
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 506
ht-degree: 13%

---

# [!UICONTROL Criteria]

[!DNL Adobe Target] [!DNL Recommendations]の[!UICONTROL Criteria]は、事前に決められた訪問者の行動セットに基づいて、推奨する製品またはコンテンツを決定するルールです。 条件は、人気の傾向、訪問者の現在および過去の行動、類似の商品およびコンテンツに基づかせることができます。 複数の条件を追加することで、複数のレコメンデーションタイプを相互にテストすることができます。

次の節では、基準キーと、各キーに使用できるレコメンデーションロジックについて詳しく説明します。 詳細については、リンクをクリックしてください。

## 業種 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

基準を作成する際に、レコメンデーション活動の目標に基づいて業種を選択します。

| 業種 | 目標 |
|--- |--- |
| [!UICONTROL Retail/Ecommerce] | 購入をもたらすコンバージョン |
| [!UICONTROL Lead Generation/B2B/Financial Services] | 購入を伴わないコンバージョン |
| [!UICONTROL Media/Publishing] | エンゲージメント |

その他の基準オプションは、選択した業界の業種によって異なります。 **[!UICONTROL Administration]>[!UICONTROL Recommendations]** ページで既定の業種の垂直性を設定するか、各条件に業種の垂直性を指定できます。

## アルゴリズムのタイプ {#section_885B3BB1B43048A88A8926F6B76FC482}

選択したアルゴリズムタイプによって、使用可能なアルゴリズムが決まります。

次の表では、様々なアルゴリズムのタイプとそれに付随するアルゴリズムについて説明します。

| アルゴリズムタイプ | 使用するタイミング | 使用可能なアルゴリズム |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | ユーザーのカートの内容に基づいてレコメンデーションを行います。 | <ul><li>[!UICONTROL People Who Viewed These, Also Viewed]</li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul>詳しくは、*の「[ カートベース ](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based)」を参照してください。レコメンデーションキー*&#x200B;に基づいてレコメンデーションを行います。 |
| [!UICONTROL Popularity-Based] | サイト全体でのアイテムの人気度や、ユーザーが好むカテゴリーや最も閲覧されたカテゴリー、ブランド、ジャンルなどの中でのアイテムの人気度にもとづいて、レコメンデーションを行うことができます。 | <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
| [!UICONTROL Item-Based] | 利用者が現在閲覧している項目や最近閲覧した項目と類似する項目を見つけることで、レコメンデーションを行うことができます。 | <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
| [!UICONTROL User-Based] | 利用者の行動にもとづいてレコメンデーションする： | <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
| [!UICONTROL Custom Criteria] | アップロードしたカスタムファイルにもとづいて、レコメンデーションを作成できます。 | <ul><li>カスタムアルゴリズム</li></ul> |

各アルゴリズムについて詳しくは、[ レコメンデーションキーに基づいてレコメンデーションを作成する](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)を参照してください。

## カスタムレコメンデーションキーの使用 {#custom-key}

また、カスタムプロファイル属性の値に基づいてレコメンデーションを行うこともできます。

>[!NOTE]
>
>カスタムプロファイルパラメーターは、JavaScript、API、または統合機能を使用して[!DNL Target]に渡すことができます。 カスタムプロファイル属性について詳しくは、[訪問者プロファイル ](/help/main/c-target/c-visitor-profile/visitor-profile.md)を参照してください。

例えば、ユーザーが最後にキューに追加したムービーに基づいて、推奨ムービーを表示するとします。

1. **[!UICONTROL Recommendations]**／**[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL Create Criteria]**／**[!UICONTROL Create Criteria]**&#x200B;をクリックします。

1. [基本情報セクション ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)に情報を入力します。

1. [推奨アルゴリズム ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo) セクションで、**[!UICONTROL Algorithm Type]** リストから&#x200B;**[!UICONTROL Item Based]**&#x200B;を選択します。

1. **[!UICONTROL Algorithm]** リストから&#x200B;**[!UICONTROL People Who Viewed This, Viewed That]**&#x200B;を選択します。

1. **[!UICONTROL Recommendation Key]** リストからカスタムプロファイル属性を選択します（例：[!UICONTROL Last Show Added to Watchlist]）。

## 条件情報の表示 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

[!UICONTROL Name]列の目的の条件をクリックすると、条件の詳細を表示できます。

「**[!UICONTROL Attributes]**」と「詳細」セクションでは、[!UICONTROL Name]、[!UICONTROL Description]、[!UICONTROL Industry Vertical]、[!UICONTROL Page Types]、[!UICONTROL Recommendation Key]、[!UICONTROL Recommendation Logic]、[!UICONTROL Algorithm ID]、最終変更情報（アルゴリズムを変更した日付およびユーザー）など、選択した条件に関する一般的な情報を表示できます。

**[!UICONTROL Usage]** セクションでは、選択した条件を参照するアクティビティのリストを表示できます。

>[!NOTE]
>
>[!UICONTROL Algorithm Usage]機能は現在、[!DNL Recommendations] アクティビティでのみサポートされています。 この機能は、現在、[のレコメンデーションをオファー](/help/main/c-recommendations/recommendations-as-an-offer.md)として含む[!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target]および[!UICONTROL Experience Targeting] （XT）アクティビティではサポートされていません。
