---
keywords: 多変量分析テスト；アクティビティ URL
description: テストで使用され、 [!UICONTROL 多変量分析テスト] アクティビティは [!DNL Adobe Target].
title: アクティビティ URL とは [!UICONTROL 多変量分析テスト] (MVT) アクティビティ
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 7853d8c5934e40d1026e067dfa413f520ecba931
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 77%

---

# アクティビティ URL

アクティビティ URL は、[!UICONTROL 多変量分析テスト]（MVT）で使用され、[!DNL Adobe Target] でテストが設計された場合に表示されるページを指定します。

[アクティビティ作成](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)中にアクティビティ URL の入力を求められたら、URL を指定します。`https://` を含む完全な URL を入力して、「**[!UICONTROL 次へ]**」をクリックします。

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `https://www.adobe.com`] と [!DNL `http://www.adobe.com`] の両方が一致します。

デフォルトでは、[!UICONTROL Visual Experience Composer]（VEC）は [Visual Experience Composer 設定](/help/main/administrating-target/visual-experience-composer-set-up.md)で指定されているページを開きます。アクティビティ作成中に、異なるページを指定することもできます。

VEC を開いた後に異なるページを表示するには、「**[!UICONTROL 設定]**」アイコンをクリックして「**[!UICONTROL ページ配信]**」を選択し、URL を指定します。

![ページ配信ダイアログボックス](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

アクティビティにさらにページまたはセクションを追加するには、「**[!UICONTROL テンプレートルールを追加]**」をクリックします。

追加のルールは、以下のいずれかに基づいています。

* URL
* ドメイン
* パス
* ハッシュ（#）フラグメント
* クエリ
* パラメーター

追加のルールを、AND または OR でアクティビティ URL に結合できます。 追加するすべてのルールは、AND を使用して互いに評価されます。

終了したら「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
> の JavaScript コードを含まないサイトの URL を入力すると、ページ要素を選択できません。[!DNL Target]

デフォルトでは、バナーの回転など JavaScript を含む要素については、VEC で変更できません。**[!UICONTROL Visual Experience Composer]** を使用してこのような要素を変更するには、「[!UICONTROL JavaScript を使用してレンダリング]」をオフにします。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。
