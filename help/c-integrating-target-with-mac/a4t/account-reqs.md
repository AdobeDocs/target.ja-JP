---
keywords: レポートソースとしてのAnalytics;a4t;A4T；要件
description: Analytics for Analytics(A4T)を使用して、Adobe TargetでAdobe Analyticsベースのアクティビティを作成するのに必要なユーザーアカウントの要件を設定する方法について説明します。
title: A4Tに必要なユーザー権限の要件を教えてください。
feature: Analytics for Target (A4T)
solution: Target,Analytics
translation-type: tm+mt
source-git-commit: a4f67638c00f571565d548afb9c10026c232dfd5
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 36%

---


# ユーザー権限の要件

（A4T）で [!DNL Adobe Analytics]のベースとなるアクティビティ[!DNL Adobe Target] を作成するためのユーザーアカウント要件に関する情報です。

[!DNL Analytics]アクティビティを定義するときは、レポートスイートを選択する前に、 [!DNL Analytics]ユーザーアカウントと[!DNL Target]ユーザーアカウントの両方が必要になります。

次の節の説明に従って、ユーザーアカウントを設定する必要があります。

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

[!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com) で、次の作業を実行します。

### ソリューションアカウントを Adobe ID にリンクします。

あなたの[!DNL Analytics]および[!DNL Target]のユーザーアカウントは Adobe ID にリンクされている必要があります。

詳しくは、[組織とアカウントのリンク](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html)を参照してください。

### Experience Cloud グループのメンバーシップを設定します。

あなたは[!DNL Analytics] と [!DNL Target]にアクセスできる 1 つ以上の[!DNL Experience Cloud]グループのメンバーでなければなりません。

詳しくは、[Experience Cloudユーザーと製品の管理](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)を参照してください。

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

特定のレポートスイートでA4Tを使用するには、そのレポートスイートへのアクセス権を持っており、[!DNL Web Services Access]グループにアクセス権を付与している必要があります。

1. **[!UICONTROL Admin Console]**&#x200B;で、[!DNL Analytics]製品プロファイルをクリックし、**[!UICONTROL 権限]**&#x200B;タブをクリックします。

   その後、プロファイルがアクセス権を持つレポートスイートを確認できます。

1. [!DNL Target]内のアクセス権を持つレポートスイートが、所属する製品プロファイルにリストされているレポートスイートの1つであることを確認します。

   次の図は、すべてのレポートスイートにアクセスできる製品プロファイルの例です。

   ![「Admin Console権限」タブ](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. [!UICONTROL Webサービスアクセス]グループへのアクセスを設定します。

   [!DNL Analytics]の[!UICONTROL Web Services Access]グループへのアクセスは、[!DNL Target]のレポートソースとして[!DNL Analytics]を使用できるようにする必要があります。


## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

追加の権限は必要ありません。
