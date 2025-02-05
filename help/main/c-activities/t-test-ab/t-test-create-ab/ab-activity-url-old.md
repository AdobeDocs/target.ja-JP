---
keywords: アクティビティ url;url；別の url
description: テストで使用され、 [!DNL Adobe Target] を使用してテストをデザインしたときに開くページを決定するアクティビティ URL を指定する方法について説明します。
title: A/B アクティビティ内のアクティビティ URL は何ですか？
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 44%

---

# アクティビティ URL

アクティビティ URL は、テストで使用され、Adobe Targetを使用したテストの設計時に開くページを特定します。

アクティビティ作成中にアクティビティ URL の入力を求められたら、URL を指定します。完全な URL （`https://` を含む）を入力し、「**[!UICONTROL Create]**」をクリックします。

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `http://www.adobe.com`] と [!DNL `https://www.adobe.com`] の両方が一致します。

## 異なる URL の指定

デフォルトでは、[!UICONTROL Visual Experience Composer] は [Visual Experience Composer 設定 ](/help/main/administrating-target/visual-experience-composer-set-up.md) で指定されているページを開きます。 アクティビティ作成中に、異なるページを指定することもできます。

1. [!UICONTROL Visual Experience Composer] ージを開いた後に別のページを表示するには、**[!UICONTROL Experiences]** のページで **[!UICONTROL Configure]** 歯車アイコンをクリックし、「**[!UICONTROL Page Delivery]**」を選択します。

1. **[!UICONTROL URL]** フィールドに URL を指定します。

   ![ページ配信ダイアログボックス](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

1. （条件付き） **[!UICONTROL Add Template Rule]** をクリックして、アクティビティにさらにページまたはセクションを追加します。

   追加のルールは、以下のいずれかに基づいています。

   * URL
   * ドメイン
   * パス
   * ハッシュ（#）フラグメント
   * クエリ
   * mbox パラメーター

   追加のルールは、AND または OR を使用してアクティビティ URL と結合できます。追加したすべてのルールは、AND を使用してお互いに評価されます。

1. 完了したら「**[!UICONTROL Save]**」をクリックします。

Standard の JavaScript コードを含まないサイトの URL を入力すると、ページ要素を選択できません。[!DNL Target]

デフォルトでは、バナーの回転など、JavaScriptを含む要素を変 [!UICONTROL Visual Experience Composer] することはできません。 [!UICONTROL Visual Experience Composer] を使用してこれらの要素を変更できるようにする場合は、**[!UICONTROL Render using JavaScript]** をオフに切り替えることができます。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。
