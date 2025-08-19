---
keywords: 多変量分析テスト；アクティビティ URL
description: テストで使用され、[!UICONTROL Multivariate Test] しいアクティビティが  [!DNL Adobe Target] を使用して設計されたときに開くページを決定するアクティビティ URL を指定する方法を説明します。
title: '[!UICONTROL Multivariate Test] （MVT）アクティビティのアクティビティ URL とは何ですか？'
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 31%

---

# アクティビティ URL

アクティビティ URL は、[!UICONTROL Multivariate Test] （MVT）で使用され、テストが [!DNL Adobe Target] でデザインされる際に開くページを決定します。

1. [アクティビティ作成](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)中にアクティビティ URL の入力を求められたら、URL を指定します。完全な URL （`https://` を含む）を入力し、「**[!UICONTROL Create]**」をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `https://www.adobe.com`] と [!DNL `http://www.adobe.com`] の両方が一致します。

   デフォルトでは、[!UICONTROL Visual Experience Composer] （VEC）は [Visual Experience Composer 設定 ](/help/main/administrating-target/visual-experience-composer-set-up.md) で指定されているページを開きます。 アクティビティ作成中に、異なるページを指定することもできます。

1. （条件付き） VEC が開いた後に別のページを表示するには、「**[!UICONTROL Configure]**」アイコンをクリックして「**[!UICONTROL Page Delivery]**」を選択し、URL を指定します。

1. （条件付き） **[!UICONTROL Add Rule]** をクリックして、アクティビティにさらにページまたはセクションを追加します。

   追加のルールは、以下のいずれかに基づいています。

   * [!UICONTROL &#x200B; URL]
   * [!UICONTROL Domain]
   * [!UICONTROL Path]
   * [!UICONTROL Hash (#) Fragment]
   * [!UICONTROL Query]
   * [!UICONTROL Custom]

   追加のルールは、AND または OR を使用してアクティビティ URL に結合できます。 追加したすべてのルールは、AND で相互に評価されます。

   完了したら「**[!UICONTROL Save]**」をクリックします。

>[!NOTE]
>
>[!DNL Target] JavaScript コードを含まないサイトの URL を入力した場合は、ページ要素を選択できません。
>
>デフォルトでは、バナーの回転など JavaScript を含む要素については、VEC で変更できません。**[!UICONTROL Render using JavaScript]** を使用してこれらの要素を変更できるようにする場合は、[!UICONTROL Visual Experience Composer] をオフに切り替えることができます。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。
