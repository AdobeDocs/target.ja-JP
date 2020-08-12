---
keywords: Analytics as reporting source;a4t;A4T
description: Adobe Analytics に基づいたアクティビティを Adobe Target 内で作成する場合（A4T）のユーザーアカウントの要件です。
title: ユーザー権限の要件
feature: null
solution: Target,Analytics
topic: Reports and analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 63%

---


# ユーザー権限の要件 {#user-permission-requirements}

（A4T）で [!DNL Adobe Analytics]のベースとなるアクティビティ[!DNL Adobe Target] を作成するためのユーザーアカウント要件に関する情報です。

[!DNL Analytics]アクティビティを定義するときは、レポートスイートを選択する前に、 [!DNL Analytics]ユーザーアカウントと[!DNL Target]ユーザーアカウントの両方が必要になります。

次の節の説明に従って、ユーザーアカウントを設定する必要があります。

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

[!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com) で、次の作業を実行します。

### ソリューションアカウントを Adobe ID にリンクします。

あなたの[!DNL Analytics]および[!DNL Target]のユーザーアカウントは Adobe ID にリンクされている必要があります。

For more information, see [Organizations and account linking](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html).

### Experience Cloud グループのメンバーシップを設定します。

あなたは[!DNL Analytics] と [!DNL Target]にアクセスできる 1 つ以上の[!DNL Experience Cloud]グループのメンバーでなければなりません。

For more information, see [Manage Experience Cloud users and products](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

次の作業を実行します。[!DNL Adobe Analytics]

### Analytics レポートスイートへのアクセスの設定

Before creating or viewing reports for an [!DNL Analytics]-powered activity, you must be a member of the **[!UICONTROL All Report Access]** group, or a member of a group that has access to at least one report in the report suite that you want to use. レポートを表示できない場合は、これらのいずれかのグループのメンバーであることを確認してください。

詳しくは、「 [製品のプロファイルとグループ](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html#section_AB50558124D541CF80A0D3D76D35A4BF)」を参照してください。

### Web サービスアクセスグループへのアクセスの設定

[!DNL Target]のレポートソースとして[!DNL Analytics]を使用できるようにするには、[!DNL Analytics]の Web サービスアクセスグループに属している必要があります。

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

追加の権限は必要ありません。
