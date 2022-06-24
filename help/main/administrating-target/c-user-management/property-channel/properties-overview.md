---
keywords: ユーザーの追加;プロジェクト;ユーザーグループ;プロパティ;ワークスペース;プロパティの管理;プロパティ;at_property;役割;権限
description: ユーザーをAdobe Targetに追加する方法を学ぶワークスペース、ユーザーグループ、プロパティを作成する。実装を更新する。役割と権限を指定します。
title: Enterprise 権限を設定する方法を教えてください。
feature: Administration & Configuration
role: Admin
exl-id: 6494fc86-d2d3-4382-9d2e-63be435ba935
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 66%

---

# ![PREMIUM](/help/main/assets/premium.png) Enterprise 権限の設定

ユーザーを [!DNL Target] 実装；ワークスペース、ユーザーグループ、プロパティを作成する。を更新します。 [!DNL Target] を含める実装 `at_property` パラメータ；役割と権限を指定します。

>[!NOTE]
>
>プロパティと権限の機能は [Target Premium](/help/main/c-intro/intro.md#premium) ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

次の表に、プロパティを作成し、ユーザーの役割および権限を割り当てるために必要なタスクを示します。各タスクについて詳しくは、以下のセクションを参照してください。

| タスク | 実行場所 |
|--- |--- |
| 1.ユーザーを追加します（オプション） | [!DNL Adobe Admin Console for Enterprise] |
| 2.ワークスペース（製品プロファイル）の作成 | [!DNL Adobe Admin Console for Enterprise] |
| 3.ユーザーグループの作成（オプション） | [!DNL Adobe Admin Console for Enterprise] |
| 4. プロパティの作成 | [!DNL Target] UI |
| 5:実装を更新して、 `at_property` パラメータ | [!DNL Target] UI、at.js 関数、タグ ( [!DNL Adobe Experience Platform] |
| 6. 役割および権限の指定 | [!DNL Adobe Admin Console for Enterprise] |

で実行されるタスクの [!DNL Adobe Admin Console for Enterprise]次の手順に従って、コンソールにアクセスします。

1. Adobe Targetで、 **[!UICONTROL 管理]** > **[!UICONTROL プロパティ]** > **[!UICONTROL ワークスペースにプロパティを割り当て]**.

   または

   に移動します。 [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) / Adobe IDを使用してログイン（まだログインしていない場合）。


1. （条件付き）複数の組織の [!DNL Admin Console for Enterprise] へのアクセス権を持っている場合、右隅または上部のナビゲーションバーにあるユーザーアバターをクリックしてから、目的の組織を選択します。

## 手順 1.ユーザーの追加（オプション） {#section_A92AF0F921B743FEB9E9033433BD816A}

新しい[!UICONTROL プロパティ]機能を使用し始める場合、すべてのユーザー管理は、[!DNL Adobe Admin Console for Enterprise] で実行する必要があります。ただし、[!DNL Target] のすべての既存のユーザーは、[!DNL Target] から [!DNL Admin Console for Enterprise] に移行されます。

1. [Admin Console](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE) で、ページ上部の「**[!UICONTROL ユーザー]**」タブをクリックした後、「**[!UICONTROL ユーザーを追加]**」をクリックして、新しいユーザーを作成するか、既存のユーザーを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の [Experience Cloud でのユーザーとグループの管理](https://helpx.adobe.com/jp/enterprise/help/users.html)の手順に従ってください。

## 手順 2：ワークスペース（製品プロファイル）の作成 {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

ワークスペース（製品プロファイル）を使用すると、組織は特定のユーザーのセットを特定のプロパティのセットに割り当てることができます。 多くの点で、ワークスペースは [!DNL Analytics] のレポートスイートに似ています。

組織は、 [!DNL Admin Console]，割り当て [!DNL Target] プロパティをこれらのワークスペースに追加し、ユーザーを「デフォルトのワークスペース」設定から、より新しくアクセスが制限されたワークスペースに移動します。

これらのワークスペースを使用して、地域別、ビジネスユニット別、サイトセクション別または選択したその他の方法で、様々なチームにアクセス権を分割できます。

ユーザーは複数のワークスペースに属すことができ、各ワークスペースで異なる役割を持つこともできます。

1. [!DNL Admin Console] で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

   ![ワークスペース](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

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

Enterprise 権限を活用するには、ワークスペース ID を渡す必要があります。 [Target API](https://developer.adobe.com/target/implement/server-side/){target=_blank}。

1. [Adobe Admin Console ](https://adminconsole.adobe.com)で 、[!UICONTROL 「製品」] タブをクリックし、左側のメニューで製品をクリックして、PLC（ワークスペース）」リストを表示します。
1. 目的のPLC（ワークスペース）をクリックし、次に示す URL で「プロファイル」 ID を探します。

   ![ワークスペース ID](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## 手順 3.ユーザーグループの作成（オプション） {#section_5F5CB9AA7A9F4D26953E22016DA59605}

開発者、アナリスト、マーケティング担当者、エグゼクティブなどのユーザーグループを作成して、複数のアドビ製品およびワークスペースにわたって権限を割り当てることができます。新しいチームメンバーに様々なアドビ製品にわたるすべての適切な権限を割り当てることは、特定のユーザーグループに追加するくらいに簡単です。

1. Admin Console で、ページ上部の「**[!UICONTROL ユーザー]**」タブをクリックした後、「**[!UICONTROL ユーザーグループ]**」をクリックして、新しいユーザーグループを作成するか、既存のユーザーグループを編集します。
1. *Enterprise ユーザーガイド*&#x200B;の[製品構成のユーザーおよびグループを管理する](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)の手順に従ってください。

## 手順 4.プロパティの作成 {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

プロパティは、任意の呼び出し（Target 呼び出し、API 呼び出しなど）で、特定の名前と値のペアをパラメーターとして追加することで有効化されます。 to Target.

プロパティは、特定のチャネル（Web、モバイル、電子メールおよび API／その他）に属しています。

**ヒント**：プロパティの作成方法について詳しくは、以下のトレーニングビデオをご覧ください。

1. In [!DNL Target]をクリックし、 **[!UICONTROL 管理]** > **[!UICONTROL プロパティ]** 表示する [!UICONTROL プロパティ] リスト。
1. 「**プロパティを作成**」をクリックします。

   以下のフィールドを設定します。

   * **プロパティ名（必須）:** プロパティのわかりやすい名前を指定します。
   * **説明：**（オプション）プロパティの説明を指定します。
   * **チャネル：** Web、モバイル、アプリ、電子メールまたはその他／API（例えばセットトップボックスや PlayStation コンソール）から、プロパティ用の目的のチャネルを選択します。

1. クリック **[!UICONTROL コピー]** を使用して、 [5:at_property パラメーターを含めるための実装の更新](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8).
1. 終了したら「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>プロパティ作成について詳しくは、以下のトレーニングビデオをご覧ください。

## 手順 5:at_property パラメーターを含めるように実装を更新する {#section_9B17A59807A94712BE642942442EBBC8}

次の手順で [!DNL Target] ユーザー権限機能を使用する場合は、 `at_property` をヒットする任意の呼び出しのパラメーター [!DNL Target] （Target 呼び出し、API 呼び出しなど）。

**`at_property` パラメーターコードを取得するには：**

1. （条件付き）[4.プロパティの作成](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD)の手順を実行しながら生成してクリップボードに保存した実装コードを使用して、手順 2 に進みます。

   または

   In [!DNL Target]をクリックし、 **[!UICONTROL 管理]** > **[!UICONTROL プロパティ]** 表示する [!UICONTROL プロパティ] リスト。

   1. 目的のプロパティの[!UICONTROL 最終更新日]列の上にマウスポインターを置いて、[!UICONTROL コード]アイコンを表示し、クリックします。

      ![プロパティホバーコード](/help/main/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. 強調表示された実装コードを右クリックして、クリップボードにコピーします。

1. の更新 [!DNL Target] 前の手順で取得した実装コードを使用した実装。

   [!DNL Target] 実装を更新するには、いくつかの方法があります。例えば、Web ページには次の方法を使用できます。

   * **タグ内の「カスタムパラメーター」を使用 [!DNL Adobe Experience Platform]:**

      詳しくは、 [Add Mbox Params](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=en#add-mbox-params) 内 *タグの概要* ドキュメント。

   * **targetPageParamsAll() 関数を使用：** 次のコードを `<head>` タグを使用します。

      ```javascript
      <script>
       function targetPageParamsAll() {
        return {
         "at_property": "5f8bd98b-1456-a84c-2a96-11s9b8e2b112"
        };
       }
      </script>
      ```

      at.js を使用してこれをおこなう方法について詳しくは、 [targetPageParamsAll](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/){target=_blank}。

## 手順 6:役割と権限の指定 {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. Admin Console で「**[!UICONTROL 製品]**」をクリックしてから、目的の製品名を選択します。

   ![ワークスペース](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 目的のプロファイルの名前（「デフォルトのワークスペース」など）をクリックします。

   ![デフォルトのワークスペース](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. 「**[!UICONTROL ユーザー]**」をクリックします。

   「[!UICONTROL ユーザー]」タブにワークスペースのすべてのユーザーが表示されます。

   ![設定ユーザー](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. 各ユーザーのドロップダウンリストを使用して、目的の権限の役割（承認者、編集者、監視者、投稿者）を選択します。 [!UICONTROL 製品の役割] 列。

   ![製品の役割ドロップダウンリスト](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 役割 | 説明 |
   |--- |--- |
   | 承認者 | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | 編集者 | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | 監視者 | アクティビティを表示できますが、作成または編集はできません。 |
   | 発行者 | 監視者の役割と同様です（アクティビティを表示できますが、作成または編集はできません）。ただし、発行者の役割には、アクティビティをアクティブ化する追加の権限があります。 |

   詳しくは、*Enterprise ユーザーガイド*&#x200B;の [Admin Console での製品の権限およびロールの管理](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)を参照してください。

## トレーニングビデオ

以下のビデオは、この記事で説明する概念についてさらに詳しく説明しています。

>[!NOTE]
>
>パフォーマンスを向上、新機能のリリースに要するメンテナンス時間を短縮、製品全体でのユーザーエクスペリエンスが向上するため、[!DNL Target] [!UICONTROL 管理]メニュー（以前の[!UICONTROL 設定]）のデザインが一新されました。以下のビデオの情報は、通常正しいです。ただし、オプションの場所が若干異なる場合があります。 更新されたビデオは間もなく投稿される予定です。

### Adobe Target Workspaces の設定方法(6:55) ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、ワークスペースの作成方法を説明します。

* Adobe Target のインターフェイスから Adobe Admin Console にアクセスします（3 つの方法）
* Adobe Admin Console でワークスペースを設定します

   * ユーザーをワークスペースに追加します
   * プロパティをワークスペースに追加します

* デフォルトのワークスペースの概要を説明します

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### Adobe Targetでプロパティを作成する方法(3:05) ![チュートリアルバッジ](/help/main/assets/tutorial.png)

* [!DNL Adobe Target] インターフェイス内でプロパティを作成する方法
* プロパティトークンを生成してプロパティの実装に含める方法
* 次の 3 つの実装方法について説明します。

   * Web
   * モバイルアプリ
   * 電子メール、セットトップボックス、API 呼び出し

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
