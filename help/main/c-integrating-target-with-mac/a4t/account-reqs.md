---
keywords: レポートソースとしての Analytics;A4T;A4T；要件
description: AdobeでAdobe Analyticsベースのアクティビティを作成するために必要なユーザーアカウント要件を設定する方法について説明します [!DNL Target] 用に Analytics を使用する [!DNL Target] (A4T)。
title: A4T に必要なユーザー権限の要件を教えてください。
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 34%

---

# ユーザー権限の要件

（A4T）で [!DNL Adobe Analytics]のベースとなるアクティビティ[!DNL Adobe Target] を作成するためのユーザーアカウント要件に関する情報です。

[!DNL Analytics]アクティビティを定義するときは、レポートスイートを選択する前に、 [!DNL Analytics]ユーザーアカウントと[!DNL Target]ユーザーアカウントの両方が必要になります。

次の節の説明に従って、ユーザーアカウントを設定する必要があります。

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

[!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com) で、次の作業を実行します。

### ソリューションアカウントを Adobe ID にリンクします。

あなたの[!DNL Analytics]および[!DNL Target]のユーザーアカウントは Adobe ID にリンクされている必要があります。

詳しくは、 [組織とアカウントのリンク](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en).

### Experience Cloud グループのメンバーシップを設定します。

あなたは[!DNL Analytics] と [!DNL Target]にアクセスできる 1 つ以上の[!DNL Experience Cloud]グループのメンバーでなければなりません。

詳しくは、 [Experience Cloudユーザーと製品を管理する](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

特定のレポートスイートで A4T を使用するには、そのレポートスイートへのアクセス権を持っていて、 [!DNL Web Services Access] グループ化します。

1. In **[!UICONTROL Admin Console]**、 [!DNL Analytics] 製品プロファイルを選択し、 **[!UICONTROL 権限]** タブをクリックします。

   その後、プロファイルがアクセスできるレポートスイートを確認できます。

1. でアクセス権を持つレポートスイートがあることを確認します。 [!DNL Target] は、自分が属している製品プロファイルにリストされているものの 1 つです。

   次の図は、すべてのレポートスイートにアクセスできる製品プロファイルの例です。

   ![Admin Console権限タブ](/help/main/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. へのアクセスの設定 [!UICONTROL Web サービスへのアクセス] グループ化します。

   へのアクセス [!UICONTROL Web サービスへのアクセス] グループ化 [!DNL Analytics] は、 [!DNL Analytics] レポートソースとして [!DNL Target].


## アドビ [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

追加の権限は必要ありません。
