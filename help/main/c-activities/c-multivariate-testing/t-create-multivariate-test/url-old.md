---
keywords: 多変量テスト；アクティビティ URL
description: '[!UICONTROL 多変量テスト ] アクティビティが [!DNL Adobe Target]を使用して設計されたときに開く、テストで使用されるページを決定するアクティビティ URLを指定する方法を説明します。'
title: '[!UICONTROL 多変量テスト ] （MVT）アクティビティのアクティビティ URLは何ですか？'
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 45%

---

# アクティビティ URL

アクティビティ URLにより、[!UICONTROL 多変量テスト ] （MVT）で使用され、[!DNL Adobe Target]でテストが設計されたときに開くページが決まります。

[アクティビティ作成](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)中にアクティビティ URL の入力を求められたら、URL を指定します。 完全なURL （`https://`を含む）を入力し、**[!UICONTROL 次へ]**&#x200B;をクリックします。

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。 結果、[!DNL `https://www.adobe.com`]と[!DNL `http://www.adobe.com`]は両方とも一致します。

デフォルトでは、[!UICONTROL Visual Experience Composer] （VEC）は[Visual Experience Composer設定](/help/main/administrating-target/visual-experience-composer-set-up.md)で指定されたページを開きます。 アクティビティ作成中に、異なるページを指定することもできます。

VECが開いた後に別のページを表示するには、**[!UICONTROL 設定]** アイコンをクリックし、**[!UICONTROL ページ配信]**&#x200B;を選択してから、URLを指定します。

![ページ配信ダイアログボックス](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

アクティビティにさらにページまたはセクションを追加するには、「**[!UICONTROL テンプレートルールを追加]**」をクリックします。

追加のルールは、以下のいずれかに基づいています。

* URL
* ドメイン
* パス
* ハッシュ（#）フラグメント
* クエリ
* パラメーター

追加のルールは、ANDまたはORを使用してアクティビティ URLに結合できます。 追加したすべてのルールは、ANDを使用して相互に評価されます。

終了したら「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>[!DNL Target] JavaScript コードを含まないサイトのURLを入力した場合、ページ要素を選択することはできません。

デフォルトでは、バナーの回転など JavaScript を含む要素については、VEC で変更できません。 [!UICONTROL Visual Experience Composer] を使用してこのような要素を変更するには、「**[!UICONTROL JavaScript を使用してレンダリング]**」をオフにします。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。
