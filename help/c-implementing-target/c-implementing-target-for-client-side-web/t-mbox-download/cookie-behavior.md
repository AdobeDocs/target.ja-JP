---
keywords: 概要とリファレンス;webkit
description: Adobe Targetのレガシーmbox.js実装について説明します。 Adobe Experience PlatformWeb SDK(AEP Web SDK)またはat.jsの最新バージョンに移行します。
title: mbox.jsのCookieに関する情報はどこで入手できますか。
feature: at.js
role: Developer
exl-id: 1c4e5b0b-8ae4-4526-aea0-318a33f4d247
translation-type: tm+mt
source-git-commit: 0a685427a047bfc0a2f5e81525b32df70af6d69f
workflow-type: tm+mt
source-wordcount: '1654'
ht-degree: 92%

---

# mbox.js の Cookie{#mbox-js-cookies}

Cookie の動作は、その Cookie がファーストパーティ Cookie であるか、ファーストパーティ Cookie を伴うサードパーティ Cookie であるか、サードパーティ Cookie のみであるかによって異なります。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリをサポートし [!DNL Adobe Target] なくなりました。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。
>
>サイトに発生する可能性のある問題を回避するため、すべてのお客様に、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに今日までに移行することをお勧めします。 詳しくは、[概要：クライアント側web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)のターゲットを実装します。

>[!NOTE]
>
>このトピックには、`mboxSession` および `mboxPC` に関する情報が含まれています。実装に関するアドビのベストプラクティスでは、Cookie データ（`mboxSession` または `mboxPC`）に機密情報をリンクしたり格納したりしないことが推奨されています。

「[ターゲットcookie](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cookie-deleting.md)の削除」も参照してください。

## ファーストパーティ Cookie またはサードパーティ Cookie を使用するタイミング {#section_F71B29420C004A7FA3B1921E619B326E}

