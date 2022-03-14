---
keywords: 変数、プロファイル、パラメーター、組み込みプロファイル、メソッド、url変数、地域プロファイル、サードパーティプロファイル、mbox変数、campaign変数、顧客属性
description: Adobe Targetのプロファイルスクリプトで役立つ様々なプロファイル、変数およびパラメーターのリストを表示します。
title: Target で使用されるプロファイル、変数、パラメーターは何ですか？
feature: Audiences
exl-id: 96ef9a56-fe76-428e-a164-c01829fdf45d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 86%

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
| user.header | すべての `user.header` プロファイルは、mbox リクエストヘッダーデータから組み込まれます |
| user.header(&#39;x-forwarded-for&#39;) | 訪問者がいるネットワーク接続の公開される IP アドレス。<br>これは [whatismyip.com](https://www.whatismyip.com/)/など、いくつかの方法で入手できます。IP アドレスは、10.、192.168. または 172 から始まる NAT アドレス（内部アドレス）ではありません。<br>注意：user.header(&#39;x-cluster-client-ip&#39;) は非推奨（廃止予定）となりました。 |
| user.header(&#39;host&#39;) | Web サイトのホスト名 |
| user.header(&#39;cookie&#39;) | 訪問者の cookie データ |
| user.header(&#39;user-agent&#39;) | 訪問者のブラウザーのユーザーエージェント |
| user.header(&#39;accept-language&#39;) | 訪問者の言語 |
| user.header(&#39;accept-encoding&#39;) | 訪問者の文字エンコード |
| user.header(&#39;accept&#39;) | 訪問者の言語および文字エンコード |
| user.header(&#39;connection&#39;) | サーバー接続。例：keep-live |
| user.header(&#39;referrer&#39;) | 訪問者の現在のページの Web サイト URL。Internet Explorer では動作しません。 |
| user.getLocal(&#39;param_name&#39;,&#39;value&#39;); |  |
| user.setLocal(&#39;param_name&#39;,&#39;value&#39;); |  |
| user.get(&#39;param_name&#39;) |  |
| user.parameter | プロファイルスクリプトから作成されたプロファイル属性を保持します。また、ジオロケーションや訪問回数などの「システム」プロファイルも参照します。 |
| profile.get(&#39;param_name&#39;) | プロファイルスクリプトで使用するプロファイルパラメーターを取得する正しい方法は、 profile.get(&#39;param_name&#39;) メソッドです。 |
| profile.param(&#39;param_name&#39;); |  |
| profile.parameter(&#39;parameter_name&#39;); | profile.  prefix. |
| profile.browserTime | 訪問者のブラウザーのローカル時間。システム時間については、プロファイルスクリプトで新しい日付オブジェクトを作成します。 |
| profile.averageDaysBetweenVisits |  |
| profile.sessionCount |  |
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
| リクエストごとに自動的に渡されるパラメーター：<ul><li>mbox.param(&#39;browserHeight&#39;)</li><li>mbox.param(&#39;browserTimeOffset&#39;)</li><li>mbox.param(&#39;browserWidth&#39;)</li><li>mbox.param(&#39;colorDepth&#39;)</li><li>mbox.param(&#39;mboxXDomain&#39;)</li><li>mbox.param(&#39;mboxTime&#39;)</li><li>mbox.param(&#39;screenHeight&#39;)</li><li>mbox.param(&#39;screenWidth&#39;)</li></ul> |
| 発注 mbox と共に渡されるパラメーター：<ul><li>mbox.param(&#39;orderId&#39;)</li><li>mbox.param(&#39;orderTotal&#39;)</li><li>mbox.param(&#39;productPurchasedId&#39;)</li></ul> |
| mbox3rdPartyId | 顧客 ID と Target の mboxPCID を同期するための mbox パラメーター。顧客 ID は、CRM ID やメンバーシップ ID など、会社が訪問者を追跡するために使用する ID です。そのため、この ID は、プロファイル API および[顧客属性](/help/main/c-target/c-visitor-profile/working-with-customer-attributes.md). |
| mboxPageValue | mbox の呼び出しごとに、ページに値が割り当てられます。 |
| mboxDebug | デバッグ情報にのみ使用されます。at.js が探すページ URL に追加されます。 |
| mboxOverride.browserIp | 実際の場所とは異なる地域を設定して、別の場所でどのように表示されるかをテストできます。<br>**注意：** mboxOverride パラメーターは、アクティビティをテストするときにのみ使用し、実稼動環境で使用しないでください。任意のmboxOverrideパラメーターを使用すると、Analytics for [Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用する際にレポートの相違が生じる可能性があります。アクティビティをテスト中に [アクティビティQAモード](/help/main/c-activities/c-activity-qa/activity-qa.md) を使用して、アクティビティが本番環境にプッシュされる前に期待どおりに動作することを確認してください。 |

## 顧客属性 {#section_62B4821EB6564FF4A14159A837AD4EDB}

顧客属性は、プロファイルスクリプトで参照でき、形式 `crs.get('<Datasource Name>.<Attribute name>')`　設定されています。

この属性は、プロファイルスクリプトでトークンとして、また、プロファイルスクリプトを使用せずにオファー内で直接使用可能になりました。トークンはフォームに含まれている必要があります。 `${crs.datasourceName.attributeName}` を参照してください。なお、 `datasourceName` は、任意の API 呼び出しから削除する必要があります。
