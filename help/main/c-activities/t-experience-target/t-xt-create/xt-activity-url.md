---
keywords: エクスペリエンスのターゲット設定；xt；アクティビティ URL;url
description: 次の項目を指定する方法を説明します。 [!UICONTROL アクティビティ URL] この変数は、テストで使用され、 [!UICONTROL エクスペリエンスのターゲット設定] アクティビティは [!DNL Adobe Target].
title: とは [!UICONTROL アクティビティ URL] 内、 [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ？
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 24513d8cb39d38dcfbc74bf40961d5517cc90a4b
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 48%

---

# のアクティビティ URL [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ

The [!UICONTROL アクティビティ URL] は、 [!DNL Adobe Target] [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ これは、 [!UICONTROL Visual Experience Composer] (VEC) または [!UICONTROL フォームベースの Experience Composer] （アクティビティを設計する際に使用）。

1. [XT アクティビティを作成する](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)際にアクティビティ URL の入力を求められたら、URL を指定します。`https://` を含む完全な URL を入力して、「**[!UICONTROL アクティビティを作成]**」をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `https://www.adobe.com`] と [!DNL `http://www.adobe.com`] の両方が一致します。
   >
   >デフォルトでは、VEC または [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) をクリックして、 [Visual Experience Composer の設定](/help/main/administrating-target/visual-experience-composer-set-up.md). アクティビティ作成中に、異なるページを指定することもできます。
   >
   >サイトの URL を指定し、 [[!DNL Target] at.js JavaScript ライブラリまたは [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html?lang=ja){target=_blank}の場合、ページ要素は選択できません。

1. （条件付き）VEC を開いた後に異なるページを表示するには、 **[!UICONTROL 設定]**&#x200B;を選択します。 **[!UICONTROL ページ配信]**」をクリックし、 [!UICONTROL URL] フィールドに入力します。

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
