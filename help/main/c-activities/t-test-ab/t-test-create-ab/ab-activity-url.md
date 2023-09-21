---
keywords: アクティビティ url;url；別の url
description: テストで使用され、を使用してテストが設計された場合に表示されるページを決定するアクティビティ URL を指定する方法について説明します。 [!DNL Adobe Target].
title: A/B アクティビティのアクティビティ URL とは何ですか？
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: 6bca763d24649349dbc7cdf6e5f2dbc4ac0a480d
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 64%

---

# アクティビティ URL

アクティビティ URL は、Adobe Targetを使用して設計されたテストで使用され、そのテストで表示されるページを指定します。

アクティビティ作成中にアクティビティ URL の入力を求められたら、URL を指定します。`https://` を含む完全な URL を入力して、「**[!UICONTROL 作成]**」をクリックします。

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `http://www.adobe.com`] と [!DNL `https://www.adobe.com`] の両方が一致します。

## 異なる URL の指定

デフォルトでは、 [!UICONTROL Visual Experience Composer] をクリックして、 [Visual Experience Composer の設定](/help/main/administrating-target/visual-experience-composer-set-up.md). アクティビティ作成中に、異なるページを指定することもできます。

1. ページの後に別のページを表示するには [!UICONTROL Visual Experience Composer] 開く ( **[!UICONTROL エクスペリエンス]** ページで、 **[!UICONTROL 設定]** 歯車アイコンをクリックし、「 **[!UICONTROL ページ配信]**.

1. URL を **[!UICONTROL URL]** フィールドに入力します。

   ![ページ配信ダイアログボックス](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

1. （条件付き）アクティビティにさらにページまたはセクションを追加するには、「**[!UICONTROL テンプレートルールを追加]**」をクリックします。

   追加のルールは、以下のいずれかに基づいています。

   * URL
   * ドメイン
   * パス
   * ハッシュ（#）フラグメント
   * クエリ
   * mbox パラメーター

   追加のルールは、AND または OR を使用してアクティビティ URL と結合できます。追加したすべてのルールは、AND を使用してお互いに評価されます。

1. 終了したら「**[!UICONTROL 保存]**」をクリックします。

Standard の JavaScript コードを含まないサイトの URL を入力すると、ページ要素を選択できません。[!DNL Target]

デフォルトでは、バナーの回転など JavaScript を含む要素については、[!UICONTROL Visual Experience Composer] で変更できません。**[!UICONTROL Visual Experience Composer]** を使用してこのような要素を変更するには、「[!UICONTROL JavaScript を使用してレンダリング]」をオフにします。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。
