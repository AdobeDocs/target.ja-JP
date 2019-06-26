---
description: ユーザーを Target 実装に追加するために必要なタスクに関する情報です。ワークスペース、ユーザーグループ、プロパティを作成する方法や、Target 実装を更新して、at_property パラメーターを追加する方法、役割と権限を指定する方法について説明します。
keywords: ユーザーの追加;プロジェクト;ユーザーグループ;プロパティ;ワークスペース;プロパティの管理;プロパティ;at_property;役割;権限
seo-description: ユーザーを Target 実装に追加するために必要なタスクに関する情報です。ワークスペース、ユーザーグループ、プロパティを作成する方法や、Target 実装を更新して、at_property パラメーターを追加する方法、役割と権限を指定する方法について説明します。
seo-title: Enterprise 権限の設定
solution: 'Target '
subtopic: 導入
title: Enterprise 権限の設定
title-outputclass: premium
topic: Premium
uuid: 2f44ecd5-5c43-49c3-b1c3-58d28531c859
badge: premium
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![PREMIUM](/help/assets/premium.png) Enterprise 権限の設定{#configure-enterprise-permissions}

ユーザーを Target 実装に追加するために必要なタスクに関する情報です。ワークスペース、ユーザーグループ、プロパティを作成する方法や、Target 実装を更新して、`at_property` パラメーターを追加する方法、役割と権限を指定する方法について説明します。

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

Adobe Admin Console for Enterprise で実行するタスクの場合は、次の手順でコンソールにアクセスします。

1. Go to [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) &gt; sign in using your Adobe ID, if you have not already logged in.

   または

   If you are already logged in to the Experience Cloud, go to [https://www.experiencecloud.adobe.com](https://experiencecloud.adobe.com), then click the [!UICONTROL App] icon in the top navigation bar &gt; click **[!UICONTROL Admin]** on the right side.

1. （条件付き）複数の組織の [!DNL Admin Console for Enterprise] へのアクセス権を持っている場合、右隅または上部のナビゲーションバーにあるユーザーアバターをクリックしてから、目的の組織を選択します。

## 手順 1.ユーザーの追加（オプション）{#section_A92AF0F921B743FEB9E9033433BD816A}

新しい[!UICONTROL プロパティ]機能を使用し始める場合、すべてのユーザー管理は、[!DNL Adobe Admin Console for Enterprise] で実行する必要があります。ただし、[!DNL Target] のすべての既存のユーザーは、[!DNL Target] から [!DNL Admin Console for Enterprise] に移行されます。

1. [管理コンソール](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE)で、ページ上部の **[!UICONTROL 「ユーザー]** 」タブをクリックし、新規ユーザーを作成するか、既存のユーザーを編集するための「ユーザー **[!UICONTROL ]** を追加」タブをクリックします。
1. *Enterprise ユーザーガイド*の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/enterprise/help/users.html)の手順に従ってください。

## 手順 2：ワークスペース（製品プロファイル）の作成{#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

ワークスペース（製品プロファイル）を使用すると、組織は特定のユーザーのセットを特定のプロパティのセットに割り当てることができます。多くの点で、ワークスペースは [!DNL Analytics] のレポートスイートに似ています。

Admin Console 内で新しいワークスペースを作成し、それらのワークスペースに Target プロパティを割り当て、「デフォルトのワークスペース」設定からこれらのアクセス制限付きの新しいワークスペースにユーザーを移行することで、Enterprise 権限機能を活用できるようになります。

ユーザーはこれらのワークスペースを使用して、地域別、ビジネスユニット別、サイトセクション別、または選択した他の方法で、様々なチームへのアクセスを分けることができます。

ユーザーは複数のワークスペースに属すことができ、各ワークスペースで異なる役割を持つこともできます。

1. Admin Console で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

   ![ワークスペース](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. 目的のワークスペース（製品プロファイル）を作成します。

   * **デフォルトアクセス：** 既存のすべてのアクティビティは、「デフォルトアクセス」と呼ばれる単一のプロジェクトに結合されます。これは、顧客には影響しません。すべてのユーザーの役割および機能は、この変更より前とまったく同じように残ります。

      [!DNL Adobe Experience Manager]（AEM）、[!DNL Adobe Mobile Services] および [!DNL Target Classic] を使用して作成されたすべてのアクティビティも、「デフォルトアクセス」ワークスペースの一部です。現在は、プロジェクトを「デフォルトアクセス」から別のプロジェクトに移動することはできません。

   * **新規ワークスペース（製品プロファイル）：** 次の手順を実行することで、新しい権限機能の利用を開始できます。

      * [!DNL Admin Console for Enterprise] での新しいワークスペースの作成。
      * Target プロパティのワークスペースへの割り当て。
   これらのワークスペースを使用して、地域別、ビジネスユニット別、サイトセクション別または選択したその他の方法で、様々なチームにアクセス権を分割できます。ユーザーは複数のワークスペースに属すことができ、各ワークスペースで異なる役割を持つことができます。

1. *Enterprise ユーザーガイド*の[製品構成の作成と管理](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)の手順に従ってください。

>[!NOTE]
>ワークスペース設定について詳しくは、以下のトレーニングビデオをご覧ください。

### Obtain your Workspace ID {#workspace-id}

[Target API](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) の Enterprise 権限を活用するには、ワークスペース IDを渡す必要があります。

1. [Adobe Admin Console ](https://adminconsole.adobe.com)で 、[!UICONTROL 「製品」] タブをクリックし、左側のメニューで製品をクリックして、PLC（ワークスペース）」リストを表示します。
1. 目的のPLC（ワークスペース）をクリックし、次に示す URL で「プロファイル」 ID を探します。

   ![ワークスペース ID](/help/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## 手順 3.ユーザーグループの作成（オプション）{#section_5F5CB9AA7A9F4D26953E22016DA59605}

開発者、アナリスト、マーケティング担当者、エグゼクティブなどのユーザーグループを作成して、複数のアドビ製品およびワークスペースにわたって権限を割り当てることができます。新しいチームメンバーに様々なアドビ製品にわたるすべての適切な権限を割り当てることは、特定のユーザーグループに追加するくらいに簡単です。

1. Admin Console で、ページ上部の「**[!UICONTROL ユーザー]**」タブをクリックした後、「**[!UICONTROL ユーザーグループ]**」をクリックして、新しいユーザーグループを作成するか、既存のユーザーグループを編集します。
1. *Enterprise ユーザーガイド*の[製品構成のユーザーおよびグループを管理する](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)の手順に従ってください。

## 手順 4.プロパティの作成 {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

プロパティは、任意の呼び出し（mbox、api など）で、特定の名前と値のペアをパラメーターとして Target に追加することで有効化されます。をターゲットに設定します。

プロパティは、特定のチャネル（Web、モバイル、電子メールおよび API／その他）に属していますを参照してください。

**ヒント**：プロパティの作成方法について詳しくは、以下のトレーニングビデオをご覧ください。

1. [!DNL Target] で、**[!UICONTROL セットアップ]**／**[!UICONTROL プロパティ]** をクリックして、[!UICONTROL プロパティ]リストを表示します。
1. 「**プロパティを作成**」をクリックします。

   ![新規プロパティダイアログボックス](/help/administrating-target/c-user-management/property-channel/assets/new_property1.png)

   以下のフィールドを設定します。

   * **チャネル:** プロパティの目的のチャネルを選択します。Web、モバイルアプリ、電子メール、またはその他/API（セットトップボックスまたはPlayStationコンソールなど）。
   * **名前（必須）：** プロパティのわかりやすい名前を指定します。
   * **説明：**（オプション）プロパティの説明を指定します。

1. 「**[!UICONTROL コードを生成]**」をクリックして、[5. at_property パラメーターを含めるための実装の更新](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8)のステップの実行時に使用するコードを生成します。
1. コードをクリップボードにコピーします。
1. 終了したら「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>プロパティ作成について詳しくは、以下のトレーニングビデオをご覧ください。

## ステップ 5. at_property パラメーターを含めるための実装の更新 {#section_9B17A59807A94712BE642942442EBBC8}

[!DNL Target] のユーザー権限機能を使用するには、Target をヒットするすべての呼び出し（mbox、api など）に `at_property` パラメーターを追加する必要があります。

**`at_property`パラメーターコードを取得するには：**

1. （条件付き）[4.プロパティの作成](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD)の手順を実行しながら生成してクリップボードに保存した実装コードを使用して、手順 2 に進みます。

   または

   [!DNL Target] で、**[!UICONTROL セットアップ]**／**[!UICONTROL プロパティ]** をクリックして、[!UICONTROL プロパティ]リストを表示します。

   1. 目的のプロパティの[!UICONTROL 最終更新日]列の上にマウスポインターを置いて、[!UICONTROL コード]アイコンを表示し、クリックします。

      ![プロパティホバーコード](/help/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. 強調表示された実装コードを右クリックして、クリップボードにコピーします。

      ![プロパティコード](/help/administrating-target/c-user-management/property-channel/assets/code_property_2_new.png)

1. 前の手順で取得した実装コードを使用して、Target 実装を更新します。

   [!DNL Target] 実装を更新するには、いくつかの方法があります。例えば、Web ページには次の方法を使用できます。

   * **「グローバルパラメーター[!DNL Adobe Launch]」の&quot;**

      For more information, see [Add Global Mbox Params](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension#add-global-mbox-params) in the *Adobe Experience Platform Launch* documentation.

   * **「グローバルパラメーター」の使用[!DNL Dynamic Tag Management]:**

      ![](assets/property_token_2.png)

      詳しくは、Dynamic Tag Management 製品ドキュメント**の[グローバルパラメーター - Adobe Target](https://docs.adobe.com/content/help/en/dtm/using/tools-reference/target.html#global-parameters---adobe-target) を参照してください。

   * **targetPageParams() 関数を使用：** タグの以下のコードを <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> at.js または mbox.js 参照の上に置きます。

      ![](assets/property_token_1.png)

      at.js を使用してこれをおこなう方法については、[targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) を参照してください。

   * **mboxCreate() 関数を使用：**

      ![](assets/property_token_3.png)

      at.js を使用してこれをおこなう方法については、[targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) および [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)。

## ステップ 6. 役割および権限の指定 {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. Admin Console で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

   ![ワークスペース](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

   >[!NOTE]
   >
   >The Properties and Permissions functionality applies to [Target Standard/Premium](/help/c-intro/intro.md#premium) only. この機能は [!DNL Target Classic] では使用できません。

1. 目的のプロファイルの名前をクリックします。
1. 「**[!UICONTROL ユーザー]**」をクリックします。

   [!UICONTROL 「ユーザー] 」タブには、そのワークスペース内のすべてのユーザーが表示されます。

   ![ユーザーの設定](/help/administrating-target/c-user-management/property-channel/assets/configuration_users_new.png)

1. [!UICONTROL 製品の役割]列の各ユーザーのドロップダウンリストを使用して、目的の権限の役割（承認者、編集者、監視者）を選択します。

   | 役割 | 説明 |
   |--- |--- |
   | 監視者 | アクティビティを表示できますが、作成または編集はできません。 |
   | 編集者 | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | 承認者 | アクティビティの作成、編集、アクティブ化、停止ができます。 |

   詳しくは、*Enterprise ユーザーガイド*の [Admin Console での製品の権限およびロールの管理](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)を参照してください。

## トレーニングビデオ

以下のビデオは、この記事で説明する概念についてさらに詳しく説明しています。

### Target のワークスペースの設定方法（6:55）

このビデオでは、ワークスペースの作成方法を説明します。

* Adobe Target のインターフェイスから Adobe Admin Console にアクセスします（3 つの方法）
* Adobe Admin Console でワークスペースを設定します

   * ユーザーをワークスペースに追加します
   * プロパティをワークスペースに追加します

* デフォルトのワークスペースの概要を説明します

>[!VIDEO](https://video.tv.adobe.com/v/19463/?captions=jpn)

### Adobe Target でプロパティを作成する方法（3:05）

* [!DNL Adobe Target] インターフェイス内でプロパティを作成する方法
* プロパティトークンを生成してプロパティの実装に含める方法
* 次の 3 つの実装方法について説明します。

   * Web
   * モバイルアプリ
   * 電子メール、セットトップボックス、API 呼び出し

>[!VIDEO](https://video.tv.adobe.com/v/18990/?captions=jpn)
