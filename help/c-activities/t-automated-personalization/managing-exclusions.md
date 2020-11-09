---
keywords: dedupe;allow duplicates;exclude duplicate offers;automated personalization;disallow duplicate offers
description: Adobe Target の自動パーソナライゼーション（AP）アクティビティでの除外グループの作成、重複オファーの除外、特定のエクスペリエンスの除外、デフォルトコンテンツの除外により、除外を管理します。
title: 除外の管理
feature: ap
solution: Target,Analytics
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '960'
ht-degree: 97%

---


# ![Premium バッジ](/help/assets/premium.png) 除外の管理{#manage-exclusions}

自動パーソナライゼーション（AP）アクティビティでの除外グループの作成、重複オファーの除外、特定のエクスペリエンスの除外、デフォルトコンテンツの除外により、除外を管理します。

## 除外グループの作成 {#task_AAAA6C7239A84F7696C8492F04B575A2}

自動パーソナライゼーション（AP）アクティビティで除外グループを作成し、指定したオファーを含むエクスペリエンスが自動的に除外されるようにします。

除外グループは、複数の場所における同一のエクスペリエンスで、不適切なオファーが提示されないようにできる便利な機能です。例えば、全商品を対象とした 20％割引と 15％割引の 2 つのオファーがあるとします。この 2 つのオファーが、同一のエクスペリエンスの訪問者に提示されないようにする必要があります。その場合はこの 2 つのオファーを除外グループに追加することで対処できます。

また、どのオーディエンスが AP アクティビティの特定のオファーを表示できるかを制限できます。詳しくは、[Target の自動パーソナライゼーションオファー](/help/c-activities/t-automated-personalization/ap-target-offers.md)を参照してください。

**除外グループを作成する手順は次のとおりです。**

1. [AP アクティビティの作成または編集](/help/c-activities/t-automated-personalization/create-ap-activity.md)時に、ヘッダーバーの「**[!UICONTROL コンテンツを管理]**」をクリックします。

   ![コンテンツを管理リンク](/help/c-activities/t-automated-personalization/assets/manage-content.png)

