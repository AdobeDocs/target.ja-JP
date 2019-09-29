---
description: アクティビティ URL は、エクスペリエンスターゲット設定アクティビティで使用され、アクティビティを設計する際に Visual Experience Composer（VEC）やフォームベースの Experience Composer で開くページを指定します。
keywords: ターゲット設定
seo-description: アクティビティ URL は、エクスペリエンスターゲット設定アクティビティで使用され、アクティビティを設計する際に Adobe Target Visual Experience Composer（VEC）やフォームベースの Experience Composer で開くページを指定します。
seo-title: アクティビティ URL
solution: 'Target '
title: アクティビティ URL
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# アクティビティ URL{#activity-url}

アクティビティ URL は、エクスペリエンスターゲット設定（XT）アクティビティで使用され、アクティビティを設計する際に Visual Experience Composer（VEC）やフォームベースの Experience Composer で開くページを指定します。

1. [XT アクティビティを作成する](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)際にアクティビティ URL の入力を求められたら、URL を指定します。`https://` を含む完全な URL を入力して、「**[!UICONTROL アクティビティを作成]**」をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `https://www.adobe.com`] と [!DNL `http://www.adobe.com`] の両方が一致します。
   >
   >デフォルトでは、[アカウントの基本設定](/help/administrating-target/r-target-account-preferences/target-account-preferences.md)で指定されたページが VEC または フォームベースの Experience Composer で開かれます。アクティビティ作成中に、異なるページを指定することもできます。
   >
   >Target Standard の JavaScript コードを含まないサイトの URL を指定すると、ページ要素を選択できません。

1. （条件付き）VEC を開いた後に異なるページを表示するには、「**[!UICONTROL 設定]**」をクリックして「**[!UICONTROL ページ配信]**」を選択し、「[!UICONTROL URL]」フィールドに URL を指定します。

   ![ページ配信ダイアログボックス](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

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