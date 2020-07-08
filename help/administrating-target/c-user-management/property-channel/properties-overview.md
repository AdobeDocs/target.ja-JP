---
keywords: add user;project;user group;properties;workspace;manage property;property;at_property;roles;permissions
description: ユーザーを Target 実装に追加するために必要なタスクに関する情報です。ワークスペース、ユーザーグループ、プロパティを作成する方法や、Target 実装を更新して、at_property パラメーターを追加する方法、役割と権限を指定する方法について説明します。
title: Enterprise 権限の設定
subtopic: Getting Started
uuid: 2f44ecd5-5c43-49c3-b1c3-58d28531c859
translation-type: tm+mt
source-git-commit: c7664f9674234565a3657f453541095811fa5aa6
workflow-type: tm+mt
source-wordcount: '1469'
ht-degree: 70%

---


# ![PREMIUM](/help/assets/premium.png) Enterprise 権限の設定{#configure-enterprise-permissions}

Information about the tasks required to add users to your [!DNL Target] implementation; create workspaces, user groups, and properties; update your [!DNL Target] implementation to include the `at_property` parameter; and specify roles and permissions.

>[!NOTE]
>
>このトピックの情報は更新され、Target Standard/Premium 20.6.1リリース（2020年7月）で行われるUIの変更点を最新の状態に更新しました。 このトピックに示す情報のほとんどは、現在のUIに適用されます。 ただし、オプションが少し異なる場所にある場合もあります。

>[!NOTE]
>
>プロパティと権限の機能は [Target Premium](/help/c-intro/intro.md#premium) ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

次の表に、プロパティを作成し、ユーザーの役割および権限を割り当てるために必要なタスクを示します。各タスクについて詳しくは、以下のセクションを参照してください。

| タスク | 実行場所 |
|--- |--- |
| 1. ユーザーの追加（オプション） | [!DNL Adobe Admin Console for Enterprise] |
| 2. ワークスペース（製品プロファイル）の作成 | [!DNL Adobe Admin Console for Enterprise] |
| 3. ユーザーグループの作成（オプション） | [!DNL Adobe Admin Console for Enterprise] |
| 4. プロパティの作成 | [!DNL Target] UI |
| 5. `at_property` パラメーターを含めるための実装の更新 | [!DNL Target] UI、at.js 関数、[!DNL Adobe Launch]、または [!DNL Dynamic Tag Management] |
| 6. 役割および権限の指定 | [!DNL Adobe Admin Console for Enterprise] |

For those tasks performed in the [!DNL Adobe Admin Console for Enterprise], access the console by following these steps:

1. Adobe Targetで、 **[!UICONTROL 管理]** / **[!UICONTROL プロパティ]** /プロパティをワークスペースに **[!UICONTROL 割り当てをクリックします]**。

   または

   Go to [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) > sign in using your Adobe ID, if you have not already logged in.


1. （条件付き）複数の組織の [!DNL Admin Console for Enterprise] へのアクセス権を持っている場合、右隅または上部のナビゲーションバーにあるユーザーアバターをクリックしてから、目的の組織を選択します。

## 手順 1.Add users (Optional) {#section_A92AF0F921B743FEB9E9033433BD816A}

新しい[!UICONTROL プロパティ]機能を使用し始める場合、すべてのユーザー管理は、[!DNL Adobe Admin Console for Enterprise] で実行する必要があります。ただし、[!DNL Target] のすべての既存のユーザーは、[!DNL Target] から [!DNL Admin Console for Enterprise] に移行されます。

1. [Admin Console](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE) で、ページ上部の「**[!UICONTROL ユーザー]**」タブをクリックした後、「**[!UICONTROL ユーザーを追加]**」をクリックして、新しいユーザーを作成するか、既存のユーザーを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/enterprise/help/users.html)の手順に従ってください。

## 手順 2：Create a workspace (product profile) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

ワークスペース(製品プロファイル)を使用すると、組織は特定のユーザーのセットを特定のプロパティのセットに割り当てることができます。 多くの点で、ワークスペースは [!DNL Analytics] のレポートスイートに似ています。

Organizations can begin taking advantage of Enterprise permissions functionality by creating new workspaces within [!DNL Admin Console], assigning [!DNL Target] properties to these workspaces, and moving users from the &quot;Default Workspace&quot; configuration to these newer, limited-access workspaces.

