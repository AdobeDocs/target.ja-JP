---
keywords: 重複；重複を許可；重複するオファーを除外；Automated Personalization；重複するオファーを許可しない；除外；デフォルトコンテンツ；
description: '[!UICONTROL Automated Personalization] （AP）アクティビティの除外を管理します。'
title: '[!UICONTROL Automated Personalization] アクティビティで除外を管理するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: c5016d212edafa908b8755044e73d28167e20e8a
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 39%

---

# 除外の管理

[!UICONTROL Automated Personalization] の [!DNL Adobe Target] （AP）アクティビティでの重複オファーの除外、特定のエクスペリエンスの除外、デフォルトコンテンツの除外により、除外を管理します。

## 重複するオファーを除外 {#concept_4EF78013F80E48EFA024AE0274C9F037}

オファーライブラリからのオファーがアクティビティの複数のロケーションで使用される場合に重複 [!UICONTROL Automated Personalization] ないようにします。

例えば、ページ上で 6 つのロケーションと 12 件のオファーがあるアクティビティがあるとします。同じオファーがアクティビティ内の 1 つまたは複数のロケーションに配置される場合があります。この機能では、同一アクティビティ内の別の場所で、重複するオファーが同時に表示されるのを防ぐことができます。

**[!UICONTROL Configure]** アイコン/**[!UICONTROL Duplicate Offers]** をクリックし、「**[!UICONTROL Allow Duplicates]**」または「**[!UICONTROL Disallow Duplicates]**」をクリックします。

![重複オファーのオプション](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## 特定のエクスペリエンスを除外 {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

特定のオファーの組み合わせをエクスペリ [!UICONTROL Automated Personalization] ンスアクティビティから除外したい場合は、特定のエクスペリエンスを除外できます。

連携できない特定の組み合わせがあるか、テストしたエクスペリエンスの数を制限してアクティビティのトラフィック要件を減らしている可能性があります。

1. [AP アクティビティの作成または編集](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)時に、ヘッダーバーの「**コンテンツを管理**」をクリックします。

   ![コンテンツを管理リンク](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   [!UICONTROL Experiences] のリストには、すべてのコンテンツと場所のオプションの並べ替えから生成された各エクスペリエンスが表示されます。

1. 必要に応じてエクスペリエンスを除外します。

   エクスペリエンスを除外する際は、対象のエクスペリエンスにマウスポインターを置いてから除外アイコンをクリックします。

   ![マウスポインターを置いてエクスペリエンスを除外](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   または、関連するエクスペリエンスのチェックボックスを選択し、ダイアログボックスの右上隅にある「**[!UICONTROL Exclude]**」アイコンをクリックすることで、エクスペリエンスをバッチ除外できます。 1 つ以上のエクスペリエンスがチェックされると、[!UICONTROL Exclude] のアイコンが表示されます。

   ![エクスペリエンスの一括除外](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   [!UICONTROL Status] のドロップダウンリストをクリックすると、このリスト表示をフィルタリングして、除外されたアクティビティのみを表示したり、含まれたアクティビティのみを表示したりできます。

   エクスペリエンスがアクティビティから除外され、[!UICONTROL Status] が [!UICONTROL Excluded] のように表示されるようになりました。

   ![除外されたエクスペリエンス](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## デフォルトコンテンツを除外 {#task_DCB4528989DF4C05A3A4729E5891D18F}

デフォルトコンテンツを [!UICONTROL Automated Personalization] アクティビティの一部として含めない場合もあります。 この設定方法は、除外グループの作成方法とは異なります。この方法を使用すれば、ある場所の 1 つのオファー（デフォルトのコンテンツとは異なる）のみを AP アクティビティに含めることができます。

AP アクティビティでテストするオファーに合わせてページの他の部分のデザインを変更したい場合は、デフォルトのコンテンツを除外する方法が効果的です。例えば、テスト対象のオファーのカラーパレットを一致させたい場合は、ページの背景色を変更し、デフォルトの背景色を除外します。

**[!UICONTROL Visual Experience Composer] （VEC）を使用してデフォルトコンテンツを除外するには：**

1. [AP アクティビティの作成または編集 ](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) 中に、置き換えるコンテンツを選択し、クリックして **[!UICONTROL Change Text/HTML]**、**[!UICONTROL Change Image]**、**[!UICONTROL Change Background Color]** にアクセスします。
1. ダイアログボックスで、新しいコンテンツを作成し、デフォルトコンテンツの右側にある **含める** チェックボックスをオフにします（または、[!UICONTROL Select Content] 画面でデフォルトの画像/ビデオのチェックボックスをオフにします）。

   コンテンツやオファーのタイプによって、「[!UICONTROL Include]」チェックボックスは若干異なる場所にあります。

   テキスト／HTML コンテンツの場合：

   ![テキスト / HTML を編集ダイアログボックスの「含める」チェックボックス](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   画像／ビデオコンテンツの場合：

   ![コンテンツを選択ダイアログボックスの「含める」チェックボックス](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   背景色の場合：

   ![背景色を編集ダイアログボックスの「含める」チェックボックス](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. **[!UICONTROL Save]** をクリックします。

   「[!UICONTROL Manage Content]」で指定したオファーから作成されたエクスペリエンスを表示できます。 除外したデフォルトのオファーを使用して、[!UICONTROL Manage Content] でエクスペリエンスが作成されないことに注意してください。

   ![exclude_content_vec_4 画像 ](assets/exclude_content_vec_4.png)

**[!UICONTROL Form-Based Experience Composer] を使用してデフォルトコンテンツを除外するには：**

1. AP アクティビティを作成または編集する際に、「**[!UICONTROL Change Text/HTML]**」の下の「**[!UICONTROL Change Image Offer]**」または「**[!UICONTROL Content]**」をクリックします。
1. ダイアログボックスで、新しいコンテンツを作成し、デフォルトコンテンツの右側にある **[!UICONTROL Include]** のチェックボックスをオフにします（または、[!UICONTROL Select Content] の画面でデフォルトの画像/ビデオのチェックボックスをオフにします）。

   コンテンツやオファーのタイプによって、「[!UICONTROL Include]」チェックボックスは若干異なる場所にあります。

   テキスト／HTML コンテンツの場合：

   ![exclude_content_form_1 画像 ](assets/exclude_content_form_1.png)

   画像／ビデオコンテンツの場合：

   ![exclude_content_form_2 画像 ](assets/exclude_content_form_2.png)

1. **[!UICONTROL Save]** をクリックします。

   「[!UICONTROL Manage Content]」で指定したオファーから作成されたエクスペリエンスを表示できます。 除外したデフォルトのオファーを使用して、[!UICONTROL Manage Content] でエクスペリエンスが作成されないことに注意してください。

   ![exclude_content_form_3 画像 ](assets/exclude_content_form_3.png)
