---
keywords: アクティビティ url;url；別のurl
description: '[!UICONTROL Activity URL]を設定してテストページを定義し、正確なテスト設計を確保する方法を説明します。'
title: A/B アクティビティのアクティビティ URLは何ですか？
feature: A/B Tests
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
reason: republish
TQID: https://experienceleague.adobe.com/arQWsSfBKYtrayq9AI8ejU1T-Uor-oL5j2Sp2JKKXZE
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 32%

---

# アクティビティ URL

アクティビティ URLは、テストで使用され、[!DNL Adobe Target]を使用してテストを設計するときに開くページを決定します。

アクティビティ作成中にアクティビティ URL の入力を求められたら、URL を指定します。 完全なURL （`https://`を含む）を入力し、**[!UICONTROL Create]**&#x200B;をクリックします。

>[!NOTE]
>
>[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。 結果、[!DNL `http://www.adobe.com`]と[!DNL `https://www.adobe.com`]は両方とも一致します。

## 異なる URL の指定

デフォルトでは、[!UICONTROL Visual Experience Composer]は[Visual Experience Composer設定](/help/main/administrating-target/visual-experience-composer-set-up.md)で指定されたページを開きます。 アクティビティ作成中に、異なるページを指定することもできます。

1. （条件付き） [!UICONTROL Visual Experience Composer]が開いた後に別のページを表示するには、**[!UICONTROL Experiences]** ページで、ページの上部にある&#x200B;**[!UICONTROL Configure]**&#x200B;をクリックし、**[!UICONTROL Page Delivery]**&#x200B;を選択します。

1. **[!UICONTROL URL]** フィールドにURLを指定します。

1. （条件付き） **[!UICONTROL Add Rule]**&#x200B;をクリックして、アクティビティにページまたはセクションを追加します。

   追加のルールは、以下のいずれかに基づいています。

   * URL
   * ドメイン
   * パス
   * ハッシュ（#）フラグメント
   * クエリ
   * mbox パラメーター
   * カスタム

   追加のルールは、ANDまたはORを使用してアクティビティ URLに結合できます。 追加したすべてのルールは、AND を使用してお互いに評価されます。

1. 完了したら、**[!UICONTROL Save]**&#x200B;をクリックします。

   [!DNL Target]s JavaScript コードを含まないサイトのURLを入力した場合、ページ要素を選択することはできません。

   デフォルトでは、[!UICONTROL Visual Experience Composer]は、バナーの回転など、JavaScriptを含む要素への変更を許可しません。 [!UICONTROL Visual Experience Composer]を使用してこれらの要素を変更する場合は、**[!UICONTROL Render using JavaScript]**&#x200B;をオフに切り替えることができます。—>

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。
