---
keywords: ユーザーの追加;ユーザーの管理;ユーザー権限
description: ' [!DNL Adobe Admin Console]  を使用して、 [!DNL Adobe Target Standard] でユーザーとその権限と権限を管理する方法を説明します。'
title: ユーザーを追加し、 [!DNL Target Standard]  アカウントの権限を管理する方法？
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
TQID: https://experienceleague.adobe.com/DdNQ81TpmyIRuPkmy4OIOq43CXwaMtm-uH2HtPjdx10
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
subfeature_v2:
  - id: c011fe9c-b94b-4a88-93d8-f2acece55112
  - id: cd7b6938-5837-4ee0-9790-5840997133d9
  - id: cf6b8469-14d0-4c0e-90ee-fb54066a035e
  - id: faed1c89-faf7-4df1-910d-a88263e03b15
  - id: fc9c2184-9102-403f-bd6c-0055021e4bea
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 925
ht-degree: 60%

---

# ユーザー

[!DNL Target Standard] アカウントの [!DNL Adobe Admin Console] でユーザーを追加し、その権限を管理します。

>[!NOTE]
>
>[!UICONTROL &#x200B; プロパティ &#x200B;]および[!UICONTROL 権限]機能は、[!DNL Target Premium] ソリューションの一部として利用できます。 [!DNL Target] Premium ライセンスのない [!DNL Target] Standard では利用できません。
>
>[!DNL Target] UIの上部にある[!UICONTROL 管理] リンクをクリックすると、組織が[!UICONTROL Standard]または[!UICONTROL Premium] ライセンスを持っているかどうかを確認できます。
>
>* **[!DNL Target]&#x200B;[!UICONTROL 標準]のお客様**:「[!UICONTROL &#x200B; ユーザー]」タブ（[!UICONTROL 管理> ユーザー]）が表示されている場合（**[!UICONTROL プロパティ]** タブではない）、組織には[!DNL Target] [!UICONTROL 標準] ライセンスがあります。[!DNL Target] [!UICONTROL Standard]のお客様は、この記事の手順に従ってユーザーを追加し、[!DNL Adobe Admin Console]で権限を割り当てる必要があります。
>
>* **[!DNL Target]プレミアム顧客**:「[!UICONTROL &#x200B; ユーザー]」タブと「[!UICONTROL &#x200B; プロパティ &#x200B;]」タブ（[!UICONTROL 管理> プロパティ &#x200B;]）が表示されている場合、組織には[!DNL Target] プレミアムライセンスがあります。[!DNL Target] プレミアムのお客様は、[&#x200B; エンタープライズユーザー権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)および[&#x200B; エンタープライズ権限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)の手順に従って、ユーザーを追加し、[!DNL Adobe Admin Console]で権限を割り当てる必要があります。
>
>ユーザーと権限の管理方法について詳しくは、[製品およびプロファイルの管理](https://helpx.adobe.com/jp/enterprise/using/manage-products-and-profiles.html)の&#x200B;*エンタープライズおよびチームユーザーガイド*&#x200B;を参照してください。

[!DNL Adobe Target] を初めて使用するときには、[!DNL Adobe Experience Cloud] アカウントのところに、「Adobe.com」で終わる ID があらかじめ表示されています。 これらの ID は [!DNL Adobe] チームのメンバーのもので、新しいアカウントや [!DNL Adobe Target] の使い方について疑問点があるときに、メンバーに質問をすることができます。 質問があるときは、通常の方法で Adobe チームにご連絡ください。

ユーザーが[!DNL Adobe Experience Cloud] アカウントを使用してログインし、[!DNL Target]にログインするまで、新しいユーザーが[!UICONTROL &#x200B; ユーザー] ページに表示されません。

デフォルトでは、すべての[!DNL Target] ユーザーは[!UICONTROL Observer]権限で始まります。

管理者ユーザーは、[!UICONTROL &#x200B; ユーザー] リストで特定されます。 アクセスレベルの変更が必要な場合は、いずれかのシステム管理者ユーザーにお問い合わせください。

## [!DNL Target]内からユーザー情報を表示する

ワークスペースごとの役割やメールアドレスなど、[!DNL Target] UI で現在のユーザーのリストを表示できます。

[!UICONTROL &#x200B; ユーザー] ページを表示するには、**[!UICONTROL 管理]** > **[!UICONTROL ユーザー]**&#x200B;をクリックします。

>[!NOTE]
>
>既存のユーザーを管理するか、新しいユーザーを追加するには、以下に示すように[!UICONTROL Adobe Admin Console]を使用する必要があります。

## [!DNL Adobe Admin Console] へのアクセス {#access}

[!DNL Adobe Admin Console] で実行するタスクの場合は、次の手順でコンソールにアクセスします。

1. [!DNL Target]内から、**[!UICONTROL 管理]** > **[!UICONTROL ユーザー]** > **[!UICONTROL ユーザー管理]**&#x200B;をクリックします。

   または

   [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) に移動し、まだの場合は Adobe ID でログインします。

1. （条件付き）複数の組織の [!DNL Admin Console for Enterprise] へのアクセス権を持っている場合、右隅または上部のナビゲーションバーにあるユーザーアバターをクリックしてから、目的の組織を選択します。

## ユーザーの追加 {#add-users}

ユーザー管理操作は、すべて [!DNL Adobe Admin Console for Enterprise] で実行する必要があります。 ただし、[!DNL Target] のすべての既存のユーザーは、[!DNL Target] から [!DNL Admin Console for Enterprise] に移行されます。

1. [Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)で、**[!UICONTROL Users]** > **[!UICONTROL Users]**&#x200B;をクリックして、新規ユーザーを作成するか、既存のユーザーを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/jp/enterprise/help/users.html)の手順に従ってください。

## ユーザーグループの作成 {#user-groups}

開発者、アナリスト、マーケター、エグゼクティブなどのユーザーグループを作成し、複数の [!DNL Adobe] 製品とワークスペースに権限を割り当てることができます。 新しいチームメンバーに様々な [!DNL Adobe] 製品にわたるすべての適切な権限を割り当てることは、特定のユーザーグループに追加するのと同じくらいに簡単です。

1. [Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)で、**[!UICONTROL ユーザー]**/**[!UICONTROL ユーザーグループ]**&#x200B;をクリックして、新しいユーザーグループを作成するか、既存のグループを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/jp/enterprise/help/users.html)の手順に従ってください。

## 役割および権限の指定 {#roles-permissions}

システム管理者のみ、[!DNL Target] のユーザーの役割を指定できます。 例えば、[!UICONTROL Standard]の承認者ユーザーは、[!DNL Experience Cloud]の管理者権限を持たずに、オブザーバーを承認者に変更することはできません。

システム管理者ユーザーはシステムにユーザーを追加する必要があります。 ユーザーは自動的には追加されません。 ユーザーのアカウントを登録する前に、[!DNL Experience Cloud] から招待メールを送信して、メールアドレスを確認する必要があります。

>[!NOTE]
>
>[!DNL Target]のアクティビティを表示するには、少なくとも[!UICONTROL Observer]の役割を持つワークスペースにユーザーを直接割り当てる必要があります。 ユーザーグループだけでは課題に対処できません。 通常、デフォルトのワークスペースへのアクセス権をユーザーに付与することをお勧めします。

1. [Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

1. 目的のワークスペース（デフォルトのワークスペースなど）をクリックします。

   「[!UICONTROL &#x200B; ユーザー]」タブには、そのワークスペース内のすべてのユーザーが表示されます。

1. [!UICONTROL 製品ロール &#x200B;]列の各ユーザーのドロップダウンリストを使用して、目的の権限ロール（[!UICONTROL 承認者]、[!UICONTROL 編集者]、[!UICONTROL &#x200B; オブザーバー]または[!UICONTROL 発行者]）を選択します。

   | 役割 | 説明 |
   |--- |--- |
   | [!UICONTROL 承認者] | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | [!UICONTROL 編集者] | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | [!UICONTROL &#x200B; オブザーバー] | アクティビティを表示できますが、作成または編集はできません。 |
   | [!UICONTROL 発行者] | [!UICONTROL Observer]の役割と同様です（アクティビティを表示できますが、作成または編集することはできません）。 ただし、[!UICONTROL 発行者]の役割には、アクティビティをアクティブ化するための追加の権限があります。 |

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
>[!DNL Target] [!UICONTROL 管理] メニューUI （旧称[!UICONTROL &#x200B; セットアップ &#x200B;]）は、パフォーマンスの向上、新機能のリリース時に必要なメンテナンス時間の短縮、製品全体でのユーザーエクスペリエンスの向上を目的として再設計されました。 次のビデオの情報は、一般的には正確ですが、オプションの場所が若干異なる場合があります。 更新されたビデオは間もなく投稿される予定です。

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
