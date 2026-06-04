---
keywords: 重複排除；重複を許可；重複するオファーを除外；自動パーソナライゼーション；重複するオファーを許可しない；除外；デフォルトコンテンツ；除外グループ；
description: ' [!DNL Adobe Target] [!UICONTROL Automated Personalization] （AP）アクティビティの除外を管理します。 除外グループを作成し、重複するオファー、特定のエクスペリエンス、デフォルトコンテンツを除外します。'
title: '[!UICONTROL Automated Personalization] アクティビティの除外を管理するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 49%

---

# 除外の管理

除外グループを作成し、重複するオファーを除外し、特定のエクスペリエンスを除外し、[!UICONTROL Automated Personalization] （AP）アクティビティのデフォルトコンテンツを[!DNL Adobe Target]で除外することで、除外を管理します。

## 除外グループの作成 {#task_AAAA6C7239A84F7696C8492F04B575A2}

[!UICONTROL Automated Personalization] （AP）アクティビティで除外グループを作成して、指定されたオファーを含むエクスペリエンスが自動的に除外されるようにします。

除外グループは、複数の場所における同一のエクスペリエンスで、不適切なオファーが提示されないようにできる便利な機能です。 例えば、2つのオファーがある場合、1つは全商品の20%割引、もう1つは15%割引です。 訪問者に対して、この2つのオファーを同じエクスペリエンスで提示することは避けたいものです。 除外グループにこれら2つのオファーを追加する場合、この状況が決してそうでないことを確認できます。

また、どのオーディエンスが AP アクティビティの特定のオファーを表示できるかを制限できます。 詳しくは、[Target のAutomated Personalizationオファー](/help/main/c-activities/t-automated-personalization/ap-target-offers.md)を参照してください。

**除外グループを作成する手順は次のとおりです。**

