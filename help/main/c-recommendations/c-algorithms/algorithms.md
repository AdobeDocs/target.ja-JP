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
source-wordcount: 657
ht-degree: 10%

---

# [!UICONTROL 条件]

[!DNL Adobe Target] [!DNL Recommendations]の[!UICONTROL 条件]は、事前に決められた訪問者の行動セットに基づいて、推奨する製品またはコンテンツを決定するルールです。 条件は、人気の傾向、訪問者の現在および過去の行動、類似の商品およびコンテンツに基づかせることができます。 複数の条件を追加することで、複数のレコメンデーションタイプを相互にテストすることができます。

次の節では、基準キーと、各キーに使用できるレコメンデーションロジックについて詳しく説明します。 詳細については、リンクをクリックしてください。

## 業種 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

基準を作成する際に、レコメンデーション活動の目標に基づいて業種を選択します。

| 業種 | 目標 |
|--- |--- |
| [!UICONTROL 小売/デジタルコマース ] | 購入をもたらすコンバージョン |
| [!UICONTROL  リードジェネレーション/B2B/金融サービス ] | 購入を伴わないコンバージョン |
| [!UICONTROL  メディア/公開] | エンゲージメント |

その他の基準オプションは、選択した業界の業種によって異なります。 **[!UICONTROL 管理] > [!UICONTROL 推奨事項]** ページで既定の業種を設定するか、各条件に業種の業種を指定できます。

## アルゴリズムのタイプ {#section_885B3BB1B43048A88A8926F6B76FC482}

選択したアルゴリズムタイプによって、使用可能なアルゴリズムが決まります。

次の表では、様々なアルゴリズムのタイプとそれに付随するアルゴリズムについて説明します。

| アルゴリズムタイプ | 使用するタイミング | 使用可能なアルゴリズム |
| --- | --- | --- |
| [!UICONTROL  カートベース ] | ユーザーのカートの内容に基づいてレコメンデーションを行います。 | <ul><li>[!UICONTROL これらを閲覧したユーザーは、]も閲覧しました</li><li>[!UICONTROL これらを閲覧したユーザーも購入しました]</li><li>[!UICONTROL これらを購入した人、また購入した人]</li></ul>詳しくは、*の「[ カートベース ](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based)」を参照してください。レコメンデーションキー*&#x200B;に基づいてレコメンデーションを行います。 |
| [!UICONTROL 人気度ベース ] | サイト全体でのアイテムの人気度や、ユーザーが好むカテゴリーや最も閲覧されたカテゴリー、ブランド、ジャンルなどの中でのアイテムの人気度にもとづいて、レコメンデーションを行うことができます。 | <ul><li>[!UICONTROL  サイト全体で最も閲覧された]</li><li>[!UICONTROL  カテゴリー別に最も閲覧された]</li><li>[!UICONTROL 項目属性]で最も閲覧された項目</li><li>サイト全体で[!UICONTROL  トップ セラー]</li><li>[!UICONTROL  カテゴリー別のトップセラー]</li><li>[!UICONTROL 項目属性]別の上位セラー</li><li>分析指標[!UICONTROL 上位]</li></ul> |
| [!UICONTROL  アイテムベース ] | 利用者が現在閲覧している項目や最近閲覧した項目と類似する項目を見つけることで、レコメンデーションを行うことができます。 | <ul><li>[!UICONTROL これを閲覧したユーザー、これを閲覧したユーザー]</li><li>[!UICONTROL これを閲覧したユーザーが購入しました]</li><li>[!UICONTROL これを購入した人、購入した人]</li><li>[!UICONTROL 類似の属性を持つアイテム ]</li></ul> |
| [!UICONTROL  ユーザーベース ] | 利用者の行動にもとづいてレコメンデーションする： | <ul><li>[!UICONTROL 最近表示された項目]</li><li>[!UICONTROL あなたにおすすめ]</li></ul> |
| [!UICONTROL  カスタム条件] | アップロードしたカスタムファイルにもとづいて、レコメンデーションを作成できます。 | <ul><li>カスタムアルゴリズム</li></ul> |

各アルゴリズムについて詳しくは、[ レコメンデーションキーに基づいてレコメンデーションを作成する](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)を参照してください。

## カスタムレコメンデーションキーの使用 {#custom-key}

また、カスタムプロファイル属性の値に基づいてレコメンデーションを行うこともできます。

>[!NOTE]
>
>カスタムプロファイルパラメーターは、JavaScript、API、または統合機能を使用して[!DNL Target]に渡すことができます。 カスタムプロファイル属性について詳しくは、[訪問者プロファイル ](/help/main/c-target/c-visitor-profile/visitor-profile.md)を参照してください。

例えば、ユーザーが最後にキューに追加したムービーに基づいて、推奨ムービーを表示するとします。

1. **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL 条件を作成]** > **[!UICONTROL 条件を作成]**&#x200B;をクリックします。

1. [基本情報セクション ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)に情報を入力します。

1. 「[推奨アルゴリズム ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo)」セクションで、**[!UICONTROL アルゴリズムタイプ]** リストから「**[!UICONTROL アイテムベース]**」を選択します。

1. 「**[!UICONTROL アルゴリズム]**」リストから「**[!UICONTROL これを表示したユーザー]**」を選択します。

1. **[!UICONTROL Recommendation Key]** リストからカスタム プロファイル属性を選択します（例：[!UICONTROL 前回のウォッチリストに追加された番組]）。

## 条件情報の表示 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

[!UICONTROL 名前]列の目的の条件をクリックすると、条件の詳細を表示できます。

**[!UICONTROL 属性]**&#x200B;および詳細セクションでは、[!UICONTROL 名前]、[!UICONTROL 説明]、[!UICONTROL 業界の垂直性]、[!UICONTROL  ページタイプ ]、[!UICONTROL  レコメンデーションキー]、[!UICONTROL  レコメンデーションロジック ]、[!UICONTROL  アルゴリズム ID]、最終変更情報（アルゴリズムを変更した日付およびユーザー）など、選択した条件に関する一般的な情報を表示できます。

**[!UICONTROL 使用状況]** セクションでは、選択した条件を参照するアクティビティのリストを表示できます。

>[!NOTE]
>
>[!UICONTROL  アルゴリズム使用状況]機能は、現在[!DNL Recommendations] アクティビティでのみサポートされています。 この機能は、現在、[のレコメンデーションをオファー](/help/main/c-recommendations/recommendations-as-an-offer.md)として含む[!UICONTROL A/B テスト ]、[!UICONTROL 自動割り当て]、[!UICONTROL 自動ターゲット ]、[!UICONTROL  エクスペリエンスのターゲット設定] （XT）アクティビティではサポートされていません。
