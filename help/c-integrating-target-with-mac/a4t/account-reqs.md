---
keywords: レポートソースとしてのAnalytics;a4t;A4T；要件
description: Adobe [!DNL Target] using Analytics for [!DNL Target] (A4T)でAdobe Analyticsベースのアクティビティを作成するために必要なユーザーアカウント要件を設定する方法を説明します。
title: A4Tに必要なユーザー権限の要件を教えてください。
feature: Analytics for Target（A4T）
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
source-git-commit: c9c335c241727c4eff1d27f52853e32b8d18b6a5
workflow-type: tm+mt
source-wordcount: '308'
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

詳しくは、[組織とアカウントのリンク](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en)を参照してください。

### Experience Cloud グループのメンバーシップを設定します。

あなたは[!DNL Analytics] と [!DNL Target]にアクセスできる 1 つ以上の[!DNL Experience Cloud]グループのメンバーでなければなりません。

詳しくは、「[Experience Cloudユーザーと製品の管理](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)」を参照してください。

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

特定のレポートスイートでA4Tを使用するには、そのレポートスイートへのアクセス権を持ち、[!DNL Web Services Access]グループに対するアクセス権を付与する必要があります。

1. **[!UICONTROL Admin Console]**&#x200B;で、[!DNL Analytics]製品プロファイルをクリックし、「**[!UICONTROL 権限]**」タブをクリックします。

   その後、プロファイルがアクセスできるレポートスイートを確認できます。

1. [!DNL Target]でアクセスするレポートスイートが、所属する製品プロファイルにリストされているレポートスイートの1つであることを確認します。

   次の図は、すべてのレポートスイートにアクセスできる製品プロファイルの例です。

   ![「Admin Console権限」タブ](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. [!UICONTROL Webサービスアクセス]グループへのアクセスを設定します。

   [!DNL Target]のレポートソースとして[!DNL Analytics]を使用するには、[!DNL Analytics]の[!UICONTROL Webサービスアクセス]グループへのアクセスが必要です。


## アドビ [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

追加の権限は必要ありません。
