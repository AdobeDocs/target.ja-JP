---
keywords: 環境データ、セッションデータ、地理データ、地理データ、デバイスデータ、モバイルデータ、属性、プロファイル属性、パーソナライゼーションアルゴリズム、機械学習アルゴリズム、機械学習アルゴリズム
description: データの確認 [!DNL Adobe Target] はを収集し、を使用して機械学習アルゴリズムを構築します。
title: 機械学習アルゴリズムを構築するために収集されるデータは何ですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '2024'
ht-degree: 56%

---

# [!DNL Target]機械学習アルゴリズムで使用するデータ

[!DNL Adobe Target] は様々なデータを自動的に収集して使用し、 [!UICONTROL Automated Personalization] (AP) および [!UICONTROL 自動ターゲット] (AT) アクティビティ 訪問者が [!UICONTROL Automated Personalization] または [!UICONTROL 自動ターゲット] アクティビティの場合、情報のスナップショットが、一連の「トレーニングレコード」（パーソナライゼーションアルゴリズムが学習する訪問者データ）に渡されます。

詳しくは、 [!DNL Target] パーソナライゼーションアルゴリズム、詳しくは、 [ランダムフォレストアルゴリズム](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## デフォルト [!DNL Target] 属性カテゴリ

次の表に、 [!UICONTROL Automated Personalization] および [!UICONTROL 自動ターゲット] デフォルトでは、の設定なしでのアクティビティ [!DNL Target] またはその他 [!DNL Adobe] ソリューション。 また、この表には、これらの属性を [パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). 入力データセットはいつでも増やすことができます。追加データのアップロード方法について詳しくは、 [のデータをアップロード中 [!DNL Target] パーソナライゼーションアルゴリズム](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| データカテゴリ | システムプレフィックス | 説明 | での表示名 [!UICONTROL インサイト] レポート |
| --- | --- | --- | --- |
| 環境パラメーター | ENV | オペレーティングシステム、ブラウザー、曜日/曜日など、ユーザーの環境に関する情報。 | ブラウザー — [属性名]<br>オペレーティングシステム — [値] |
| 地域 | 地域 | IP ルックアップ経由で取得されたユーザーの地域に関する情報。 | 地域 — [地域属性] |
| モバイルデバイス | 暴徒 | ユーザーのモバイルデバイスに関する情報。 | デバイス — [デバイス属性]<br>モバイル — [モバイル属性] |
| [!DNL Target] レポートセグメント | SEG | で設定されたレポートセグメント [!DNL Target] レポート。 | レポートセグメント —[セグメント名] |
| セッション動作 | SES | 閲覧されたページ数など、ユーザーの行動に関する情報。 | 訪問者プロファイル — [属性名] |

## カスタム [!DNL Target] 属性カテゴリ

次の表に、 [!UICONTROL Automated Personalization] および [!UICONTROL 自動ターゲット] アクティビティ。 このデータは、指定した場合にのみ収集されます。 特定の属性名とサンプル値は、システム設定に固有です。

| データカテゴリ | システムプレフィックス | 説明 | での表示名 [!UICONTROL インサイト] レポート |
| --- | --- | --- | --- |
| ページのパラメーター | BOX | への呼び出しで渡されるカスタムページパラメーター（「mbox パラメーター」） [!DNL Target]. | カスタム — mbox パラメーター — [パラメーター名] |
| [!DNL Target]プロファイル | PRO | カスタムプロファイル属性は、 [!DNL Target] API またはページパラメーターを介したプロファイルおよび [!DNL Target] プロファイルスクリプト。 | カスタム — 訪問者プロファイル — [属性名] |
| 顧客属性 | CRS | にアップロードされた顧客属性 [!DNL Target] 経由でのプロファイル [[!DNL Adobe Experience Cloud Customer Attributes Service]](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=ja){target=_blank}. | カスタム — 訪問者プロファイル — [属性名] |
| URL パラメーター | URL | 現在表示されているページの URL および任意の URL パラメーター。 | カスタム — URL パラメーター — [URL パラメーター] |
| 参照 URL | REF | 参照 URL および参照 URL の任意の URL パラメーター。 | カスタム — [参照 URL パラメーター] - [パラメーター値] |
| [!DNL Adobe Experience Cloud] 共有オーディエンス | AAM | 共有されているすべてのオーディエンス [!DNL Target] 他から [!DNL Adobe Experience Cloud] ソリューション ( 例： [!DNL Adobe Audience Manager] および [!DNL Adobe Analytics]、 [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank}) をクリックします。 | カスタム —Experience Cloudオーディエンス — [オーディエンス名] |
| [!DNL Adobe Experience Platform Real-time CDP] audiences | UPS | と共有されるプラットフォームのリアルタイム CDP オーディエンス [!DNL Target] 経由 [!UICONTROL 宛先]. |  |
| [!DNL Adobe Experience Platform Real-time CDP] 属性 | AEP | と共有されるプラットフォームのリアルタイム CDP 属性 [!DNL Target] 経由 [!UICONTROL 宛先]. |  |

## 機能をブロックする [!DNL Target] 機械学習アルゴリズム

機能は次の場所からブロックできます： [!DNL Target] 機械学習アルゴリズムを使用して、どのような場合でも使用できないようにする [!UICONTROL Automated Personalization] または [!UICONTROL 自動ターゲット] モデルまたはアクティビティ。

詳しくは、 [モデル API(ブロックリストに加える) の概要](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} （内） *[!DNL Adobe Target]開発者ガイド*.

## デバイスとモバイルデータ {#device-mobile}

| 属性名 | 属性の説明 | サンプル値 | システム名 |
| --- | --- | --- | --- |
| Mobile - Device - Brand | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスのブランド。 | Apple | MOB_targeting.mobile.vendor |
| Mobile - Device - eReader | デバイスが eReader かどうかを指定します。 | 0 は False、1 は True | MOB_targeting.mobile.ereader |
| Mobile - Device - Game Console | デバイスがゲームコンソールかどうかを指定します。 | 0 は False、1 は True | MOB_targeting.mobile.gamesConsole |
| Mobile - Device - Media Player | デバイスがメディアプレーヤーかどうかを指定します。 | 0 は False、1 は True | MOB_targeting.mobile.mediaPlayer |
| Mobile - Device - Mobile Phone | デバイスがモバイルフォンかどうかを指定します。 | 0 は False、1 は True | MOB_targeting.mobile.mobilePhone |
| Mobile - Device - Model Name | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスのモデル名。 | iPhone XS | MOB_targeting.mobile.model |
| Device - Set-Top Box | デバイスがセットトップボックスかどうかを指定します。 | 0 は False、1 は True | MOB_targeting.mobile.setTopBox |
| Mobile - Device - Tablet | デバイスがタブレットかどうかを指定します。 | 0 は False、1 は True | MOB_targeting.mobile.tablet |
| Mobile - Pixel Density (ppi) | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスのピクセル密度。 | 1、2、3 など。 | MOB_targeting.mobile.displayPpi |
| Mobile - OS - OS X ([!DNL Android], [!DNL Windows]など ) | ユーザーが OSX ( または [!DNL Android], [!DNL Windows]など ) を使用して、アクティビティにアクセスするデバイスにアクセスできます。 | 0 は False、1 は True | MOB_targeting.mobile.os[OS]<br>例えば、 MOB_targeting.mobile.osOSx、 MOB_targeting.mobile.osWindows、 MOB_targeting.mobile.osAndroid、 MOB_targeting.mobile.osLinux などです。 |
| Mobile - Screen Height (px) | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスの画面の高さ（ピクセル単位）。 | 1、2、3 など。 | MOB_targeting.mobile.displayHeight |
| Mobile - Screen Width (px) | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスの画面の幅（ピクセル単位）。 | 1、2、3 など。 | MOB_targeting.mobile.displayWidth |

## 環境データ {#env}

| 属性名 | 属性の説明 | サンプル値 | システム名 |
| --- | --- | --- | -- |
| Browser - Day of Week | 訪問者がアクティビティにアクセスしたときの曜日。 | 0 – 6.<br>（0 は日曜日） | ENV_DayOfWeek |
| Browser - Hour of Day | 訪問者がアクティビティにアクセスしたときの時刻。 | 0 ～ 23<br>（0 は午前 0 時） | ENV_UserHour |
| Browser - Hour of Week | 訪問者がアクティビティにアクセスしたときの週の時間。 | 0 ～ 168<br>（日曜日午前 0 時は 0） | ENV_WeekHour |
| Browser - Language Setting | 訪問者がアクティビティへのアクセスに使用したブラウザーで指定された言語。 | English<br>German | ENV_Language |
| Browser - Time of Day | 訪問者がアクティビティにアクセスしたときのブラウザーの時間。 | 0, 6, 12, 18<br>（0 は夜、6 は朝、<br>12 は午後、18 は夜） | ENV_LocalTimePeriod |
| Browser - Timezone | 訪問者がアクティビティにアクセスしたときのタイムゾーン。 | Pacific Time<br>Eastern Time<br>GMT | ENV_BrowserTimezoneOffsetMinutes |
| Browser - Type | 訪問者がアクティビティへのアクセスに使用したブラウザーのタイプ。 | [!DNL Chrome]<br>[!DNL Firefox]<br>[!DNL Internet Explorer]<br>[!DNL Safari]<br>その他 | ENV_Browser |
| Browser - Weekday/Weekend | 訪問者がアクティビティにアクセスしたときの作業ステータス（週末、勤務時間、平日の自由時間）。 | 土曜日と日曜日は週末です<br>月曜日～金曜日の 0900 - 1800 は勤務時間です<br>月曜日～金曜日の 1800 以降 0900 までは平日の自由時間です | ENV_UserHourType |
| Browser - Window Height (px) | 訪問者がアクティビティへのアクセスに使用したデバイスのブラウザーウィンドウの高さ（ピクセル単位）。 | 1、2、3 など | ENV_BrowserHeight |
| Browser - Window Width (px) | 訪問者がアクティビティへのアクセスに使用したデバイスのブラウザーウィンドウの幅（ピクセル単位）。 | 1、2、3 など | ENV_BrowserWidth |
| Device - Screen Height (px) | 訪問者がアクティビティへのアクセスに使用したデバイスの画面の高さ。 | 1、2、3 など | ENV_ScreenHeight |
| Device - Screen Width (px) | 訪問者がアクティビティへのアクセスに使用したデバイスの画面の幅。 | 1、2、3 など | ENV_ScreenWidth |
| オペレーティングシステム | 訪問者がアクティビティへのアクセスに使用したデバイスのオペレーティングシステム。 | [!DNL Mac OS]<br>[!DNL Windows]<br>[!DNL Linux]<br>ボットを検索<br>不明な OS | ENV_OperatingSystem |
| Operating System - Version | 訪問者がアクティビティへのアクセスに使用したオペレーティングシステムのバージョン。 | [!DNL Windows] 10<br>[!DNL Mac OS] 10 | ENV_OperatingSystemVersion |
| Traffic Sources - Referring Landing Page URL | サイトにアクセスした際に訪問者が見た最初のページ。 | `https://www.adobe.com/ecloud.html` | ENV_Referrer |

## 地理データ {#geo}

| 属性名 | 属性の説明 | サンプル値 | システム名 |
| --- | --- | --- | --- |
| Geo - City | アクティビティにアクセスした訪問者のいる都市。 | サンフランシスコ | Geo_City |
| Geo - Country | アクティビティにアクセスした訪問者のいる国。 | ドイツ | Geo_Country |
| Geo - DMA | アクティビティにアクセスした訪問者のいる Designated Marketing Area（DMA）。 | Charlottesville | Geo_DMA |
| Geo - Latitude | アクティビティにアクセスした訪問者のいる緯度。 | 47.269<br>小数点以下 3 桁で四捨五入（約 100 m の精度） | GEO_Latitude |
| Geo - Longitude | アクティビティにアクセスした訪問者のいる経度。 | -122.269<br>小数点以下 3 桁で四捨五入（約 100 m の精度） | GEO_Longitude |
| Geo - State/Region | アクティビティにアクセスした訪問者のいる州または地域。 | Utah<br>New South Wales | GEO_State<br>GEO_Region |
| Geo - Zip Code | アクティビティにアクセスした訪問者のいる場所の郵便番号。 | 84004 | GEO_ZipCode |
| Mobile - Carrier | 訪問者がアクティビティへのアクセスに使用した携帯電話会社 | [!DNL Vodafone]<br>[!DNL T-Mobile] | GEO_mobileCarrier |
| Network - Connection Speed | 訪問者がアクティビティへのアクセスに使用したデバイスのネットワーク接続速度。 | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite | GEO_ConnectionSpeed |
| Network - Domain Name | 訪問者がアクティビティにアクセスしたときのネットワークドメインの名前。 | `nnt.net` | GEO_DomainName |
| Network - ISP | アクティビティにアクセスした訪問者のいるネットワーク。 | nnt communications corporation | GEO_IspName |

## セッションデータ {#session}

| 属性名 | 属性の説明 | サンプル値 | システム名 |
| --- | --- | --- | --- |
| Visitor Profile - Activity Lifetime Order Value | 特定のアクティビティに対するすべての訪問／セッションのすべての注文の値の合計を指定します。 | ダブル | SES_CUMULATIVE_ORDER_VALUE |
| Visitor Profile - Activity Lifetime Time on Site | 訪問者のサイトでの合計滞在時間を指定します（現在のセッションを除く）。セッションの有効期限が切れると更新されます。 | ダブル、ミリ秒 | SES_TOTAL_TIME |
| Visitor Profile -Average Page Views per Visit during Activity | セッションあたりの平均ページビュー数を指定します（現在のセッションを除く）。 | ダブル | SES_REQUESTS_PER_SESSION |
| Visitor Profile - Average Time per Visit | 訪問／セッションあたりの平均滞在時間を指定します。これには現在のセッションは含まれません。 | ダブル、ミリ秒 | SES_TIME_PER_SESSION |
| Visitor Profile - First Visit | ユーザーが最初に操作した訪問の時間を指定します。 [!DNL Target]. | ダブル、ミリ秒 | SES_PROFILE_CREATION_TIME |
| Visitor Profile - Hours since Last Visit | このアクティビティへの最後の訪問からの経過時間を指定します。 | ダブル（正の整数のみ）1、2、3 など。 | SES_HOURS_SINCE_LAST_VISIT |
| Visitor Profile - Impressions of Location/Content | 特定のアクティビティでの特定の場所／コンテンツの組み合わせに対するインプレッション数を指定します。 | ダブル（正の整数のみ）1、2、3 など。 | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| 訪問者プロファイル — 最後 [!DNL Target] インタラクション | との最後のやり取りの時間を指定します。 [!DNL Target]. インタラクションは [!DNL Target] 現在の～の実装を要求する [!DNL Target] リクエストごとにプロファイルを更新します。 | ダブル、ミリ秒 | SES_PROFILE_UPDATE_TIME |
| Visitor Profile - Pages Seen Before Activity | 合計ページビュー数（インプレッション数）を指定します。訪問者がアクティビティに入るまで、現在の訪問/セッションを含めます。 | ダブル（正の整数のみ）1、2、3 など。 | SES_TOTAL_PAGE_VIEWS |
| Visitor Profile - Page Views in Current Visit | 訪問者がアクティビティに入るまでの、現在の訪問/セッションのページビュー数を指定します。 もっと正確に言えば、インプレッション数です。これらのインプレッション数は、実際のページビュー数ではなく、リクエストが到達した回数です [!DNL Target]. [!DNL Target] では、タイムアウトやユーザーがコンテンツを受け取らなかったその他の理由を区別できません。 | ダブル（正の整数のみ） | SES_SESSION_POSITION |
| Visitor Profile - Start of Current Visit | 現在の訪問/セッションの時間を指定します。 [!DNL Target] 開始しました。 次を含む訪問： [!DNL Target] は、「 」アクティビティに入らずに開始できます。 必要なのは、 [!DNL Target] リクエスト。 訪問者は、アクティビティに入り、スナップショットが作成されるまで時間がかかる場合があります。 | ダブル、ミリ秒 | SES_SESSION_START |
| Visitor Profile - Start of Most Recent Visit | 最後の訪問/セッションの時間を指定します。 [!DNL Target] 開始しました。 この属性は、セッションの有効期限が切れると更新されます。<br>これが訪問者にとっての最初のセッションの場合、結果はになります。 `LAST_SESSION_START = 0.` | ダブル、ミリ秒 | SES_LAST_SESSION_START |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | 以前のセッションとユーザーがアクティビティに入ってスナップショットが実行されたときの間の期間を指定します。 | ダブル、ミリ秒 | SES_RECENCY |
| Visitor Profile - Time in Visit Before Enter Activity | 次との最後のやり取りの差を指定 [!DNL Target] 現在の訪問が開始したとき。 この属性は、ユーザーがアクティビティに入ってスナップショットが実行されるまでの訪問／セッション期間と考えることができます。<br>セッションが開始して最後の更新時間が同じ [!DNL Target] を呼び出します。 負の値は 0（ゼロ）とみなす必要があります。 | ダブル、ミリ秒 | SES_SESSION_TIME |
| 訪問者プロファイル - 合計訪問回数 | 訪問／セッションの合計数を指定します。現在の訪問／セッションは含まれません。 | ダブル（正の整数のみ）1、2、3 など。 | SES_TOTAL_SESSIONS |
| Visitor Profile - Total Visits to Activity | 特定のアクティビティへの訪問数を指定します。以前の訪問がない場合、0（ゼロ）を返します。 | ダブル（正の整数のみ）1、2、3 など。 | SES_PREVIOUS_VISIT_COUNT |
| Visitor Profile - Total Visits to Activity with Conversion | 訪問中に少なくとも 1 つのコンバージョンがある場合の、特定のアクティビティへの訪問／セッションの数を指定します。 | ダブル | SES_CUMULATIVE_SUCCESSES |
| Visitor Profile - Visits to Activity with No Conversion | 特定のアクティビティに対するコンバージョンがない訪問／セッションの数。この値は、コンバージョンの後に 0 にリセットされます。または、コンバージョンが発生しなかった場合、-1 になります。 | ダブル（正の整数のみ）1、2、3 など。 | SES_SUCCESS_RECENCY |
