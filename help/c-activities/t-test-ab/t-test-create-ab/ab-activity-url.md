---
keywords: 概要およびリファレンス
description: アクティビティ URL は、テストで使用され、設計したテストで表示されるページを指定します。
title: アクティビティ URL
topic: Standard
uuid: 65489969-d548-4286-858f-8420120317c0
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# アクティビティ URL{#activity-url}

アクティビティ URL は、テストで使用され、設計したテストで表示されるページを指定します。

アクティビティ作成中にアクティビティ URL の入力を求められたら、URL を指定します。`https://` を含む完全な URL を入力して、「**[!UICONTROL 作成]**」をクリックします。

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `http://www.adobe.com`] と [!DNL `https://www.adobe.com`] の両方が一致します。

## 異なる URL の指定

デフォルトでは、[Target のアカウントの基本設定](/help/administrating-target/r-target-account-preferences/target-account-preferences.md)で指定されたページが [!UICONTROL Visual Experience Composer] で開かれます。アクティビティ作成中に、異なるページを指定することもできます。

[!UICONTROL Visual Experience Composer] を開いた後に異なるページを表示するには、**[!UICONTROL 設定]**&#x200B;の歯車アイコンをクリックして、「**[!UICONTROL ページ配信**」を選択します。]「アクティビティ URL」フィールドに URL を入力します。

![ページ配信ダイアログボックス](/help/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

アクティビティにさらにページまたはセクションを追加するには、「**[!UICONTROL テンプレートルールを追加]**」をクリックします。

追加のルールは、以下のいずれかに基づいています。

* URL
* ドメイン
* パス
* ハッシュ（#）フラグメント
* クエリ
* mbox パラメーター

追加のルールは、AND または OR を使用してアクティビティ URL と結合できます。追加したすべてのルールは、AND を使用してお互いに評価されます。

終了したら「**[!UICONTROL 保存]」をクリックします。**

>[!NOTE]
>
>Standard の JavaScript コードを含まないサイトの URL を入力すると、ページ要素を選択できません。[!DNL Target]

デフォルトでは、バナーの回転など JavaScript を含む要素については、[!UICONTROL Visual Experience Composer] で変更できません。**[!UICONTROL Visual Experience Composer]を使用してこのような要素を変更するには、「**[!UICONTROL JavaScript を使用してレンダリング]」をオフにします。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。
