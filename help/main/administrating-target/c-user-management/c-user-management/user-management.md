---
keywords: ユーザーの追加;ユーザーの管理;ユーザー権限
description: の使用方法を学ぶ [!DNL Adobe Admin Console] ユーザーとその権限および権限を [!DNL Adobe Target Standard].
title: ユーザーの追加方法と権限の管理方法 [!DNL Target Standard] アカウント？
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: d40c25f75103327e749ad864b17df926cb323be0
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 73%

---

# ユーザー

ユーザーを追加し、 [!DNL Adobe Admin Console] の [!DNL Target Standard] アカウント。

>[!NOTE]
>
>[!UICONTROL プロパティ]と[!UICONTROL 権限]の機能は [!DNL Target Premium] ソリューションの一部です。[!DNL Target] Premium ライセンスのない [!DNL Target] Standard では利用できません。
>
>組織が [!UICONTROL 標準] または [!UICONTROL Premium] ライセンスを取得するには、 [!UICONTROL 管理] リンクを [!DNL Target] UI
>
>* **[!DNL Target] Standarrd のお客様**：[!UICONTROL ユーザー] タブ（[!UICONTROL 管理／ユーザー]）が表示される（「**[!UICONTROL プロパティ]**」タブは表示されない）場合、組織のライセンスは[!DNL Target] Standard です。[!DNL Target] Standard のお客様は、[!DNL Adobe Admin Console] でユーザーを追加したり、権限を割り当てたりする際は、この記事の手順に従ってください。
>
>* **[!DNL Target]Premium のお客様**：「[!UICONTROL ユーザー]」タブと「[!UICONTROL プロパティ]」タブ（[!UICONTROL 管理／プロパティ]）が表示された場合、組織のライセンスは [!DNL Target] Premium です。[!DNL Target] Premium のお客様が [!DNL Adobe Admin Console] でユーザーの追加や権限の割り当てを行う際は、[Enterprise ユーザーの権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) と [Enterprise 権限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)の設定の手順に従ってください。
>
>ユーザーと権限の管理方法について詳しくは、[製品およびプロファイルの管理](https://helpx.adobe.com/jp/enterprise/using/manage-products-and-profiles.html)の&#x200B;*エンタープライズおよびチームユーザーガイド*&#x200B;を参照してください。

[!DNL Adobe Target] を初めて使用するときには、[!DNL Adobe Experience Cloud] アカウントのところに、「Adobe.com」で終わる ID があらかじめ表示されています。これらの ID は [!DNL Adobe] チームのメンバーのもので、新しいアカウントや [!DNL Adobe Target] の使い方について疑問点があるときに、メンバーに質問をすることができます。質問があるときは、通常の方法で Adobe チームにご連絡ください。

新しいユーザーは、 [!UICONTROL ユーザー] ページを開き、ユーザーが [!DNL Adobe Experience Cloud] アカウントにアクセスし、次にログインします。 [!DNL Target].

デフォルトでは、すべて [!DNL Target] ユーザーが開始する [!UICONTROL 監視者] 権限。

管理者ユーザーは、「[!UICONTROL ユーザー]」リストを見るとわかります。アクセスレベルの変更が必要な場合は、いずれかのシステム管理者ユーザーにお問い合わせください。

##  内からユーザー情報を表示する[!DNL Target]

現在のユーザーのリストは、 [!DNL Target] UI（ワークスペースごとの役割や電子メールアドレスを含む）

次の手順で、 [!UICONTROL ユーザー] ページ、クリック **[!UICONTROL 管理]** > **[!UICONTROL ユーザー]**.

![Target 内からのユーザーリスト](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>既存のユーザーを管理したり、新しいユーザーを追加したりするには、以下に説明するように、[!UICONTROL Adobe Admin Console] を使用する必要があります。

## 次にアクセス： [!DNL Adobe Admin Console] {#access}

で実行されるタスクの場合 [!DNL Adobe Admin Console]次の手順に従って、コンソールにアクセスします。

1. [!DNL Target] 内から、**[!UICONTROL 管理]**／**[!UICONTROL ユーザー]**／**[!UICONTROL ユーザー管理]**&#x200B;をクリックします。

   または

   [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) に移動し、まだの場合は Adobe ID でログインします。

1. （条件付き）複数の組織の [!DNL Admin Console for Enterprise] へのアクセス権を持っている場合、右隅または上部のナビゲーションバーにあるユーザーアバターをクリックしてから、目的の組織を選択します。

## ユーザーの追加 {#add-users}

ユーザー管理操作は、すべて [!DNL Adobe Admin Console for Enterprise] で実行する必要があります。ただし、[!DNL Target] のすべての既存のユーザーは、[!DNL Target] から [!DNL Admin Console for Enterprise] に移行されます。

1. [Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) で&#x200B;**[!UICONTROL ユーザー]**／**[!UICONTROL ユーザー]**&#x200B;をクリックして、新しいユーザーを作成するか、既存のユーザーを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/jp/enterprise/help/users.html)の手順に従ってください。

## ユーザーグループの作成 {#user-groups}

開発者、アナリスト、マーケター、エグゼクティブなどのユーザーグループを作成して、複数のユーザーにわたる権限を割り当てることができます [!DNL Adobe] 製品とワークスペース。 新しいチームメンバーに、異なる複数のチームメンバーに対する適切な権限をすべて割り当てる [!DNL Adobe] 製品は、特定のユーザーグループに追加するのと同じくらい簡単にできます。

1. [Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) で&#x200B;**[!UICONTROL ユーザー]**／**[!UICONTROL ユーザーグループ]**&#x200B;をクリックして、新しいユーザーグループを作成するか、既存のユーザーグループを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/jp/enterprise/help/users.html)の手順に従ってください。

## 役割および権限の指定 {#roles-permissions}

システム管理者のみ、[!DNL Target] のユーザーの役割を指定できます。例えば、 [!UICONTROL 標準] 承認者ユーザーは、同じく [!DNL Experience Cloud] 管理者権限。

システム管理者ユーザーはシステムにユーザーを追加する必要があります。ユーザーは自動的には追加されません。ユーザーのアカウントを登録する前に、[!DNL Experience Cloud] から招待メールを送信して、メールアドレスを確認する必要があります。

1. [Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

   ![「製品」タブ](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 目的のワークスペース（デフォルトのワークスペースなど）をクリックします。

   ![デフォルトのワークスペース](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   「[!UICONTROL ユーザー]」タブにワークスペースのすべてのユーザーが表示されます。

   ![設定ユーザー](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. 目的の権限の役割 ([!UICONTROL 承認者], [!UICONTROL 編集者], [!UICONTROL 監視者] または [!UICONTROL 投稿者]) を選択します。 [!UICONTROL 製品の役割] 列。

   ![製品の役割ドロップダウンリスト](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 役割 | 説明 |
   |--- |--- |
   | [!UICONTROL 承認者] | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | [!UICONTROL 編集者] | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | [!UICONTROL 監視者] | アクティビティを表示できますが、作成または編集はできません。 |
   | [!UICONTROL 発行者] | 次に類似 [!UICONTROL 監視者] 役割（アクティビティを表示できますが、作成または編集はできません）。 ただし、[!UICONTROL 発行者]の役割には、アクティビティをアクティブ化する追加の権限があります。 |

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
