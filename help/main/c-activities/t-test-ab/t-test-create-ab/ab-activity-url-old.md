---
keywords: アクティビティ url;url；別のurl
description: テストで使用され、 [!DNL Adobe Target]を使用してテストが設計されたときに開くページを決定するアクティビティ URLを指定する方法を説明します。
title: A/B アクティビティのアクティビティ URLは何ですか？
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 55%

---

# アクティビティ URL

アクティビティ URLは、テストで使用され、テストがAdobe Targetを使用して設計されたときに開くページを決定します。

アクティビティ作成中にアクティビティ URL の入力を求められたら、URL を指定します。 完全なURL （`https://`を含む）を入力し、**[!UICONTROL 作成]**&#x200B;をクリックします。

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。 結果、[!DNL `http://www.adobe.com`]と[!DNL `https://www.adobe.com`]は両方とも一致します。

## 異なる URL の指定

デフォルトでは、[!UICONTROL Visual Experience Composer]は[Visual Experience Composer設定](/help/main/administrating-target/visual-experience-composer-set-up.md)で指定されたページを開きます。 アクティビティ作成中に、異なるページを指定することもできます。

1. [!UICONTROL Visual Experience Composer]が開いた後に別のページを表示するには、**[!UICONTROL Experiences]** ページで、**[!UICONTROL Configure]** ギアアイコンをクリックし、**[!UICONTROL Page Delivery]**&#x200B;を選択します。

1. 「**[!UICONTROL URL]**」フィールドにURLを指定します。

   ![ページ配信ダイアログボックス](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

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

Standard の JavaScript コードを含まないサイトの URL を入力すると、ページ要素を選択できません。[!DNL Target]

デフォルトでは、バナーの回転など JavaScript を含む要素については、[!UICONTROL Visual Experience Composer] で変更できません。 [!UICONTROL Visual Experience Composer] を使用してこのような要素を変更するには、「**[!UICONTROL JavaScript を使用してレンダリング]**」をオフにします。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。
