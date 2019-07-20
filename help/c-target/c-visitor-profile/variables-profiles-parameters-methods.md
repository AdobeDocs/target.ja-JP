---
description: このページには、プロファイルスクリプトで役立つプロファイル、変数およびパラメーターの一覧を記載しています。
keywords: 変数、プロファイル、パラメーター、組み込みプロファイル、メソッド、url変数、地域プロファイル、サードパーティプロファイル、mbox変数、campaign変数、顧客属性
seo-description: このページには、プロファイルスクリプトで役立つプロファイル、変数およびパラメーターの一覧を記載しています。
seo-title: プロファイルと変数の用語集
solution: 'Target '
title: プロファイルと変数の用語集
topic: Standard
uuid: 9286467c-cbb5-42be-99c0-6687ffab0969
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# プロファイルと変数の用語集{#profile-and-variable-glossary}

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
| user.header('x-cluster-client-ip') | 訪問者がいるネットワーク接続の公開される IP アドレス。<br>これは [whatismyip.com](https://www.whatismyip.com/)/など、いくつかの方法で入手できます。IP アドレスは、10.、192.168. または 172 から始まる NAT アドレス（内部アドレス）ではありません。 |
| user.header('host') | Web サイトのホスト名 |
| user.header('cookie') | 訪問者の cookie データ |
| user.header('user-agent') | 訪問者のブラウザーのユーザーエージェント |
| user.header('accept-language') | 訪問者の言語 |
| user.header('accept-encoding') | 訪問者の文字エンコード |
| user.header('accept') | 訪問者の言語および文字エンコード |
| user.header('connection') | サーバー接続。例：keep-live |
| user.header('referrer') | 訪問者の現在のページの Web サイト URL。Internet Explorer では動作しません。 |
| user.getLocal('param_name','value'); |  |
| user.setLocal('param_name','value'); |  |
| user.get('param_name') |  |
| user.parameter | プロファイルスクリプトから作成されたプロファイル属性を保持します。また、ジオロケーションや訪問回数などの「システム」プロファイルも参照します。 |
| profile.get('param_name') |  |
| profile.param('param_name'); |  |
| profile.parameter('parameter_name'); | profile.  prefix. |
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
| mbox.param('param_name') |  |
| リクエストごとに自動的に渡されるパラメーター：<ul><li>mbox.param('browserHeight')</li><li>mbox.param('browserTimeOffset')</li><li>mbox.param('browserWidth')</li><li>mbox.param('colorDepth')</li><li>mbox.param('mboxXDomain')</li><li>mbox.param('mboxTime')</li><li>mbox.param('screenHeight')</li><li>mbox.param('screenWidth')</li></ul> |
| 発注 mbox と共に渡されるパラメーター：<ul><li>mbox.param('orderId')</li><li>mbox.param('orderTotal')</li><li>mbox.param('productPurchasedId')</li></ul> |
| mbox3rdPartyId | 顧客 ID と Target の mboxPCID を同期するための mbox パラメーター。顧客 ID は、CRM ID やメンバーシップ ID など、会社が訪問者を追跡するために使用する ID です。そのため、この ID は、プロファイル API および[顧客属性](/help/c-target/c-visitor-profile/working-with-customer-attributes.md). |
| mboxPageValue | mbox の呼び出しごとに、ページに値が割り当てられます。 |
| mboxDebug | デバッグ情報にのみ使用されます。mbox.js が探すページ URL に追加されます。 |
| mboxOverride.browserIp | 実際の場所とは異なる地域を設定して、別の場所でどのように表示されるかをテストできます。<br>**注意：** mboxOverride パラメーターは、アクティビティをテストするときにのみ使用し、実稼動環境で使用しないでください。任意のmboxOverrideパラメーターを使用すると、Analytics for [Target](/help/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用する際にレポートの相違が生じる可能性があります。アクティビティをテスト中に [アクティビティQAモード](/help/c-activities/c-activity-qa/activity-qa.md) を使用して、アクティビティが本番環境にプッシュされる前に期待どおりに動作することを確認してください。 |

## 顧客属性 {#section_62B4821EB6564FF4A14159A837AD4EDB}

顧客属性は、プロファイルスクリプトで参照でき、形式 `crs.get('<Datasource Name>.<Attribute name>')`　設定されています。

この属性は、プロファイルスクリプトでトークンとして、また、プロファイルスクリプトを使用せずにオファー内で直接使用可能になりました。トークンはフォームに含まれている必要があります。 `$crs.datasourceName.attributeName` を参照してください。
