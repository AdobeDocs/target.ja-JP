---
keywords: target ユーザーインターフェイス；ユーザーインターフェイス；ui；お知らせ；イベント；通知
description: ユーザーインターフェイスに慣れ、 [!DNL Target] を最大限に活用するための詳細情報へのリンクを見つけます。
title: ' [!DNL Target] UI の使用方法'
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: df0a0aea7348bfde9114399fd6c1131b740f3c24
workflow-type: tm+mt
source-wordcount: '1463'
ht-degree: 22%

---

# [!DNL Target] UI について

ユーザーインターフェイスは、[!DNL Adobe Target] を最大限に活用できるよう、論理的かつユーザーにわかりやすい形式で配置されています。以下の概要は、[!DNL Target] に慣れるのに役立ち、より詳細な情報と手順を説明するリンクを提供します。

>[!NOTE]
>
>2025 の新機能で、[!DNL Target] は更新された UI と [!UICONTROL Visual Experience Composer] （VEC）を導入しています。 詳しくは、次のリンクをクリックしてください。
>
>* [[!DNL Target Standard/Premium] 25.2.1 （2025 年 2 月 17 日（PT））リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2):[!UICONTROL Activities]、[!UICONTROL Recommendations] および [!UICONTROL Visual Experience Composer] （VEC）の [!DNL Target] の主な UI の変更点の概要を説明します。
>
>* [[!DNL Target Standard/Premium] 25.1.1 （2025 年 1 月 9 日（PT））リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1):[!UICONTROL Offers Library] の [!DNL Target] での主な UI の変更点の概要を説明します。
>
>* [ [!DNL Target] UI について ](/help/main/c-intro/understand-the-target-ui.md):[!DNL Target] に慣れるのに役立つ概要と、より詳細な情報と手順を説明するリンクを提供します。
>
>* [[!UICONTROL Visual Experience Composer] の変更点 ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1 リリース（2015 年 2 月 17 日（PT））では、更新された [!UICONTROL Visual Experience Composer] （VEC）が導入されています。 この記事では、VEC のレガシーバージョンと更新バージョンの違いについて説明します。
>
>* [[!UICONTROL Visual Experience Composer] options](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：この記事では、更新された VEC UI とそのオプションについて説明します。

## [!DNL Target] UI ヘッダー

[!DNL Target] UI の上部のヘッダーには、ソリューションの様々な機能を移動するのに役立つタブとオプションが含まれています。 また、組織や [!DNL Adobe Experience Cloud] ソリューションの切り替え、Beta プログラムに参加している場合のフィードバックの提供、AI アシスタントへのアクセス、ヘルプと通知の受け取り、[!DNL Adobe] プロファイルの管理、[!DNL Target] からのログアウトを行うこともできます。

![Target ヘッダー](/help/main/c-intro/assets/target-header.png)

左側のタブを使って [!DNL Target] の様々な機能にアクセスできます。これについては後ほど説明します。 タブについて説明する前に、まず、右側のオプションについて説明します。

### [!UICONTROL Organization]

*組織*&#x200B;とは、管理者がグループおよびユーザーを設定し、[!DNL Adobe Experience Cloud] でのシングルサインオンを制御するために使用するエンティティです。組織は、すべての [!DNL Experience Cloud] 製品およびソリューションをまたいだログイン会社のように機能します。ほとんどの場合、組織は、会社名です。ただし、会社は多数の組織を持つことができます。

会社に複数の組織がある場合は、[!UICONTROL Organization] のドロップダウンリストから目的の組織を選択します。

![組織ドロップダウンリスト](/help/main/c-intro/assets/organizations.png)

### [!UICONTROL Beta Feedback]

（条件付き） [!DNL Target] Betaの公式プログラムに参加している場合は、「[!UICONTROL Beta Feedback]」アイコンが表示される場合があります。

![Beta フィードバックアイコン ](/help/main/c-intro/assets/beta-feedback.png)

フィードバックの説明を入力し、該当するファイルやスクリーンショット、必要に応じて追加の詳細を含めて、「**[!UICONTROL Submit]**」をクリックします。

### [!DNL AI Assistant]

（条件付き） [!DNL AI Assistant] を使用する権限が組織から付与されている場合は、「[!DNL AI Assistant]」アイコンをクリックします。

詳しくは、[Adobe Experience Platform AI アシスタントの概要 ](/help/main/c-intro/ai-assistant.md) を参照してください。

### ヘルプ

[!UICONTROL Help] アイコン（![ ヘルプアイコン ](/help/main/assets/icons/HelpOutline.svg)）をクリックすると、[!DNL Target] をより効果的に使用するために、情報、ビデオ、ブログなどにアクセスできます。 サポートチケットの作成、サポート用電話番号の検索、Twitter での質問、[!DNL Target] に関するフィードバックの提供により、[!DNL Target] チームの活動状況を把握できます。

![ヘルプ](/help/main/c-intro/assets/help.png)

### リクエスト、通知、お知らせ {#notifications-announcements}

[!UICONTROL Requests]、[!UICONTROL Notifications]、[!UICONTROL Announcements] の各パネルを使用すると、[!DNL Adobe Target] のすべてに関する最新情報を入手できます。 プロアクティブ通知は、ソリューションと [!DNL Target] イベントのステータス [!DNL Adobe Experience Cloud] 常に把握するのに役立ちます。 プロアクティブ通知では、停止イベントおよびメンテナンスイベントを警告します。

ヘッダーの [!UICONTROL Notifications] アイコン（![ 通知アイコン ](/help/main/assets/icons/Bell.svg)）をクリックして、通知を表示します。

パネルには、[!UICONTROL Requests]、[!UICONTROL Notifications] および [!UICONTROL Announcements] のタブが含まれています。

![ 通知 ](assets/notifications.png)

次の節では、各タブの情報と、通知とお知らせの設定方法について説明します。

#### [!UICONTROL Requests]

製品とソリューション、他のユーザーとのコラボレーション、その他の関連する更新に関する重要な情報を [!UICONTROL Requests] のパネルで受け取ることがで [!DNL Adobe] ます。

オブジェクトの承認リクエストまたはオブジェクトへのアクセス権の付与リクエストが送信されると、そのリクエストが [!UICONTROL Requests] のパネルに表示されます。

#### 通知 {#notifications}

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

個々の通知を読み取り済みとしてマークするには、目的の通知にカーソルを合わせて [!UICONTROL Mark as Read] ールアイコン（![ 読み取りとしてマーク ](/help/main/assets/icons/CheckmarkCircle.svg) アイコン（）をクリックします。 パネルの下部にある「[!UICONTROL Mark as Read]」または「[!UICONTROL View All]」をクリックして、すべての通知を読み取り済みまたは表示することができます。

通知の上にマウスポインターを置き、通知アイコン（![ 再通知アイコン ](/help/main/assets/icons/Clock.svg)）をクリックすると、リマインダーが再度 [!UICONTROL Snooze] 信されるように設定することもできます。 通知を受信する時間を、5 分、15 分、1 時間または明日から選択できます。

#### 発表

プロアクティブ通知では、停止イベントおよびメンテナンスイベントを警告します。

詳しくは、[Adobeのステータス ](https://status.adobe.com/ja) ページを参照してください。

### 通知とお知らせの設定

通知の環境設定を編集するには：

1. [!UICONTROL Edit Preferences] （環境設定を編集アイコン ![ アイコンをクリックし ](/help/main/assets/icons/Setting.svg) 左パネルで「**[!UICONTROL Notifications]**」をクリックします。
1. 「**[!UICONTROL Target]**」で、通知方法を選択します。

   * [!UICONTROL In-app]
   * [!UICONTROL Email]
   * [!DNL Slack]

1. 優先度が高いと見なすカテゴリを選択します。

   >[!NOTE]
   >
   >[!DNL Target] に適用される通知カテゴリは&quot;[!UICONTROL New releases]&quot;と&quot;[!UICONTROL Updates on content]&quot;のみです。 その他のカテゴリは、他の [!DNL Adobe] ソリューションに適用されます。

1. ブラウザーにアラートを表示する通知を選択します。

   これらのアラートは、ブラウザーの右上隅に数秒間表示されます。 優先度の高いカテゴリ、すべてのカテゴリを表示するか、すべての通知ポップアップを非表示にするかを選択できます。 また、通知を閉じるまで表示しておくかどうかを設定したり、通知期間を設定したりすることもできます。

1. 通知メールの受信頻度を選択します。

   * [!UICONTROL Don't send emails]
   * [!UICONTROL Instant notifications]
   * [!UICONTROL Daily digest]
   * [!UICONTROL Weekly digest]

1. ワークスペース用のSlack通知を設定します。

### アプリ切り替えツール

アプリ切り替えボタンをクリックすると、自分がアクセス権を持っている [!DNL Adobe Experience Cloud] ソリューションにすばやくアクセスできます。

![アプリ切り替えツール](/help/main/c-intro/assets/apps.png)

### プロファイル

[!DNL Adobe Experience Cloud] の環境設定を編集したり、[!DNL Target] からサインアウトしたりするには、プロファイルのアバターをクリックします。また、[!DNL Adobe] プロファイルにアクセスや編集することもできます。

![プロファイルアバター](/help/main/c-intro/assets/change-language.png)

次に、[!DNL Target] ヘッダーの左側のタブについて説明します。

## アクティビティ

**[!UICONTROL Activities]** リストは、[!DNL Target] を開いたときのデフォルトのビューです。 このページからアクティビティを作成し、既存のアクティビティを管理できます。

[!DNL Target] で利用可能なアクティビティの種類に関する詳細、およびアクティビティリストのユーザーインターフェイスに関する詳細は、[ アクティ [!UICONTROL Activity] ティ ](/help/main/c-activities/activities.md) を参照してください。

## オーディエンス

「**[!UICONTROL Audiences]**」タブをクリックすると、[!UICONTROL Audiences] リストが表示されます。このリストで、オーディエンスを作成し、既存のオーディエンスを管理できます。

オーディエンスは、ターゲット設定されたアクティビティを表示する類似アクティビティ参加者のグループです。 オーディエンスは、新規訪問者、再訪問者、中西部からの再訪問者など、同じ特性を持つ人々のグループです。 [!UICONTROL Audience] 機能を使用すると、様々なコンテンツやエクスペリエンスを特定のオーディエンスにターゲット設定することで、的確なメッセージを最適な対象者にタイミングよく表示し、デジタルマーケティングを最適化できます。 訪問者がターゲットオーディエンスに当てはまる場合は、[!DNL Target] により、アクティビティ作成時に定義された条件に基づいて、そのユーザーに表示するエクスペリエンスが決定されます。

[!DNL Target] のオーディエンスタイプに関する詳細およびオーディエンスリストのユーザーインターフェイスに関する詳細は、[ オーディ [!UICONTROL Audience] ンスの作成 ](/help/main/c-target/c-audiences/create-audience.md) を参照してください。

## オファー

「**[!UICONTROL Offers]**」タブをクリックして [!UICONTROL Offers] リストを表示します。このリストで、エクスペリエンスやオファーを作成し、既存のエクスペリエンスやオファーを管理できます。

エクスペリエンスは、オファー、画像、テキスト、ボタン、ビデオ、ページ上のこれらの様々な要素の組み合わせ、Web ページ全体、購入ファネルやその他のページの論理的シーケンスを形成するページのセットである可能性があります。また、音声アシスタント応答、カスタマーサービスのスクリプト、自動販売機のパーソナライズされたフレーバーであることもあります。[!DNL Target] アクティビティのエクスペリエンスをテストまたはパーソナライズします。

[!DNL Target] のオファータイプに関する詳細およびオファーリストのユーザーインターフェイスに関する詳細は、[ オフ [!UICONTROL Offer] ー ](/help/main/c-experiences/c-manage-content/manage-content.md) を参照してください。

## レコメンデーション

「**[!UICONTROL Recommendations]**」タブをクリックしてアクセス [!DNL Target Recommendations] ます。

>[!NOTE]
>
>[!UICONTROL Recommendations] アクティビティは、 [!DNL Target Premium] ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では、[!UICONTROL Recommendations] のアクティビティは使用できません。 詳細情報は、*ターゲットの紹介*&#x200B;の [Target Premium](/help/main/c-intro/intro.md#premium) を参照してください。

[!UICONTROL Recommendations] のアクティビティは、以前のユーザーアクティビティまたはその他のアルゴリズムを基にして、顧客が興味を持つ可能性のある製品またはコンテンツを自動的に表示します。 Recommendations を使うと、顧客が知らなかったであろう関連商品を紹介するのに役立ちます。

[!DNL Target] での [!UICONTROL Recommendations] の詳細および [!UICONTROL Recommendations] ユーザーインターフェイスの詳細については、[Recommendations](/help/main/c-recommendations/recommendations.md) を参照してください。

## 管理

「**[!UICONTROL Administration]**」タブをクリックして、[!UICONTROL Administration] ページにアクセスします。

[!UICONTROL Administration] のページでは、[!UICONTROL Visual Experience Composer] （VEC）、レポート、[!DNL Scene7] 設定、実装、ホスト、環境、応答トークン、ユーザー、推奨事項の設定などの [!DNL Target] ータを管理できます。

詳細およびユーザーインターフェイスについては、[Target の管理の概要](/help/main/administrating-target/administrating-target.md)を参照してください。

## Visual Experience Composer（VEC）

[!DNL Target] の UI に加えて、VEC UI についても熟知しておく必要があります。 詳しくは、[[!DNL Visual Experience Composer] options](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) を参照してください。
