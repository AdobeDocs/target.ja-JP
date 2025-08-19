---
keywords: エクスペリエンスのターゲット設定；xt；アクティビティ url;url
description: テストで使用され、[!UICONTROL Activity URL] アクティビティが [!UICONTROL Experience Targeting] を使用してデザインされたときに開くページを決定する  [!DNL Adobe Target] ールの指定方法を説明します。
title: '[!UICONTROL Activity URL] （XT）アクティビティの [!UICONTROL Experience Targeting] とは何ですか。'
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 38%

---

# [!UICONTROL Experience Targeting] （XT）アクティビティのアクティビティ URL

[!UICONTROL Activity URL] は、[!DNL Adobe Target] [!UICONTROL Experience Targeting] （XT）アクティビティで使用されるページを決定します。 アクティビティが設計されると、[!UICONTROL Visual Experience Composer] （VEC）または [!UICONTROL Form-Based Experience Composer] で開くページです。

1. [XT アクティビティを作成する](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)際にアクティビティ URL の入力を求められたら、URL を指定します。完全な URL （`https://` を含む）を入力し、「**[!UICONTROL Create Activity]**」をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `https://www.adobe.com`] と [!DNL `http://www.adobe.com`] の両方が一致します。
   >
   >デフォルトでは、VEC または [ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) は、[Visual Experience Composer 設定 ](/help/main/administrating-target/visual-experience-composer-set-up.md) で指定されているページを開きます。 アクティビティ作成中に、異なるページを指定することもできます。
   >
   >[[!DNL Target] at.js JavaScript ライブラリまたは  [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html?lang=ja){target=_blank} を含まないサイトの URL を指定した場合、ページ要素を選択できません。

1. （条件付き） VEC が開いた後に別のページを表示するには、「**[!UICONTROL Configure]**」をクリックして「**[!UICONTROL Page Delivery]**」を選択し、「[!UICONTROL URL]」フィールドで URL を指定します。

   >[!NOTE]
   >
   >1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。

1. （条件付き） **[!UICONTROL Add Rule]** をクリックして、アクティビティにさらにページまたはセクションを追加します。

   追加のルールは、以下のいずれかに基づいています。

   * URL
   * ドメイン
   * パス
   * ハッシュ（#）フラグメント
   * クエリ
   * mbox パラメーター

   追加のルールは、AND または OR を使用してアクティビティ URL と結合できます。追加したすべてのルールは、AND を使用してお互いに評価されます。

1. 完了したら「**[!UICONTROL Save]**」をクリックします。
