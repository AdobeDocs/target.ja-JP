---
description: Adobe Target では、様々なデータを自動的に収集し、それを基に自動パーソナライゼーション（AP）と自動ターゲット（AT）アクティビティのパーソナライゼーションアルゴリズムを構築します。訪問者に AP または AT アクティビティが提供されると、情報のスナップショットが「トレーニングレコード」（パーソナライゼーションアルゴリズムによる学習の基になる訪問者データ）のセットに渡されます。
keywords: 環境データ;セッションデータ;ジオデータ;地理データ;デバイスデータ;モバイルデータ;属性;プロファイル属性
seo-description: Adobe Target では、様々なデータを自動的に収集し、それを基に自動パーソナライゼーション（AP）と自動ターゲット（AT）アクティビティのパーソナライゼーションアルゴリズムを構築します。訪問者に AP または AT アクティビティが提供されると、情報のスナップショットが「トレーニングレコード」（パーソナライゼーションアルゴリズムによる学習の基になる訪問者データ）のセットに渡されます。
seo-title: Adobe Target のパーソナライゼーションアルゴリズムのデータ収集
solution: 'Target '
title: Target のパーソナライゼーションアルゴリズムのデータ収集
title-outputclass: Premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: Premium
translation-type: tm+mt
source-git-commit: 156587a0375fe2dbf8c461e310b2eae04b491b57

---


# ![PREMIUM](/help/assets/premium.png) Target パーソナライゼーションアルゴリズムのデータ収集{#data-collection-for-the-target-personalization-algorithms}

Target では、様々なデータを自動的に収集し、それを基に自動パーソナライゼーション（AP）と自動ターゲット（AT）アクティビティのパーソナライゼーションアルゴリズムを構築します。訪問者に AP または AT アクティビティが提供されると、情報のスナップショットが「トレーニングレコード」（パーソナライゼーションアルゴリズムによる学習の基になる訪問者データ）のセットに渡されます。

Target のパーソナライゼーションアルゴリズムについて詳しくは、[ランダムフォレストアルゴリズム](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA)を参照してください。

以下の表に、マーケティング担当者が何もしなくてもデフォルトで自動パーソナライゼーションおよび自動ターゲットで収集されるデータと、これらの属性を[パーソナライゼーションインサイトレポート](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)で表示するときに使用する命名規則を示します。入力データセットはいつでも増やすことができます。追加データのアップロード方法について詳しくは、[Target のパーソナライゼーションアルゴリズムのデータのアップロード](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6)を参照してください。

