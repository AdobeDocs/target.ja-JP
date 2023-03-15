---
keywords: レコメンデーション；レコメンデーションアクティビティ；条件；アルゴリズム；レコメンデーションキー；カスタムキー；業種；小売；e コマース；リードジェネレーション；b2b；金融サービス；メディア；公開
description: Adobeでの条件の使用方法を説明します [!DNL Target] [!DNL Recommendations].
title: での条件の使用方法 [!DNL Target] Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 23%

---

# 条件

の条件 [!DNL Adobe Target] [!DNL Recommendations] は、事前に定義されている訪問者の行動に基づいて、レコメンデーションする製品またはコンテンツを決定するルールです。 条件は、人気の傾向、訪問者の現在および過去の行動、類似の商品およびコンテンツに基づかせることができます。複数の条件を追加することで、複数のレコメンデーションタイプを相互にテストすることができます。

次の節では、条件キーと、各キーで使用できるレコメンデーションロジックについて詳しく説明します。 詳細は、リンクをクリックしてください。

## 業種 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

条件を作成する際に、レコメンデーションアクティビティの目標に基づいて業種を選択します。

| 業種 | 目標 |
|--- |--- |
| 小売／e コマース | 購入をもたらすコンバージョン |
| リードジェネレーション／B2B／金融サービス | 購入を伴わないコンバージョン |
| メディア／投稿 | エンゲージメント |

その他の条件オプションは、選択した業種に応じて異なります。 デフォルトの業種を **[!UICONTROL Recommendations /設定]** ページを開くか、各条件の業種を指定できます。

## アルゴリズムのタイプ {#section_885B3BB1B43048A88A8926F6B76FC482}

選択したアルゴリズムのタイプによって、使用可能なアルゴリズムが決まります。 複数のアルゴリズムの種類があり、を設定する際に条件カードとして表示されます。 [!DNL Recommendations] アクティビティ。

![条件ページ](assets/criteria-page.png)

次の表に、様々なアルゴリズムのタイプとそれに伴うアルゴリズムを示します。

| アルゴリズムタイプ | 使用するタイミング | 利用可能なアルゴリズム |
| --- | --- | --- |
| [!UICONTROL 買い物かごベース] | ユーザーの買い物かごの内容に基づいてレコメンデーションをおこないます。 | <ul><li>これらを閲覧した人がそれらを閲覧しました</li><li>これらを閲覧した人が購入したもの</li><li>これらを購入した人が購入したもの</li></ul>詳しくは、 [買い物かごベース](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) in *レコメンデーションキーに基づくレコメンデーションの設定*. |
| [!UICONTROL 人気度ベース] | サイト全体での品目の全体的な人気度に基づいて、またはユーザーのお気に入りまたは最も多く閲覧されたカテゴリ、ブランド、ジャンルなど内の品目の人気度に基づいてレコメンデーションをおこないます。 | <ul><li>サイト全体で最も多く閲覧された</li><li>カテゴリ別の最も多く閲覧された項目</li><li>品目属性別最も多く閲覧された品目</li><li>サイト全体のトップセラー</li><li>カテゴリ別のトップセラー</li><li>品目属性別トップセラー</li><li>Analytics 指標別の上位</li></ul> |
| [!UICONTROL 項目ベース] | ユーザーが現在表示している品目や最近表示した品目に類似した品目を見つけることに基づいてレコメンデーションをおこないます。 | <ul><li>これを閲覧した人が他に閲覧したもの</li><li>これを閲覧した人が購入したもの</li><li>これを購入した人が他に購入したもの</li><li>類似の属性を持つ品目</li></ul> |
| [!UICONTROL ユーザーベース] | ユーザーの行動に基づいてレコメンデーションをおこなう。 | <ul><li>最近表示された項目</li><li>お勧め</li></ul> |
| [!UICONTROL カスタム条件] | アップロードしたカスタムファイルに基づいてレコメンデーションをおこないます。 | <ul><li>カスタムアルゴリズム</li></ul> |

各アルゴリズムについて詳しくは、 [レコメンデーションキーに基づくレコメンデーションの設定](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## カスタムレコメンデーションキーの使用 {#custom-key}

また、カスタムプロファイル属性の値に基づくレコメンデーションを設定することもできます。

>[!NOTE]
>
>カスタムプロファイルパラメーターはに渡すことができます [!DNL Target] JavaScript、API、統合を使用する。 カスタムプロファイル属性について詳しくは、 [訪問者プロファイル](/help/main/c-target/c-visitor-profile/visitor-profile.md).

例えば、ユーザーが最近キューに追加したムービーに基づいて、お勧めのムービーを表示するとします。

1. クリック **[!UICONTROL Recommendations]** > **[!UICONTROL 条件]**.

1. クリック **[!UICONTROL 条件の作成]** > **[!UICONTROL 条件の作成]**.

1. 次の項目に情報を入力します。 [「基本情報」セクション](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. 内 [推奨アルゴリズム](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo) セクション、選択 **[!UICONTROL 項目ベース]** から **[!UICONTROL アルゴリズムタイプ]** リスト。

1. 選択 **[!UICONTROL これを閲覧した人が他に閲覧したもの]** から **[!UICONTROL アルゴリズム]** リスト。

1. カスタムプロファイル属性を **[!UICONTROL レコメンデーションキー]** リスト ( 例： [!UICONTROL 最後の番組をウォッチリストに追加しました]) をクリックします。

   ![新しい条件を作成ダイアログボックス](assets/custom-key1.png)

## 条件情報の表示 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

ポップアップカードにマウスポインターを置いてから、条件カードの情報アイコンをクリックすると、条件を開くことなくポップアップカードの条件の詳細を表示できます。

![条件カードにマウスポインターを置く](/help/main/c-recommendations/c-algorithms/assets/criteria_hover.png)

「**[!UICONTROL アルゴリズム情報]**」タブをクリックして、選択した条件に関する一般的な情報（名前、説明、業種、ページタイプ、レコメンデーションキー、レコメンデーションロジック、アルゴリズム ID など）を表示します。

![「アルゴリズム情報」タブ](/help/main/c-recommendations/c-algorithms/assets/criteria_info.png)

「**[!UICONTROL アルゴリズム使用状況]**」タブをクリックして、選択した条件を参照するアクティビティのリストを表示します。カードには、アクティブ、非アクティブおよびドラフトのアクティビティが一覧表示されます。 ライブアクティビティ/非アクティブなアクティビティ/ドラフトアクティビティドロップダウンリストをクリックして、その条件を参照するアクティビティのリスト全体を表示します。 アクティビティリンクをクリックすると、編集するアクティビティを開くことができます。

![「アルゴリズム使用状況」タブ](/help/main/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>この [!UICONTROL アルゴリズム使用状況] 機能は、現在、Recommendationsアクティビティでのみサポートされています。 この機能は、現在、A/B テスト、自動配分、自動ターゲットおよびエクスペリエンスのターゲット設定 (XT) のアクティビティで、 [オファーとしてのレコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md).
