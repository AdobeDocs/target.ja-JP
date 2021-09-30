---
keywords: ユーザーの追加;プロジェクト;ユーザーグループ;プロパティ;ワークスペース;プロパティの管理;プロパティ;at_property;役割;権限
description: ユーザーをAdobe Targetに追加する方法を説明します。ワークスペース、ユーザーグループ、プロパティの作成実装の更新役割と権限を指定します。
title: Enterprise 権限の設定方法を教えてください。
feature: Administration & Configuration
role: Admin
exl-id: 6494fc86-d2d3-4382-9d2e-63be435ba935
source-git-commit: ea3485a8db00a5aa5ef5bede3006dd62dca5559a
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 63%

---

# ![PREMIUM](/help/assets/premium.png) Enterprise 権限の設定

[!DNL Target] 実装にユーザーを追加するために必要なタスクに関する情報。ワークスペース、ユーザーグループ、プロパティの作成[!DNL Target] 実装を更新して `at_property` パラメーターを含めます。役割と権限を指定します。

>[!NOTE]
>
>プロパティと権限の機能は [Target Premium](/help/c-intro/intro.md#premium) ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

次の表に、プロパティを作成し、ユーザーの役割および権限を割り当てるために必要なタスクを示します。各タスクについて詳しくは、以下のセクションを参照してください。

| タスク | 実行場所 |
|--- |--- |
| 1.ユーザーの追加（オプション） | [!DNL Adobe Admin Console for Enterprise] |
| 2.ワークスペース（製品プロファイル）の作成 | [!DNL Adobe Admin Console for Enterprise] |
| 3.ユーザーグループの作成（オプション） | [!DNL Adobe Admin Console for Enterprise] |
| 4. プロパティの作成 | [!DNL Target] UI |
| 5:`at_property` パラメーターを含めるように実装を更新します。 | [!DNL Target] UI、at.js 関数、タグ (  [!DNL Adobe Experience Platform] |
| 6. 役割および権限の指定 | [!DNL Adobe Admin Console for Enterprise] |

[!DNL Adobe Admin Console for Enterprise] で実行するタスクの場合は、次の手順でコンソールにアクセスします。

1. Adobe Targetで、**[!UICONTROL 管理]** / **[!UICONTROL プロパティ]** / **[!UICONTROL プロパティをワークスペースに割り当て]** をクリックします。

   または

   [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) に移動し、まだログインしていない場合はAdobe IDを使用してログインします。


1. （条件付き）複数の組織の [!DNL Admin Console for Enterprise] へのアクセス権を持っている場合、右隅または上部のナビゲーションバーにあるユーザーアバターをクリックしてから、目的の組織を選択します。

## 手順 1.ユーザーの追加（オプション） {#section_A92AF0F921B743FEB9E9033433BD816A}

新しい[!UICONTROL プロパティ]機能を使用し始める場合、すべてのユーザー管理は、[!DNL Adobe Admin Console for Enterprise] で実行する必要があります。ただし、[!DNL Target] のすべての既存のユーザーは、[!DNL Target] から [!DNL Admin Console for Enterprise] に移行されます。

1. [Admin Console](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE) で、ページ上部の「**[!UICONTROL ユーザー]**」タブをクリックした後、「**[!UICONTROL ユーザーを追加]**」をクリックして、新しいユーザーを作成するか、既存のユーザーを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/enterprise/help/users.html)の手順に従ってください。

## 手順 2：ワークスペース（製品プロファイル）の作成 {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

ワークスペース（製品プロファイル）を使用すると、組織は特定のユーザーのセットを特定のプロパティのセットに割り当てることができます。 多くの点で、ワークスペースは [!DNL Analytics] のレポートスイートに似ています。

[!DNL Admin Console] 内で新しいワークスペースを作成し、[!DNL Target] プロパティを割り当て、「Default Workspace」設定から新しい制限付きワークスペースにユーザーを移動することで、企業権限の機能の活用を開始できます。

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

### ワークスペース ID の取得 {#workspace-id}

[Target API](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) の Enterprise 権限を活用するには、ワークスペース IDを渡す必要があります。

1. [Adobe Admin Console ](https://adminconsole.adobe.com)で 、[!UICONTROL 「製品」] タブをクリックし、左側のメニューで製品をクリックして、PLC（ワークスペース）」リストを表示します。
1. 目的のPLC（ワークスペース）をクリックし、次に示す URL で「プロファイル」 ID を探します。

   ![ワークスペース ID](/help/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## 手順 3.ユーザーグループの作成（オプション） {#section_5F5CB9AA7A9F4D26953E22016DA59605}

開発者、アナリスト、マーケティング担当者、エグゼクティブなどのユーザーグループを作成して、複数のアドビ製品およびワークスペースにわたって権限を割り当てることができます。新しいチームメンバーに様々なアドビ製品にわたるすべての適切な権限を割り当てることは、特定のユーザーグループに追加するくらいに簡単です。

1. Admin Console で、ページ上部の「**[!UICONTROL ユーザー]**」タブをクリックした後、「**[!UICONTROL ユーザーグループ]**」をクリックして、新しいユーザーグループを作成するか、既存のユーザーグループを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の[製品構成のユーザーおよびグループを管理する](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)の手順に従ってください。

## 手順 4.プロパティの作成 {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

プロパティは、任意の呼び出し（Target の呼び出し、API の呼び出しなど）で、特定の名前と値のペアをパラメーターとして追加することで、 to Target.

プロパティは、特定のチャネル（Web、モバイル、電子メールおよび API／その他）に属しています。

**ヒント**：プロパティの作成方法について詳しくは、以下のトレーニングビデオをご覧ください。

1. [!DNL Target] で、**[!UICONTROL 管理]** /**[!UICONTROL プロパティ]** をクリックして、[!UICONTROL  プロパティ ] リストを表示します。
1. 「**プロパティを作成**」をクリックします。

   ![新規プロパティダイアログボックス](/help/administrating-target/c-user-management/property-channel/assets/new_property1.png)

   以下のフィールドを設定します。

   * **プロパティ名（必須）:** プロパティのわかりやすい名前を指定します。
   * **説明：**（オプション）プロパティの説明を指定します。
   * **チャネル：** Web、モバイル、アプリ、電子メールまたはその他／API（例えばセットトップボックスや PlayStation コンソール）から、プロパティ用の目的のチャネルを選択します。

1. **[!UICONTROL コピー]** をクリックして、[5 の手順の実行中に使用するコードをクリップボードにコピーします。at_property パラメーター ](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8) を含めるための実装の更新。
1. 終了したら「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>プロパティ作成について詳しくは、以下のトレーニングビデオをご覧ください。

## 手順 5:at_property パラメーターを含めるように実装を更新する {#section_9B17A59807A94712BE642942442EBBC8}

[!DNL Target] ユーザー権限機能を使用するには、[!DNL Target] をヒットするすべての呼び出し（Target の呼び出し、API の呼び出しなど）に `at_property` パラメーターを追加する必要があります。

**`at_property` パラメーターコードを取得するには：**

1. （条件付き）[4.プロパティの作成](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD)の手順を実行しながら生成してクリップボードに保存した実装コードを使用して、手順 2 に進みます。

   または

   [!DNL Target] で、**[!UICONTROL 管理]** /**[!UICONTROL プロパティ]** をクリックして、[!UICONTROL  プロパティ ] リストを表示します。

   1. 目的のプロパティの[!UICONTROL 最終更新日]列の上にマウスポインターを置いて、[!UICONTROL コード]アイコンを表示し、クリックします。

      ![プロパティホバーコード](/help/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. 強調表示された実装コードを右クリックして、クリップボードにコピーします。

      ![プロパティコード](/help/administrating-target/c-user-management/property-channel/assets/code_property_2_new.png)

1. 前の手順で取得した実装コードで [!DNL Target] 実装を更新します。

   [!DNL Target] 実装を更新するには、いくつかの方法があります。例えば、Web ページには次の方法を使用できます。

   * **次のタグの「グローバルパラメーター」を使用  [!DNL Adobe Experience Platform]:**

      詳しくは、*タグの概要* ドキュメントの [ グローバルターゲットパラメーターの追加 ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=en#add-global-mbox-params) を参照してください。

   * **targetPageParamsAll() 関数を使用：** 次のコードを `<head>` タグの at.js 参照の上に配置します。

      ```javascript
      <script>
       function targetPageParamsAll() {
        return {
         "at_property": "5f8bd98b-1456-a84c-2a96-11s9b8e2b112"
        };
       }
      </script>
      ```

      at.js でこれをおこなう方法について詳しくは、[targetPageParamsAll](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) を参照してください。

   * **mboxCreate() 関数を使用：**

      ![](assets/property_token_3.png)

      at.js を使用してこれをおこなう方法については、  [](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) targetPageParamsAlland   [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)を参照してください。

## 手順 6:役割と権限の指定 {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. Admin Console で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

   ![ワークスペース](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 目的のプロファイルの名前（「デフォルトのワークスペース」など）をクリックします。

   ![デフォルトのワークスペース](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. 「**[!UICONTROL ユーザー]**」をクリックします。

   「[!UICONTROL ユーザー]」タブにワークスペースのすべてのユーザーが表示されます。

   ![設定ユーザー](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. [!UICONTROL  製品の役割 ] 列の各ユーザーのドロップダウンリストを使用して、目的の権限の役割（承認者、編集者、監視者、投稿者）を選択します。

   ![製品の役割ドロップダウンリスト](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 役割 | 説明 |
   |--- |--- |
   | 承認者 | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | 編集者 | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | 監視者 | アクティビティを表示できますが、作成または編集はできません。 |
   | 発行者 | 監視者の役割と同様です（アクティビティは表示できますが、作成または編集はできません）。 ただし、発行者の役割には、アクティビティをアクティブ化する追加の権限があります。 |

   詳しくは、*Enterprise ユーザーガイド*&#x200B;の [Admin Console での製品の権限およびロールの管理](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)を参照してください。

## トレーニングビデオ

以下のビデオは、この記事で説明する概念についてさらに詳しく説明しています。

>[!NOTE]
>
>[!DNL Target] [!UICONTROL  管理 ] メニュー UI（旧称 [!UICONTROL  セットアップ ]）が再設計され、パフォーマンスの向上、新機能のリリースに必要なメンテナンス時間の短縮、製品全体でのユーザーエクスペリエンスの向上が実現しました。 次のビデオの情報は、通常正しいです。ただし、オプションの位置は若干異なる場合があります。 更新されたビデオは近日中に投稿されます。

### Adobe Target Workspaces (6:55)の設定方法 ![ チュートリアルバッジ ](/help/assets/tutorial.png)

このビデオでは、ワークスペースの作成方法を説明します。

* Adobe Target のインターフェイスから Adobe Admin Console にアクセスします（3 つの方法）
* Adobe Admin Console でワークスペースを設定します

   * ユーザーをワークスペースに追加します
   * プロパティをワークスペースに追加します

* デフォルトのワークスペースの概要を説明します

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### Adobe Target (3:05)でプロパティを作成する方法 ![ チュートリアルバッジ ](/help/assets/tutorial.png)

* [!DNL Adobe Target] インターフェイス内でプロパティを作成する方法
* プロパティトークンを生成してプロパティの実装に含める方法
* 次の 3 つの実装方法について説明します。

   * Web
   * モバイルアプリ
   * 電子メール、セットトップボックス、API 呼び出し

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
