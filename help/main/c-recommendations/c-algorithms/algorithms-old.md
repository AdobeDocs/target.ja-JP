---
keywords: レコメンデーション；レコメンデーションアクティビティ；基準；アルゴリズム；レコメンデーションキー；カスタムキー；業界縦組み；小売；e コマース；リードジェネレーション；b2b；金融サービス；メディア；公開
description: Adobe [!DNL Target] [!DNL Recommendations]で条件を使用する方法について説明します。
title: ' [!DNL Target] Recommendationsで条件を使用するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 25%

---

# 条件

[!DNL Adobe Target] [!DNL Recommendations]の条件は、事前に決められた訪問者の行動セットに基づいて、推奨する製品またはコンテンツを決定するルールです。 条件は、人気の傾向、訪問者の現在および過去の行動、類似の商品およびコンテンツに基づかせることができます。 複数の条件を追加することで、複数のレコメンデーションタイプを相互にテストすることができます。

次の節では、基準キーと各キーに使用できるレコメンデーションロジックについて詳しく説明します。 詳細については、リンクをクリックしてください。

## 業種 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

基準を作成する際に、レコメンデーション活動の目標に基づいて業種を選択します。

| 業種 | 目標 |
|--- |--- |
| 小売／e コマース | 購入をもたらすコンバージョン |
| リードジェネレーション／B2B／金融サービス | 購入を伴わないコンバージョン |
| メディア／投稿 | エンゲージメント |

その他の基準オプションは、選択した業界の業種によって異なります。 **[!UICONTROL 推奨事項/設定]** ページでデフォルトの業種を設定するか、各条件に業種の業種を指定できます。

## アルゴリズムのタイプ {#section_885B3BB1B43048A88A8926F6B76FC482}

選択したアルゴリズムタイプによって、使用可能なアルゴリズムが決まります。 いくつかのアルゴリズムタイプがあり、[!DNL Recommendations] アクティビティの設定時に基準カードとして表されます。

![条件ページ &#x200B;](assets/criteria-page.png)

次の表では、様々なアルゴリズムのタイプとそれに付随するアルゴリズムについて説明します。

| アルゴリズムタイプ | 使用するタイミング | 使用可能なアルゴリズム |
| --- | --- | --- |
| [!UICONTROL &#x200B; カートベース &#x200B;] | ユーザーのカートの内容に基づいてレコメンデーションを行います。 | <ul><li>これらを見た人、見た人</li><li>これらを見た人、購入した人</li><li>これらを買った人は、それを買った</li></ul>詳しくは、*の「[&#x200B; カートベース &#x200B;](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based)」を参照してください。レコメンデーションキー*&#x200B;に基づいてレコメンデーションを行います。 |
| [!UICONTROL 人気度ベース &#x200B;] | サイト全体でのアイテムの人気度や、ユーザーが好むカテゴリーや最も閲覧されたカテゴリー、ブランド、ジャンルなどの中でのアイテムの人気度にもとづいて、レコメンデーションを行うことができます。 | <ul><li>サイト全体で最も閲覧されたページ</li><li>カテゴリー別閲覧者数</li><li>項目属性で最も閲覧された項目</li><li>サイト全体でトップ売り手</li><li>カテゴリー別のトップセラー</li><li>項目属性によるトップセラー</li><li>分析指標で上位</li></ul> |
| [!UICONTROL &#x200B; アイテムベース &#x200B;] | 利用者が現在閲覧している項目や最近閲覧した項目と類似する項目を見つけることで、レコメンデーションを行うことができます。 | <ul><li>これを閲覧した人が他に閲覧したもの</li><li>これを閲覧した人が購入したもの</li><li>これを購入した人が他に購入したもの</li><li>類似の属性を持つ項目</li></ul> |
| [!UICONTROL &#x200B; ユーザーベース &#x200B;] | 利用者の行動にもとづいてレコメンデーションする： | <ul><li>最近表示された項目</li><li>あなたにおすすめ</li></ul> |
| [!UICONTROL &#x200B; カスタム条件] | アップロードしたカスタムファイルにもとづいて、レコメンデーションを作成できます。 | <ul><li>カスタムアルゴリズム</li></ul> |

各アルゴリズムについて詳しくは、[&#x200B; レコメンデーションキーに基づいてレコメンデーションを作成する](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)を参照してください。

## カスタムレコメンデーションキーの使用 {#custom-key}

また、カスタムプロファイル属性の値に基づいてレコメンデーションを行うこともできます。

>[!NOTE]
>
>カスタムプロファイルパラメーターは、JavaScript、API、または統合機能を使用して[!DNL Target]に渡すことができます。 カスタムプロファイル属性について詳しくは、[訪問者プロファイル &#x200B;](/help/main/c-target/c-visitor-profile/visitor-profile.md)を参照してください。

例えば、ユーザーが最後にキューに追加したムービーに基づいて、推奨ムービーを表示するとします。

1. **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL 条件を作成]** > **[!UICONTROL 条件を作成]**&#x200B;をクリックします。

1. [基本情報セクション &#x200B;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)に情報を入力します。

1. 「[推奨アルゴリズム &#x200B;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo)」セクションで、**[!UICONTROL アルゴリズムタイプ]** リストから「**[!UICONTROL アイテムベース]**」を選択します。

1. 「**[!UICONTROL アルゴリズム]**」リストから「**[!UICONTROL これを表示したユーザー]**」を選択します。

1. **[!UICONTROL Recommendation Key]** リストからカスタム プロファイル属性を選択します（例：[!UICONTROL 前回のウォッチリストに追加された番組]）。

   ![新しい条件を作成ダイアログボックス &#x200B;](assets/custom-key1.png)

## 条件情報の表示 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

ポップアップカードにマウスポインターを置いてから、条件カードの情報アイコンをクリックすると、条件を開くことなくポップアップカードの条件の詳細を表示できます。

![条件カードにマウスポインターを置く](/help/main/c-recommendations/c-algorithms/assets/criteria_hover.png)

「**[!UICONTROL アルゴリズム情報]**」タブをクリックして、選択した条件に関する一般的な情報（名前、説明、業種、ページタイプ、レコメンデーションキー、レコメンデーションロジック、アルゴリズム ID など）を表示します。

![「アルゴリズム情報」タブ](/help/main/c-recommendations/c-algorithms/assets/criteria_info.png)

「**[!UICONTROL アルゴリズム使用状況]**」タブをクリックして、選択した条件を参照するアクティビティのリストを表示します。 カードには、アクティブ、非アクティブ、ドラフトの各アクティビティが一覧表示されます。 「ライブアクティビティ/非アクティブアクティビティ/ドラフトアクティビティ」ドロップダウンリストをクリックして、その条件を参照するアクティビティのリスト全体を表示します。 アクティビティリンクをクリックすると、編集するアクティビティを開くことができます。

![&#x200B; アルゴリズム使用状況タブ &#x200B;](/help/main/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>[!UICONTROL &#x200B; アルゴリズム使用状況]機能は、現在、Recommendations アクティビティでのみサポートされています。 この機能は、現在、[推奨事項をオファー](/help/main/c-recommendations/recommendations-as-an-offer.md)として含むA/B テスト、自動配分、自動ターゲット、およびエクスペリエンスターゲティング （XT）アクティビティではサポートされていません。
