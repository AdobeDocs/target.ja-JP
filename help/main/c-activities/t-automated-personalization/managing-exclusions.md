---
keywords: 重複；重複を許可；重複するオファーを除外；Automated Personalization；重複するオファーを許可しない；除外；デフォルトコンテンツ；
description: '[!UICONTROL Automated Personalization] （AP）アクティビティの除外を管理します。'
title: '[!UICONTROL Automated Personalization] アクティビティで除外を管理するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: 2715e803938ee552e2c6db438ed4dbece4b6220e
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 23%

---

# 除外の管理

除外をマスターすることで、[!UICONTROL Automated Personalization] （AP）戦略を制御します。 オファーの重複を防ぐ場合でも、エクスペリエンスの組み合わせを調整する場合でも、デフォルトコンテンツを削除する場合でも、除外を使用すると、目標とオーディエンスの期待に沿った、よりクリーンで関連性の高いエクスペリエンスを提供できます。

## 重複するオファーを許可または禁止 {#concept_4EF78013F80E48EFA024AE0274C9F037}

オファーライブラリからのオファーが AP アクティビティの複数のロケーションで使用される場合に重複しないようにします。

例えば、ページ上で 6 つのロケーションと 12 件のオファーがあるアクティビティがあるとします。同じオファーがアクティビティ内の 1 つまたは複数のロケーションに配置される場合があります。この機能を使用すると、同じアクティビティ内の異なる場所に重複したオファーが同時に表示されるのを防ぐことができます。

1. [AP アクティビティの作成または編集 &#x200B;](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) 中に、**[!UICONTROL Configure]** アイコン（![&#x200B; 設定アイコン &#x200B;](/help/main/assets/icons/Setting.svg)）をクリックし、**[!UICONTROL Allow Duplicate Offers]** をクリックして、この機能のオン/オフを必要に応じて切り替えます。

## 特定のエクスペリエンスを除外 {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

特定のオファーの組み合わせを AP アクティビティから除外したい場合は、特定のエクスペリエンスを除外できます。

連携できない特定の組み合わせがあるか、テストしたエクスペリエンスの数を制限してアクティビティのトラフィック要件を減らしている可能性があります。

1. [AP アクティビティの作成または編集 &#x200B;](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) 中に、**コンテンツを管理** アイコン（![&#x200B; コンテンツを管理アイコン &#x200B;](/help/main/assets/icons/Experience.svg)）をクリックします。

   [!UICONTROL Experiences] のリストには、すべてのコンテンツと場所のオプションの並べ替えから生成された各エクスペリエンスが表示されます。

1. 必要に応じてエクスペリエンスを除外します。

   特定のエクスペリエンスを除外するには、[!UICONTROL **その他のアクション**] アイコン（![&#x200B; その他のアクション アイコン &#x200B;](/help/main/assets/icons/MoreSmall.svg)）をクリックしてから、[!UICONTROL **除外**] をクリックします。

   または、関連するエクスペリエンスのチェックボックスを選択し、「**[!UICONTROL Exclude]**」をクリックすることで、エクスペリエンスをバッチ除外できます。 1 つ以上のエクスペリエンスがチェックされると、[!UICONTROL Exclude] のアイコンが表示されます。

   ![エクスペリエンスの一括除外](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   エクスペリエンスがアクティビティから除外され、[!UICONTROL Status] が [!UICONTROL Excluded] のように表示されるようになりました。

## デフォルトコンテンツを除外 {#task_DCB4528989DF4C05A3A4729E5891D18F}

場合によっては、デフォルトコンテンツを AP アクティビティの一部として含めたくない場合があります。 この方法を使用すると、アクティビティの一部として、1 つの場所に（デフォルトコンテンツとは異なる）オファーを 1 つだけ含めることができます。

AP アクティビティでテストするオファーに合わせてページの他の部分のデザインを変更したい場合は、デフォルトのコンテンツを除外する方法が効果的です。例えば、テスト対象のオファーのカラーパレットを一致させたい場合は、ページの背景色を変更し、デフォルトの背景色を除外します。

**[!UICONTROL Visual Experience Composer] （VEC）を使用してデフォルトコンテンツを除外するには：**

1. [AP アクティビティの作成または編集 &#x200B;](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) 中に、置き換えるコンテンツを選択し、クリックして **[!UICONTROL Change Text/HTML]**、**[!UICONTROL Change Image Offer]**、**[!UICONTROL Change Background Color]** にアクセスします。 使用できるオプションは、コンテンツのタイプによって異なります。

   ![&#x200B; オプションを変更 &#x200B;](/help/main/c-activities/t-automated-personalization/assets/options.png)
1. 新しいコンテンツを作成します。

1. **[!UICONTROL More Actions]** （その他のアクション ![&#x200B; アイコン）アイコンをクリックし &#x200B;](/help/main/assets/icons/Setting.svg)**デフォルトオファーを除外/デフォルトオファーを含める**/切り替えスイッチをクリックして、デフォルトオファーを除外または含めます。

   <!-- Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![Include checkbox in Edit Text/HTML dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   For Image/Video content: 

   ![Include checkbox in Select Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   For background color: 

   ![Include checkbox in Edit Background Color dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)-->

<!-- 1. Click **[!UICONTROL Save]**.

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

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)-->