| データタイプ | 説明 | データタイプの命名規則 | 属性の例 |
| --- | --- | --- | --- |
| [デバイスとモバイルデータ](#device-mobile) | デバイスおよびモバイルに特有の情報。<br>後述の「デバイスとモバイルデータ」を参照。 | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | モバイルデバイス OS<br>モバイル画面サイズ |
| [環境データ](#env) | 訪問者のオペレーティングシステムおよび訪問者がアクティビティにいつどのようにしてアクセスするかに関する情報。 | `Browser - / Operating System] - [Attribute Name]` | Browser - Type |
| Experience Cloud セグメント | Audience Manager または Analytics で作成したオーディエンスおよび Experience Cloud の共有アクセス | `Custom - Experience Cloud Audience - [Audience Name]` | カスタムデータ |
| [地理データ](#geo) | 訪問者の所在地に関する情報。<br>後述の「地理データ」を参照。 | `Geo - [geo attribute]` | 市町村<br>国<br>地域／州<br>郵便番号<br>緯度<br>経度<br>ISP または携帯電話会社 |
| プロファイル属性 | 更新 API を使用して Target プロファイルに直接アップロードされるプロファイルスクリプトまたは属性 | `Custom - Visitor Profile - [attribute name]` | カスタムデータ |
| 参照 URL パラメーター | 一般に参照 URL とは、mbox 呼び出しが実行された特定のページを参照した URL のことを指します。<br>この変数は、サイトでのユーザーの行動と、サイトの技術的実装の影響を受ける場合があります。 | `Custom - [Referring URL Parameter] - [Parameter value]` | カスタムデータ |
| レポートするセグメント | アクティビティ設定で設定したセグメント | `Reporting Segment -[Segment Name]` | カスタムデータ |
| [セッションデータ](#session) | アクティビティへのアクセス時のセッションでの訪問者の行動に関する情報。 | `Visitor Profile - [Attribute Name]` | Visitor Profile - Start of Most Recent Visit |
| URL パラメーター | Target では、URL を解析して URL パラメーターを抽出します。 | `Custom - URL Parameter - [URL Parameter]` | カスタムデータ |

以下の節には、属性名、説明、サンプル値を含む、様々なデータタイプに関する詳細情報が含まれています。

## デバイスとモバイルデータ {#device-mobile}

| 属性名 | 属性の説明 | サンプル値 |
| --- | --- | --- |
| Mobile - Device - Brand | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスのブランド。 | Apple |
| Mobile - Device - eReader | デバイスが eReader かどうかを指定します。 | 0 は False、1 は True |
| Mobile - Device - Game Console | デバイスがゲームコンソールかどうかを指定します。 | 0 は False、1 は True |
| Mobile - Device - Media Player | デバイスがメディアプレーヤーかどうかを指定します。 | 0 は False、1 は True |
| Mobile - Device - Mobile Phone | デバイスがモバイルフォンかどうかを指定します。 | 0 は False、1 は True |
| Mobile - Device - Model Name | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスのモデル名。 | iPhone XS |
| Device - Set-Top Box | デバイスがセットトップボックスかどうかを指定します。 | 0 は False、1 は True |
| Mobile - Device - Tablet | デバイスがタブレットかどうかを指定します。 | 0 は False、1 は True |
| Mobile - Pixel Density (ppi) | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスのピクセル密度。 | 1、2、3、など。 |
| Mobile - OS – OSX（Android、Windows、など） | ユーザーが OSX（または Android、Windows など）デバイスをアクティビティへのアクセスに使用したかどうかを指定します。 | 0 は False、1 は True |
| Mobile - Screen Height (px) | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスの画面の高さ（ピクセル単位）。 | 1、2、3、など。 |
| Mobile - Screen Width (px) | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスの画面の幅（ピクセル単位）。 | 1、2、3、など。 |

## 環境データ {#env}

| 属性名 | 属性の説明 | サンプル値 |
| --- | --- | --- |
| Browser - Day of Week | 訪問者がアクティビティにアクセスしたときの曜日。 | 0 ～ 6。<br>（0 は日曜日） |
| Browser - Hour of Day | 訪問者がアクティビティにアクセスしたときの時刻。 | 0 ～ 23<br>（0 は午前 0 時） |
| Browser - Hour of Week | 訪問者がアクティビティにアクセスしたときの週の時間。 | 0 ～ 168<br>（日曜日午前 0 時は 0） |
| Browser - Language Setting | 訪問者がアクティビティへのアクセスに使用したブラウザーで指定された言語。 | English<br>German |
| Browser - Screen Height (px) | 訪問者がアクティビティへのアクセスに使用したデバイスのブラウザー画面の高さ（ピクセル単位）。 | 1、2、3、など。 |
| Browser - Time of Day | 訪問者がアクティビティにアクセスしたときのブラウザーの時間。 | 0, 6, 12, 18<br>（0 は夜、6 は朝、<br>12 は午後、18 は夜） |
| Browser - Timezone | 訪問者がアクティビティにアクセスしたときのタイムゾーン。 | Pacific Time<br>Eastern Time<br>GMT |
| Browser - Type | 訪問者がアクティビティへのアクセスに使用したブラウザーのタイプ。 | Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Other |
| Browser - Weekday/Weekend | 訪問者がアクティビティにアクセスしたときの作業ステータス（週末、勤務時間、平日の自由時間）。 | 土曜日および日曜日は週末<br>月曜日～金曜日の 0900 ～ 1800 は勤務時間<br>月曜日～金曜日の 1800 以降 0900 までは平日の自由時間 |
| Browser - Window Height (px) | 訪問者がアクティビティへのアクセスに使用したデバイスのブラウザーウィンドウの高さ（ピクセル単位）。 | 1、2、3、など。 |
| Browser - Window Width (px) | 訪問者がアクティビティへのアクセスに使用したデバイスのブラウザーウィンドウの幅（ピクセル単位）。 | 1、2、3、など。 |
| Device - Screen Height | 訪問者がアクティビティへのアクセスに使用したデバイスの画面の高さ。 | 1、2、3、など。 |
| Device - Screen Width | 訪問者がアクティビティへのアクセスに使用したデバイスの画面の幅。 | 1、2、3、など。 |
| オペレーティングシステム | 訪問者がアクティビティへのアクセスに使用したデバイスのオペレーティングシステム。 | Mac OS<br>Windows<br>Linux<br>Search Bot<br>OS Unknown |
| Operating System - Version | 訪問者がアクティビティへのアクセスに使用したオペレーティングシステムのバージョン。 | Windows 10<br>Mac OS 10 |
| Traffic Sources - Referring Landing Page URL | サイトにアクセスした際に訪問者が見た最初のページ。 | `https://www.adobe.com/ecloud.html` |

## 地理データ {#geo}

| 属性名 | 属性の説明 | サンプル値 |
| --- | --- | --- |
| Geo - City | アクティビティにアクセスした訪問者のいる都市。 | サンフランシスコ |
| Geo - Country | アクティビティにアクセスした訪問者のいる国。 | ドイツ |
| Geo - DMA | アクティビティにアクセスした訪問者のいる Designated Marketing Area（DMA）。 | Charlottesville |
| Geo - Latitude | アクティビティにアクセスした訪問者のいる緯度。 | 47.269<br>小数点以下 3 桁で四捨五入（約 100 m の精度） |
| Geo - Longitude | アクティビティにアクセスした訪問者のいる経度。 | -122.269<br>小数点以下 3 桁で四捨五入（約 100 m の精度） |
| Geo - State/Region | アクティビティにアクセスした訪問者のいる州または地域。 | Utah<br>New South Wales |
| Geo - Zip Code | アクティビティにアクセスした訪問者のいる場所の郵便番号。 | 84004 |
| Mobile - Carrier | 訪問者がアクティビティへのアクセスに使用した携帯電話会社 | Vodafone<br>T-Mobile |
| Network - Connection Speed | 訪問者がアクティビティへのアクセスに使用したデバイスのネットワーク接続速度。 | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite |
| Network - Domain Name | 訪問者がアクティビティにアクセスしたときのネットワークドメインの名前。 | `nnt.net` |
| Network - ISP | アクティビティにアクセスした訪問者のいるネットワーク。 | nnt communications corporation |

## セッションデータ {#session}

| 属性名 | 属性の説明 | サンプル値 |
| --- | --- | --- |
| Visitor Profile - Activity Lifetime Order Value | 特定のアクティビティに対するすべての訪問／セッションのすべての注文の値の合計を指定します。 | ダブル |
| Visitor Profile - Activity Lifetime Time on Site | 訪問者のサイトでの合計滞在時間を指定します（現在のセッションを除く）。セッションの有効期限が切れると更新されます。 | ダブル、ミリ秒 |
| Visitor Profile -Average Page Views per Visit during Activity | セッションあたりの平均ページビュー数を指定します（現在のセッションを除く）。 | ダブル |
| Visitor Profile - Average Time per Visit | 訪問／セッションあたりの平均滞在時間を指定します。これには現在のセッションは含まれません。 | ダブル、ミリ秒 |
| Visitor Profile - First Visit | ユーザーが Target とやり取りした最初の訪問の時間を指定します。 | ダブル、ミリ秒 |
| Visitor Profile - Hours since Last Visit | このアクティビティへの最後の訪問からの経過時間を指定します。 | ダブル（正の整数のみ）1、2、3 など |
| Visitor Profile - Impressions of Location/Content | 特定のアクティビティでの特定の場所／コンテンツの組み合わせに対するインプレッション数を指定します。 | ダブル（正の整数のみ）1、2、3 など |
| Visitor Profile - Last Target Interaction | Target との最後のやり取りの時間を指定します。Target の現在の実装はリクエストごとにプロファイルを更新するので、やり取りは mbox リクエストごとに発生します。 | ダブル、ミリ秒 |
| Visitor Profile - Pages Seen Before Activity | 合計ページビュー数（インプレッション）を指定します（訪問者がアクティビティに入るまでは、現在の訪問／セッションを含む）。 | ダブル（正の整数のみ）1、2、3 など |
| Visitor Profile - Page Views in Current Visit | 訪問者がアクティビティに入るまでの、現在の訪問／セッションのページビュー数を指定します。もっと正確に言えば、インプレッション数です。これらのインプレッション数は、実際のページビュー数ではなく、リクエストが Target に到達した回数です。Target では、タイムアウトやユーザーがコンテンツを受け取らなかった／表示したその他の理由を区別できません。 | ダブル（正の整数のみ） |
| Visitor Profile - Start of Current Visit | Target を使用した現在の訪問／セッションが開始した時間を指定します。Target を使用した訪問は、アクティビティに入らなくても開始できます。必要なのは任意の mbox への呼び出しだけです。訪問者は、アクティビティに入り、スナップショットが取られるまで時間がかかる可能性があります。 | ダブル、ミリ秒 |
| Visitor Profile - Start of Most Recent Visit | Target を使用した最後の訪問／セッションが開始した時間を指定します。この属性は、セッションの有効期限が切れると更新されます。<br>これが訪問者にとっての最初のセッションの場合、結果は `LAST_SESSION_START = 0.` になります。 | ダブル、ミリ秒 |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | 以前のセッションとユーザーがアクティビティに入ってスナップショットが実行されたときの間の期間を指定します。 | ダブル、ミリ秒 |
| Visitor Profile - Time in Visit Before Enter Activity | Target との最後のやり取りと現在の訪問が開始したときの間の差を指定します。この属性は、ユーザーがアクティビティに入ってスナップショットが実行されるまでの訪問／セッション期間と考えることができます。<br>セッションが開始して最後の更新時間が同じ mbox 呼び出しでトリガーされる場合、負の値になります。負の値は 0（ゼロ）とみなす必要があります。 | ダブル、ミリ秒 |
| 訪問者プロファイル - 合計訪問回数 | 訪問／セッションの合計数を指定します。現在の訪問／セッションは含まれません。 | ダブル（正の整数のみ）1、2、3 など |
| Visitor Profile - Total Visits to Activity | 特定のアクティビティへの訪問数を指定します。以前の訪問がない場合、0（ゼロ）を返します。 | ダブル（正の整数のみ）1、2、3 など |
| Visitor Profile - Total Visits to Activity with Conversion | 訪問中に少なくとも 1 つのコンバージョンがある場合の、特定のアクティビティへの訪問／セッションの数を指定します。 | ダブル |
| Visitor Profile - Visits to Activity with No Conversion | 特定のアクティビティに対するコンバージョンがない訪問／セッションの数。この値は、コンバージョンの後に 0 にリセットされます。または、コンバージョンが発生しなかった場合、-1 になります。 | ダブル（正の整数のみ）1、2、3 など |
