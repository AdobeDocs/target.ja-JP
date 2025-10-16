---
keywords: ユーザーの追加;ユーザーの管理;ユーザー権限
description: ' [!DNL Adobe Admin Console]  を使用して、 [!DNL Adobe Target Standard] でユーザーとその権限と権限を管理する方法を説明します。'
title: ユーザーを追加し、 [!DNL Target Standard]  アカウントの権限を管理する方法？
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: 484971ab0fcd07205935c0fef3ea1484f40c3e96
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 64%

---

# ユーザー

[!DNL Target Standard] アカウントの [!DNL Adobe Admin Console] でユーザーを追加し、その権限を管理します。

>[!NOTE]
>
>[!UICONTROL Properties] と [!UICONTROL Permissions] の機能は [!DNL Target Premium] ソリューションの一部です。 [!DNL Target] Premium ライセンスのない [!DNL Target] Standard では利用できません。
>
>組織が [!UICONTROL Standard] ライセンスまたは [!UICONTROL Premium] ライセンスを持っているかどうかを確認するには、[!UICONTROL Administration] UI の上部にある [!DNL Target] リンクをクリックします。
>
>* **[!DNL Target]&#x200B;[!UICONTROL Standard] のお客様**: 「[!UICONTROL Users]」タブ（[!UICONTROL Administration > Users]）が表示され、「**[!UICONTROL Properties]**」タブが表示されない場合、組織の [!DNL Target] ライセンスは [!UICONTROL Standard] です。 [!DNL Target] [!UICONTROL Standard] のお客様は、[!DNL Adobe Admin Console] でユーザーを追加したり、権限を割り当てたりする際は、この記事の手順に従ってください。
>
>* **[!DNL Target]Premium のお客様**:「[!UICONTROL Users]」タブと「[!UICONTROL Properties]」タブ（[!UICONTROL Administration > Properties]）が表示された場合、組織のライセンスは [!DNL Target] Premium です。 [!DNL Target] Premium のお客様が [!DNL Adobe Admin Console] でユーザーの追加や権限の割り当てを行う際は、[Enterprise ユーザーの権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) と [Enterprise 権限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)の設定の手順に従ってください。
>
>ユーザーと権限の管理方法について詳しくは、[製品およびプロファイルの管理](https://helpx.adobe.com/jp/enterprise/using/manage-products-and-profiles.html)の&#x200B;*エンタープライズおよびチームユーザーガイド*&#x200B;を参照してください。

[!DNL Adobe Target] を初めて使用するときには、[!DNL Adobe Experience Cloud] アカウントのところに、「Adobe.com」で終わる ID があらかじめ表示されています。これらの ID は [!DNL Adobe] チームのメンバーのもので、新しいアカウントや [!DNL Adobe Target] の使い方について疑問点があるときに、メンバーに質問をすることができます。質問があるときは、通常の方法で Adobe チームにご連絡ください。

新しいユーザーは、[!UICONTROL Users] アカウントを使用してログインしてから、[!DNL Adobe Experience Cloud] にログインするまでは、[!DNL Target] ページに表示されません。

デフォルトでは、すべての [!DNL Target] ユーザーはまず [!UICONTROL Observer] の権限を持ちます。

管理者ユーザーは、[!UICONTROL Users] リストを見るとわかります。 アクセスレベルの変更が必要な場合は、いずれかのシステム管理者ユーザーにお問い合わせください。

## [!DNL Target]内からユーザー情報を表示する

ワークスペースごとの役割やメールアドレスなど、[!DNL Target] UI で現在のユーザーのリストを表示できます。

[!UICONTROL Users] ページを表示するには、**[!UICONTROL Administration]**/**[!UICONTROL Users]** をクリックします。

>[!NOTE]
>
>既存のユーザーを管理したり、新しいユーザーを追加したりするには、以下に説明するように、[!UICONTROL Adobe Admin Console] を使用する必要があります。

## [!DNL Adobe Admin Console] へのアクセス {#access}

[!DNL Adobe Admin Console] で実行するタスクの場合は、次の手順でコンソールにアクセスします。

1. [!DNL Target] 内から、**[!UICONTROL Administration]**/**[!UICONTROL Users]**/**[!UICONTROL Users Management]** をクリックします。

   または

   [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) に移動し、まだの場合は Adobe ID でログインします。

1. （条件付き）複数の組織の [!DNL Admin Console for Enterprise] へのアクセス権を持っている場合、右隅または上部のナビゲーションバーにあるユーザーアバターをクリックしてから、目的の組織を選択します。

## ユーザーの追加 {#add-users}

ユーザー管理操作は、すべて [!DNL Adobe Admin Console for Enterprise] で実行する必要があります。ただし、[!DNL Target] のすべての既存のユーザーは、[!DNL Target] から [!DNL Admin Console for Enterprise] に移行されます。

1. [Admin Consoleで &#x200B;](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)、**[!UICONTROL Users]**/**[!UICONTROL Users]** をクリックして、新しいユーザーを作成するか、既存のユーザーを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/jp/enterprise/help/users.html)の手順に従ってください。

