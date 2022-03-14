---
keywords: アクティビティ url;url；別の url
description: Adobe Targetを使用してテストを設計した場合に、テストで使用され、開くページを決定するアクティビティ URL を指定する方法について説明します。
title: A/B アクティビティのアクティビティ URL とは何ですか？
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 73%

---

# アクティビティ URL

アクティビティ URL は、Adobe Targetを使用して設計されたテストで、テストで使用され、開くページを指定します。

アクティビティ作成中にアクティビティ URL の入力を求められたら、URL を指定します。`https://` を含む完全な URL を入力して、「**[!UICONTROL 作成]**」をクリックします。

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `http://www.adobe.com`] と [!DNL `https://www.adobe.com`] の両方が一致します。

## 異なる URL の指定

デフォルトでは、 [!UICONTROL Visual Experience Composer] は、 [Visual Experience Composer の設定](/help/main/administrating-target/visual-experience-composer-set-up.md)
. アクティビティ作成中に、異なるページを指定することもできます。

[!UICONTROL Visual Experience Composer] を開いた後に異なるページを表示するには、**[!UICONTROL 設定]**&#x200B;の歯車アイコンをクリックして、「**[!UICONTROL ページ配信」を選択します。]**「アクティビティ URL」フィールドに URL を入力します。

![ページ配信ダイアログボックス](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

アクティビティにさらにページまたはセクションを追加するには、「**[!UICONTROL テンプレートルールを追加]**」をクリックします。

追加のルールは、以下のいずれかに基づいています。

* URL
* ドメイン
* パス
* ハッシュ（#）フラグメント
* クエリ
* mbox パラメーター

追加のルールは、AND または OR を使用してアクティビティ URL と結合できます。追加したすべてのルールは、AND を使用してお互いに評価されます。

終了したら「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>Standard の JavaScript コードを含まないサイトの URL を入力すると、ページ要素を選択できません。[!DNL Target]

デフォルトでは、バナーの回転など JavaScript を含む要素については、[!UICONTROL Visual Experience Composer] で変更できません。**[!UICONTROL Visual Experience Composer]** を使用してこのような要素を変更するには、「[!UICONTROL JavaScript を使用してレンダリング]」をオフにします。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。
