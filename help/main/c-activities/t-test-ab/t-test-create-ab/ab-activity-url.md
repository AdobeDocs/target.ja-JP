---
keywords: アクティビティ url;url；別のurl
description: A/B、エクスペリエンスのターゲット設定、または多変量テスト アクティビティで[!UICONTROL &#x200B; アクティビティ URL]を設定して、テスト ページを定義し、正確なテスト デザインを確保する方法を説明します。
title: A/B、エクスペリエンスのターゲット設定、または多変量テストアクティビティのアクティビティ URLは何ですか？
feature: A/B Tests
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
reason: republish
TQID: 'https://experienceleague.adobe.com/arQWsSfBKYtrayq9AI8ejU1T-Uor-oL5j2Sp2JKKXZE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aad553690f1f399177214c94a2276d038f46d9cb
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 25%
---
# アクティビティ URL {#ab-activity-url}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、A/B、エクスペリエンスのターゲット設定（XT）、多変量テスト（MVT）アクティビティのアクティビティ URLを指定する方法、別のページを表示する方法、より多くのページやセクションにルールを追加する方法について説明します。

>[!ENDSHADEBOX]

[!UICONTROL &#x200B; アクティビティ URL]によって、アクティビティで使用されるページが決まります。 これは、[!UICONTROL Visual Experience Composer] （VEC）または[!UICONTROL &#x200B; フォームベースのExperience Composer]で開くページで、[!DNL Adobe Target]でアクティビティが設計されている場合に表示されます。

## アクティビティ URLを指定 {#specify-url}

アクティビティ作成中にアクティビティ URL の入力を求められたら、URL を指定します。 完全なURL （`https://`を含む）を入力し、**[!UICONTROL 作成]**&#x200B;をクリックします。

>[!NOTE]
>
>[!DNL Target]は、URL プロトコル （[!DNL https]と[!DNL http]）を区別しません。 結果、[!DNL `http://www.adobe.com`]と[!DNL `https://www.adobe.com`]は両方とも一致します。

[!DNL Target] [at.js JavaScript ライブラリまたは [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html){target=_blank}を含まないサイトのURLを指定した場合、ページ要素を選択することはできません。

## 別のページを表示 {#different-page}

デフォルトでは、VECまたは[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)は、[Visual Experience Composer設定](/help/main/administrating-target/visual-experience-composer-set-up.md)で指定されたページを開きます。 アクティビティ作成中に、異なるページを指定することもできます。

VECが開いた後に別のページを表示するには：

1. **[!UICONTROL エクスペリエンス]** ページで、ページの上部にある&#x200B;**[!UICONTROL 設定]**&#x200B;をクリックし、**[!UICONTROL ページ配信]**&#x200B;を選択します。

1. 「**[!UICONTROL URL]**」フィールドにURLを指定します。

1. 終了したら「**[!UICONTROL 保存]**」をクリックします。

デフォルトでは、バナーの回転など JavaScript を含む要素については、VEC で変更できません。 VECを使用してこれらの要素を変更する場合は、**[!UICONTROL JavaScriptを使用したレンダリング]**&#x200B;をオフに切り替えることができます。

>[!NOTE]
>
>1 つ以上のエクスペリエンスに対してページに変更を加えた後、URL を変更すると、エクスペリエンスは新しいページを使用してリセットされ、おこなった変更が失われます。

## その他のページまたはセクションのルールを追加 {#add-rules}

アクティビティにページまたはセクションをさらに追加するには、**[!UICONTROL ページ配信]**&#x200B;設定の&#x200B;**[!UICONTROL ルールを追加]**&#x200B;をクリックし、完了したら&#x200B;**[!UICONTROL 保存]**&#x200B;をクリックします。

追加のルールは、以下のいずれかに基づいています。

* URL
* ドメイン
* パス
* ハッシュ（#）フラグメント
* クエリ
* mbox パラメーター
* カスタム

追加のルールは、ANDまたはORを使用してアクティビティ URLに結合できます。 追加したすべてのルールは、AND を使用してお互いに評価されます。