サイトの設定によって、どの Cookie を使用するかが決まります。ファーストパーティ Cookie およびサードパーティ Cookie を理解するには、Target の仕組みを理解することが役立ちます。詳しくは、[Adobe Target の仕組み](/help/c-intro/how-target-works.md#concept_459AB4DEE7364A9290C2FD405DC29584)を参照してください。

Cookie について、3 つの主要な使用例を次に示します。

1. 1 つのドメインの場合。

   すべてのテストは、1 つのトップレベルドメイン（[!DNL `www.domain.com`]、[!DNL store.domain.com]、[!DNL anysub.domain.com]、など）内で実施します。

   方法：ファーストパーティ Cookie だけを使用します。これはデフォルトの設定です。

1. ユーザーが異なるドメインにアクセスし、それらのドメイン間における行動を追跡し、テストする場合。

   例：買い物をするためにお客様のサイトにアクセスしたユーザーが、Yahoo ストアを経由してチェックアウトする場合。次の 3 つの方法があります（最適な方法を決めるには、アカウント担当者に相談してください）。

   * ファーストパーティ Cookie およびサードパーティ Cookie を有効にする。
   * サードパーティ Cookie のみを有効にする（ほとんど利用されませんが、ドメイン外に mbox の Cookie を保持できるという利点があります）。
   * ファーストパーティ Cookie のみを有効にし、異なるドメインにアクセスするときに `mboxSession` パラメーターを渡す。

      `mboxSession` パラメーターは、[!DNL mbox.js] を参照しているランディングページに渡す必要があります。中間のリダイレクターページにすることはできません。

1. サードパーティサイトで adbox または flashbox のみを使用している場合。

   次の 2 つの方法があります（最適な方法を決めるには、クライアントサービスマネージャーに相談してください）。

   * ファーストパーティ Cookie およびサードパーティ Cookie を有効にする。

      ファーストパーティ Cookie およびサードパーティ Cookie は、flashbox と動的クリエイティブで必要になります。
   * サードパーティ Cookie のみを有効にする。

      この方法は、adbox の実装がオンサイトのターゲット化なしで使用されている場合にのみ適していますが、こうしたケースはまれです。

## ファーストパーティ Cookie の動作 {#section_CE6313D979EA4D0897D2F661E7A8AFA7}

ファーストパーティ Cookie は [!DNL clientdomain.com] に保存されます。ここでは、`clientdomain` がお客様のドメインになります。

[!DNL Mbox.js] によって `mboxSession ID` が生成され、mbox の Cookie に保存されます。最初の mbox の応答にはオファーが含まれています。また、アプリケーションによって生成された `mboxPC ID` を mbox の Cookie に保存するための JavaScript も含まれています。

>[!NOTE]
>
>[!DNL AMCV_###@AdobeOrg] ファーストパーティ Cookie には、Experience Cloud 訪問者 ID が常に設定されます。

## サードパーティ Cookie の動作 {#section_4C3A83990BF8415BB1806602D84AED48}

サードパーティ Cookie は [!DNL clientcode.tt.omtrdc.net] に保存され、ファーストパーティ Cookie は [!DNL clientdomain.com] に保存されます。ここでは、`clientdomain` がお客様のドメインになります。

[!DNL Mbox.js] によって `mboxSession ID` が生成されます。最初の場所のリクエストは、HTTP 応答ヘッダーを返します。このヘッダーによって、`mboxSession` および `mboxPC` という名前のサードパーティ Cookie の設定が試行され、リダイレクトリクエストが追加のパラメーター（`mboxXDomainCheck=true`）と共に戻されます。

ブラウザーがサードパーティ Cookie を受け入れる場合、リダイレクトリクエストにはそれらの Cookie が含まれており、オファーが返されます。

ブラウザーがサードパーティ Cookie を拒否する場合、リダイレクトリクエストにはそれらの Cookie が含まれておらず、ページのすべての場所についてデフォルトのコンテンツが表示されます。Cookie が設定されていないので、すべてのページリクエストに対して、これと同じ処理がおこなわれます。

>[!NOTE]
>
>サードパーティ Cookie がブロックされない場合、[!DNL demdex.net] Cookie が設定されます。

## サードパーティ Cookie とファーストパーティ Cookie の動作{#section_F0C9AD8BFDF8457A999C4A07A0F7A981}

サードパーティ Cookie は [!DNL clientcode.tt.omtrdc.net] に保存され、ファーストパーティ Cookie は [!DNL clientdomain.com] に保存されます。ここでは、`clientdomain` がお客様のドメインになります。

[!DNL Mbox.js] によって `mboxSession ID` が生成されます。最初の場所のリクエストは、HTTP 応答ヘッダーを返します。このヘッダーによって、`mboxSession` および `mboxPC` という名前のサードパーティ Cookie の設定が試行され、リダイレクトリクエストが追加のパラメーター（`mboxXDomainCheck=true`）と共に戻されます。

ブラウザーがサードパーティ Cookie を受け入れる場合、リダイレクトリクエストにはそれらの Cookie が含まれており、オファーが返されます。

一部のブラウザーではサードパーティ Cookie が拒否されます。サードパーティ Cookie がブロックされた場合でも、ファーストパーティ Cookie は引き続き動作します。Target でサードパーティ Cookie の設定が試行され、設定できなかった場合は、クライアントの特定のドメインのみが追跡されます。サードパーティ Cookie がブロックされた場合、クロスドメインのリンクに `mboxSession` が追加されていない限り、クロスドメイントラッキングは動作しません。この場合、別のファーストパーティ Cookie が設定され、前のドメインのファーストパーティ Cookie と同期されます。

## Cookie の設定 {#section_B498B8D1A34A444BBF84CC720EE9D87F}

Cookie にはいくつかのデフォルト設定があります。cookie の期間を除き、必要に応じてこれらの設定を変更できます。Cookie の設定を変更する場合は、アカウント担当者にお問い合わせください。

| 設定 | 情報 |
|--- |--- |
| cookie 名 | mbox。 |
| cookie ドメイン | コンテンツを提供するドメインの 2 番目および最上位のレベルです。会社のドメインなので、cookie はファーストパーティ cookie になります。<br>例:  `mycompany.com`. |
| サーバードメイン | `clientcode.tt.omtrdc.net`。アカウントのクライアントコードを使用します。 |
| cookie の期間 | cookie が訪問者のブラウザーに残る期間は、訪問者が最後にログインしてから 2 週間です。cookie の期間は変更できません。 |
| P3P ポリシー | ほとんどのブラウザーのデフォルト設定の要求に従って、cookie は P3P ポリシーに基づいて発行されます。P3P ポリシーはブラウザーに対して、cookie を扱うユーザーおよびその情報の使用方法を指示します。 |

Cookie は、キャンペーンでの訪問者のエクスペリエンスを管理するための様々な値を保持します。

| 値 | 定義 |
|--- |--- |
| session ID | ユーザーセッションの一意の ID。デフォルトでは、30 分間存続します。 |
| pc ID | 訪問者のブラウザーの半永久的な ID。14 日間存続します。 |
| check | 訪問者が cookie をサポートするかどうかを判別するために使用される簡単なテスト値。訪問者がページをリクエストするたびに設定されます。 |
| disable | 訪問者の読み込み時間が mbox.js ファイルで設定されているタイムアウトを超えた場合に設定されます。デフォルトでは、1 時間存続します。 |

## Safari 訪問者の Target に対する Apple WebKit 追跡の変更の影響 {#section_2A2E5730ED7D4A0985C904AFEA310AAE}

**Adobe Target 追跡の仕組み**

| Cookie | 詳細 |
|--- |--- |
| ファーストパーティドメイン | これは、Target のお客様の標準的な実装です。「mbox」Cookie はお客様のドメインで設定されます。 |
| サードパーティ追跡 | サードパーティ追跡は、Target および Adobe Audience Manager（AAM）で広告およびターゲット設定を利用する場合に重要です。サードパーティ追跡には、クロスサイトスクリプティング技法が必要となります。Target では、`clientcode.tt.omtrd.net` ドメインで設定される「mboxSession」と「mboxPC」の 2 つの Cookie を使用します。 |


**Apple のアプローチについて**

Apple の発表内容：

「Intelligent Tracking Prevention は、Cookie およびその他の Web サイトデータを制限してクロスサイト追跡を減らすための WebKit の新機能です。」

「これはクロスサイト追跡と呼ばれ、`example-tracker.com` によって使用される Cookie はサードパーティ Cookie と呼ばれます。当社のテストでは、人気のある Web サイトで 70 を超えるこのようなトラッカーが見つかりました。これらのトラッカーはすべて、認識されることなくユーザーのデータを収集しています。」

| アプローチ | 詳細 |
|--- |--- |
| Intelligent tracking prevention | 詳しくは、WebKit オープンソース Web ブラウザーエンジン Web サイトの [Intelligent Tracking Prevention](https://webkit.org/blog/7675/intelligent-tracking-prevention/) を参照してください。 |
| Cookie | Safari における Cookie の処理方法：<ul><li>ユーザーが直接アクセスするドメインにないサードパーティ Cookie は保存されません。この動作は新しいものではありません。既に Safari ではサードパーティ Cookie はサポートされていません。</li><li>ユーザーが直接アクセスするドメインで設定されたサードパーティ Cookie は、24 時間後に消去されます。</li><li>ファーストパーティドメインがサイトを横断してユーザーを追跡していると分類されている場合、そのファーストパーティ Cookie は 30 日後に削除されます。この問題は、異なるドメインにオンラインでユーザーを送信する大企業で起こる可能性があります。Apple では、これらのドメインがどのように分類されるか、またドメインがサイトを横断してユーザーを追跡していると分類されているかどうかを調べる方法について明確にしていません。</li></ul> |
| 機械学習によるクロスサイトドメインの識別 | Apple の発表内容：<br>機械学習分類子：非公開で管理されるトップドメインがサイトを横断してユーザーを追跡できるかどうかについて、収集された統計情報に基づいて分類するために、機械学習モデルが使用されます。収集された様々な統計情報から、多数の一意のドメインの下位にあるサブリソース、多数の一意のドメインの下位にあるサブフレーム、多数の一意のドメインへのリダイレクト、という 3 つのベクトルが現在の追跡方法に基づく分類に対する強力なシグナルとなることがわかりました。すべてのデータ収集と分類はデバイス上でおこなわれます。<br>ただし、ユーザーが example.com を最上位ドメイン（多くの場合、ファーストパーティドメインと呼ばれます）として操作している場合、Intelligent Tracking Prevention は、これをユーザーが Web サイトに関心を持っているシグナルと見なし、一時的に動作を調整します（次のタイムラインを参照）。<br>ユーザーが example.com を過去 24 時間に操作した場合、その Cookie は `example.com` がサードパーティの場合に使用可能になります。これにより、「Y で X アカウントを使用してサインインする」ログインシナリオが可能になります。<ul><li>トップレベルドメインとして訪問されるドメインは影響を受けません。例えば、OKTA のようなサイト</li><li>複数の一意のドメインを横断する現在のページのサブドメインまたはサブフレームであるドメインを識別します。</li></ul> |

**アドビが受ける影響**

| 影響を受ける機能 | 詳細 |
|--- |--- |
| オプトアウトのサポート | Apple の WebKit 追跡における変更により、オプトアウトのサポートが影響を受けます。<br>Target のオプトアウトでは、`clientcode.tt.omtrdc.net` ドメインの Cookie が使用されます。詳しくは、「[プライバシー](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md)」を参照してください。<br>Target では、次の 2 種類のオプトアウトがサポートされます。<ul><li>クライアントごと（クライアントがオプトアウトリンクを管理します）。</li><li>アドビ経由。すべてのお客様のすべての Target 機能からユーザーをオプトアウトします。</li></ul>どちらの方法でもサードパーティ Cookie が使用されます。 |
| Target アクティビティ | お客様は、Target アカウントの[プロファイルの有効期間](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md)を選択できます（最長 90 日）。問題として、アカウントのプロファイルの有効期間が 30 日を超過し、お客様のドメインがサイトを横断してユーザーを追跡するとマークされているという理由でファーストパーティ Cookie が消去された場合、Target の次の領域で Safari 訪問者に対する動作が影響を受けることが考えられます。<br>**Target レポート**： Safari ユーザーがアクティビティに参加してから 30 日後に戻り、コンバージョンを達成すると、そのユーザーは、2 人の訪問者と 1 つのコンバージョンとしてカウントされます。<br>この動作は、Analytics をレポートソースに使用する（A4T）アクティビティでも同じです。<br>**プロファイルおよびアクティビティメンバーシップ**：<ul><li>プロファイルデータは、ファーストパーティ Cookie の有効期限が切れた時点で消去されます。</li><li>アクティビティメンバーシップは、ファーストパーティ Cookie の有効期限が切れた時点で消去されます。</li><li> サードパーティ Cookie 実装またはファーストパーティおよびサードパーティ Cookie 実装を使用しているアカウントの Safari では、Target は動作しません。この動作は新しいものではありません。Safari では、サードパーティ Cookie を以前から許可していません。</li></ul><br>**提案**：顧客ドメインがセッションを横断して訪問者を追跡しているとマークされているか心配な場合、Target でプロファイルの有効期間を 30 日以下に設定するのが安全です。これにより、ユーザーは Safari と他のすべてのブラウザーで同様に追跡されます。 |
