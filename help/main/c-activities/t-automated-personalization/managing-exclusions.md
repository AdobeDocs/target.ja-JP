---
keywords: 重複；重複を許可；重複するオファーを除外；自動パーソナライゼーション；重複するオファーを許可しない；除外；デフォルトコンテンツ；除外グループ；
description: での除外の管理 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) アクティビティ 除外グループを作成し、重複するオファー、特定のエクスペリエンスおよびデフォルトコンテンツを除外します。
title: での除外の管理方法 [!UICONTROL Automated Personalization] アクティビティ？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: b5f06878a6ca8b4c571bfe05a52bfb3f471a697e
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 59%

---

# 除外の管理

での除外グループの作成、重複オファーの除外、特定のエクスペリエンスの除外、デフォルトコンテンツの除外により、除外を管理します。 [!UICONTROL Automated Personalization] (AP) アクティビティ [!DNL Adobe Target].

## 除外グループの作成 {#task_AAAA6C7239A84F7696C8492F04B575A2}

での除外グループの作成 [!UICONTROL Automated Personalization] (AP) アクティビティを使用して、指定されたオファーを含むエクスペリエンスが自動的に除外されるようにします。

除外グループは、複数の場所における同一のエクスペリエンスで、不適切なオファーが提示されないようにできる便利な機能です。例えば、2 つのオファーがあるとします。1 つはすべての商品の 20%割引で、もう 1 つは 15%割引です。 同じエクスペリエンスで、この 2 つのオファーを訪問者に提示したくない場合。 この 2 つのオファーを除外グループに追加すると、この状況が発生しないようにすることができます。

また、どのオーディエンスが AP アクティビティの特定のオファーを表示できるかを制限できます。詳しくは、[Target のAutomated Personalizationオファー](/help/main/c-activities/t-automated-personalization/ap-target-offers.md)を参照してください。

**除外グループを作成する手順は次のとおりです。**