1. [!UICONTROL コンテンツを管理]ダイアログボックスで、「**[!UICONTROL 除外グループ]**」をクリックします。

   ![コンテンツを管理／除外グループダイアログボックス](/help/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   以前に作成した除外グループがある場合は、リスト内に表示されます。除外グループをまだ作成していない場合は、作成するよう求められます。

1. 「**[!UICONTROL 除外グループを作成]**」をクリックします。

   ![除外グループを作成ダイアログボックス](/help/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. （必須）除外グループにわかりやすい名前を付けます。

   わかりやすい名前を付ければ、そのグループをすばやく見つけたり、用途を把握したりしやすくなります。

1. 除外グループに追加するオファーを見つけて選択します。

   除外グループでは同じ場所から複数のオファーを選択できます。

1. 「**[!UICONTROL 保存]**」をクリックします。

除外グループのオファーは、以降、同一のエクスペリエンスから自動的に除外されます。

## 重複するオファーの除外 {#concept_4EF78013F80E48EFA024AE0274C9F037}

オファーライブラリからのオファーが[!UICONTROL 自動パーソナライゼーション]アクティビティの複数のロケーションで使用される場合に重複しないようにします。

例えば、ページ上で 6 つのロケーションと 12 件のオファーがあるアクティビティがあるとします。同じオファーがアクティビティ内の 1 つまたは複数のロケーションに配置される場合があります。この機能では、同一アクティビティ内の別の場所で、重複するオファーが同時に表示されるのを防ぐことができます。

**[!UICONTROL 設定]**／**[!UICONTROL 重複オファー]**&#x200B;をクリックしてから、「**[!UICONTROL 重複を許可]**」または「**[!UICONTROL 重複を許可しない]**」をクリックします。

![重複オファーのオプション](/help/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## 特定のエクスペリエンスの除外 {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

特定のオファーの組み合わせを自動パーソナライゼーションアクティビティから除外したい場合は、特定のエクスペリエンスを除外できます。

効果的ではない組み合わせがある場合や、テスト対象のエクスペリエンスの数を制限し、アクティビティのトラフィック要件を下げたい場合もあるでしょう。

1. [AP アクティビティの作成または編集](/help/c-activities/t-automated-personalization/create-ap-activity.md)時に、ヘッダーバーの「**コンテンツを管理**」をクリックします。

   ![コンテンツを管理リンク](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   [!UICONTROL エクスペリエンス]のリストに、すべてのコンテンツと場所のオプションの順列を基に作成された各エクスペリエンスが表示されます。

1. 必要に応じてエクスペリエンスを除外します。

   エクスペリエンスを除外する際は、対象のエクスペリエンスにマウスポインターを置いてから除外アイコンをクリックします。

   ![マウスポインターを置いてエクスペリエンスを除外](/help/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   複数のエクスペリエンスのチェックボックスをオンにしてから、ダイアログボックスの右上隅にある「**[!UICONTROL 除外]**」アイコンをクリックすることで、エクスペリエンスを一括で除外（または追加）できます。「[!UICONTROL 除外]」アイコンは、1 つ以上のエクスペリエンスのチェックボックスがオンになっている場合に表示されます。

   ![エクスペリエンスの一括除外](/help/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   このリスト表示では、[!UICONTROL ステータス]ドロップダウンリストをクリックすることでフィルターを適用し、除外済みのアクティビティまたは追加済みのアクティビティのみを表示できます。

   以上でアクティビティからエクスペリエンスが除外され、[!UICONTROL ステータス]が[!UICONTROL 除外]になります。

   ![除外されたエクスペリエンス](/help/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## デフォルトコンテンツの除外 {#task_DCB4528989DF4C05A3A4729E5891D18F}

デフォルトのコンテンツを、自動パーソナライゼーションアクティビティから除外したい場合もあるでしょう。この設定方法は、除外グループの作成方法とは異なります。この方法を使用すれば、ある場所の 1 つのオファー（デフォルトのコンテンツとは異なる）のみを AP アクティビティに含めることができます。

AP アクティビティでテストするオファーに合わせてページの他の部分のデザインを変更したい場合は、デフォルトのコンテンツを除外する方法が効果的です。例えば、テスト対象のオファーのカラーパレットを一致させたい場合は、ページの背景色を変更し、デフォルトの背景色を除外します。

**Visual Experience Composer（VEC）を使用してデフォルトのコンテンツを除外する方法は次のとおりです。**

1. While [creating or editing an AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md), select the content you want to replace and click to access **[!UICONTROL Change Text/HTML]**, **[!UICONTROL Change Image]**, or **[!UICONTROL Change Background Color]**.
1. ダイアログボックスで新しいコンテンツを作成し、デフォルトコンテンツの右側にある「**含める**」をオフにします（またはコンテンツを選択画面の「デフォルト画像 / ビデオ」をオフにします）。

   コンテンツ／オファーのタイプによっては、「[!UICONTROL 含める]」チェックボックスの位置が若干異なります。

   テキスト／HTML コンテンツの場合：

   ![テキスト / HTML を編集ダイアログボックスの「含める」チェックボックス](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   画像／ビデオコンテンツの場合：

   ![コンテンツを選択ダイアログボックスの「含める」チェックボックス](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   背景色の場合：

   ![背景色を編集ダイアログボックスの「含める」チェックボックス](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   [!UICONTROL コンテンツを管理]で、指定したオファーを基に作成されたエクスペリエンスを確認できます。[!UICONTROL コンテンツを管理]には、除外したデフォルトのオファーを使用して作成されたエクスペリエンスがないことがわかります。

   ![](assets/exclude_content_vec_4.png)

**フォームベースの Experience Composer を使用してデフォルトのコンテンツを除外する方法は次のとおりです。**

1. AP アクティビティを作成または編集しているときに、「**[!UICONTROL コンテンツ]**」で「**[!UICONTROL テキスト／HTML を変更]**」または「**[!UICONTROL 画像オファーを変更]**」をクリックします。
1. ダイアログボックスで新しいコンテンツを作成し、デフォルトコンテンツの右側にある「**[!UICONTROL 含める]**」をオフにします（またはコンテンツを選択画面の「デフォルト画像 / ビデオ」をオフにします）。

   コンテンツ／オファーのタイプによっては、「含める」チェックボックスの位置が若干異なります。

   テキスト／HTML コンテンツの場合：

   ![](assets/exclude_content_form_1.png)

   画像／ビデオコンテンツの場合：

   ![](assets/exclude_content_form_2.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   [!UICONTROL コンテンツを管理]で、指定したオファーを基に作成されたエクスペリエンスを確認できます。[!UICONTROL コンテンツを管理]には、除外したデフォルトのオファーを使用して作成されたエクスペリエンスがないことがわかります。

   ![](assets/exclude_content_form_3.png)
