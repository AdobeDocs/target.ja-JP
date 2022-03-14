---
keywords: エクスペリエンスのターゲット設定；xt；アクティビティ URL;url
description: Adobe Targetを使用してエクスペリエンスのターゲット設定アクティビティが設計された場合に、テストで使用され、開くページを決定するアクティビティ URL を指定する方法について説明します。
title: エクスペリエンスターゲット設定 (XT) アクティビティのアクティビティ URL とは何ですか？
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 63%

---

# エクスペリエンスターゲット設定 (XT) アクティビティのアクティビティ URL

この [!UICONTROL アクティビティ URL] は、 [!DNL Adobe Target] [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティに含まれ、 [!UICONTROL Visual Experience Composer] (VEC) または [!UICONTROL フォームベースの Experience Composer] （アクティビティを設計する際に使用）。

1. [XT アクティビティを作成する](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)際にアクティビティ URL の入力を求められたら、URL を指定します。`https://` を含む完全な URL を入力して、「**[!UICONTROL アクティビティを作成]**」をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `https://www.adobe.com`] と [!DNL `http://www.adobe.com`] の両方が一致します。
   >
   >デフォルトでは、VEC またはフォームベースの Experience Composer は、 [Visual Experience Composer の設定](/help/main/administrating-target/visual-experience-composer-set-up.md). アクティビティ作成中に、異なるページを指定することもできます。
   >
   >Target Standard の JavaScript コードを含まないサイトの URL を指定すると、ページ要素を選択できません。

1. （条件付き）VEC を開いた後に異なるページを表示するには、「**[!UICONTROL 設定]**」をクリックして「**[!UICONTROL ページ配信]**」を選択し、「[!UICONTROL URL]」フィールドに URL を指定します。

   ![ページ配信ダイアログボックス](/help/main/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。

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
