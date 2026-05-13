---
keywords: 重複排除；重複を許可；重複するオファーを除外；自動パーソナライゼーション；重複するオファーを許可しない；除外；デフォルトコンテンツ；
description: '[!UICONTROL Automated Personalization] （AP） アクティビティの除外を管理します。'
title: '[!UICONTROL Automated Personalization] アクティビティの除外を管理するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
TQID: https://experienceleague.adobe.com/ERpNwQPsIRBmU0vTZbGa-lYg30BYl-uJxA8UT0f6060
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 492
ht-degree: 25%

---

# 除外の管理

除外を管理することで、[!UICONTROL Automated Personalization] （AP）戦略を管理します。 重複するオファーの作成、エクスペリエンスの組み合わせの改善、デフォルトのコンテンツの削除など、目標やオーディエンスの期待に沿って、よりクリーンで関連性の高いエクスペリエンスを提供するための除外機能を利用できます。

## 重複するオファーを許可または禁止 {#concept_4EF78013F80E48EFA024AE0274C9F037}

AP アクティビティの異なる場所で使用する場合、オファーライブラリのオファーが重複するのを防ぎます。

例えば、ページ上で 6 つのロケーションと 12 件のオファーがあるアクティビティがあるとします。 同じオファーがアクティビティ内の 1 つまたは複数のロケーションに配置される場合があります。 この機能を使用すると、同じアクティビティ内の異なる場所に重複するオファーを同時に表示しないようにできます。

1. [AP アクティビティの作成または編集中](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)、**[!UICONTROL Configure]** アイコン （![設定アイコン &#x200B;](/help/main/assets/icons/Setting.svg)）をクリックし、**[!UICONTROL Allow Duplicate Offers]**&#x200B;をクリックして、必要に応じてこの機能のオンとオフを切り替えます。

## 特定のエクスペリエンスの除外 {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

AP アクティビティから特定のオファーの組み合わせを除外する場合は、特定のエクスペリエンスを除外します。

特定の組み合わせで連携しない場合や、テストしたエクスペリエンスの数を制限して、アクティビティのトラフィック要件を軽減する場合などがあります。

1. [AP アクティビティの作成または編集中](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)、**コンテンツの管理** アイコン（![&#x200B; コンテンツの管理アイコン &#x200B;](/help/main/assets/icons/Experience.svg)）をクリックします。

   [!UICONTROL Experiences] リストには、すべてのコンテンツと場所のオプションの置換から生成された各エクスペリエンスが表示されます。

1. 必要に応じてエクスペリエンスを除外します。

   特定のエクスペリエンスを除外するには、[!UICONTROL **詳細アクション**] アイコン （![詳細アクション アイコン &#x200B;](/help/main/assets/icons/MoreSmall.svg)）をクリックし、[!UICONTROL **除外**]&#x200B;をクリックします。

   または、関連するエクスペリエンスのチェックボックスを選択し、**[!UICONTROL Exclude]**&#x200B;をクリックして、エクスペリエンスをバッチで除外することもできます。 1つ以上のエクスペリエンスがチェックされると、[!UICONTROL Exclude] アイコンが表示されます。

   ![エクスペリエンスの一括除外](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   エクスペリエンスがアクティビティから除外され、その[!UICONTROL Status]が[!UICONTROL Excluded]として表示されるようになりました。

## デフォルトコンテンツを除外 {#task_DCB4528989DF4C05A3A4729E5891D18F}

AP アクティビティの一部として、デフォルトのコンテンツを含めたくない場合があります。 この方法を使用すると、アクティビティの一部として、1つの場所に1つのオファー（デフォルトのコンテンツとは異なる）のみを設定できます。

AP アクティビティでテストするオファーに合わせてページの他の部分のデザインを変更したい場合は、デフォルトのコンテンツを除外する方法が効果的です。 例えば、テスト対象のオファーのカラーパレットを一致させたい場合は、ページの背景色を変更し、デフォルトの背景色を除外します。

**[!UICONTROL Visual Experience Composer] （VEC）を使用してデフォルトコンテンツを除外するには：**

1. [AP アクティビティの作成または編集中](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)に、置き換えるコンテンツを選択し、クリックして&#x200B;**[!UICONTROL Change Text/HTML]**、**[!UICONTROL Change Image Offer]**、または&#x200B;**[!UICONTROL Change Background Color]**&#x200B;にアクセスします。 利用可能なオプションは、コンテンツの種類によって異なります。

   ![&#x200B; オプションの変更](/help/main/c-activities/t-automated-personalization/assets/options.png)
1. 新しいコンテンツの制作。

1. **[!UICONTROL More Actions]** （![その他のアクション アイコン &#x200B;](/help/main/assets/icons/Setting.svg)）アイコンをクリックし、「**デフォルトのオファーを除外/デフォルトのオファーを含める**/」トグルをクリックして、デフォルトのオファーを除外または含めます。

   <!--
   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![Include checkbox in Edit Text/HTML dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   For Image/Video content: 

   ![Include checkbox in Select Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   For background color: 

   ![Include checkbox in Edit Background Color dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)
   -->

<!--
1. Click **[!UICONTROL Save]**.

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_vec_4 image](assets/exclude_content_vec_4.png)

**To exclude default content using the [!UICONTROL Form-Based Experience Composer]:** 

1. While creating or editing an AP activity, click **[!UICONTROL Change Text/HTML]** or **[!UICONTROL Change Image Offer]** under **[!UICONTROL Content]**. 
1. In the dialog box, create your new content and uncheck **[!UICONTROL Include]** to the right of the default content (or uncheck the Default Image/Video in the [!UICONTROL Select Content] screen). 

   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![exclude_content_form_1 image](assets/exclude_content_form_1.png)

   For Image/Video content: 

   ![exclude_content_form_2 image](assets/exclude_content_form_2.png)

1. Click **[!UICONTROL Save]**. 

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)
-->