## ユーザーグループの作成 {#user-groups}

開発者、アナリスト、マーケター、エグゼクティブなどのユーザーグループを作成し、複数の [!DNL Adobe] 製品とワークスペースに権限を割り当てることができます。新しいチームメンバーに様々な [!DNL Adobe] 製品にわたるすべての適切な権限を割り当てることは、特定のユーザーグループに追加するのと同じくらいに簡単です。

1. [Admin Consoleで &#x200B;](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)、**[!UICONTROL Users]**/**[!UICONTROL User Groups]** をクリックして、新しいユーザーグループを作成するか、既存のユーザーグループを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/jp/enterprise/help/users.html)の手順に従ってください。

## 役割および権限の指定 {#roles-permissions}

システム管理者のみ、[!DNL Target] のユーザーの役割を指定できます。例えば、[!UICONTROL Standard] の承認者ユーザーは、の管理者権限を併せ持たない限り、監視者を承認者 [!DNL Experience Cloud] 変更できません。

システム管理者ユーザーはシステムにユーザーを追加する必要があります。ユーザーは自動的には追加されません。ユーザーのアカウントを登録する前に、[!DNL Experience Cloud] から招待メールを送信して、メールアドレスを確認する必要があります。

>[!NOTE]
>
>[!DNL Target] でアクティビティを表示するには、ユーザーは、少なくとも [!UICONTROL Observer] の役割を持つワークスペースに直接割り当てられている必要があります。 ユーザーグループのみを介した割り当ては不十分です。 デフォルトワークスペースへのアクセス権をユーザーに付与することを一般的にお勧めします。

1. [Admin Consoleで &#x200B;](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) 「**[!UICONTROL Products]**」をクリックしてから、目的の商品名を選択します。

1. 目的のワークスペース（デフォルトのワークスペースなど）をクリックします。

   「[!UICONTROL Users]」タブには、そのワークスペース内のすべてのユーザーが表示されます。

1. [!UICONTROL Approver] 列の各ユーザーのドロップダウンリストを使用して、目的の権限の役割（[!UICONTROL Editor]、[!UICONTROL Observer]、[!UICONTROL Publisher]、[!UICONTROL Product Role]）を選択します。

   | 役割 | 説明 |
   |--- |--- |
   | [!UICONTROL Approver] | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | [!UICONTROL Editor] | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | [!UICONTROL Observer] | アクティビティを表示できますが、作成または編集はできません。 |
   | [!UICONTROL Publisher] | [!UICONTROL Observer] の役割と同様です（アクティビティを表示できますが、作成または編集はできません）。 ただし、[!UICONTROL Publisher] の役割には、アクティビティをアクティブ化する追加の権限があります。 |

詳しくは、*Enterprise ユーザーガイド*&#x200B;の [Admin Console での製品の権限およびロールの管理](https://helpx.adobe.com/jp/enterprise/help/manage-permissions-and-roles.html)を参照してください。

## トレーニングビデオ：Adobe Target Workspaces の設定方法 ![チュートリアルバッジ](/help/main/assets/tutorial.png)

学習内容：

* Adobe Target インターフェイスから Adobe Admin Console へのアクセス（3 つの方法）
* Adobe Admin Console でのワークスペースの設定
   * ユーザーをワークスペースに追加します
   * プロパティをワークスペースに追加します
* デフォルトのワークスペースの概要を説明します

>[!NOTE]
>
>パフォーマンスを向上、新機能のリリースに要するメンテナンス時間を短縮、製品全体でのユーザーエクスペリエンスが向上するため、[!DNL Target] [!UICONTROL Administration] メニュー（以前の [!UICONTROL Setup]）のデザインが一新されました。 次のビデオの情報は、一般的には正確ですが、オプションの場所が若干異なる場合があります。更新されたビデオは間もなく投稿される予定です。

>[!VIDEO](https://video.tv.adobe.com/v/3421733?captions=jpn)
