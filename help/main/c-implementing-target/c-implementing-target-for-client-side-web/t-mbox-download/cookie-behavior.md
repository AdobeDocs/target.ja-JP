---
keywords: 概要とリファレンス；Webkit;Cookie；ファーストパーティ；サードパーティ；ファーストパーティ；サードパーティ
description: 詳細 [!DNL Target] Cookie の動作（ファーストパーティ Cookie、ファーストパーティ Cookie を伴うサードパーティ Cookie、またはサードパーティ Cookie のみ）。
title: 情報の入手先 [!DNL Target] クッキー？
feature: at.js
role: Developer
exl-id: 1c4e5b0b-8ae4-4526-aea0-318a33f4d247
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '1557'
ht-degree: 58%

---

# Target の Cookie

Cookie の動作は、その Cookie がファーストパーティ Cookie であるか、ファーストパーティ Cookie を伴うサードパーティ Cookie であるか、サードパーティ Cookie のみであるかによって異なります。

>[!NOTE]
>
>このトピックには、`mboxSession` および `mboxPC` に関する情報が含まれています。実装のベストプラクティスでは、機密情報を Cookie データにリンクしたり格納したりしないことをお勧めします。 `mboxSession` または `mboxPC`.

関連トピック [Target の Cookie の削除](https://developer.adobe.com/target/before-implement/privacy/cookie-deleting/){target=_blank}。

## ファーストパーティ Cookie またはサードパーティ Cookie を使用するタイミング {#section_F71B29420C004A7FA3B1921E619B326E}

サイトの設定によって、どの Cookie を使用するかが決まります。これは、 [!DNL Target] は、ファーストパーティ Cookie とサードパーティ Cookie を理解しようとするときに機能します。 詳しくは、 [方法 [!DNL Adobe Target] 仕事](/help/main/c-intro/how-target-works.md#concept_459AB4DEE7364A9290C2FD405DC29584) を参照してください。

Cookie について、3 つの主要な使用例を次に示します。

1. 1 つのドメインの場合。

   すべてのテストは、1 つのトップレベルドメイン (`www.domain.com`, `store.domain.com`, `anysub.domain.com`など ) を含める必要があります。

   アプローチ：ファーストパーティ Cookie のみを使用します（デフォルト）。

1. ユーザーが異なるドメインにアクセスし、それらのドメイン間における行動を追跡し、テストする場合。

   例：買い物をするためにお客様のサイトにアクセスしたユーザーが、Yahoo ストアを経由してチェックアウトする場合。次の 3 つの方法があります（最適な方法を決めるには、アカウント担当者に相談してください）。

   * ファーストパーティ Cookie およびサードパーティ Cookie を有効にする。
   * サードパーティ Cookie のみを有効にする（まれにですが、ドメイン外に mbox Cookie を保持できるという利点があります）。
   * ファーストパーティ Cookie のみを有効にし、異なるドメインにアクセスするときに `mboxSession` パラメーターを渡す。

      この `mboxSession` パラメーターは、ランディングページに渡し、JavaScript ライブラリ (Adobe Experience Platform Web SDK または at.js) から参照する必要があります。 中間のリダイレクターページにすることはできません。

1. サードパーティサイトで adbox または flashbox のみを使用している場合。

   次の 2 つの方法があります（最適な方法を決定するには、アカウント担当者にお問い合わせください）。

   * ファーストパーティ Cookie およびサードパーティ Cookie を有効にする。

      ファーストパーティ Cookie およびサードパーティ Cookie は、flashbox と動的クリエイティブで必要になります。

   * サードパーティ Cookie のみを有効にする。

      この方法は、adbox の実装がオンサイトのターゲット化なしで使用されている場合にのみ適していますが、こうしたケースはまれです。

## ファーストパーティ Cookie の動作 {#section_CE6313D979EA4D0897D2F661E7A8AFA7}

ファーストパーティ Cookie は [!DNL clientdomain.com] に保存されます。ここでは、`clientdomain` がお客様のドメインになります。

JavaScript ライブラリは、 `mboxSession ID` そして、 [!DNL Target] cookie. 最初の mbox の応答にはオファーが含まれています。また、 `mboxPC ID` を mbox の Cookie に生成します。

>[!NOTE]
>
>[!DNL AMCV_###@AdobeOrg] ファーストパーティ Cookie は、常に [!DNL Experience Cloud Visitor ID] と共に設定されます。

## サードパーティ Cookie の動作 {#section_4C3A83990BF8415BB1806602D84AED48}

サードパーティ Cookie は [!DNL clientcode.tt.omtrdc.net] に保存され、ファーストパーティ Cookie は [!DNL clientdomain.com] に保存されます。ここでは、`clientdomain` がお客様のドメインになります。

JavaScript ライブラリは、 `mboxSession ID`. 最初の場所のリクエストは、HTTP 応答ヘッダーを返します。このヘッダーによって、`mboxSession` および `mboxPC` という名前のサードパーティ Cookie の設定が試行され、リダイレクトリクエストが追加のパラメーター（`mboxXDomainCheck=true`）と共に戻されます。

ブラウザーがサードパーティ Cookie を受け入れる場合、リダイレクトリクエストにはそれらの Cookie が含まれており、オファーが返されます。

ブラウザーがサードパーティ Cookie を拒否する場合、リダイレクトリクエストにはそれらの Cookie が含まれておらず、ページのすべての場所についてデフォルトのコンテンツが表示されます。Cookie が設定されていないので、すべてのページリクエストに対して、これと同じ処理がおこなわれます。

>[!NOTE]
>
>サードパーティ Cookie がブロックされない場合、[!DNL demdex.net] Cookie が設定されます。

## サードパーティ Cookie とファーストパーティ Cookie の動作 {#section_F0C9AD8BFDF8457A999C4A07A0F7A981}

サードパーティ Cookie は [!DNL clientcode.tt.omtrdc.net] に保存され、ファーストパーティ Cookie は [!DNL clientdomain.com] に保存されます。ここでは、`clientdomain` がお客様のドメインになります。

JavaScript ライブラリは、 `mboxSession ID`. 最初の場所のリクエストは、HTTP 応答ヘッダーを返します。このヘッダーによって、`mboxSession` および `mboxPC` という名前のサードパーティ Cookie の設定が試行され、リダイレクトリクエストが追加のパラメーター（`mboxXDomainCheck=true`）と共に戻されます。

ブラウザーがサードパーティ Cookie を受け入れる場合、リダイレクトリクエストにはそれらの Cookie が含まれており、オファーが返されます。

一部のブラウザーではサードパーティ Cookie が拒否されます。サードパーティ Cookie がブロックされた場合でも、ファーストパーティ Cookie は引き続き動作します。[!DNL Target] でサードパーティ Cookie の設定が試行され、設定できなかった場合、[!DNL Target] はクライアントの特定のドメインのみを追跡できます。サードパーティ Cookie がブロックされた場合、クロスドメイントラッキングは機能しません ( ただし、 `mboxSession` が追加されます。 この場合、別のファーストパーティ Cookie が設定され、前のドメインのファーストパーティ Cookie と同期されます。

## Cookie の設定 {#section_B498B8D1A34A444BBF84CC720EE9D87F}

Cookie にはいくつかのデフォルト設定があります。cookie の期間を除き、必要に応じてこれらの設定を変更できます。 Cookie の設定を変更する場合は、アカウント担当者にお問い合わせください。

| 設定 | 情報 |
|--- |--- |
| cookie 名 | mbox。 |
| cookie ドメイン | コンテンツを提供するドメインの 2 番目および最上位のレベルです。会社のドメインなので、cookie はファーストパーティ cookie になります。<br>例: `mycompany.com`. |
| サーバードメイン | `clientcode.tt.omtrdc.net`。アカウントのクライアントコードを使用します。 |
| cookie の期間 | cookie が訪問者のブラウザーに残る期間は、最後のログインから 2 週間です。 cookie の期間は変更できません。 |
| P3P ポリシー | ほとんどのブラウザーのデフォルト設定の要求に従って、cookie は P3P ポリシーに基づいて発行されます。P3P ポリシーは、Cookie を提供しているブラウザーに対し、その情報の使用方法を示します。 |

cookie には、訪問者がキャンペーンを体験する方法を管理するための様々な値が保持されます。

| 値 | 定義 |
|--- |--- |
| session ID | ユーザーセッションの一意の ID。デフォルトでは、この ID は 30 分間存続します。 |
| pc ID | 訪問者のブラウザーの半永久的な ID。14 日間存続します。 |
| check | 訪問者が cookie をサポートするかどうかを判別するために使用される簡単なテスト値。訪問者がページをリクエストするたびに設定されます。 |
| disable | 訪問者の読み込み時間が JavaScript ライブラリファイルで設定されているタイムアウトを超えた場合に設定されます。 デフォルトでは、この値は 1 時間存続します。 |

## 影響 [!DNL Target] Apple WebKit 追跡の変更による Safari 訪問者の場合 {#section_2A2E5730ED7D4A0985C904AFEA310AAE}

**方法 [!DNL Adobe Target] 追跡作業？**

| Cookie | 詳細 |
|--- |--- |
| ファーストパーティドメイン | の標準実装 [!DNL Target] 顧客。 「mbox」Cookie はお客様のドメインで設定されます。 |
| サードパーティ追跡 | サードパーティ追跡は、 [!DNL Target] および [!DNL Adobe Audience Manager] (AAM)。 サードパーティ追跡には、クロスサイトスクリプティング技法が必要となります。[!DNL Target] では、`clientcode.tt.omtrd.net` ドメインで設定される「mboxSession」と「mboxPC」の 2 つの Cookie を使用します。 |
**Apple のアプローチについて**

Apple の発表内容：

「Intelligent Tracking Prevention は、Cookie およびその他の Web サイトデータを制限してクロスサイト追跡を減らすための WebKit の新機能です。」

「これはクロスサイト追跡と呼ばれ、`example-tracker.com` によって使用される Cookie はサードパーティ Cookie と呼ばれます。当社のテストでは、人気のある Web サイトで 70 を超えるこのようなトラッカーが見つかりました。これらのトラッカーはすべて、認識されることなくユーザーのデータを収集しています。」

| アプローチ | 詳細 |
|--- |--- |
| Intelligent tracking prevention | 詳しくは、WebKit オープンソース Web ブラウザーエンジン Web サイトの [Intelligent Tracking Prevention](https://webkit.org/blog/7675/intelligent-tracking-prevention/) を参照してください。 |
| Cookie | Safari における Cookie の処理方法：<ul><li>ユーザーが直接アクセスするドメインにないサードパーティ Cookie は保存されません。この動作は新しいものではありません。既に Safari ではサードパーティ Cookie はサポートされていません。</li><li>ユーザーが直接アクセスするドメインで設定されたサードパーティ Cookie は、24 時間後に消去されます。</li><li>ファーストパーティドメインがサイトを横断してユーザーを追跡していると分類されている場合、そのファーストパーティ Cookie は 30 日後に削除されます。この問題は、異なるドメインにオンラインでユーザーを送信する大企業で起こる可能性があります。Appleでは、これらのドメインがどのように正確に分類されているか、またはドメインがサイトを横断してユーザーを追跡しているかどうかを判断する方法について明確にしていません。</li></ul> |
| 機械学習によるクロスサイトドメインの識別 | Apple の発表内容：<br>機械学習分類子：機械学習モデルは、非公開で管理されるトップドメインが、収集された統計に基づいて、サイトを横断してユーザーを追跡できるかを分類するために使用されます。 収集された様々な統計情報から、多数の一意のドメインの下位にあるサブリソース、多数の一意のドメインの下位にあるサブフレーム、多数の一意のドメインへのリダイレクト、という 3 つのベクトルが現在の追跡方法に基づく分類に対する強力なシグナルとなることがわかりました。すべてのデータ収集と分類はデバイス上でおこなわれます。<br>ただし、ユーザーが `example.com` トップドメイン（ファーストパーティドメインとも呼ばれる）は、Intelligent Tracking Prevention では、ユーザーが web サイトに興味を持ったことを示すシグナルと見なし、次のタイムラインに示すように動作を一時的に調整します。<br>ユーザーが `example.com` 過去 24 時間、 `example.com` はサードパーティです。 この方法を使用すると、「Y で X アカウントを使用してサインインする」ログインシナリオが可能になります。<ul><li>トップレベルドメインとして訪問されるドメインは影響を受けません。 例えば、OKTA のようなサイト</li><li>複数の一意のドメインを横断する現在のページのサブドメインまたはサブフレームであるドメインを識別します </li></ul> |

**Adobeの影響**

| 影響を受ける機能 | 詳細 |
|--- |--- |
| オプトアウトのサポート | Apple の WebKit 追跡における変更により、オプトアウトのサポートが影響を受けます。<br>[!DNL Target] のオプトアウトでは、`clientcode.tt.omtrdc.net` ドメインの Cookie が使用されます。詳しくは、 [プライバシー](https://developer.adobe.com/target/before-implement/privacy/privacy/){target=_blank}。<br>[!DNL Target] は、次の 2 つのオプトアウトをサポートします。<ul><li>クライアントごと（クライアントがオプトアウトリンクを管理します）。</li><li>1 つの経由 [!DNL Adobe] すべての [!DNL Target] の機能をすべてのお客様に適用できます。</li></ul>どちらの方法でもサードパーティ Cookie が使用されます。 |
| [!DNL Target] アクティビティ | 顧客は、 [プロファイルの有効期間](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) その [!DNL Target] アカウント（最大 90 日）。 お客様のドメインがサイトを横断してユーザーを追跡しているとマークされているので、アカウントのプロファイル有効期間が 30 日を超え、ファーストパーティ cookie が消去されると、Safari 訪問者の行動が [!DNL Target]:<br>**[!DNL Target] レポート&#x200B;**:Safari ユーザーがアクティビティに参加し、30 日後に戻ってコンバージョンをおこなうと、そのユーザーは 2 人の訪問者と 1 つのコンバージョンとしてカウントされます。<br>[!DNL Analytics]この動作は、 をレポートソースに使用する（A4T）アクティビティでも同じです。<br>**&#x200B;プロファイルとアクティビティのメンバーシップ&#x200B;**:<ul><li>プロファイルデータは、ファーストパーティ Cookie の有効期限が切れた時点で消去されます。</li><li>アクティビティメンバーシップは、ファーストパーティ Cookie の有効期限が切れた時点で消去されます。</li><li> [!DNL Target]サードパーティ Cookie 実装またはファーストパーティおよびサードパーティ Cookie 実装を使用しているアカウントの Safari では、 は動作しません。この動作は新しいものではありません。Safari では、しばらくの間、サードパーティ Cookie を許可していません。</li></ul><br>**候補**:顧客ドメインがセッションをまたいで訪問者を追跡しているとマークされる可能性がある問題が発生した場合、でプロファイルの有効期間を 30 日以下に設定するのが安全です。 [!DNL Target]. この制限により、ユーザーは Safari と他のすべてのブラウザーで同様に追跡されます。 |