1. [AP アクティビティの作成または編集](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)時に、ヘッダーバーの「**[!UICONTROL コンテンツを管理]**」をクリックします。

   ![コンテンツを管理リンク](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

1. Adobe Analytics の [!UICONTROL コンテンツを管理] ダイアログボックスで、 **[!UICONTROL 除外グループ]**.

   ![コンテンツを管理／除外グループダイアログボックス](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   以前に作成した除外グループがある場合は、リスト内に表示されます。除外グループをまだ作成していない場合は、作成するよう求められます。

1. 「**[!UICONTROL 除外グループを作成]**」をクリックします。

   ![除外グループを作成ダイアログボックス](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. （必須）除外グループにわかりやすい名前を付けます。

   わかりやすい名前を付ければ、そのグループをすばやく見つけたり、用途を把握したりしやすくなります。

1. 除外グループに追加するオファーを見つけて選択します。

   除外グループでは同じ場所から複数のオファーを選択できます。

1. 「**[!UICONTROL 保存]**」をクリックします。

除外グループのオファーは、今後、同じエクスペリエンスから自動的に除外されます。

## 重複するオファーの除外 {#concept_4EF78013F80E48EFA024AE0274C9F037}

オファーライブラリからのオファーが[!UICONTROL Automated Personalization]アクティビティの複数のロケーションで使用される場合に重複しないようにします。

例えば、ページ上で 6 つのロケーションと 12 件のオファーがあるアクティビティがあるとします。同じオファーがアクティビティ内の 1 つまたは複数のロケーションに配置される場合があります。この機能では、同一アクティビティ内の別の場所で、重複するオファーが同時に表示されるのを防ぐことができます。

次をクリック： **[!UICONTROL 設定]** 歯車オプション/ **[!UICONTROL 重複するオファー]**&#x200B;を選択し、次に **[!UICONTROL 重複を許可]** または **[!UICONTROL 重複を許可しない]**.

![重複オファーのオプション](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## 特定のエクスペリエンスの除外 {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

特定のオファーの組み合わせを [!UICONTROL Automated Personalization] アクティビティ。

連携しない特定の組み合わせが存在する場合や、テストするエクスペリエンスの数を制限してアクティビティのトラフィック要件を下げている場合があります。

1. [AP アクティビティの作成または編集](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)時に、ヘッダーバーの「**コンテンツを管理**」をクリックします。

   ![コンテンツを管理リンク](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   [!UICONTROL エクスペリエンス]のリストに、すべてのコンテンツと場所のオプションの順列を基に作成された各エクスペリエンスが表示されます。

1. 必要に応じてエクスペリエンスを除外します。

   エクスペリエンスを除外する際は、対象のエクスペリエンスにマウスポインターを置いてから除外アイコンをクリックします。

   ![マウスポインターを置いてエクスペリエンスを除外](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   複数のエクスペリエンスのチェックボックスをオンにしてから **[!UICONTROL 除外]** アイコンをクリックします。 The [!UICONTROL 除外] アイコンは、1 つ以上のエクスペリエンスのチェックボックスがオンになっているときに表示されます。

   ![エクスペリエンスの一括除外](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   このリスト表示では、[!UICONTROL ステータス]ドロップダウンリストをクリックすることでフィルターを適用し、除外済みのアクティビティまたは追加済みのアクティビティのみを表示できます。

   エクスペリエンスがアクティビティとそのエクスペリエンスから除外されるようになりました [!UICONTROL ステータス] 次の形式で表示 [!UICONTROL 除外済み].

   ![除外されたエクスペリエンス](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## デフォルトコンテンツの除外 {#task_DCB4528989DF4C05A3A4729E5891D18F}

デフォルトのコンテンツを [!UICONTROL Automated Personalization] アクティビティ。 この設定方法は、除外グループの作成方法とは異なります。この方法を使用すれば、ある場所の 1 つのオファー（デフォルトのコンテンツとは異なる）のみを AP アクティビティに含めることができます。

AP アクティビティでテストするオファーに合わせてページの他の部分のデザインを変更したい場合は、デフォルトのコンテンツを除外する方法が効果的です。例えば、テスト対象のオファーのカラーパレットを一致させたい場合は、ページの背景色を変更し、デフォルトの背景色を除外します。

**Visual Experience Composer（VEC）を使用してデフォルトのコンテンツを除外する方法は次のとおりです。**

1. While [AP アクティビティの作成または編集](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)、置き換えるコンテンツを選択し、「 」をクリックしてアクセスします **[!UICONTROL テキスト/HTMLを変更]**, **[!UICONTROL 画像を変更]**&#x200B;または **[!UICONTROL 背景色の変更]**.
1. ダイアログボックスで新しいコンテンツを作成し、デフォルトコンテンツの右側にある「**含める**」をオフにします（またはコンテンツを選択画面の「デフォルト画像 / ビデオ」をオフにします）。

   コンテンツまたはオファータイプに応じて、 [!UICONTROL 次を含む] チェックボックスは少し異なる場所にあります。

   テキスト／HTML コンテンツの場合：

   ![テキスト / HTML を編集ダイアログボックスの「含める」チェックボックス](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   画像／ビデオコンテンツの場合：

   ![コンテンツを選択ダイアログボックスの「含める」チェックボックス](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   背景色の場合：

   ![背景色を編集ダイアログボックスの「含める」チェックボックス](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   [!UICONTROL コンテンツを管理]で、指定したオファーを基に作成されたエクスペリエンスを確認できます。ではエクスペリエンスが作成されていません。 [!UICONTROL コンテンツを管理] 除外したデフォルトオファーを使用する。

   ![exclude_content_vec_4 image](assets/exclude_content_vec_4.png)

**デフォルトコンテンツを除外するには、 [!UICONTROL フォームベースの Experience Composer]:**

1. AP アクティビティを作成または編集しているときに、「**[!UICONTROL コンテンツ]**」で「**[!UICONTROL テキスト／HTML を変更]**」または「**[!UICONTROL 画像オファーを変更]**」をクリックします。
1. ダイアログボックスで新しいコンテンツを作成し、デフォルトコンテンツの右側にある「**[!UICONTROL 含める]**」をオフにします（またはコンテンツを選択画面の「デフォルト画像 / ビデオ」をオフにします）。

   コンテンツまたはオファータイプに応じて、 [!UICONTROL 次を含む] チェックボックスは少し異なる場所にあります。

   テキスト／HTML コンテンツの場合：

   ![exclude_content_form_1 image](assets/exclude_content_form_1.png)

   画像／ビデオコンテンツの場合：

   ![exclude_content_form_2 image](assets/exclude_content_form_2.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   [!UICONTROL コンテンツを管理]で、指定したオファーを基に作成されたエクスペリエンスを確認できます。ではエクスペリエンスが作成されていません。 [!UICONTROL コンテンツを管理] 除外したデフォルトオファーを使用する。

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)
