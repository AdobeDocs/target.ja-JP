---
keywords: ユーザーの追加;プロジェクト;ユーザーグループ;プロパティ;ワークスペース;プロパティの管理;プロパティ;at_property;役割;権限
description: Adobe Targetにユーザーを追加する方法、ワークスペース、ユーザーグループ、プロパティを作成する方法、実装を更新する方法、役割と権限を指定する方法について説明します。
title: エンタープライズ権限を設定するにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Administration & Configuration
role: Admin
exl-id: 6494fc86-d2d3-4382-9d2e-63be435ba935
TQID: https://experienceleague.adobe.com/hMnPeT5NMMeNPLRdTtgcikwXWxcEjuMtycy1RNBi0Q4
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ceid: dfc8a233-f2b5-4811-bf63-b4262aebc5a5id: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2: id: c011fe9c-b94b-4a88-93d8-f2acece55112id: cd7b6938-5837-4ee0-9790-5840997133d9id: cf6b8469-14d0-4c0e-90ee-fb54066a035eid: faed1c89-faf7-4df1-910d-a88263e03b15id: fc9c2184-9102-403f-bd6c-0055021e4beaid: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1509
ht-degree: 55%

---

# Enterprise 権限の設定

ユーザーを[!DNL Target]実装に追加するために必要なタスクに関する情報。ワークスペース、ユーザーグループ、およびプロパティを作成し、`at_property` パラメーターを含めるように[!DNL Target]実装を更新し、役割と権限を指定します。

>[!NOTE]
>
>プロパティと権限の機能は [Target Premium](/help/main/c-intro/intro.md#premium) ソリューションの一部です。 [!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

次の表に、プロパティを作成し、ユーザーの役割および権限を割り当てるために必要なタスクを示します。 各タスクについて詳しくは、以下のセクションを参照してください。

| タスク | 実行場所 |
|--- |--- |
| &#x200B;1. ユーザーの追加（オプション） | [!DNL Adobe Admin Console for Enterprise] |
| &#x200B;2. ワークスペースの作成（製品プロファイル） | [!DNL Adobe Admin Console for Enterprise] |
| &#x200B;3. ユーザーグループの作成（オプション） | [!DNL Adobe Admin Console for Enterprise] |
| &#x200B;4. プロパティを作成 | [!DNL Target] UI |
| 5: `at_property` パラメーターを含めるように実装を更新します | [!DNL Target] UI、at.js関数、または[!DNL Adobe Experience Platform]のタグ |
| &#x200B;6. 役割および権限の指定 | [!DNL Adobe Admin Console for Enterprise] |

[!DNL Adobe Admin Console for Enterprise]で実行されたタスクについては、次の手順に従ってコンソールにアクセスします。

1. Adobe Targetで、**[!UICONTROL 管理]** > **[!UICONTROL プロパティ]** > **[!UICONTROL プロパティをワークスペースに割り当て]**&#x200B;をクリックします。

   または

   まだログインしていない場合は、[https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/)/Adobe IDを使用してログインに移動します。


1. （条件付き）複数の組織の [!DNL Admin Console for Enterprise] へのアクセス権を持っている場合、右隅または上部のナビゲーションバーにあるユーザーアバターをクリックしてから、目的の組織を選択します。

## 手順 1. ユーザーの追加（オプション） {#section_A92AF0F921B743FEB9E9033433BD816A}

新しい[!UICONTROL  プロパティ ]機能の使用を開始する場合、すべてのユーザー管理を[!DNL Adobe Admin Console for Enterprise]で実行する必要があります。 ただし、[!DNL Target] のすべての既存のユーザーは、[!DNL Target] から [!DNL Admin Console for Enterprise] に移行されます。

1. [Admin Console](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE)で、ページの上部にある「**[!UICONTROL ユーザー]**」タブをクリックし、「**[!UICONTROL ユーザーを追加]**」をクリックして、新しいユーザーを作成するか、既存のユーザーを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/jp/enterprise/help/users.html)の手順に従ってください。

## 手順 2： ワークスペースの作成（製品プロファイル） {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

ワークスペース（製品プロファイル）を使用すると、組織は特定のユーザーセットを特定のプロパティセットに割り当てることができます。 多くの点で、ワークスペースは [!DNL Analytics] のレポートスイートに似ています。

組織は、[!DNL Admin Console]内に新しいワークスペースを作成し、[!DNL Target]個のプロパティをこれらのワークスペースに割り当て、ユーザーを「デフォルトのWorkspace」設定からこれらの新しいアクセス制限ワークスペースに移動することで、エンタープライズ権限機能を利用できます。

