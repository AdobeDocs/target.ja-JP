---
keywords: ユーザーの追加;プロジェクト;ユーザーグループ;プロパティ;ワークスペース;プロパティの管理;プロパティ;at_property;役割;権限
description: Adobe Targetにユーザーを追加する方法、ワークスペース、ユーザーグループ、プロパティを作成する方法、実装を更新する方法、役割と権限を指定する方法について説明します。
title: Enterprise 権限を設定するにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Administration & Configuration
role: Admin
exl-id: 6494fc86-d2d3-4382-9d2e-63be435ba935
source-git-commit: 0ab5b7d7cbfaef86b9a045883f597900dba72416
workflow-type: tm+mt
source-wordcount: '1392'
ht-degree: 56%

---

# Enterprise 権限の設定

[!DNL Target] 実装にユーザーを追加するために必要なタスクに関する情報。ワークスペース、ユーザーグループ、プロパティの作成、[!DNL Target] 実装を更新して `at_property` パラメーターを含めること、役割と権限の指定について説明します。

>[!NOTE]
>
>プロパティと権限の機能は [Target Premium](/help/main/c-intro/intro.md#premium) ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

次の表に、プロパティを作成し、ユーザーの役割および権限を割り当てるために必要なタスクを示します。各タスクについて詳しくは、以下のセクションを参照してください。

| タスク | 実行場所 |
|--- |--- |
| &#x200B;1. ユーザーを追加（オプション） | [!DNL Adobe Admin Console for Enterprise] |
| &#x200B;2. ワークスペースの作成（製品プロファイル） | [!DNL Adobe Admin Console for Enterprise] |
| &#x200B;3. ユーザーグループの作成（オプション） | [!DNL Adobe Admin Console for Enterprise] |
| &#x200B;4. プロパティの作成 | [!DNL Target] UI |
| 5:`at_property` パラメーターを含めるように実装を更新する | [!DNL Target] UI、at.js 関数または [!DNL Adobe Experience Platform] のタグ |
| &#x200B;6. 役割および権限の指定 | [!DNL Adobe Admin Console for Enterprise] |

[!DNL Adobe Admin Console for Enterprise] で実行するタスクの場合は、次の手順でコンソールにアクセスします。

1. Adobe Targetで、**[!UICONTROL Administration]**/**[!UICONTROL Properties]**/**[!UICONTROL Assign Properties to Workspaces]** をクリックします。

   または

   まだログインしていない場合は、[https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) /Adobe IDを使用してログインします。


1. （条件付き）複数の組織の [!DNL Admin Console for Enterprise] へのアクセス権を持っている場合、右隅または上部のナビゲーションバーにあるユーザーアバターをクリックしてから、目的の組織を選択します。

## 手順 1.ユーザーを追加（オプション） {#section_A92AF0F921B743FEB9E9033433BD816A}

新しい [!UICONTROL Properties] 機能の使用を開始する際は、すべてのユーザー管理を [!DNL Adobe Admin Console for Enterprise] で実行する必要があります。 ただし、[!DNL Target] のすべての既存のユーザーは、[!DNL Target] から [!DNL Admin Console for Enterprise] に移行されます。

1. [Admin Consoleで ](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE)、ページ上部の「**[!UICONTROL Users]**」タブ/ **[!UICONTROL Add Users]** をクリックして、新規ユーザーを作成するか、既存のユーザーを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/jp/enterprise/help/users.html)の手順に従ってください。

## 手順 2：ワークスペースの作成（製品プロファイル） {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

ワークスペース（製品プロファイル）を使用すると、組織は特定のユーザーセットを特定のプロパティセットに割り当てることができます。 多くの点で、ワークスペースは [!DNL Analytics] のレポートスイートに似ています。

各組織は、[!DNL Admin Console] 内に新しいワークスペースを作成し、これらのワークスペースに [!DNL Target] のプロパティを割り当て、ユーザーを「デフォルトのWorkspace」構成からアクセスが制限された新しいワークスペースに移動することによって、エンタープライズ・パーミッション機能の活用を開始できます。

これらのワークスペースを使用して、地域別、ビジネスユニット別、サイトセクション別または選択したその他の方法で、様々なチームにアクセス権を分割できます。

ユーザーは複数のワークスペースに属すことができ、各ワークスペースで異なる役割を持つこともできます。

