---
keywords: target ユーザーインターフェイス；ユーザーインターフェイス；ui；お知らせ；イベント；通知
description: ユーザーインターフェイスに慣れ、 [!DNL Target] を最大限に活用するための詳細情報へのリンクを見つけます。
title: ' [!DNL Target] UI の使用方法'
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: 6bef27637c06f39ffc0e755f19e8a0870ec749e5
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 31%

---

# [!DNL Target] UI について

ユーザーインターフェイスは、[!DNL Adobe Target] を最大限に活用できるよう、論理的かつユーザーにわかりやすい形式で配置されています。以下の概要は、[!DNL Target] に慣れるのに役立ち、より詳細な情報と手順を説明するリンクを提供します。

[!DNL Target] UI の上部のヘッダーには、ソリューションの様々な機能を移動するのに役立つタブとオプションが含まれています。 また、組織と [!DNL Adobe Experience Cloud] ソリューションの切り替え、ヘルプと通知の取得、[!DNL Adobe] プロファイルの管理、[!DNL Target] からのログアウトを行うこともできます。

![Target ヘッダー](/help/main/c-intro/assets/target-header.png)

左側のタブを使って [!DNL Target] の様々な機能にアクセスできます。これについては後ほど説明します。 タブに進める前に、まず、右側のオプションについて説明します。

## 組織

*組織*&#x200B;とは、管理者がグループおよびユーザーを設定し、[!DNL Adobe Experience Cloud] でのシングルサインオンを制御するために使用するエンティティです。組織は、すべての [!DNL Experience Cloud] 製品およびソリューションをまたいだログイン会社のように機能します。ほとんどの場合、組織は、会社名です。ただし、会社は多数の組織を持つことができます。

会社に複数の組織がある場合は、[!UICONTROL Organization] のドロップダウンリストで目的の組織を選択します。

![組織ドロップダウンリスト](/help/main/c-intro/assets/organizations.png)

## Apps

アプリ切り替えボタンをクリックすると、自分がアクセス権を持っている [!DNL Adobe Experience Cloud] ソリューションにすばやくアクセスできます。

![アプリ切り替えツール](/help/main/c-intro/assets/apps.png)

## ヘルプ

ヘルプアイコンを使用すると、[!DNL Target] をより効果的に使用するために、情報、ビデオ、ブログなどにアクセスできます。サポートチケットの作成、サポート用電話番号の検索、Twitterでの質問、または [!DNL Target] チームの活動状況を知らせるフィードバックの提供が [!DNL Target] 能です。

![ヘルプ](/help/main/c-intro/assets/help.png)

## 通知とお知らせ {#notifications-announcements}

[!UICONTROL Notifications] と [!UICONTROL Announcements] のパネルを使用すると、[!DNL Adobe Target] のすべてに関する最新情報を入手できます。 プロアクティブ通知は、ソリューションと [!DNL Target] イベントのステータス [!DNL Adobe Experience Cloud] 常に把握するのに役立ちます。 プロアクティブ通知では、停止イベントおよびメンテナンスイベントを警告します。

ヘッダーのベルアイコンをクリックして、通知を表示します。

![ 通知とお知らせのベルのアイコン ](assets/bell-icon.png)

パネルには、[!UICONTROL Notifications] と [!UICONTROL Announcements] のタブが含まれています。

![ 通知 ](assets/notifications.png)

次の節では、各タブの情報と、通知とお知らせの設定方法について説明します。

### 通知 {#notifications}

イベント通知に [!DNL Target]、次のものが含まれます。

