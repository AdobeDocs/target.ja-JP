---
keywords: add user;manage user;user permissions
description: Adobe Admin Console でユーザーを追加したり権限を管理したりできます。
title: ユーザー
subtopic: Getting Started
topic: Standard
uuid: 9b311dd3-b8fa-483d-aedd-96761cfcd67e
translation-type: tm+mt
source-git-commit: 2c34371005be851b2a86113050c01182334c2dc9
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 62%

---


# ユーザー{#users}

You can add users and manage their permissions in the [!DNL Adobe Admin Console].

>[!NOTE]
>
>[!UICONTROL プロパティ]と[!UICONTROL 権限] の機能は [!DNL Target] Premium ソリューションの一部です。[!DNL Target] Premium ライセンスのない [!DNL Target] Standard では利用できません。
>You can tell whether your organization has a Standard or Premium license by clicking the [!UICONTROL Administration] link at the top of the [!DNL Target] UI.
>
>**[!DNL Target]標準顧客&#x200B;**: 「[!UICONTROL ユーザー]」タブ([!UICONTROL 管理/ユーザー])が表示される(「**[!UICONTROL プロパティ&#x200B;]**」タブが表示されない)場合は、組織に[!DNL Target]標準ライセンスがあります。 [!DNL Target Standard のお客様は、[!DNL Adobe Admin Console]でユーザーを追加したり、権限を割り当てたりする際は、この記事の手順に従ってください。
>
>**[!DNL Target]Premiumのお客様&#x200B;**: 「[!UICONTROL ユーザー]」タブと「[!UICONTROL プロパティ]」タブ(管理/プロパティ[!UICONTROL )が表示される場合は、組織に][!DNL Target]Premiumライセンスがあります。[!DNL Target]Premium のお客様は、[!DNL Adobe Admin Console]でユーザーを追加したり、権限を割り当てたりする際は、[Enterprise ユーザーの権限](/help/administrating-target/c-user-management/property-channel/property-channel.md)と[Enterprise 権限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)の設定の手順に従ってください。

ユーザーと権限を管理するには、『 [Enterprise &amp; Teams User Guide](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) 』の「製品とプロファイルの *管理*」を参照してください。

[!DNL Adobe Target] を初めて使用するときには、[!DNL Adobe Experience Cloud] アカウントのところに、「Adobe.com」で終わる ID があらかじめ表示されています。これらの ID は Adobe チームのメンバーのもので、新しいアカウントや [!DNL Adobe Target] の使い方について疑問点があるときに、メンバーに質問をすることができます。質問があるときは、通常の方法で Adobe チームにご連絡ください。

You will not see the new user listed on the [!UICONTROL Users] page until the user logs in using his or her [!DNL Adobe Experience Cloud] account and then logs in to [!DNL Target Standard/Premium].

デフォルトでは、すべての [!DNL Target] ユーザーはまず監視者権限を持ちます。

Admin users are identified in the [!UICONTROL Users] list. アクセスレベルの変更が必要な場合は、システム管理者ユーザーに問い合わせてください。

## Adobe Admin Console へのアクセス {#access}

Adobe Admin Console で実行するタスクの場合は、次の手順でコンソールにアクセスします。

1. 内で、 [!DNL Target]管理 **[!UICONTROL /]** ユーザー **[!UICONTROL /]** ユーザー管理をクリックします ****。

   または

   Go to [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/), then sign in using your Adobe ID, if you have not already logged in.

1. （条件付き）複数の組織の [!DNL Admin Console for Enterprise] へのアクセス権を持っている場合、右隅または上部のナビゲーションバーにあるユーザーアバターをクリックしてから、目的の組織を選択します。

## ユーザーの追加 {#add-users}

ユーザー管理操作は、すべて [!DNL Adobe Admin Console for Enterprise] で実行する必要があります。ただし、[!DNL Target] のすべての既存のユーザーは、[!DNL Target] から [!DNL Admin Console for Enterprise] に移行されます。

1. [管理コンソールで](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)、 **[!UICONTROL ユーザー]** / **[!UICONTROL ユーザー]** (Users)をクリックして、新しいユーザーを作成したり、既存のユーザーを編集したりします。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/enterprise/help/users.html)の手順に従ってください。

## ユーザーグループの作成 {#user-groups}

開発者、アナリスト、マーケティング担当者、エグゼクティブなどのユーザーグループを作成して、複数のアドビ製品およびワークスペースにわたって権限を割り当てることができます。新しいチームメンバーに様々なアドビ製品にわたるすべての適切な権限を割り当てることは、特定のユーザーグループに追加するくらいに簡単です。

1. [管理コンソールで](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)、 **[!UICONTROL ユーザー]** / **** ユーザーグループをクリックして、新しいユーザーグループを作成するか、既存のグループを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/enterprise/help/users.html)の手順に従ってください。

## 役割および権限の指定 {#roles-permissions}

システム管理者のみ、[!DNL Target] のユーザーの役割を指定できます。For example, a Standard approver user cannot change an observer to an approver, without also having [!DNL Experience Cloud] Admin rights.

システム管理者ユーザーはシステムにユーザーを追加する必要があります。ユーザーは自動的には追加されません。They are invited by email from the [!DNL Experience Cloud] and must confirm their email addresses before their accounts are registered.

1. [Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

   ![「製品」タブ](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. 目的のワークスペース（例えば、デフォルトのワークスペース）をクリックします。

   ![デフォルトのワークスペース](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace.png)

   「[!UICONTROL ユーザー]」タブにワークスペースのすべてのユーザーが表示されます。

   ![設定ユーザー](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new.png)

1. [!UICONTROL 製品の役割]列の各ユーザーのドロップダウンリストを使用して、目的の権限の役割（承認者、編集者、監視者）を選択します。

   ![「製品の役割」ドロップダウンリスト](/help/administrating-target/c-user-management/c-user-management/assets/product-role.png)

   | 役割 | 説明 |
   |--- |--- |
   | 承認者 | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | 編集者 | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | 監視者 | アクティビティを表示できますが、作成または編集はできません。 |

詳しくは、*Enterprise ユーザーガイド*&#x200B;の [Admin Console での製品の権限およびロールの管理](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)を参照してください。

## Training video: How to Configure Target Workspaces ![Tutorial badge](/help/assets/tutorial.png)

学習内容：

* Adobe Target インターフェイスから Adobe Admin Console へのアクセス（3 つの方法）
* Adobe Admin Console でのワークスペースの設定
   * ユーザーをワークスペースに追加します
   * プロパティをワークスペースに追加します
* デフォルトのワークスペースの概要を説明します

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
