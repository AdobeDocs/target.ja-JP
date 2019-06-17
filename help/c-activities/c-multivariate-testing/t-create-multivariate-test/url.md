---
description: アクティビティURLは、多変量分析テスト（MVT）で使用され、テストがTargetでデザインされたときに開くページを決定します。
keywords: ターゲット設定
seo-description: アクティビティURLは、多変量分析テスト（MVT）で使用されるページ、およびテストがAdobe Targetでデザインされたときに表示されます。
seo-title: アクティビティ URL
solution: 'Target '
title: アクティビティ URL
uuid: ddc7330c-199a-4e38-b3d4-6786e3997783
translation-type: tm+mt
source-git-commit: 0730d5f8f6aa2b72c2069c81d6e5a0183489e91c

---


# アクティビティ URL{#activity-url}

アクティビティURLは [!M、&quot;Ultiavatate Test] （MVT）」で使用され、テストが設計されたときに開くページを決定 [!DNL Adobe Target]します。

[アクティビティの作成](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)中に、アクティビティURLを指定します。完全なURL（を含む `https://`）を入力し、「 **[!UICONTROL 次へ]**」をクリックします。

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `https://www.adobe.com`] と [!DNL `http://www.adobe.com`] の両方が一致します。

デフォルトで [!UICONTROL は、Visual Experience Composer] （VEC）は [、アカウント環境設定で指定されたページを開き](/help/administrating-target/r-target-account-preferences/target-account-preferences.md)ます。アクティビティ作成中に、異なるページを指定することもできます。

VECを開いた後に異なるページを表示するには **[!UICONTROL 、設定]** アイコンをクリックし、「ページ配信 **[!UICONTROL 」を選択]** してURLを指定します。

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

デフォルトでは、バナーの回転などJavaScriptを含む要素に対する変更は許可されません。**[!UICONTROL Visual Experience Composer]を使用してこのような要素を変更するには、「**[!UICONTROL JavaScript を使用してレンダリング]」をオフにします。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。