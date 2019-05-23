---
description: Adobe Analytics に基づいたアクティビティを Adobe Target 内で作成する場合（A4T）のユーザーアカウントの要件です。
keywords: レポートソースとしてのAnalytics;a4t;A4T
seo-description: Adobe Analytics に基づいたアクティビティを Adobe Target 内で作成する場合（A4T）のユーザーアカウントの要件です。
seo-title: ユーザー権限の要件
solution: Target,Analytics
title: ユーザー権限の要件
topic: Reports and Analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: e1d5f642505ce62900fc55784b178ba0fb320184

---


# ユーザー権限の要件 {#user-permission-requirements}

（A4T）で [!DNL Adobe Analytics][!DNL Adobe Target] のベースとなるアクティビティを作成するためのユーザーアカウント要件に関する情報です。

アクティビティを [!DNL Analytics] 定義するときにレポートスイートを選択するには、 [!DNL Analytics] ユーザーアカウントと [!DNL Target] ユーザーアカウントの両方が必要です。

次の節の説明に従って、ユーザーアカウントを設定する必要があります。

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

管理コンソールで [!DNL Adobe Experience Cloud][次のタスクを実行](https://adminconsole.adobe.com)します。

### ソリューションアカウントのAdobe IDへのリンク

ユーザー [!DNL Analytics] アカウントと [!DNL Target] ユーザーアカウントは、Adobe IDにリンクされている必要があります。

詳しくは [、組織とアカウントのリンク](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html)を参照してください。

### Experience Cloudグループメンバーシップの設定

アクセス権を持つ1つまたは複数 [!DNL Experience Cloud] のグループのメンバーである [!DNL Analytics][!DNL Target]必要があります。

詳しくは、Experience Cloudユーザーと製品 [の管理](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)を参照してください。


## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

次のタスクを実行します [!DNL Adobe Analytics]。

### Analyticsレポートスイートへのアクセスの設定

Analyticsによるアクティビティのレポートを作成または表示する前に **[!UICONTROL 、「全レポートアクセス]** 」グループのメンバー、または使用するレポートスイート内の少なくとも1つのレポートにアクセスできるグループのメンバーである必要があります。レポートを表示できない場合は、これらのいずれかのグループのメンバーであることを確認してください。

詳しくは [、製品プロファイルとグループ](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html#section_AB50558124D541CF80A0D3D76D35A4BF)を参照してください。

### Webサービスアクセスグループへのアクセスの設定

のレポートソースとして使用できるようにするには、の [!DNL Adobe Analytics] Webサービスアクセスグループ [!DNL Analytics] に所属 [!DNL Target]している必要があります。

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

追加の権限は必要ありません。
