---
description: アクティビティURLは、アクティビティの設計時に、エクスペリエンスターゲット設定アクティビティで使用されるページと、Visual Experience Composer（VEC）またはフォームベースのExperience Composerで表示されるページを決定します。
keywords: ターゲット設定
seo-description: アクティビティURLは、アクティビティの設計時に、エクスペリエンスターゲット設定アクティビティで使用されるページと、Adobe Target Visual Experience Composer（VEC）またはフォームベースのExperience Composerで表示されるページを決定します。
seo-title: アクティビティ URL
solution: 'Target '
title: アクティビティ URL
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: ca9639ccca286dac182728f7bbd43fac78217209

---


# アクティビティ URL{#activity-url}

アクティビティURLは、アクティビティの設計時に、エクスペリエンスターゲット設定（XT）アクティビティで使用されるページ、およびVisual Experience Composer（VEC）またはフォームベースのExperience Composerで表示されるページを決定します。

1. XTアクティビティ [](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)の作成時に、アクティビティURLを指定します。`https://` を含む完全な URL を入力して、「**[!UICONTROL アクティビティを作成]**」をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `https://www.adobe.com`] と [!DNL `http://www.adobe.com`] の両方が一致します。
   >
   >デフォルトでは、VECまたはフォームベースのExperience Composerは [、アカウント環境設定で指定したページを開き](/help/administrating-target/r-target-account-preferences/target-account-preferences.md)ます。アクティビティ作成中に、異なるページを指定することもできます。
   >
   >Target StandardのJavaScriptコードを含まないサイトのURLを指定すると、ページエレメントを選択できません。

1. (Conditional) To display a different page after the VEC opens, click **[!UICONTROL Configure]**, select **[!UICONTROL Page Delivery]**, and specify the URL in the [!UICONTROL URL] field.

   ![ページ配信ダイアログボックス](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。

1. （オプション）「テンプレートルール **[!UICONTROL ]** を追加」をクリックして、アクティビティにページまたはセクションを追加します。

   追加のルールは、以下のいずれかに基づいています。

   * URL
   * ドメイン
   * パス
   * ハッシュ（#）フラグメント
   * クエリ
   * mbox パラメーター
   追加のルールは、AND または OR を使用してアクティビティ URL と結合できます。追加したすべてのルールは、AND を使用してお互いに評価されます。

1. 終了したら「**[!UICONTROL 保存]**」をクリックします。