1. [!DNL Admin Console] で「**[!UICONTROL Products]**」をクリックしてから、目的の製品名を選択します。

   ![ワークスペース](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. 目的のワークスペース（製品プロファイル）を作成します。

   * **デフォルトアクセス：**&#x200B;既存のすべてのアクティビティは、「デフォルトアクセス」と呼ばれる単一のプロジェクトに結合されます。これは、顧客には影響しません。すべてのユーザーの役割および機能は、この変更より前とまったく同じように残ります。

     [!DNL Adobe Experience Manager]（AEM）、[!DNL Adobe Mobile Services] および [!DNL Target Classic] を使用して作成されたすべてのアクティビティも、「デフォルトアクセス」ワークスペースの一部です。現在は、プロジェクトを「デフォルトアクセス」から別のプロジェクトに移動することはできません。

   * **新規ワークスペース（製品プロファイル）：**&#x200B;次の手順を実行することで、新しい権限機能の利用を開始できます。

      * [!DNL Admin Console for Enterprise] での新しいワークスペースの作成。
      * Target プロパティのワークスペースへの割り当て。

   これらのワークスペースを使用して、地域別、ビジネスユニット別、サイトセクション別または選択したその他の方法で、様々なチームにアクセス権を分割できます。ユーザーは複数のワークスペースに属すことができ、各ワークスペースで異なる役割を持つことができます。

1. *Enterprise ユーザーガイド*&#x200B;の[製品構成の作成と管理](https://helpx.adobe.com/jp/enterprise/help/manage-products-and-configurations.html)の手順に従ってください。

>[!NOTE]
>ワークスペース設定について詳しくは、以下のトレーニングビデオをご覧ください。

### ワークスペース ID の取得 {#workspace-id}

[Target API](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/server-side-overview.html?lang=ja){target=_blank} の Enterprise 権限を活用するには、ワークスペース IDを渡す必要があります。

1. [Adobe Admin Console](https://adminconsole.adobe.com) で [[!UICONTROL Products]] タブをクリックし、左メニューで商品をクリックして PLC （Workspace）一覧を表示します。
1. 目的のPLC（ワークスペース）をクリックし、次に示す URL で「プロファイル」 ID を探します。

   ![ワークスペース ID](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## 手順 3.ユーザーグループの作成（オプション） {#section_5F5CB9AA7A9F4D26953E22016DA59605}

開発者、アナリスト、マーケティング担当者、エグゼクティブなどのユーザーグループを作成して、複数のアドビ製品およびワークスペースにわたって権限を割り当てることができます。新しいチームメンバーに様々なアドビ製品にわたるすべての適切な権限を割り当てることは、特定のユーザーグループに追加するくらいに簡単です。

1. Admin Consoleで、ページ上部の「**[!UICONTROL Users]**」タブをクリックして、新しいユーザーグループを作成するか、既存のグループを編集し **[!UICONTROL User Groups]** す。
1. *Enterprise ユーザーガイド*&#x200B;の[製品構成のユーザーおよびグループを管理する](https://helpx.adobe.com/jp/enterprise/help/manage-products-and-configurations.html)の手順に従ってください。

## 手順 4.プロパティの作成 {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

プロパティを有効にするには、任意の呼び出し（[!DNL Target] 呼び出し、api 呼び出しなど）を持つパラメーターとして、特定の名前と値のペアを追加 [!DNL Target] ます。

プロパティは、特定のチャネル（web、モバイル、メール、API/その他）に属しています。

**ヒント**：プロパティの作成方法について詳しくは、以下のトレーニングビデオをご覧ください。

1. [!DNL Target] で、**[!UICONTROL Administration]**/**[!UICONTROL Properties]** をクリックして、[!UICONTROL Properties] リストを表示します。
1. 「**プロパティを作成**」をクリックします。

   以下のフィールドを設定します。

   * **プロパティ名（必須）:** プロパティのわかりやすい名前を指定します。
   * **説明：**（オプション）プロパティの説明を指定します。
   * **チャネル：** Web、モバイル、アプリ、電子メールまたはその他／API（例えばセットトップボックスや PlayStation コンソール）から、プロパティ用の目的のチャネルを選択します。

1. 「**[!UICONTROL Copy]**」をクリックして、「[5:at_property パラメーターを含めるように実装を更新 ](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8) の手順を実行する際に使用するコードをクリップボードにコピーします。
1. 終了したら「**[!UICONTROL Save]**」をクリックします。

>[!NOTE]
>プロパティ作成について詳しくは、以下のトレーニングビデオをご覧ください。

## 手順 5：実装を更新して at_property パラメーターを含める {#section_9B17A59807A94712BE642942442EBBC8}

[!DNL Target] のユーザー権限機能を使用するには、`at_property` にヒットするすべての呼び出し（Target 呼び出し、API 呼び出しなど）に [!DNL Target] パラメーターを追加する必要があります。

**`at_property` パラメーターコードを取得するには：**

1. （条件付き）[4.プロパティの作成](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD)の手順を実行しながら生成してクリップボードに保存した実装コードを使用して、手順 2 に進みます。

   または

   [!DNL Target] で、**[!UICONTROL Administration]**/**[!UICONTROL Properties]** をクリックして、[!UICONTROL Properties] リストを表示します。

   1. 表示する目的のプロパティの「[!UICONTROL Last Updated]」列にマウスポインターを置き、[!UICONTROL Code] アイコン（![ コードアイコン ](/help/main/assets/icons/Code.svg)）をクリックします。

      ![プロパティホバーコード](/help/main/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. 強調表示された実装コードを右クリックして、クリップボードにコピーします。

1. 前の手順で取得した実装コードを使用して [!DNL Target] 実装を更新します。

   [!DNL Target] 実装を更新するには、いくつかの方法があります。例えば、Web ページには次の方法を使用できます。

   * **[!DNL Adobe Experience Platform] 内のタグの「カスタムパラメーター」を使用：**

     詳しくは、[ タグの概要 ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=ja#add-mbox-params) ドキュメントの *mbox パラメーターの追加* を参照してください。

   * **targetPageParamsAll （）関数を使用：** 次のコードを `<head>` タグ内の at.js 参照の上に配置します。

     ```javascript
     <script>
      function targetPageParamsAll() {
       return {
        "at_property": "5f8bd98b-1456-a84c-2a96-11s9b8e2b112"
       };
      }
     </script>
     ```

     at.js を使用してこれを行う方法について詳しくは、[targetPageParamsAll](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetpageparamsall.html?lang=ja){target=_blank} を参照してください。

## 手順 6：役割と権限の指定 {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. Admin Consoleで「**[!UICONTROL Products]**」をクリックしてから、目的の商品名を選択します。

   ![ワークスペース](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 目的のプロファイルの名前（デフォルトのWorkspaceなど）をクリックします。

   ![デフォルトのワークスペース](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. **[!UICONTROL Users]** をクリックします。

   「[!UICONTROL Users]」タブには、そのワークスペース内のすべてのユーザーが表示されます。

   ![設定ユーザー](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. [!UICONTROL Product Role] 列の各ユーザーのドロップダウンリストを使用して、目的の権限の役割（承認者、編集者、監視者、発行者）を選択します。

   ![製品の役割ドロップダウンリスト](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 役割 | 説明 |
   |--- |--- |
   | 承認者 | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | 編集者 | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | 監視者 | アクティビティを表示できますが、作成または編集はできません。 |
   | 発行者 | 監視者の役割と同様です（アクティビティを表示できますが、作成または編集はできません）。ただし、発行者の役割には、アクティビティをアクティブ化する追加の権限があります。 |

   詳しくは、*Enterprise ユーザーガイド*&#x200B;の [Admin Console での製品の権限およびロールの管理](https://helpx.adobe.com/jp/enterprise/help/manage-permissions-and-roles.html)を参照してください。

## トレーニングビデオ

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

>[!NOTE]
>
>パフォーマンスを向上、新機能のリリースに要するメンテナンス時間を短縮、製品全体でのユーザーエクスペリエンスが向上するため、[!DNL Target] [!UICONTROL Administration] メニュー（以前の [!UICONTROL Setup]）のデザインが一新されました。 以下のビデオの情報は、通常、正確です。ただし、オプションの場所が若干異なる場合があります。 更新されたビデオは間もなく投稿される予定です。

### Adobe Target Workspaces の設定方法（6:55） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、ワークスペースの作成方法を説明します。

* Adobe Target のインターフェイスから Adobe Admin Console にアクセスします（3 つの方法）
* Adobe Admin Console でワークスペースを設定します

   * ユーザーをワークスペースに追加します
   * プロパティをワークスペースに追加します

* デフォルトのワークスペースの概要を説明します

>[!VIDEO](https://video.tv.adobe.com/v/3421733?captions=jpn)

### Adobe Targetでプロパティを作成する方法（3:05） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

* [!DNL Adobe Target] インターフェイス内でプロパティを作成する方法
* プロパティトークンを生成してプロパティの実装に含める方法
* 次の 3 つの実装方法について説明します。

   * Web
   * モバイルアプリ
   * メール、トップボックスまたは API 呼び出しの設定

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
