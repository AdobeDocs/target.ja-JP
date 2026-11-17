---
keywords: 重複排除；重複を許可；重複するオファーを除外；自動パーソナライゼーション；重複するオファーを許可しない；除外；デフォルトコンテンツ；
description: '[!UICONTROL Automated Personalization] （AP）アクティビティの除外を管理します。'
title: '[!UICONTROL Automated Personalization] アクティビティの除外を管理するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
TQID: 'https://experienceleague.adobe.com/ERpNwQPsIRBmU0vTZbGa-lYg30BYl-uJxA8UT0f6060'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 7%
---
# 除外の管理 {#manage-exclusions}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;で、**[!UICONTROL Automated Personalization]**&#x200B;のアクティビティで、オファーの重複を防止し、特定のエクスペリエンスを除外し、デフォルトコンテンツを除外する方法を説明します。

>[!ENDSHADEBOX]

除外は、**[!UICONTROL Automated Personalization]** （AP）アクティビティが提供するオファーとエクスペリエンスを制御します。 これにより、同じオファーが2回表示されるのを防ぎ、連携しないオファーの組み合わせを削除し、デフォルトのコンテンツを削除します。これにより、目標やオーディエンスに合わせて、よりクリーンで関連性の高いエクスペリエンスを提供するためのアクティビティを構築できます。

## 重複するオファーを許可または禁止 {#allow-duplicate-offers}

<a id="concept_4EF78013F80E48EFA024AE0274C9F037"></a>

AP アクティビティの異なる場所で使用する場合、オファーライブラリのオファーが重複するのを防ぎます。

アクティビティには、例えば、12件のオファーを含むページ上の6つの場所を含めることができるため、同じオファーを複数の場所に配置できます。 重複するオファーを許可しないと、同じアクティビティ内の異なる場所に同じオファーが同時に表示されなくなります。

1. [AP アクティビティの作成または編集中](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)、**[!UICONTROL 設定]** アイコン （![設定アイコン ](/help/main/assets/icons/Setting.svg)）をクリックします。

1. 「**[!UICONTROL オファーの重複を許可]**」をクリックして、必要に応じてこの機能のオンとオフを切り替えます。

   ![ アイコンの設定](../assets/exclusion-1.png)

## 特定のエクスペリエンスの除外 {#exclude-experiences}

<a id="task_C17D36EF58AF4908B17A3D84CA6DE85A"></a>

特定のエクスペリエンスを除外して、AP アクティビティから特定のオファーの組み合わせを削除します。 一部の組み合わせが連携しない場合や、アクティビティのトラフィック要件を軽減するために、テストするエクスペリエンスの数を制限する場合があります。

1. [AP アクティビティの作成または編集中](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)、**[!UICONTROL コンテンツの管理]** アイコン（![ コンテンツの管理アイコン ](/help/main/assets/icons/Experience.svg)）をクリックします。

   **[!UICONTROL エクスペリエンス]**&#x200B;のリストに、すべてのコンテンツと場所のオプションの順列を基に作成された各エクスペリエンスが表示されます。

1. テストしないエクスペリエンスは除外します。

   * 1つのエクスペリエンスを除外するには、**[!UICONTROL 詳細アクション]** アイコン （![詳細アクション アイコン ](/help/main/assets/icons/MoreSmall.svg)）をクリックし、**[!UICONTROL 除外]**&#x200B;をクリックします。
   * 複数のエクスペリエンスを一度に除外するには、各エクスペリエンスのチェックボックスを選択し、**[!UICONTROL 除外]**&#x200B;をクリックします。 1つ以上のエクスペリエンスを選択すると、**[!UICONTROL 除外]** アイコンが表示されます。

   ![エクスペリエンスの一括除外](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   エクスペリエンスはアクティビティから除外され、その&#x200B;**[!UICONTROL ステータス]**&#x200B;は&#x200B;**[!UICONTROL 除外]**&#x200B;と表示されるようになりました。

## デフォルトコンテンツを除外 {#exclude-default-content}

<a id="task_DCB4528989DF4C05A3A4729E5891D18F"></a>

AP アクティビティに含めない場合は、デフォルトコンテンツを除外します。これにより、デフォルトコンテンツとは異なるオファーが1つだけ場所に含まれるようになります。 このアプローチでは、テストするオファーに合わせて、ページの残りの部分のルック&amp;フィールも変更できます。 例えば、オファーのカラーパレットを一致させるために、ページの背景色を変更し、デフォルトの背景色を除外することができます。

1. [AP アクティビティの作成または編集中](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)に、置き換えるコンテンツを選択し、**[!UICONTROL テキストの変更/HTML]**、**[!UICONTROL 画像オファーの変更]**、**[!UICONTROL 背景色の変更]**&#x200B;をクリックします。 利用可能なオプションは、コンテンツの種類によって異なります。

   ![ オプションの変更](../assets/exclusion-1.png)

1. 新しいコンテンツの制作。

1. 「**[!UICONTROL その他のアクション]**」アイコン（![その他のアクション アイコン ](/help/main/assets/icons/Setting.svg)）をクリックし、「**デフォルトのオファーを除外/デフォルトのオファーを含める**」トグルをクリックして、デフォルトのオファーを除外または含めます。

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