これらのワークスペースを使用して、地域別、ビジネスユニット別、サイトセクション別または選択したその他の方法で、様々なチームにアクセス権を分割できます。

ユーザーは複数のワークスペースに属すことができ、各ワークスペースで異なる役割を持つこともできます。

1. [!DNL Admin Console]で、**[!UICONTROL 製品]**&#x200B;をクリックし、目的の製品の名前を選択します。

   ![ワークスペース](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. 目的のワークスペース（製品プロファイル）を作成します。

   * **デフォルトアクセス：**&#x200B;既存のすべてのアクティビティは、「デフォルトアクセス」と呼ばれる単一のプロジェクトに結合されます。 これは、顧客には影響しません。 すべてのユーザーの役割および機能は、この変更より前とまったく同じように残ります。

     [!DNL Adobe Experience Manager]（AEM）、[!DNL Adobe Mobile Services] および [!DNL Target Classic] を使用して作成されたすべてのアクティビティも、「デフォルトアクセス」ワークスペースの一部です。 現在は、プロジェクトを「デフォルトアクセス」から別のプロジェクトに移動することはできません。

   * **新規ワークスペース（製品プロファイル）：**&#x200B;次の手順を実行することで、新しい権限機能の利用を開始できます。

      * [!DNL Admin Console for Enterprise] での新しいワークスペースの作成。
      * Target プロパティのワークスペースへの割り当て。

   これらのワークスペースを使用して、地域別、ビジネスユニット別、サイトセクション別または選択したその他の方法で、様々なチームにアクセス権を分割できます。 ユーザーは複数のワークスペースに属すことができ、各ワークスペースで異なる役割を持つことができます。

1. *Enterprise ユーザーガイド*&#x200B;の[製品構成の作成と管理](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)の手順に従ってください。

>[!NOTE]
>ワークスペース設定について詳しくは、以下のトレーニングビデオをご覧ください。

### ワークスペース IDの取得 {#workspace-id}

[Target API](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/server-side-overview.html?lang=ja){target=_blank} の Enterprise 権限を活用するには、ワークスペース IDを渡す必要があります。

1. [Adobe Admin Console](https://adminconsole.adobe.com)で、「[!UICONTROL 製品]」タブをクリックし、左側のメニューの製品をクリックしてPLC （ワークスペース）リストを表示します。
1. 目的のPLC（ワークスペース）をクリックし、次に示す URL で「プロファイル」 ID を探します。

   ![ワークスペース ID](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## 手順 3. ユーザーグループの作成（オプション） {#section_5F5CB9AA7A9F4D26953E22016DA59605}

開発者、アナリスト、マーケティング担当者、エグゼクティブなどのユーザーグループを作成して、複数のアドビ製品およびワークスペースにわたって権限を割り当てることができます。 新しいチームメンバーに様々なアドビ製品にわたるすべての適切な権限を割り当てることは、特定のユーザーグループに追加するくらいに簡単です。

1. Admin Consoleで、ページの上部にある「**[!UICONTROL ユーザー]**」タブ/「**[!UICONTROL ユーザーグループ]**」をクリックして、新しいユーザーグループを作成するか、既存のグループを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の[製品構成のユーザーおよびグループを管理する](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)の手順に従ってください。

## 手順 4. プロパティを作成 {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

プロパティは、任意の呼び出し（[!DNL Target]呼び出し、api呼び出しなど）を持つパラメーターとして特定の名前と値のペアを追加することで有効になります。 [!DNL Target]へ。

プロパティは特定のチャネル（Web、モバイル、電子メール、API/その他）に属します。

**ヒント**：プロパティの作成方法について詳しくは、以下のトレーニングビデオをご覧ください。

1. [!DNL Target]で、**[!UICONTROL 管理]** > **[!UICONTROL プロパティ]**&#x200B;をクリックして、[!UICONTROL  プロパティ ]のリストを表示します。
1. 「**プロパティを作成**」をクリックします。

   以下のフィールドを設定します。

   * **プロパティ名（必須）:** プロパティのわかりやすい名前を指定します。
   * **説明：**（オプション）プロパティの説明を指定します。
   * **チャネル：** Web、モバイル、アプリ、電子メールまたはその他／API（例えばセットトップボックスや PlayStation コンソール）から、プロパティ用の目的のチャネルを選択します。

1. 「**[!UICONTROL コピー]**」をクリックして、コードをクリップボードにコピーします。このコードは、[5の手順を実行する際に使用します。「実装を更新してat_property パラメーター](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8)を含める」の手順を実行します。
1. 終了したら「**[!UICONTROL Save]**」をクリックします。

>[!NOTE]
>プロパティ作成について詳しくは、以下のトレーニングビデオをご覧ください。

## 手順5:at_property パラメーターを含めるように実装を更新する {#section_9B17A59807A94712BE642942442EBBC8}

[!DNL Target] ユーザー権限機能を使用するには、[!DNL Target] （Target呼び出し、API呼び出しなど）にヒットしているすべての呼び出しに`at_property` パラメーターを追加する必要があります。

**`at_property` パラメーターコードを取得するには：**

1. （条件付き）[4. プロパティの作成](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD)の手順を実行しながら生成してクリップボードに保存した実装コードを使用して、手順 2 に進みます。

   または

   [!DNL Target]で、**[!UICONTROL 管理]** > **[!UICONTROL プロパティ]**&#x200B;をクリックして、[!UICONTROL  プロパティ ]のリストを表示します。

   1. 目的のプロパティを表示するには、[!UICONTROL 最終更新日]列にマウスポインターを置き、[!UICONTROL  コード ] アイコン （![ コードアイコン ](/help/main/assets/icons/Code.svg)）をクリックします。

      ![プロパティホバーコード](/help/main/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. 強調表示された実装コードを右クリックして、クリップボードにコピーします。

1. 前の手順で取得した実装コードを使用して、[!DNL Target]実装を更新します。

   [!DNL Target] 実装を更新するには、いくつかの方法があります。 例えば、Web ページには次の方法を使用できます。

   * **[!DNL Adobe Experience Platform]:**&#x200B;内のタグの「カスタムパラメーター」経由

     詳しくは、*タグの概要* ドキュメントの[Mbox パラメーターの追加](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=en#add-mbox-params)を参照してください。

   * **targetPageParamsAll （）関数を使用：** at.js参照の上の`<head>` タグに次のコードを配置します。

     ```javascript
     <script>
      function targetPageParamsAll() {
       return {
        "at_property": "5f8bd98b-1456-a84c-2a96-11s9b8e2b112"
       };
      }
     </script>
     ```

     at.jsでこれを行う方法について詳しくは、[targetPageParamsAll](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetpageparamsall.html?lang=en){target=_blank}を参照してください。

## 手順6：役割と権限の指定 {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. Admin Console で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

   ![ワークスペース](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 目的のプロファイルの名前（例：デフォルトのWorkspace）をクリックします。

   ![デフォルトのワークスペース](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. 「**[!UICONTROL ユーザー]**」をクリックします。

   「[!UICONTROL  ユーザー]」タブには、そのワークスペース内のすべてのユーザーが表示されます。

   ![設定ユーザー](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. [!UICONTROL 製品の役割]列の各ユーザーのドロップダウンリストを使用して、目的の権限の役割（承認者、編集者、オブザーバー、または発行者）を選択します。

   ![製品の役割ドロップダウンリスト](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 役割 | 説明 |
   |--- |--- |
   | 承認者 | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | 編集者 | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | 監視者 | アクティビティを表示できますが、作成または編集はできません。 |
   | 発行者 | 監視者の役割と同様です（アクティビティを表示できますが、作成または編集はできません）。 ただし、発行者の役割には、アクティビティをアクティブ化する追加の権限があります。 |

   詳しくは、*Enterprise ユーザーガイド*&#x200B;の [Admin Console での製品の権限およびロールの管理](https://helpx.adobe.com/jp/enterprise/help/manage-permissions-and-roles.html)を参照してください。

## トレーニングビデオ

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

>[!NOTE]
>
>[!DNL Target] [!UICONTROL 管理] メニューUI （旧称[!UICONTROL  セットアップ ]）は、パフォーマンスの向上、新機能のリリース時に必要なメンテナンス時間の短縮、製品全体でのユーザーエクスペリエンスの向上を目的として再設計されました。 次のビデオの情報は一般的に正しいですが、オプションは少し異なる場所にある場合があります。 更新されたビデオは間もなく投稿される予定です。

### Adobe Target Workspacesの設定方法（6:55） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、ワークスペースの作成方法を説明します。

* Adobe Target のインターフェイスから Adobe Admin Console にアクセスします（3 つの方法）
* Adobe Admin Console でワークスペースを設定します

   * ユーザーをワークスペースに追加します
   * プロパティをワークスペースに追加します

* デフォルトのワークスペースの概要を説明します

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### Adobe Targetでプロパティを作成する方法（3:05） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

* [!DNL Adobe Target] インターフェイス内でプロパティを作成する方法
* プロパティトークンを生成してプロパティの実装に含める方法
* 次の 3 つの実装方法について説明します。

   * Web
   * モバイルアプリ
   * 電子メール、セットトップボックス、またはAPI呼び出し

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
