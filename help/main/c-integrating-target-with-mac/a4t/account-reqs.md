---
keywords: レポートソースとしての Analytics;a4t;A4T；要件
description: ' [!DNL Target]  Analytics for [!DNL Target]  （A4T）を使用してAdobeでAdobe Analytics ベースのアクティビティを作成するために必要なユーザーアカウント要件を設定する方法について説明します。'
title: A4T に必要なユーザー権限要件を教えてください。
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 36%

---

# ユーザー権限の要件

（A4T）で [!DNL Adobe Analytics]のベースとなるアクティビティ[!DNL Adobe Target] を作成するためのユーザーアカウント要件に関する情報です。

[!DNL Analytics]アクティビティを定義するときは、レポートスイートを選択する前に、 [!DNL Analytics]ユーザーアカウントと[!DNL Target]ユーザーアカウントの両方が必要になります。

次の節の説明に従って、ユーザーアカウントを設定する必要があります。

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

[!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com) で次のタスクを実行します。

### ソリューションアカウントを Adobe ID にリンクします。

あなたの[!DNL Analytics]および[!DNL Target]のユーザーアカウントは Adobe ID にリンクされている必要があります。

詳しくは、[ 組織とアカウントのリンク ](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=ja) を参照してください。

### Experience Cloud グループのメンバーシップを設定します。

あなたは[!DNL Analytics] と [!DNL Target]にアクセスできる 1 つ以上の[!DNL Experience Cloud]グループのメンバーでなければなりません。

詳しくは、[Experience Cloud ユーザーと製品の管理 ](https://experienceleague.adobe.com/ja/docs/core-services/interface/administration/admin-tool-experience-cloud) を参照してください。

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

特定のレポートスイートで A4T を使用するには、そのレポートスイートへのアクセス権を持ち、レポートグループへのアクセス権を付与する必要が [!DNL Web Services Access] ります。

1. **[!UICONTROL Admin Console]** で、[!DNL Analytics] の製品プロファイルをクリックしてから、「**[!UICONTROL Permissions]**」タブをクリックします。

   その後、プロファイルがアクセスできるレポートスイートを確認できます。

1. [!DNL Target] でアクセスするレポートスイートが、属する製品プロファイルにリストされているレポートスイートのいずれかであることを確認します。

   次の図は、すべてのレポートスイートにアクセスできる製品プロファイルの例です。

   ![Admin Consoleの「権限」タブ ](/help/main/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. [!UICONTROL Web Services Access] グループへのアクセスを設定します。

   [!UICONTROL Web Services Access] を [!DNL Analytics] のレポートソースとして使用するには、[!DNL Analytics] の [!DNL Target] グループにアクセスできる必要があります。


## アドビ [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

追加の権限は必要ありません。