これらのワークスペースを使用して、地域別、ビジネスユニット別、サイトセクション別または選択したその他の方法で、様々なチームにアクセス権を分割できます。

ユーザーは複数のワークスペースに属すことができ、各ワークスペースで異なる役割を持つこともできます。

1. [!DNL Admin Console] で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

   ![ワークスペース](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. 目的のワークスペース（製品プロファイル）を作成します。

   * **デフォルトアクセス：**&#x200B;既存のすべてのアクティビティは、「デフォルトアクセス」と呼ばれる単一のプロジェクトに結合されます。これは、顧客には影響しません。すべてのユーザーの役割および機能は、この変更より前とまったく同じように残ります。

      [!DNL Adobe Experience Manager]（AEM）、[!DNL Adobe Mobile Services] および [!DNL Target Classic] を使用して作成されたすべてのアクティビティも、「デフォルトアクセス」ワークスペースの一部です。現在は、プロジェクトを「デフォルトアクセス」から別のプロジェクトに移動することはできません。

   * **新規ワークスペース（製品プロファイル）：**&#x200B;次の手順を実行することで、新しい権限機能の利用を開始できます。

      * [!DNL Admin Console for Enterprise] での新しいワークスペースの作成。
      * Target プロパティのワークスペースへの割り当て。

   これらのワークスペースを使用して、地域別、ビジネスユニット別、サイトセクション別または選択したその他の方法で、様々なチームにアクセス権を分割できます。ユーザーは複数のワークスペースに属すことができ、各ワークスペースで異なる役割を持つことができます。

1. *Enterprise ユーザーガイド*&#x200B;の[製品構成の作成と管理](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)の手順に従ってください。

>[!NOTE]
>ワークスペース設定について詳しくは、以下のトレーニングビデオをご覧ください。

### Obtain your workspace ID {#workspace-id}

[Target API](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) の Enterprise 権限を活用するには、ワークスペース IDを渡す必要があります。

1. [Adobe Admin Console ](https://adminconsole.adobe.com)で 、[!UICONTROL 「製品」] タブをクリックし、左側のメニューで製品をクリックして、PLC（ワークスペース）」リストを表示します。
1. 目的のPLC（ワークスペース）をクリックし、次に示す URL で「プロファイル」 ID を探します。

   ![ワークスペース ID](/help/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## 手順 3.Create user groups (Optional) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

開発者、アナリスト、マーケティング担当者、エグゼクティブなどのユーザーグループを作成して、複数のアドビ製品およびワークスペースにわたって権限を割り当てることができます。新しいチームメンバーに様々なアドビ製品にわたるすべての適切な権限を割り当てることは、特定のユーザーグループに追加するくらいに簡単です。

1. Admin Console で、ページ上部の「**[!UICONTROL ユーザー]**」タブをクリックした後、「**[!UICONTROL ユーザーグループ]**」をクリックして、新しいユーザーグループを作成するか、既存のユーザーグループを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の[製品構成のユーザーおよびグループを管理する](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)の手順に従ってください。

## 手順 4.プロパティの作成 {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

プロパティは、任意の呼び出し(Target呼び出し、api呼び出しなど)で、特定の名前と値のペアをパラメーターとして追加することで有効にします。 をTargetに追加します。

プロパティは、特定のチャネル（Web、モバイル、電子メールおよび API／その他）に属しています。

**ヒント**：プロパティの作成方法について詳しくは、以下のトレーニングビデオをご覧ください。

1. In [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.
1. 「**プロパティを作成**」をクリックします。

   ![新規プロパティダイアログボックス](/help/administrating-target/c-user-management/property-channel/assets/new_property1.png)

   以下のフィールドを設定します。

   * **プロパティ名（必須）:** プロパティにわかりやすい名前を指定します。
   * **説明：**（オプション）プロパティの説明を指定します。
   * **チャネル：** Web、モバイル、アプリ、電子メールまたはその他／API（例えばセットトップボックスや PlayStation コンソール）から、プロパティ用の目的のチャネルを選択します。

1. 「 **[!UICONTROL コピー]** 」をクリックして、 [5の手順を実行する際に使用するコードをクリップボードにコピーします。 at_propertyパラメーターを含めるように実装を更新します](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8)。
1. 終了したら「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>プロパティ作成について詳しくは、以下のトレーニングビデオをご覧ください。

## Step 5: Update your implementation to include the at_property parameter {#section_9B17A59807A94712BE642942442EBBC8}

To use the [!DNL Target] user-permissions functionality, you must add the `at_property` parameter to any call that is hitting [!DNL Target] (Target call, api call, etc.).

**`at_property`パラメーターコードを取得するには：**

1. （条件付き）[4.プロパティの作成](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD)の手順を実行しながら生成してクリップボードに保存した実装コードを使用して、手順 2 に進みます。

   または

   In [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.

   1. 目的のプロパティの[!UICONTROL 最終更新日]列の上にマウスポインターを置いて、[!UICONTROL コード]アイコンを表示し、クリックします。

      ![プロパティホバーコード](/help/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. 強調表示された実装コードを右クリックして、クリップボードにコピーします。

      ![プロパティコード](/help/administrating-target/c-user-management/property-channel/assets/code_property_2_new.png)

1. Update your [!DNL Target] implementation with the implementation code obtained in the previous step.

   [!DNL Target] 実装を更新するには、いくつかの方法があります。例えば、Web ページには次の方法を使用できます。

   * **の「グローバルパラメーター」を使用[!DNL Adobe Launch]：**

      For more information, see [Add Global Target Params](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension#add-global-mbox-params) in the *Adobe Experience Platform Launch* documentation.

   * **の「グローバルパラメーター」を使用[!DNL Dynamic Tag Management]：**

      ![](assets/property_token_2.png)

      詳しくは、Dynamic Tag Management 製品ドキュメント&#x200B;**&#x200B;の[グローバルパラメーター - Adobe Target](https://docs.adobe.com/content/help/en/dtm/using/tools-reference/target.html#global-parameters---adobe-target) を参照してください。

   * **targetPageParams() 関数を使用：**&#x200B;タグの以下のコードを <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> at.js または mbox.js 参照の上に置きます。

      ![](assets/property_token_1.png)

      at.js を使用してこれをおこなう方法については、[targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) を参照してください。

   * **mboxCreate() 関数を使用：**

      ![](assets/property_token_3.png)

      at.js を使用してこれをおこなう方法については、[targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) および [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)。

## Step 6: Specify roles and permissions {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. Admin Console で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

   ![ワークスペース](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 目的のプロファイルの名前（例えば、デフォルトのワークスペース）をクリックします。

   ![デフォルトのワークスペース](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. 「**[!UICONTROL ユーザー]**」をクリックします。

   「[!UICONTROL ユーザー]」タブにワークスペースのすべてのユーザーが表示されます。

   ![設定ユーザー](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Select the desired permissions role (Approver, Editor, Observer, or Publisher) by using the drop-down list for each user in the [!UICONTROL Product Role] column.

   ![「製品の役割」ドロップダウンリスト](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 役割 | 説明 |
   |--- |--- |
   | 承認者 | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | 編集者 | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | 監視者 | アクティビティを表示できますが、作成または編集はできません。 |
   | 発行者 | オブザーバーロールに似ています(表示アクティビティは可能ですが、作成または編集はできません)。 ただし、「発行者」の役割には、アクティビティをアクティブ化する追加の権限があります。 |

   詳しくは、*Enterprise ユーザーガイド*&#x200B;の [Admin Console での製品の権限およびロールの管理](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)を参照してください。

## トレーニングビデオ

以下のビデオは、この記事で説明する概念についてさらに詳しく説明しています。

### Target のワークスペースの設定方法（6:55） ![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオでは、ワークスペースの作成方法を説明します。

* Adobe Target のインターフェイスから Adobe Admin Console にアクセスします（3 つの方法）
* Adobe Admin Console でワークスペースを設定します

   * ユーザーをワークスペースに追加します
   * プロパティをワークスペースに追加します

* デフォルトのワークスペースの概要を説明します

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### How to Create Properties in Adobe Target (3:05) ![Tutorial badge](/help/assets/tutorial.png)

* [!DNL Adobe Target] インターフェイス内でプロパティを作成する方法
* プロパティトークンを生成してプロパティの実装に含める方法
* 次の 3 つの実装方法について説明します。

   * Web
   * モバイルアプリ
   * 電子メール、セットトップボックス、API 呼び出し

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
