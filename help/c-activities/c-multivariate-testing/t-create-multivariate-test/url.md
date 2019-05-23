---
description: アクティビティ URL は、テストで使用され、設計したテストで表示されるページを指定します。
keywords: ターゲット設定
seo-description: アクティビティ URL は、テストで使用され、設計したテストで表示されるページを指定します。
seo-title: アクティビティ URL
solution: 'Target '
title: アクティビティ URL
uuid: ddc7330c-199a-4e38-b3d4-6786e3997783
translation-type: tm+mt
source-git-commit: 761771a48c0ae957d455974b1f04fa3a8350a8a0

---


# アクティビティ URL{#activity-url}

アクティビティ URL は、テストで使用され、設計したテストで表示されるページを指定します。

アクティビティ作成中にアクティビティ URL の入力を求められたら、URL を入力します。`https://` を含む完全な URL を入力して、「**[!UICONTROL アクティビティを作成]**」をクリックします。

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `https://www.adobe.com`] と [!DNL `http://www.adobe.com`] の両方が一致します。

デフォルトでは、アカウントの基本設定で指定されたページが Visual Experience Composer で開かれます。アクティビティ作成中に、異なるページを指定することもできます。

Visual Experience Composer を開いた後に異なるページを表示するには、「**[!UICONTROL 設定]**」をクリックして「**[!UICONTROL URL]**」を選択し、「アクティビティ URL」ボックスに URL を入力します。

![](assets/url-config.png)

アクティビティにさらにページまたはセクションを追加するには、「**[!UICONTROL テンプレートルールを追加]」をクリックします。**

追加のルールは、以下のいずれかに基づいています。

* URL
* ドメイン
* パス
* ハッシュ（#）フラグメント
* クエリ
* mbox パラメーター

追加のルールは、AND または OR を使用してアクティビティ URL と結合できます。追加したすべてのルールは、AND を使用してお互いに評価されます。

終了したら「**[!UICONTROL 保存]」をクリックします。**

>[!NOTE]
>
>Target Standard の JavaScript コードを含まないサイトの URL を入力すると、ページ要素を選択できません。

デフォルトでは、バナーの回転など JavaScript を含む要素については、[!UICONTROL Visual Experience Composer] で変更できません。**[!UICONTROL Visual Experience Composer]を使用してこのような要素を変更するには、「**[!UICONTROL JavaScript を使用してレンダリング]」をオフにします。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、行った変更が失われます。

