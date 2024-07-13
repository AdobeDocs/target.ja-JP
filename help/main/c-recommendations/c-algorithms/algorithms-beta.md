---
keywords: recommendations;recommendations アクティビティ；条件；アルゴリズム；レコメンデーションキー；カスタムキー；industry vertical；小売；eccommerce；リード生成；b2b；金融サービス；メディア；公開
description: Adobe [!DNL Target] [!DNL Recommendations] で条件を使用する方法を説明します。
title: ' [!DNL Target] Recommendationsでの条件の使用方法？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 9c6ff35269a81aa0c2ea331985c6f5ddd5c8ccb3
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 8%

---

# [!UICONTROL Criteria]

[!DNL Adobe Target] [!DNL Recommendations] の [!UICONTROL Criteria] は、事前に定義された訪問者の行動に基づいて、どの製品やコンテンツをレコメンデーションするかを決定するルールです。 条件は、人気のあるトレンド、訪問者の現在および過去の行動、類似の製品およびコンテンツに基づくことができます。 複数の条件を追加することで、複数のレコメンデーションタイプを相互にテストすることができます。

次の節では、条件キーと、各キーに使用できるレコメンデーションロジックの詳細について説明します。 詳しくは、リンクをクリックしてください。

## 業種 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

条件を作成する際は、Recommendations アクティビティの目標に基づいて、業界の業種を選択します。

| 業種 | 目標 |
|--- |--- |
| [!UICONTROL Retail/Ecommerce] | 購入をもたらすコンバージョン |
| [!UICONTROL Lead Generation/B2B/Financial Services] | 購入を伴わないコンバージョン |
| [!UICONTROL Media/Publishing] | エンゲージメント |

その他の条件オプションは、選択した業種に応じて変わります。 デフォルトの業種は、**[!UICONTROL Administration]>[!UICONTROL Recommendations]** ページで設定することも、各条件に対して業種を指定することもできます。

## アルゴリズムのタイプ {#section_885B3BB1B43048A88A8926F6B76FC482}

選択するアルゴリズムタイプによって、使用可能なアルゴリズムが決まります。

![ 条件ページ ](assets/criteria-page-new.png)

次の表に、様々なアルゴリズムタイプとそれに付随するアルゴリズムを説明します。

| アルゴリズムタイプ | 使用するタイミング | 使用可能なアルゴリズム |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | ユーザーの買い物かごの中身に基づいてお勧めを紹介します。 | <ul><li>[!UICONTROL People Who Viewed These, Also Viewed]</li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul>詳しくは、[ レコメンデーションキーに基づくレコメンデーションのベース *の ](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) 買い物かごベース* を参照してください。 |
| [!UICONTROL Popularity-Based] | サイト全体でのアイテムの全体的な人気度に基づいて、またはユーザーのお気に入りのカテゴリや最も多く閲覧されたカテゴリ、ブランド、ジャンルなどのアイテムの人気度に基づいて、レコメンデーションを作成します。 | <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
| [!UICONTROL Item-Based] | ユーザーが現在表示している項目または最近表示した項目に類似した項目を見つけることに基づいてお勧めを紹介します。 | <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
| [!UICONTROL User-Based] | ユーザーの行動に基づいてお勧めを紹介します。 | <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
| [!UICONTROL Custom Criteria] | アップロードしたカスタムファイルに基づいてお勧めを紹介します。 | <ul><li>カスタムアルゴリズム</li></ul> |

各アルゴリズムについて詳しくは、[ レコメンデーションキーに基づくレコメンデーションのベース ](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) を参照してください。

## カスタムレコメンデーションキーの使用 {#custom-key}

また、カスタムプロファイル属性の値に基づいてレコメンデーションを行うこともできます。

>[!NOTE]
>
>カスタムプロファイルパラメーターは、JavaScript、API または統合を通じて [!DNL Target] に渡すことができます。 カスタムプロファイル属性について詳しくは、[ 訪問者プロファイル ](/help/main/c-target/c-visitor-profile/visitor-profile.md) を参照してください。

例えば、ユーザーが最後にキューに追加したムービーに基づいて、お勧めのムービーを表示するとします。

1. **[!UICONTROL Recommendations]**／**[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL Create Criteria]**／**[!UICONTROL Create Criteria]**&#x200B;をクリックします。

1. [ 基本情報 ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) の情報を入力します。

1. 「[ 推奨されるアルゴリズム ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo)」セクションで、リストから **[!UICONTROL Item Based]** を選 **[!UICONTROL Algorithm Type]** します。

1. リストから **[!UICONTROL People Who Viewed This, Viewed That]** を選 **[!UICONTROL Algorithm]** します。

1. **[!UICONTROL Recommendation Key]** リストからカスタムプロファイル属性（例：[!UICONTROL Last Show Added to Watchlist]）を選択します。

## 条件情報の表示 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

[!UICONTROL Name] 列で目的の条件をクリックすると、条件の詳細を表示できます。

![条件カードにマウスポインターを置く](/help/main/c-recommendations/c-algorithms/assets/criteria-hover.png)

「**[!UICONTROL Algorithm Info]**」タブでは、[!UICONTROL Name]、[!UICONTROL Description]、[!UICONTROL Industry Vertical]、[!UICONTROL Page Types]、[!UICONTROL Recommendation Key]、[!UICONTROL Recommendation Logic]、[!UICONTROL Algorithm ID]、最終変更日（アルゴリズムを変更した日付とユーザー）など、選択した基準に関する一般的な情報を表示できます。

「**[!UICONTROL Algorithm Usage]**」セクションでは、選択した条件を参照するアクティビティのリストを表示できます。

>[!NOTE]
>
>[!UICONTROL Algorithm Usage] 機能は現在、[!DNL Recommendations] アクティビティでのみサポートされています。 この機能は、現在、（オファーとしてのレコメンデーション [ を含む [!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target] および [!UICONTROL Experience Targeting] （XT）アクティビティではサポートされてい ](/help/main/c-recommendations/recommendations-as-an-offer.md) せん。