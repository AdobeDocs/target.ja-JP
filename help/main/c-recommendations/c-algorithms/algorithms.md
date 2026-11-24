---
keywords: レコメンデーション；レコメンデーションアクティビティ；基準；アルゴリズム；レコメンデーションキー；カスタムキー；業界縦組み；小売；e コマース；リードジェネレーション；b2b；金融サービス；メディア；公開
description: Adobe [!DNL Target] [!DNL Recommendations]で条件を使用する方法について説明します。
title: '[!DNL Target]件のレコメンデーションで条件を使用するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
TQID: 'https://experienceleague.adobe.com/Wo7I3piBQ7zwYF7kqRphDeWjcBCpyvIvTkwKK0t0f9U'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
    internal-label: Integrations
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 8%
---
# [!UICONTROL 条件]を使用する {#get-started-criteria}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、[!DNL Adobe Target Recommendations]での基準の仕組みと、業界の垂直方向、アルゴリズムの種類、および推奨事項のキーオプションを利用できることについて説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target] [!DNL Recommendations]の&#x200B;**[!UICONTROL 条件]**&#x200B;は、事前に決められた訪問者の行動セットに基づいて、推奨する製品またはコンテンツを決定するルールです。 条件は、人気の傾向、訪問者の現在および過去の行動、類似の商品およびコンテンツに基づかせることができます。 アクティビティに複数の基準を追加して、複数のレコメンデーションタイプを比較してテストできます。

選択された業界標準とアルゴリズムタイプによって、基準の作成時に使用できるオプションが決まります。

## 業種 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

基準を作成すると、レコメンデーション アクティビティの目標に基づいて業界標準が選択されます。

| 業種 | 目標 |
|--- |--- |
| **[!UICONTROL 小売/デジタルコマース]** | 購入をもたらすコンバージョン |
| **[!UICONTROL リードジェネレーション/B2B/金融サービス]** | 購入を伴わないコンバージョン |
| **[!UICONTROL メディア/公開]** | エンゲージメント |

その他の基準オプションは、選択した業界の垂直方向に基づいて変更されます。 既定の業種は、**[!UICONTROL 管理]** > **[!UICONTROL 推奨事項]** ページで設定するか、各条件に業種の業種を指定できます。

## アルゴリズムのタイプ {#section_885B3BB1B43048A88A8926F6B76FC482}

選択したアルゴリズムタイプによって、使用可能なアルゴリズムが決まります。 次の表では、アルゴリズムの種類とそれに付随するアルゴリズムについて説明します。

| アルゴリズムタイプ | 使用するタイミング | 使用可能なアルゴリズム |
| --- | --- | --- |
| **[!UICONTROL カートベース]** | ユーザーのカートの内容に基づいてレコメンデーションを行います。 | <ul><li>**[!UICONTROL これらを閲覧したユーザーは、]**&#x200B;も閲覧しました</li><li>**[!UICONTROL これらを閲覧したユーザーも購入しました]**</li><li>**[!UICONTROL これらを購入した人、また購入した人]**</li></ul>詳しくは、*の「[ カートベース ](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based)」を参照してください。レコメンデーションキー*&#x200B;に基づいてレコメンデーションを行います。 |
| **[!UICONTROL 人気度ベース]** | サイト全体でのアイテムの全体的な人気度、またはユーザーのお気に入りまたは最も閲覧されたカテゴリ、ブランド、ジャンルなどの中のアイテムの人気度に基づいてレコメンデーションを行います。 | <ul><li>**[!UICONTROL サイト全体で最も閲覧された]**</li><li>**[!UICONTROL カテゴリー別に最も閲覧された]**</li><li>**[!UICONTROL 項目属性]**&#x200B;で最も閲覧された項目</li><li>**[!UICONTROL プロファイル属性別で最も多く閲覧された]**</li><li>サイト全体で&#x200B;**[!UICONTROL トップ セラー]**</li><li>**[!UICONTROL カテゴリー別のトップセラー]**</li><li>**[!UICONTROL 項目属性]**&#x200B;別の上位セラー</li><li>プロファイル属性&#x200B;]**による**[!UICONTROL  トップセラー</li><li>分析指標&#x200B;**[!UICONTROL 上位]**</li></ul> |
| **[!UICONTROL アイテムベース]** | 利用者が現在閲覧中または最近閲覧した項目と類似する項目にもとづいて、レコメンデーションを作成できます。 | <ul><li>**[!UICONTROL これを閲覧したユーザー、これを閲覧したユーザー]**</li><li>**[!UICONTROL これを閲覧したユーザーが購入しました]**</li><li>**[!UICONTROL これを購入した人、購入した人]**</li><li>**[!UICONTROL 類似の属性を持つアイテム]**</li></ul> |
| **[!UICONTROL ユーザーベース]** | 利用者の行動にもとづいてレコメンデーションする： | <ul><li>**[!UICONTROL 最近表示された項目]**</li><li>**[!UICONTROL あなたにおすすめ]**</li></ul> |
| **[!UICONTROL カスタム条件]** | アップロードされたカスタムファイルにもとづいて、レコメンデーションを作成します。 | <ul><li>カスタムアルゴリズム</li></ul> |

