---
keywords: アクティビティ url;url；別の url
description: テストページを定義し、正確なテスト設計を確実に行うための [!UICONTROL Activity URL] の設定方法を説明します。
title: A/B アクティビティ内のアクティビティ URL は何ですか？
feature: A/B Tests
hide: true
hidefromtoc: true
source-git-commit: 6e9d18b8347d8ae68be699640c4cde91bdec762c
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 40%

---

# アクティビティ URL

アクティビティ URL は、テストで使用され、[!DNL Adobe Target] を使用したテストの設計時に開くページを決定します。

アクティビティ作成中にアクティビティ URL の入力を求められたら、URL を指定します。完全な URL （`https://` を含む）を入力し、「**[!UICONTROL Create]**」をクリックします。

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `http://www.adobe.com`] と [!DNL `https://www.adobe.com`] の両方が一致します。

## 異なる URL の指定

デフォルトでは、[!UICONTROL Visual Experience Composer] は [Visual Experience Composer 設定 ](/help/main/administrating-target/visual-experience-composer-set-up.md) で指定されているページを開きます。 アクティビティ作成中に、異なるページを指定することもできます。

1. [!UICONTROL Visual Experience Composer] ージを開いた後に別のページを表示するには、**[!UICONTROL Experiences]** のページで、ページの上部にある [**[!UICONTROL Configure]**] をクリックし、[**[!UICONTROL Page Delivery]**] を選択します。

1. **[!UICONTROL URL]** フィールドに URL を指定します。

1. （条件付き） **[!UICONTROL Add Rule]** をクリックして、アクティビティにさらにページまたはセクションを追加します。

   追加のルールは、以下のいずれかに基づいています。

   * URL
   * ドメイン
   * パス
   * ハッシュ（#）フラグメント
   * クエリ
   * mbox パラメーター

   追加のルールは、AND または OR を使用してアクティビティ URL に結合できます。 追加したすべてのルールは、AND を使用してお互いに評価されます。

1. 完了したら「**[!UICONTROL Save]**」をクリックします。

<!-- If you entered a URL for a site that does not include the [!DNL Target]s JavaScript code, you cannot select page elements.

By default, the [!UICONTROL Visual Experience Composer] does not allow changes to elements containing JavaScript, such as rotating banners. You can toggle off **[!UICONTROL Render using JavaScript]** if you want to be able to alter those elements using the [!UICONTROL Visual Experience Composer].-->

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。