---
keywords: エクスペリエンスのターゲット設定；xt；アクティビティ url;url
description: テストで使用され、[!UICONTROL  エクスペリエンスのターゲット設定] アクティビティが [!DNL Adobe Target]を使用して設計されたときに開くページを決定する[!UICONTROL  アクティビティ URL]を指定する方法を説明します。
title: '[!UICONTROL  エクスペリエンスターゲティング ] （XT）アクティビティの[!UICONTROL  アクティビティ URL]とは何ですか？'
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
TQID: https://experienceleague.adobe.com/igvyk-2atEe7JdYuFj3IXlXyE1CzVkLuwv50DSmSxuY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 35%

---

# [!UICONTROL Experience Targeting] （XT） アクティビティのアクティビティ URL

[!UICONTROL  アクティビティ URL]は、[!DNL Adobe Target] [!UICONTROL  エクスペリエンスのターゲット設定] （XT） アクティビティで使用されるページを決定します。 これは、アクティビティの設計時に[!UICONTROL Visual Experience Composer] （VEC）または[!UICONTROL  フォームベース Experience Composer]で開くページです。

1. [XT アクティビティを作成する](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)際にアクティビティ URL の入力を求められたら、URL を指定します。 完全なURL （`https://`を含む）を入力し、**[!UICONTROL アクティビティの作成]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。 結果、[!DNL `https://www.adobe.com`]と[!DNL `http://www.adobe.com`]は両方とも一致します。
   >
   >デフォルトでは、VECまたは[ フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)は、[Visual Experience Composer設定](/help/main/administrating-target/visual-experience-composer-set-up.md)で指定されたページを開きます。 アクティビティ作成中に、異なるページを指定することもできます。
   >
   >[[!DNL Target] at.js JavaScript ライブラリまたは [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html){target=_blank}を含まないサイトのURLを指定した場合、ページ要素を選択することはできません。

1. （条件付き） VECが開いた後に別のページを表示するには、**[!UICONTROL 設定]**&#x200B;をクリックし、**[!UICONTROL ページ配信]**&#x200B;を選択してから、[!UICONTROL URL] フィールドにURLを指定します。

   >[!NOTE]
   >
   >1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。

1. （条件付き）「**[!UICONTROL ルールを追加]**」をクリックして、アクティビティにページまたはセクションを追加します。

   追加のルールは、以下のいずれかに基づいています。

   * URL
   * ドメイン
   * パス
   * ハッシュ（#）フラグメント
   * クエリ
   * mbox パラメーター

   追加のルールは、AND または OR を使用してアクティビティ URL と結合できます。 追加したすべてのルールは、AND を使用してお互いに評価されます。

1. 終了したら「**[!UICONTROL 保存]**」をクリックします。
