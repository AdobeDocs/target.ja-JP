---
description: アクティビティURLは、多変量分析テスト（MVT）で使用され、テストがTargetでデザインされたときに開くページを決定します。
keywords: ターゲット設定
seo-description: アクティビティURLは、多変量分析テスト（MVT）で使用されるページ、およびテストがAdobe Targetでデザインされたときに表示されます。
seo-title: アクティビティ URL
solution: 'Target '
title: アクティビティ URL
uuid: ddc7330c-199a-4e38-b3d4-6786e3997783
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# アクティビティ URL{#activity-url}

The activity URL determines the page that is used in the [!UICONTROL Multivariate Test] (MVT), and that opens when the test is designed in [!DNL Adobe Target].

[アクティビティの作成](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)中に、アクティビティURLを指定します。Type the complete URL (including `https://`), then click **[!UICONTROL Next]**.

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `https://www.adobe.com`] と [!DNL `http://www.adobe.com`] の両方が一致します。

By default, the [!UICONTROL Visual Experience Composer] (VEC) opens the page that is specified in your [Account Preferences](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). アクティビティ作成中に、異なるページを指定することもできます。

To display a different page after the VEC opens, click the **[!UICONTROL Configure]** icon, then select **[!UICONTROL Page Delivery]**, then specify the URL.

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