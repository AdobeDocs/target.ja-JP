---
keywords: recommendations;recommendations アクティビティ；条件；アルゴリズム；レコメンデーションキー；カスタムキー；industry vertical；小売；eccommerce；リード生成；b2b；金融サービス；メディア；公開
description: Adobe [!DNL Target] [!DNL Recommendations] で条件を使用する方法を説明します。
title: In [!DNL Target] Recommendations で条件を使用する方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 17%

---

# 条件

[!DNL Adobe Target] [!DNL Recommendations] の条件は、事前に定義された訪問者の行動に基づいて、どの製品やコンテンツをレコメンデーションするかを決定するルールです。 条件は、人気のあるトレンド、訪問者の現在および過去の行動、類似の製品およびコンテンツに基づくことができます。 複数の条件を追加することで、複数のレコメンデーションタイプを相互にテストすることができます。

次の節では、条件キーと、各キーに使用できるレコメンデーションロジックの詳細について説明します。 詳しくは、リンクをクリックしてください。

## 業種 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

条件を作成する際は、Recommendations アクティビティの目標に基づいて、業界の業種を選択します。

| 業種 | 目標 |
|--- |--- |
| 小売／e コマース | 購入をもたらすコンバージョン |
| リードジェネレーション／B2B／金融サービス | 購入を伴わないコンバージョン |
| メディア／投稿 | エンゲージメント |

その他の条件オプションは、選択した業種に応じて変わります。 **[!UICONTROL Recommendations > Settings]** のページで既定の業種を設定することも、各条件に対して業種を指定することもできます。

## アルゴリズムのタイプ {#section_885B3BB1B43048A88A8926F6B76FC482}

選択するアルゴリズムタイプによって、使用可能なアルゴリズムが決まります。 いくつかのアルゴリズムタイプがあり、[!DNL Recommendations] アクティビティを設定すると、条件カードとして表されます。

![&#x200B; 条件ページ &#x200B;](assets/criteria-page.png)

次の表に、様々なアルゴリズムタイプとそれに付随するアルゴリズムを説明します。

| アルゴリズムタイプ | 使用するタイミング | 使用可能なアルゴリズム |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | ユーザーの買い物かごの中身に基づいてお勧めを紹介します。 | <ul><li>これらを閲覧した人は、これらを閲覧しました</li><li>これらを閲覧した人が購入しました</li><li>これらを購入した人が、それらを購入しました</li></ul>詳しくは、[&#x200B; レコメンデーションキーに基づくレコメンデーションのベース &#x200B;](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) の *買い物かごベース* を参照してください。 |
| [!UICONTROL Popularity-Based] | サイト全体でのアイテムの全体的な人気度に基づいて、またはユーザーのお気に入りのカテゴリや最も多く閲覧されたカテゴリ、ブランド、ジャンルなどのアイテムの人気度に基づいて、レコメンデーションを作成します。 | <ul><li>サイト全体で最も多く閲覧された</li><li>カテゴリ別で最も多く閲覧された</li><li>品目属性別で最も多く閲覧された</li><li>サイト全体のトップセラー</li><li>カテゴリ別トップセラー</li><li>品目属性別の上位セラー</li><li>Analytics 指標で上位に表示</li></ul> |
| [!UICONTROL Item-Based] | ユーザーが現在表示している項目または最近表示した項目に類似した項目を見つけることに基づいてお勧めを紹介します。 | <ul><li>これを閲覧した人が他に閲覧したもの</li><li>これを閲覧した人が購入したもの</li><li>これを購入した人が他に購入したもの</li><li>類似の属性を持つ項目</li></ul> |
| [!UICONTROL User-Based] | ユーザーの行動に基づいてお勧めを紹介します。 | <ul><li>最近表示された項目</li><li>あなたにお勧め</li></ul> |
| [!UICONTROL Custom Criteria] | アップロードしたカスタムファイルに基づいてお勧めを紹介します。 | <ul><li>カスタムアルゴリズム</li></ul> |

各アルゴリズムについて詳しくは、[&#x200B; レコメンデーションキーに基づくレコメンデーションのベース &#x200B;](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) を参照してください。

## カスタムレコメンデーションキーの使用 {#custom-key}

また、カスタムプロファイル属性の値に基づいてレコメンデーションを行うこともできます。

>[!NOTE]
>
>カスタムプロファイルパラメーターは、JavaScript、API または統合を通じて [!DNL Target] に渡すことができます。 カスタムプロファイル属性について詳しくは、[&#x200B; 訪問者プロファイル &#x200B;](/help/main/c-target/c-visitor-profile/visitor-profile.md) を参照してください。

例えば、ユーザーが最後にキューに追加したムービーに基づいて、お勧めのムービーを表示するとします。

1. **[!UICONTROL Recommendations]**／**[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL Create Criteria]**／**[!UICONTROL Create Criteria]**&#x200B;をクリックします。

1. [&#x200B; 基本情報 &#x200B;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) の情報を入力します。

1. 「[&#x200B; 推奨されるアルゴリズム &#x200B;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo)」セクションで、リストから **[!UICONTROL Item Based]** を選 **[!UICONTROL Algorithm Type]** します。

1. リストから **[!UICONTROL People Who Viewed This, Viewed That]** を選 **[!UICONTROL Algorithm]** します。

1. **[!UICONTROL Recommendation Key]** リストからカスタムプロファイル属性（例：[!UICONTROL Last Show Added to Watchlist]）を選択します。

   ![&#x200B; 新しい条件を作成ダイアログボックス &#x200B;](assets/custom-key1.png)

## 条件情報の表示 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

ポップアップカードにマウスポインターを置いてから、条件カードの情報アイコンをクリックすると、条件を開くことなくポップアップカードの条件の詳細を表示できます。

![条件カードにマウスポインターを置く](/help/main/c-recommendations/c-algorithms/assets/criteria_hover.png)

「**[!UICONTROL Algorithm Info]**」タブをクリックすると、名前、説明、業種、ページタイプ、レコメンデーションキー、レコメンデーションロジック、アルゴリズム ID など、選択した基準に関する一般的な情報が表示されます。

![「アルゴリズム情報」タブ](/help/main/c-recommendations/c-algorithms/assets/criteria_info.png)

「**[!UICONTROL Algorithm Usage]**」タブをクリックして、選択した条件を参照するアクティビティのリストを表示します。 カードには、アクティブ、非アクティブ、ドラフトの各アクティビティが一覧表示されます。 「ライブアクティビティ/非アクティブなアクティビティ/ドラフトアクティビティ」ドロップダウンリストをクリックして、その条件を参照するアクティビティのリスト全体を表示します。 アクティビティリンクをクリックすると、編集するアクティビティを開くことができます。

![&#x200B; アルゴリズム使用状況タブ &#x200B;](/help/main/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>[!UICONTROL Algorithm Usage] 機能は、現在、Recommendations アクティビティでのみサポートされています。 この機能は現在、[&#x200B; オファーとしてのレコメンデーション &#x200B;](/help/main/c-recommendations/recommendations-as-an-offer.md) を含む A/B テスト、自動配分、自動ターゲット、エクスペリエンスのターゲット設定（XT）アクティビティではサポートされていません。