各アルゴリズムについて詳しくは、[ レコメンデーションキーに基づいてレコメンデーションを作成する](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)を参照してください。

## カスタムレコメンデーションキーの使用 {#custom-key}

また、カスタムプロファイル属性の値にもとづいて、レコメンデーションを行うこともできます。 例えば、ユーザーが最後にキューに追加したムービーに基づいて、推奨ムービーを表示できます。

1. **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL 条件を作成]** > **[!UICONTROL 条件を作成]**&#x200B;をクリックします。

   ![条件を作成メニューが開いた条件ページ。条件を作成および条件シーケンスを作成](../assets/criteria_1.png)が表示されている

1. [基本情報セクション ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)に情報を入力します。

1. 「[推奨アルゴリズム ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo)」セクションで、**[!UICONTROL アルゴリズムタイプ]** リストから「**[!UICONTROL アイテムベース]**」を選択します。

1. 「**[!UICONTROL アルゴリズム]**」リストから「**[!UICONTROL これを表示したユーザー]**」を選択します。

1. **[!UICONTROL Recommendation Key]** リストからカスタム プロファイル属性を選択します（例：**[!UICONTROL 前回のウォッチリストに追加された番組]**）。

   >[!NOTE]
   >
   >カスタムプロファイルパラメーターは、JavaScript、API、または統合機能を使用して[!DNL Target]に渡すことができます。 カスタムプロファイル属性について詳しくは、[訪問者プロファイル ](/help/main/c-target/c-visitor-profile/visitor-profile.md)を参照してください。

   ![条件を作成ダイアログボックスで、アルゴリズムの種類、アルゴリズム、およびレコメンデーションキーリストを含むレコメンデーションアルゴリズムのセクションが表示されます](../assets/criteria_2.png)

## 条件情報の表示 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

基準の詳細は、基準がどのように設定され、どのアクティビティがそれを使用するかを示します。

1. **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;をクリックして、条件のリストを表示します。

1. **[!UICONTROL 名前]**&#x200B;列の目的の条件をクリックします。

1. **[!UICONTROL 属性]**&#x200B;および詳細セクションで選択した条件に関する一般的な情報を表示します。これには、**[!UICONTROL 名前]**、**[!UICONTROL 説明]**、**[!UICONTROL 業界の垂直方向]**、**[!UICONTROL ページタイプ]**、**[!UICONTROL レコメンデーションキー]**、**[!UICONTROL レコメンデーションロジック]**、**[!UICONTROL アルゴリズム ID]**、最終変更情報（アルゴリズムを変更した日付および担当者）が含まれます。

1. 選択した条件を参照するアクティビティのリストを「**[!UICONTROL 使用状況]**」セクションで表示します。

   >[!NOTE]
   >
   >**[!UICONTROL アルゴリズム使用状況]**&#x200B;機能は、現在[!DNL Recommendations] アクティビティでのみサポートされています。 この機能は、現在、[のレコメンデーションをオファー](/help/main/c-recommendations/recommendations-as-an-offer.md)として含む&#x200B;**[!UICONTROL A/B テスト]**、**[!UICONTROL 自動割り当て]**、**[!UICONTROL 自動ターゲット]**、**[!UICONTROL エクスペリエンスのターゲット設定]** （XT）アクティビティではサポートされていません。

   ![属性と詳細セクションおよび使用状況セクションが強調表示された条件の詳細](../assets/criteria_3.png)
