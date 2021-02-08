---
keywords: 多変量分析テスト；アクティビティURL
description: Adobe Targetを使用して多変量分析テストアクティビティをデザインした場合に、テストで使用され、開くページを決定するアクティビティURLを指定する方法について説明します。
title: 多変量分析(MVT)アクティビティのアクティビティURLとは何ですか。
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 79%

---


# アクティビティ URL{#activity-url}

アクティビティ URL は、[!UICONTROL 多変量分析テスト]（MVT）で使用され、[!DNL Adobe Target] でテストが設計された場合に表示されるページを指定します。

[アクティビティ作成](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)中にアクティビティ URL の入力を求められたら、URL を指定します。`https://` を含む完全な URL を入力して、「**[!UICONTROL 次へ]**」をクリックします。

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `https://www.adobe.com`] と [!DNL `http://www.adobe.com`] の両方が一致します。

デフォルトでは、[!UICONTROL Visual Experience Composer](VEC)は、[Visual Experience Composerの設定](/help/administrating-target/visual-experience-composer-set-up.md)で指定されたページを開きます。 アクティビティ作成中に、異なるページを指定することもできます。

VEC を開いた後に異なるページを表示するには、「**[!UICONTROL 設定]**」アイコンをクリックして「**[!UICONTROL ページ配信]**」を選択し、URL を指定します。

![ページ配信ダイアログボックス](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

アクティビティにさらにページまたはセクションを追加するには、「**[!UICONTROL テンプレートルールを追加]**」をクリックします。

追加のルールは、以下のいずれかに基づいています。

* URL
* ドメイン
* パス
* ハッシュ（#）フラグメント
* クエリ
* パラメーター

追加のルールは、AND または OR を使用してアクティビティ URL と結合できます。追加したすべてのルールは、AND を使用してお互いに評価されます。

終了したら「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>Target Standard の JavaScript コードを含まないサイトの URL を入力すると、ページ要素を選択できません。

デフォルトでは、バナーの回転など JavaScript を含む要素については、VEC で変更できません。**[!UICONTROL Visual Experience Composer]** を使用してこのような要素を変更するには、「[!UICONTROL JavaScript を使用してレンダリング]」をオフにします。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。