* **アクティビティ**：手動で、または開始日または終了日に達したことにより、アクティビティが承認または無効化されたときの、すべてのアクティビティタイプに関する通知。 通知には、アクティビティの名前と、アクティビティの概要ページへのリンクが含まれます。

  通知は設定可能で、デフォルトでは、製品管理者、発行者および承認者によって、アクティビティのワークスペースの [!DNL Target Premium] アカウントに対して受信されます。 [!DNL Target Standard] アカウントの場合、すべての発行者と承認者が通知を受信します。

  通知は、次のサンプルのような形式になっています。

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **プロファイルスクリプト**：プロファイルスクリプトが手動または [!DNL Target] によってアクティブ化または非アクティブ化されたときの通知。

  通知は設定可能で、デフォルトでは、製品管理者と承認者が [!DNL Target Premium] アカウントと [!DNL Target Standard] アカウントの両方で受信します。

  通知は、次のサンプルのような形式になっています。

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Recommendations フィード**:[!DNL Recommendations] フィードが手動または [!DNL Target] によってアクティブ化または非アクティブ化されたときの通知。 [!DNL Recommendations] フィードが失敗した場合にも通知が送信されます。

  通知は設定可能で、デフォルトでは、[!DNL Target Premium] アカウントの製品管理者と承認者が受信します。 [!DNL Recommendations] は [!DNL Target Premium] の機能であり、[!DNL Target Standard] では使用できません。

  通知は、次のサンプルのような形式になっています。

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed`
   * `Feed {target.feed.name} has failed to import from source`

目的の通知にカーソルを合わせてチェックマークをクリックすると、個々の通知を既読としてマークできます。 パネルの下部にある「[!UICONTROL "Mark as Read"]」または「[!UICONTROL "View All"]」をクリックして、すべての通知を読み取り済みまたは表示することができます。

通知の上にマウスポインターを置き、「[!UICONTROL Remind me]」アイコンをクリックしてから、通知を受け取るタイミング（5 分、15 分、1 時間、明日）を選択することで、リマインダーに再び通知を送信するように設定することもできます。

### 発表

プロアクティブ通知では、停止イベントおよびメンテナンスイベントを警告します。

詳しくは、[Adobeのステータス ](https://status.adobe.com/ja) ページを参照してください。

### 通知とお知らせの設定

通知の環境設定を編集するには：

1. 歯車アイコン、「**[!UICONTROL Notifications]**」の順にクリックします。
1. [**[!UICONTROL Target]**] で、[**[!UICONTROL Customize]**] をクリックします。
1. 通知を受信するカテゴリを選択または選択解除します。

   * リクエスト：オブジェクトの承認リクエストまたはオブジェクトへのアクセス権の付与リクエストが送信された場合。 このカテゴリの登録を解除することはできません。
   * 自分に割り当て：誰かがあなたにオブジェクトを割り当てたとき。
   * メンション：誰かがコメントであなたにメンションを行ったとき。
   * 新しいリリース：自分がアクセス権を持っている製品またはサービスに対して新しいリリースが利用可能な場合。
   * 自分と共有：誰かがあなたとオブジェクトを共有したとき。
   * コンテンツの更新：作成またはフォローしたオブジェクトに対して誰かが編集、削除、コメントを加えた場合。
   * その他 :

   >[!NOTE]
   >
   >「新しいリリース」と「コンテンツの更新」は、[!DNL Target] に適用される唯一の通知カテゴリです。 その他のカテゴリは、他のAdobeソリューションにも当てはまります。


1. 優先度が高いと見なすカテゴリを選択します。
1. ブラウザーにアラートを表示する通知を選択します。

   これらのアラートは、ブラウザーの右上隅に数秒間表示されます。 優先度の高いカテゴリ、すべてのカテゴリを表示するか、すべての通知ポップアップを非表示にするかを選択できます。 また、通知を閉じるまで表示しておくかどうかを設定したり、通知期間を設定したりすることもできます。

1. 通知メールの受信頻度を選択します。

   * メールを送信しない
   * インスタント通知
   * デイリーダイジェスト
   * 週刊ダイジェスト

## プロファイル

[!DNL Adobe Experience Cloud] の環境設定を編集したり、[!DNL Target] からサインアウトしたりするには、プロファイルのアバターをクリックします。また、[!DNL Adobe] プロファイルにアクセスや編集することもできます。

![プロファイルアバター](/help/main/c-intro/assets/change-language.png)

次に、[!DNL Target] ヘッダーの左側のタブについて説明します。

## アクティビティ

**[!UICONTROL Activities]** リストは、[!DNL Target] を開いたときのデフォルトのビューです。 このページからアクティビティを作成し、既存のアクティビティを管理できます。

![アクティビティリスト](/help/main/c-intro/assets/activities-list.png)

[!DNL Target] で利用可能なアクティビティの種類に関する詳細、およびアクティビティリストのユーザーインターフェイスに関する詳細は、[ アクティ [!UICONTROL Activity] ティ ](/help/main/c-activities/activities.md) を参照してください。

## オーディエンス

「**[!UICONTROL Audiences]**」タブをクリックすると、[!UICONTROL Audiences] リストが表示されます。このリストで、オーディエンスを作成し、既存のオーディエンスを管理できます。

![オーディエンスリスト](/help/main/c-intro/assets/audience-list.png)

オーディエンスは、ターゲット設定されたアクティビティを表示する類似アクティビティ参加者のグループです。 オーディエンスは、新規訪問者、再訪問者、中西部からの再訪問者など、同じ特性を持つ人々のグループです。[!UICONTROL Audience] 機能を使用すると、様々なコンテンツやエクスペリエンスを特定のオーディエンスにターゲット設定することで、的確なメッセージを最適な対象者にタイミングよく表示し、デジタルマーケティングを最適化できます。 訪問者がターゲットオーディエンスに当てはまる場合は、[!DNL Target] により、アクティビティ作成時に定義された条件に基づいて、そのユーザーに表示するエクスペリエンスが決定されます。

[!DNL Target] のオーディエンスタイプに関する詳細およびオーディエンスリストのユーザーインターフェイスに関する詳細は、[ オーディ [!UICONTROL Audience] ンスの作成 ](/help/main/c-target/c-audiences/create-audience.md) を参照してください。

## オファー

「**[!UICONTROL Offers]**」タブをクリックして [!UICONTROL Offers] リストを表示します。このリストで、エクスペリエンスやオファーを作成し、既存のエクスペリエンスやオファーを管理できます。

![オファーリスト](/help/main/c-intro/assets/offers.png)

エクスペリエンスは、オファー、画像、テキスト、ボタン、ビデオ、ページ上のこれらの様々な要素の組み合わせ、Web ページ全体、購入ファネルやその他のページの論理的シーケンスを形成するページのセットである可能性があります。また、音声アシスタント応答、カスタマーサービスのスクリプト、自動販売機のパーソナライズされたフレーバーであることもあります。[!DNL Target] アクティビティのエクスペリエンスをテストまたはパーソナライズします。

[!DNL Target] のオファータイプに関する詳細およびオファーリストのユーザーインターフェイスに関する詳細は、[ オフ [!UICONTROL Offer] ー ](/help/main/c-experiences/c-manage-content/manage-content.md) を参照してください。

## レコメンデーション

「**[!UICONTROL Recommendations]**」タブをクリックしてアクセス [!DNL Target Recommendations] ます。

>[!NOTE]
>
>Recommendations アクティビティは、 [!DNL Target Premium] ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。詳細情報は、*ターゲットの紹介*&#x200B;の [Target Premium](/help/main/c-intro/intro.md#premium) を参照してください。

![Recommendations](/help/main/c-intro/assets/recommendations.png)

[!UICONTROL Recommendations] のアクティビティは、以前のユーザーアクティビティまたはその他のアルゴリズムを基にして、顧客が興味を持つ可能性のある製品またはコンテンツを自動的に表示します。 Recommendations を使うと、顧客が知らなかったであろう関連商品を紹介するのに役立ちます。

[!DNL Target] での [!UICONTROL Recommendations] の詳細および [!UICONTROL Recommendations] ユーザーインターフェイスの詳細については、[Recommendations](/help/main/c-recommendations/recommendations.md) を参照してください。

## 管理

「**[!UICONTROL Administration]**」タブをクリックして、[!UICONTROL Administration] ページにアクセスします。

![管理ページ](/help/main/c-intro/assets/administration.png)

[!UICONTROL Administration] のページでは、[!UICONTROL Visual Experience Composer] （VEC）、レポート、[!DNL Scene7] 設定、実装、ホスト、環境、応答トークン、ユーザーの設定を含む [!DNL Target] ータを管理できます。

詳細およびユーザーインターフェイスについては、[Target の管理の概要](/help/main/administrating-target/administrating-target.md)を参照してください。
