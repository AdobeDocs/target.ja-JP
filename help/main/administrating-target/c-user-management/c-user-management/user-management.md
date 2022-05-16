---
keywords: ユーザーの追加;ユーザーの管理;ユーザー権限
description: Adobe Admin Console を使用して、Adobe Target でユーザーとその権限を管理する方法を説明します。
title: ユーザーを追加し、権限を管理する方法を教えてください。
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: ht
source-wordcount: '911'
ht-degree: 100%

---

# ユーザー

[!DNL Adobe Admin Console] でユーザーを追加して権限を管理します。

>[!NOTE]
>
>[!UICONTROL プロパティ]と[!UICONTROL 権限] の機能は [!DNL Target] Premium ソリューションの一部です。[!DNL Target] Premium ライセンスのない [!DNL Target] Standard では利用できません。
>保有しているライセンスが Standard か Premium かどうかは、[!DNL Target] の UI 上部の「[!UICONTROL 管理]」リンクをクリックすることで確認できます。
>
>* **[!DNL Target]Standarrd のお客様**：[!UICONTROL ユーザー] タブ（[!UICONTROL 管理／ユーザー]）が表示される（「**[!UICONTROL プロパティ]**」タブは表示されない）場合、組織のライセンスは[!DNL Target] Standard です。[!DNL Target] Standard のお客様は、[!DNL Adobe Admin Console] でユーザーを追加したり、権限を割り当てたりする際は、この記事の手順に従ってください。
>
>* **[!DNL Target]Premium のお客様**：「[!UICONTROL ユーザー]」タブと「[!UICONTROL プロパティ]」タブ（[!UICONTROL 管理／プロパティ]）が表示された場合、組織のライセンスは [!DNL Target] Premium です。[!DNL Target] Premium のお客様が [!DNL Adobe Admin Console] でユーザーの追加や権限の割り当てを行う際は、[Enterprise ユーザーの権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) と [Enterprise 権限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)の設定の手順に従ってください。
>
>ユーザーと権限の管理方法について詳しくは、[製品およびプロファイルの管理](https://helpx.adobe.com/jp/enterprise/using/manage-products-and-profiles.html)の&#x200B;*エンタープライズおよびチームユーザーガイド*&#x200B;を参照してください。

[!DNL Adobe Target] を初めて使用するときには、[!DNL Adobe Experience Cloud] アカウントのところに、「Adobe.com」で終わる ID があらかじめ表示されています。これらの ID は [!DNL Adobe] チームのメンバーのもので、新しいアカウントや [!DNL Adobe Target] の使い方について疑問点があるときに、メンバーに質問をすることができます。質問があるときは、通常の方法で Adobe チームにご連絡ください。

新しいユーザーは、[!DNL Adobe Experience Cloud] のアカウントでログインしてから、[!DNL Target Standard/Premium] にログインするまでは、[!UICONTROL ユーザー]ページに表示されません。

デフォルトでは、すべての [!DNL Target] ユーザーはまず監視者権限を持ちます。

管理者ユーザーは、「[!UICONTROL ユーザー]」リストを見るとわかります。アクセスレベルの変更が必要な場合は、いずれかのシステム管理者ユーザーにお問い合わせください。

## Target 内からユーザー情報を表示する

Target 内から直接、ワークスペースごとの役割やメールアドレスなど、Target 環境における現在のユーザーのリストを表示できます。

ユーザーページを表示するには、**[!UICONTROL 管理]**／**[!UICONTROL ユーザー]**&#x200B;をクリックします。

![Target 内からのユーザーリスト](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>既存のユーザーを管理したり、新しいユーザーを追加したりするには、以下に説明するように、[!UICONTROL Adobe Admin Console] を使用する必要があります。

## Adobe Admin Console へのアクセス {#access}

Adobe Admin Console で実行するタスクの場合は、次の手順でコンソールにアクセスします。

1. [!DNL Target] 内から、**[!UICONTROL 管理]**／**[!UICONTROL ユーザー]**／**[!UICONTROL ユーザー管理]**&#x200B;をクリックします。

   または

   [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) に移動し、まだの場合は Adobe ID でログインします。

1. （条件付き）複数の組織の [!DNL Admin Console for Enterprise] へのアクセス権を持っている場合、右隅または上部のナビゲーションバーにあるユーザーアバターをクリックしてから、目的の組織を選択します。

## ユーザーの追加 {#add-users}

ユーザー管理操作は、すべて [!DNL Adobe Admin Console for Enterprise] で実行する必要があります。ただし、[!DNL Target] のすべての既存のユーザーは、[!DNL Target] から [!DNL Admin Console for Enterprise] に移行されます。

1. [Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) で&#x200B;**[!UICONTROL ユーザー]**／**[!UICONTROL ユーザー]**&#x200B;をクリックして、新しいユーザーを作成するか、既存のユーザーを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/jp/enterprise/help/users.html)の手順に従ってください。

## ユーザーグループの作成 {#user-groups}

開発者、アナリスト、マーケティング担当者、エグゼクティブなどのユーザーグループを作成して、複数のアドビ製品およびワークスペースにわたって権限を割り当てることができます。新しいチームメンバーに様々なアドビ製品にわたるすべての適切な権限を割り当てることは、特定のユーザーグループに追加するくらいに簡単です。

1. [Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) で&#x200B;**[!UICONTROL ユーザー]**／**[!UICONTROL ユーザーグループ]**&#x200B;をクリックして、新しいユーザーグループを作成するか、既存のユーザーグループを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/jp/enterprise/help/users.html)の手順に従ってください。

## 役割および権限の指定 {#roles-permissions}

システム管理者のみ、[!DNL Target] のユーザーの役割を指定できます。例えば、Standard の承認者ユーザーは、[!DNL Experience Cloud] の管理者権限を併せ持たない限り、監視者を承認者に変更できません。

システム管理者ユーザーはシステムにユーザーを追加する必要があります。ユーザーは自動的には追加されません。ユーザーのアカウントを登録する前に、[!DNL Experience Cloud] から招待メールを送信して、メールアドレスを確認する必要があります。

1. [Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

   ![「製品」タブ](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 目的のワークスペース（デフォルトのワークスペースなど）をクリックします。

   ![デフォルトのワークスペース](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   「[!UICONTROL ユーザー]」タブにワークスペースのすべてのユーザーが表示されます。

   ![設定ユーザー](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. [!UICONTROL 製品の役割]列の各ユーザーのドロップダウンリストを使用して、目的の権限の役割（承認者、編集者、監視者）を選択します。

   ![製品の役割ドロップダウンリスト](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 役割 | 説明 |
   |--- |--- |
   | 承認者 | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | 編集者 | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | 監視者 | アクティビティを表示できますが、作成または編集はできません。 |
   | 発行者 | 監視者の役割と同様です（アクティビティを表示できますが、作成または編集はできません）。ただし、発行者の役割には、アクティビティをアクティブ化する追加の権限があります。 |

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
>パフォーマンスを向上、新機能のリリースに要するメンテナンス時間を短縮、製品全体でのユーザーエクスペリエンスが向上するため、[!DNL Target] [!UICONTROL 管理]メニュー（以前の[!UICONTROL 設定]）のデザインが一新されました。次のビデオの情報は、一般的には正確ですが、オプションの場所が若干異なる場合があります。更新されたビデオは間もなく投稿される予定です。

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
