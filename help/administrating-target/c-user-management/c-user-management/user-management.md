---
description: Adobe Admin Console でユーザーを追加したり権限を管理したりできます。
keywords: ユーザーの追加;ユーザーの管理;ユーザー権限
seo-description: Adobe Admin Console でユーザーを追加したり権限を管理したりできます。
seo-title: ユーザー
solution: 'Target '
subtopic: 導入
title: ユーザー
topic: Standard
uuid: 9b311dd3-b8fa-483d-aedd-96761cfcd67e
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ユーザー{#users}

Adobe Admin Console でユーザーを追加したり権限を管理したりできます。

>[!NOTE]
>
>[!UICONTROL プロパティ]と[!UICONTROL 権限] の機能は [!DNL Target] Premium ソリューションの一部です。[!DNL Target] Premium ライセンスのない [!DNL Target] Standard では利用できません。
>保有しているライセンスが Standard か Premium かどうかは、[!DNL Target] の UI 上部の「[!UICONTROL 設定]」リンクをクリックすることで確認できます。
>
>**[!DNL Target]Standard のお客様**： 「[!UICONTROL ユーザー]」タブ（[!UICONTROL 設定／ユーザー]）が表示された場合、ライセンスは、[!DNL Target] Standard です。[!DNL Target Standard のお客様は、[!DNL Adobe Admin Console] でユーザーを追加したり、権限を割り当てたりする際は、この記事の手順に従ってください。
>
>**[!DNL Target]Premium のお客様**： 「[!UICONTROL プロパティ]」タブ（[!UICONTROL 設定／プロパティ]）が表示された場合、ライセンスは [!DNL Target] Premium です。[!DNL Target] Premium のお客様は、[!DNL Adobe Admin Console] でユーザーを追加したり、権限を割り当てたりする際は、[ Enterprise ユーザーの権限 ](/help/administrating-target/c-user-management/property-channel/property-channel.md) と [Enterprise 権限 ](/help/administrating-target/c-user-management/property-channel/properties-overview.md) の設定の手順に従ってください。

システム管理者ユーザーのみが、ユーザーを追加し、ユーザーの権限を管理できます。システム管理者の役割は [!DNL Experience Cloud] レベルで割り当てられます。[!DNL Experience Cloud] の役割は各ソリューションで管理される役割とは独立しています。

[!DNL Adobe Target] を初めて使用するときには、[!DNL Adobe Experience Cloud] アカウントのところに、「Adobe.com」で終わる ID があらかじめ表示されています。これらの ID は Adobe チームのメンバーのもので、新しいアカウントや [!DNL Adobe Target] の使い方について疑問点があるときに、メンバーに質問をすることができます。質問があるときは、通常の方法で Adobe チームにご連絡ください。

新しいユーザーは、Adobe Experience Cloud のアカウントでログインしてから、[!UICONTROL  カードをクリックして ] にログインするまでは、[!DNL Target Standard/Premium]ユーザー[!DNL Target] ページに表示されません。

デフォルトでは、すべての [!DNL Target] ユーザーはまず監視者権限を持ちます。

システム管理者ユーザーは、ユーザーリストで識別できます。アクセスレベルの変更が必要な場合は、いずれかのシステム管理者ユーザーにお問い合わせください。

## Adobe Admin Console へのアクセス {#access}

Adobe Admin Console で実行するタスクの場合は、次の手順でコンソールにアクセスします。

1. [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) に移動し、まだログインしていない場合は Adobe ID でサインインします。

   または

   If you are already logged in to the Experience Cloud, go to [https://www.experiencecloud.adobe.com](https://experiencecloud.adobe.com), then click the [!UICONTROL App] icon in the top navigation bar &gt; click **[!UICONTROL Admin]** on the right side.

1. （条件付き）複数の組織の [!DNL Admin Console for Enterprise] へのアクセス権を持っている場合、右隅または上部のナビゲーションバーにあるユーザーアバターをクリックしてから、目的の組織を選択します。

## ユーザーの追加 {#add-users}

ユーザー管理操作は、すべて [!DNL Adobe Admin Console for Enterprise] で実行する必要があります。ただし、[!DNL Target] のすべての既存のユーザーは、[!DNL Target] から [!DNL Admin Console for Enterprise] に移行されます。

1. [管理コンソール](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)で **[!UICONTROL 、ユーザー]** / **[!UICONTROL ユーザー]** をクリックして新しいユーザーを作成するか、既存のユーザーを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/enterprise/help/users.html)の手順に従ってください。

## ユーザーグループの作成 {#user-groups}

開発者、アナリスト、マーケティング担当者、エグゼクティブなどのユーザーグループを作成して、複数のアドビ製品およびワークスペースにわたって権限を割り当てることができます。新しいチームメンバーに様々なアドビ製品にわたるすべての適切な権限を割り当てることは、特定のユーザーグループに追加するくらいに簡単です。

1. [管理コンソール](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)で **[!UICONTROL 、ユーザー]** / **[!UICONTROL ユーザーグループ]** をクリックして、新しいユーザーグループを作成するか、既存のグループを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/enterprise/help/users.html)の手順に従ってください。

## 役割および権限の指定 {#roles-permissions}

システム管理者のみ、[!DNL Target] のユーザーの役割を指定できます。例えば、Standard の承認者ユーザーは、Experience Cloud の管理者権限を併せ持たない限り、監視者を承認者に変更できません。

システム管理者ユーザーはシステムにユーザーを追加する必要があります。ユーザーは自動的には追加されません。ユーザーのアカウントを登録する前に、Experience Cloud から招待の電子メールを送信して、電子メールアドレスを確認する必要があります。

1. [Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

   ![「製品」タブ](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. 目的の設定の名前をクリックします。
1. 「**[!UICONTROL ユーザー]**」をクリックします。

   [!UICONTROL 「ユーザー] 」タブには、そのワークスペース内のすべてのユーザーが表示されます。

   ![設定ユーザー](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new.png)

1. [!UICONTROL 製品の役割]列の各ユーザーのドロップダウンリストを使用して、目的の権限の役割（監視者、編集者、承認者）を選択します。

   | 役割 | 説明 |
   |--- |--- |
   | 監視者 | アクティビティを表示できますが、作成または編集はできません。 |
   | 編集者 | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | 承認者 | アクティビティの作成、編集、アクティブ化、停止ができます。 |

詳しくは、*Enterprise ユーザーガイド*&#x200B;の [Admin Console での製品の権限およびロールの管理](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)を参照してください。

## トレーニングビデオ:Target Workspaceの設定方法

学習内容：

* Adobe TargetインターフェイスからAdobe Admin Consoleにアクセスする（3つの方法）
* Adobe Admin Consoleでのワークスペースの設定
   * ユーザーをワークスペースに追加します
   * プロパティをワークスペースに追加します
* デフォルトのワークスペースの概要を説明します

>[!VIDEO](https://video.tv.adobe.com/v/19463/?captions=jpn)