1. [AP アクティビティの作成または編集](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)時に、ヘッダーバーの「**[!UICONTROL コンテンツを管理]**」をクリックします。

   ![コンテンツを管理リンク](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

1. [!UICONTROL  コンテンツを管理] ダイアログボックスで、**[!UICONTROL 除外グループ]**&#x200B;をクリックします。

   ![コンテンツを管理／除外グループダイアログボックス](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   以前に作成した除外グループがある場合は、リスト内に表示されます。 除外グループをまだ作成していない場合は、作成するよう求められます。

1. 「**[!UICONTROL 除外グループを作成」をクリックします。]**

   ![除外グループを作成ダイアログボックス](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. （必須）除外グループにわかりやすい名前を付けます。

   わかりやすい名前を付ければ、そのグループをすばやく見つけたり、用途を把握したりしやすくなります。

1. 除外グループに追加するオファーを見つけて選択します。

   除外グループでは同じ場所から複数のオファーを選択できます。

1. 「**[!UICONTROL 保存]**」をクリックします。

除外グループ内のオファーは、今後、同じエクスペリエンスから自動的に除外されます。

## 重複するオファーを除外 {#concept_4EF78013F80E48EFA024AE0274C9F037}

オファーライブラリからのオファーが [!UICONTROL Automated Personalization] アクティビティの複数のロケーションで使用される場合に重複しないようにします。

例えば、ページ上で 6 つのロケーションと 12 件のオファーがあるアクティビティがあるとします。 同じオファーがアクティビティ内の 1 つまたは複数のロケーションに配置される場合があります。 この機能では、同一アクティビティ内の別の場所で、重複するオファーが同時に表示されるのを防ぐことができます。

「**[!UICONTROL Configure]**」歯車オプション >**[!UICONTROL Duplicate Offers]**&#x200B;をクリックし、**[!UICONTROL Allow Duplicates]**&#x200B;または&#x200B;**[!UICONTROL Disallow Duplicates]**&#x200B;をクリックします。

![重複オファーのオプション](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## 特定のエクスペリエンスの除外 {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

特定のオファーの組み合わせを[!UICONTROL Automated Personalization] アクティビティから除外する場合は、特定のエクスペリエンスを除外します。

特定の組み合わせで連携しない場合や、テストしたエクスペリエンスの数を制限して、アクティビティのトラフィック要件を軽減する場合などがあります。

1. [AP アクティビティの作成または編集](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)時に、ヘッダーバーの「**コンテンツを管理**」をクリックします。

   ![コンテンツを管理リンク](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   [!UICONTROL エクスペリエンス]のリストに、すべてのコンテンツと場所のオプションの順列を基に作成された各エクスペリエンスが表示されます。

1. 必要に応じてエクスペリエンスを除外します。

   エクスペリエンスを除外する際は、対象のエクスペリエンスにマウスポインターを置いてから除外アイコンをクリックします。

   ![マウスポインターを置いてエクスペリエンスを除外](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   また、関連するエクスペリエンスのチェックボックスを選択し、ダイアログボックスの右上隅にある「**[!UICONTROL 除外]**」アイコンをクリックして、エクスペリエンスをバッチで除外することもできます。 1つ以上のエクスペリエンスがチェックされると、[!UICONTROL 除外] アイコンが表示されます。

   ![エクスペリエンスの一括除外](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   このリストビューをフィルタリングして、[!UICONTROL  ステータス ] ドロップダウンリストをクリックすることで、除外されたアクティビティのみを表示したり、含まれたアクティビティのみを表示したりできます。

   エクスペリエンスがアクティビティから除外され、その[!UICONTROL  ステータス ]が[!UICONTROL 除外]として表示されるようになりました。

   ![除外されたエクスペリエンス](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## デフォルトコンテンツを除外 {#task_DCB4528989DF4C05A3A4729E5891D18F}

[!UICONTROL Automated Personalization] アクティビティの一部として、デフォルトコンテンツを含めたくない場合があります。 この設定方法は、除外グループの作成方法とは異なります。 この方法を使用すれば、ある場所の 1 つのオファー（デフォルトのコンテンツとは異なる）のみを AP アクティビティに含めることができます。

AP アクティビティでテストするオファーに合わせてページの他の部分のデザインを変更したい場合は、デフォルトのコンテンツを除外する方法が効果的です。 例えば、テスト対象のオファーのカラーパレットを一致させたい場合は、ページの背景色を変更し、デフォルトの背景色を除外します。

**[!UICONTROL Visual Experience Composer] （VEC）を使用してデフォルトコンテンツを除外するには：**

1. [AP アクティビティの作成または編集中](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)に、置き換えるコンテンツを選択し、クリックして&#x200B;**[!UICONTROL テキストの変更/HTML]**、**[!UICONTROL 画像の変更]**、**[!UICONTROL 背景色の変更]**&#x200B;にアクセスします。
1. ダイアログボックスで、新しいコンテンツを作成し、デフォルトコンテンツの右側にある&#x200B;**含める**&#x200B;のチェックを外します（または、[!UICONTROL  コンテンツを選択]画面でデフォルトの画像/ビデオのチェックを外します）。

   コンテンツまたはオファーのタイプに応じて、[!UICONTROL 含める] チェックボックスは少し異なる場所にあります。

   テキスト／HTML コンテンツの場合：

   ![テキスト / HTML を編集ダイアログボックスの「含める」チェックボックス](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   画像／ビデオコンテンツの場合：

   ![コンテンツを選択ダイアログボックスの「含める」チェックボックス](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   背景色の場合：

   ![背景色を編集ダイアログボックスの「含める」チェックボックス](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   [!UICONTROL コンテンツを管理]で、指定したオファーを基に作成されたエクスペリエンスを確認できます。 [!UICONTROL  コンテンツを管理]では、除外した既定のオファーを使用してエクスペリエンスが作成されないことに注意してください。

   ![exclude_content_vec_4 image](assets/exclude_content_vec_4.png)

**フォームベースのExperience Composer [!UICONTROL を使用してデフォルトコンテンツを除外するには、]:**

1. AP アクティビティを作成または編集しているときに、**[!UICONTROL コンテンツ]**&#x200B;で「**[!UICONTROL テキスト / HTML を変更]**」または「**[!UICONTROL 画像オファーを変更]**」をクリックします。
1. ダイアログボックスで、新しいコンテンツを作成し、デフォルトコンテンツの右側にある&#x200B;**[!UICONTROL 含める]**&#x200B;のチェックを外します（または、[!UICONTROL  コンテンツを選択]画面でデフォルトの画像/ビデオのチェックを外します）。

   コンテンツまたはオファーのタイプに応じて、[!UICONTROL 含める] チェックボックスは少し異なる場所にあります。

   テキスト／HTML コンテンツの場合：

   ![exclude_content_form_1 image](assets/exclude_content_form_1.png)

   画像／ビデオコンテンツの場合：

   ![exclude_content_form_2 image](assets/exclude_content_form_2.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   [!UICONTROL コンテンツを管理]で、指定したオファーを基に作成されたエクスペリエンスを確認できます。 [!UICONTROL  コンテンツを管理]では、除外した既定のオファーを使用してエクスペリエンスが作成されないことに注意してください。

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)
