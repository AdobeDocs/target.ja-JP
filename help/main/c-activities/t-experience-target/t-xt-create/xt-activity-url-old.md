---
keywords: エクスペリエンスのターゲット設定；xt；アクティビティ url;url
description: テストで使用され、[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] アクティビティが [!DNL Adobe Target]を使用して設計されたときに開くページを決定する[!UICONTROL &#x200B; アクティビティ URL]を指定する方法を説明します。
title: '[!UICONTROL &#x200B; エクスペリエンスターゲティング &#x200B;] （XT）アクティビティの[!UICONTROL &#x200B; アクティビティ URL]とは何ですか？'
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 36%

---

# [!UICONTROL Experience Targeting] （XT） アクティビティのアクティビティ URL

[!UICONTROL &#x200B; アクティビティ URL]は、[!DNL Adobe Target] [!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （XT） アクティビティで使用されるページを決定します。 これは、アクティビティの設計時に[!UICONTROL Visual Experience Composer] （VEC）または[!UICONTROL &#x200B; フォームベース Experience Composer]で開くページです。

1. [XT アクティビティを作成する](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)際にアクティビティ URL の入力を求められたら、URL を指定します。 完全なURL （`https://`を含む）を入力し、**[!UICONTROL アクティビティの作成]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。 結果、[!DNL `https://www.adobe.com`]と[!DNL `http://www.adobe.com`]は両方とも一致します。
   >
   >デフォルトでは、VECまたは[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)は、[Visual Experience Composer設定](/help/main/administrating-target/visual-experience-composer-set-up.md)で指定されたページを開きます。 アクティビティ作成中に、異なるページを指定することもできます。
   >
   >[[!DNL Target] at.js JavaScript ライブラリまたは [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html?lang=ja){target=_blank}を含まないサイトのURLを指定した場合、ページ要素を選択することはできません。

1. （条件付き） VECが開いた後に別のページを表示するには、**[!UICONTROL 設定]**&#x200B;をクリックし、**[!UICONTROL ページ配信]**&#x200B;を選択してから、[!UICONTROL URL] フィールドにURLを指定します。

   ![ページ配信ダイアログボックス](/help/main/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。

1. （条件付き）「**[!UICONTROL テンプレートルールを追加]**」をクリックして、アクティビティにページまたはセクションを追加します。

   追加のルールは、以下のいずれかに基づいています。

   * URL
   * ドメイン
   * パス
   * ハッシュ（#）フラグメント
   * クエリ
   * mbox パラメーター

   追加のルールは、AND または OR を使用してアクティビティ URL と結合できます。 追加したすべてのルールは、AND を使用してお互いに評価されます。

1. 終了したら「**[!UICONTROL 保存]**」をクリックします。
