---
keywords: 変数、プロファイル、パラメーター、組み込みプロファイル、メソッド、url変数、地域プロファイル、サードパーティプロファイル、mbox変数、campaign変数、顧客属性
description: Adobe Targetのプロファイルスクリプトで役立つ様々なプロファイル、変数、パラメーターのリストを表示します。
title: ' [!DNL Target] で使用されるプロファイル、変数、パラメーターはどれですか？'
feature: Audiences
exl-id: 96ef9a56-fe76-428e-a164-c01829fdf45d
source-git-commit: e45ac15a60c83e35b8b2b2ba29a42727faf746df
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 67%

---

# プロファイルと変数の用語集

このページには、プロファイルスクリプトで役立つプロファイル、変数およびパラメーターの一覧を記載しています。

## ビルトインプロファイル {#section_2B694370003C4F8E8E29E0B2F6E52045}

| プロファイル | メモ |
|--- |--- |
| user. activeActivationesUser<br>. activeCampaigns | 現在のセッションでユーザーがキャンペーン／アクティビティでインタラクションをおこなっていなくても、ユーザーがいるすべてのキャンペーン／アクティビティのキャンペーン ID を返します。 |
| user.pcId |  |
| user.sessionId |  |
| user.categoryAffinity |  |
| user.categoryAffinities | 訪問者が入力した親和性の配列を返します。 |
| user.isFirstSession |  |
| user.isNewSession |  |
| user.daysSinceLastVisit |  |
| user.browser | ユーザーエージェント |
| user.browserType | ブラウザーのタイプ（safari、chrome など）を返します。 |
| user.header | すべての `user.header` プロファイルは、mbox リクエストヘッダーデータからビルトインされます |
| user.header （&#39;x-forwarded-for&#39;） | 訪問者がいるネットワーク接続の公開される IP アドレス。<br> これは、いくつかの方法で取得できます。例えば、[whatismyip.com](https://www.whatismyip.com/)。 IP アドレスは、10.、192.168. または 172 から始まる NAT アドレス（内部アドレス）ではありません。<br> メモ：user.header （&#39;x-cluster-client-ip&#39;）は非推奨（廃止予定）となりました。 |
| user.header(&#39;host&#39;) | Web サイトのホスト名 |
| user.header(&#39;cookie&#39;) | 訪問者の cookie データ |
| user.header(&#39;user-agent&#39;) | 訪問者のブラウザーのユーザーエージェント |
| user.header(&#39;accept-language&#39;) | 訪問者の言語 |
| user.header(&#39;accept-encoding&#39;) | 訪問者の文字エンコード |
| user.header(&#39;accept&#39;) | 訪問者の言語および文字エンコード |
| user.header(&#39;connection&#39;) | サーバー接続。例：keep-live |
| user.header(&#39;referrer&#39;) | 訪問者の現在のページの Web サイト URL。Internet Explorer では動作しません。 |
| user.getLocal （&#39;param_name&#39;）; | `user.setLocal` を使用して設定した値を取得します。 |
| user.setLocal （&#39;param_name&#39;,&#39;value&#39;） | プロファイルスクリプト内に、永続的なプロファイル値を作成します。 これらの値は、プロファイルスクリプトと同様に保持されますが、設定されたスクリプト内でのみアクセスできます。 |
| user.get(&#39;param_name&#39;) |  |
| user.parameter | プロファイルスクリプトから作成されたプロファイル属性を保持します。また、位置情報、訪問回数などの「システム」プロファイルも参照します。 |
| profile.get(&#39;param_name&#39;) | プロファイルスクリプトで使用するプロファイルパラメーターを取得する正しい方法は、profile.get （&#39;param_name&#39;） メソッドです。 |
| profile.param(&#39;param_name&#39;); |  |
| profile.parameter(&#39;parameter_name&#39;); | profile.  接頭辞. |
| profile.browserTime | 訪問者のブラウザーのローカル時間。システム時間については、プロファイルスクリプトで新しい日付オブジェクトを作成します。 |
| profile.averageDaysBetweenVisits |  |
| profile.sessionCount |  |
| profile.mobile.isTablet | 訪問者デバイスはタブレットです。<P>**メモ**：このプロファイルは、非推奨（廃止予定）の従来のブラウザーであるiPad オーディエンスカテゴリに代わるものです。 詳しくは、[&#x200B; ブラウザー &#x200B;](/help/main/c-target/c-audiences/c-target-rules/browser.md#profile-scripts) を参照してください。 |
| profile.mobile.isMobilePhone | 訪問者デバイスは携帯電話です。<P>**メモ**：このプロファイルは、非推奨（廃止予定）の従来のブラウザーであるiPhone オーディエンスカテゴリに代わるものです。 詳しくは、[&#x200B; ブラウザー &#x200B;](/help/main/c-target/c-audiences/c-target-rules/browser.md#profile-scripts) を参照してください。 |
| parameter= | mbox に渡された追加の値を示す一般的な用語で、通常は名前と値のペアです。`profile.parameter` か `user.parameter` を使用しない限り、永続的ではありません。 |

## URL 変数 {#section_8F25958273164EBAA6DC659302993FD3}

| `landing` | `referrer` | `page` |
|---|---|---|
| `landing.url` | `referrer.url` | `page.url` |
| `landing.domain` | `referrer.domain` | `page.domain` |
| `landing.protocol` | `referrer.protocol` | `page.protocol` |
| `landing.param` | `referrer.param` | `page.param` |
| `landing.query` | `referrer.query` | `page.query` |

## 地域および携帯電話会社のプロファイル {#section_08441DA42E7346918FBB345818854997}

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`
* `profile.geolocation.latitude`
* `profile.geolocation.longitude`

## mbox 変数 {#section_C42F0D33BD8044BE812FA0B7905CC0ED}

| 変数 | メモ |
|--- |--- |
| `mbox.name` |  |
| mbox.param(&#39;param_name&#39;) |  |
| リクエストごとに自動的に渡されるパラメーター：<ul><li>mbox.param(&#39;browserHeight&#39;)</li><li>mbox.param(&#39;browserTimeOffset&#39;)</li><li>mbox.param(&#39;browserWidth&#39;)</li><li>mbox.param(&#39;colorDepth&#39;)</li><li>mbox.param(&#39;mboxXDomain&#39;)</li><li>mbox.param(&#39;mboxTime&#39;)</li><li>mbox.param(&#39;screenHeight&#39;)</li><li>mbox.param(&#39;screenWidth&#39;)</li></ul> |  |
| 発注 mbox と共に渡されるパラメーター：<ul><li>mbox.param(&#39;orderId&#39;)</li><li>mbox.param(&#39;orderTotal&#39;)</li><li>mbox.param(&#39;productPurchasedId&#39;)</li></ul> |  |
| mbox3rdPartyId | 顧客 ID と Target の mboxPCID を同期するための mbox パラメーター。顧客 ID は、CRM ID やメンバーシップ ID など、会社が訪問者を追跡するために使用する ID です。その後、この ID を使用して、プロファイル API や [&#x200B; 顧客属性 &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/customer-attributes.html?lang=ja){target=_blank} 経由で情報を追加できます。 |
| mboxPageValue | mbox の呼び出しごとに、ページに値が割り当てられます。 |
| mboxDebug | デバッグ情報にのみ使用されます。at.js が検索するページ URL にを追加しました。 |
| mboxOverride.browserIp | 実際の場所とは異なる地域を設定して、別の場所でどのように表示されるかをテストできます。<br>**注意：** mboxOverride パラメーターは、アクティビティをテストするときにのみ使用し、実稼動環境で使用しないでください。任意のmboxOverrideパラメーターを使用すると、Analytics for [Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用する際にレポートの相違が生じる可能性があります。アクティビティをテスト中に [アクティビティQAモード](/help/main/c-activities/c-activity-qa/activity-qa.md) を使用して、アクティビティが本番環境にプッシュされる前に期待どおりに動作することを確認してください。 |

## 顧客属性 {#section_62B4821EB6564FF4A14159A837AD4EDB}

顧客属性は、プロファイルスクリプトで参照でき、形式 `crs.get('<Datasource Name>.<Attribute name>')`　設定されています。

この属性は、プロファイルスクリプトでトークンとして、また、プロファイルスクリプトを使用せずにオファー内で直接使用可能になりました。トークンは、`${crs.datasourceName.attributeName}` の形式である必要があります。 `datasourceName` のスペースは、すべての API 呼び出しから削除する必要があります。
