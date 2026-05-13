---
keywords: 多変量テスト；アクティビティ URL
description: テストで使用され、[!UICONTROL Multivariate Test] アクティビティが [!DNL Adobe Target]を使用して設計されたときに開くページを決定するアクティビティ URLを指定する方法を説明します。
title: '[!UICONTROL Multivariate Test] （MVT） アクティビティのアクティビティ URLは何ですか？'
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
TQID: https://experienceleague.adobe.com/oQKwrlZ95XKEKSJIUiWqXXo9AJJzCb20gfS1rtwGImM
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 269
ht-degree: 31%

---

# アクティビティ URL

アクティビティ URLは、[!UICONTROL Multivariate Test] （MVT）で使用され、[!DNL Adobe Target]でテストが設計されたときに開くページを決定します。

1. [アクティビティ作成](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)中にアクティビティ URL の入力を求められたら、URL を指定します。 完全なURL （`https://`を含む）を入力し、**[!UICONTROL Create]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。 結果、[!DNL `https://www.adobe.com`]と[!DNL `http://www.adobe.com`]は両方とも一致します。

   デフォルトでは、[!UICONTROL Visual Experience Composer] （VEC）は[Visual Experience Composer設定](/help/main/administrating-target/visual-experience-composer-set-up.md)で指定されたページを開きます。 アクティビティ作成中に、異なるページを指定することもできます。

1. （条件付き） VECが開いた後に別のページを表示するには、**[!UICONTROL Configure]** アイコンをクリックしてから&#x200B;**[!UICONTROL Page Delivery]**&#x200B;を選択し、URLを指定します。

1. （条件付き） **[!UICONTROL Add Rule]**&#x200B;をクリックして、アクティビティにページまたはセクションを追加します。

   追加のルールは、以下のいずれかに基づいています。

   * [!UICONTROL  URL]
   * [!UICONTROL Domain]
   * [!UICONTROL Path]
   * [!UICONTROL Hash (#) Fragment]
   * [!UICONTROL Query]
   * [!UICONTROL Custom]

   追加のルールは、ANDまたはORを使用してアクティビティ URLに結合できます。 追加したすべてのルールは、ANDを使用して相互に評価されます。

   完了したら、**[!UICONTROL Save]**&#x200B;をクリックします。

>[!NOTE]
>
>[!DNL Target] JavaScript コードを含まないサイトのURLを入力した場合、ページ要素を選択することはできません。
>
>デフォルトでは、バナーの回転など JavaScript を含む要素については、VEC で変更できません。 [!UICONTROL Visual Experience Composer]を使用してこれらの要素を変更する場合は、**[!UICONTROL Render using JavaScript]**&#x200B;をオフに切り替えることができます。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。
