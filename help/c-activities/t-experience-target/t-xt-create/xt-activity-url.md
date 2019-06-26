---
description: アクティビティURLは、アクティビティの設計時に、エクスペリエンスターゲット設定アクティビティで使用されるページと、Visual Experience Composer（VEC）またはフォームベースのExperience Composerで表示されるページを決定します。
keywords: ターゲット設定
seo-description: アクティビティURLは、アクティビティの設計時に、エクスペリエンスターゲット設定アクティビティで使用されるページと、Adobe Target Visual Experience Composer（VEC）またはフォームベースのExperience Composerで表示されるページを決定します。
seo-title: アクティビティ URL
solution: 'Target '
title: アクティビティ URL
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# アクティビティ URL{#activity-url}

アクティビティURLは、アクティビティの設計時に、エクスペリエンスターゲット設定（XT）アクティビティで使用されるページ、およびVisual Experience Composer（VEC）またはフォームベースのExperience Composerで表示されるページを決定します。

1. When prompted while [creating an XT activity](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), specify the activity URL. `https://` を含む完全な URL を入力して、「**[!UICONTROL アクティビティを作成]**」をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `https://www.adobe.com`] と [!DNL `http://www.adobe.com`] の両方が一致します。
   >
   >By default, the VEC or Form-Based Experience Composer opens the page that is specified in your [Account Preferences](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). アクティビティ作成中に、異なるページを指定することもできます。
   >
   >Target StandardのJavaScriptコードを含まないサイトのURLを指定すると、ページエレメントを選択できません。

1. (Conditional) To display a different page after the VEC opens, click **[!UICONTROL Configure]**, select **[!UICONTROL Page Delivery]**, and specify the URL in the [!UICONTROL URL] field.

   ![ページ配信ダイアログボックス](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。

1. (Conditional) Click **[!UICONTROL Add Template Rule]** to add more pages or sections to the activity.

   追加のルールは、以下のいずれかに基づいています。

   * URL
   * ドメイン
   * パス
   * ハッシュ（#）フラグメント
   * クエリ
   * mbox パラメーター
   追加のルールは、AND または OR を使用してアクティビティ URL と結合できます。追加したすべてのルールは、AND を使用してお互いに評価されます。

1. 終了したら「**[!UICONTROL 保存]**」をクリックします。