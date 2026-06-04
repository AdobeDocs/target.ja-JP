---
keywords: 環境データ；セッションデータ；地理データ；地理データ；デバイスデータ；モバイルデータ；属性；プロファイル属性；パーソナライゼーションアルゴリズム；機械学習アルゴリズム；機械学習アルゴリズム
description: 機械学習アルゴリズムを構築するために収集および使用するデータを学習します。 [!DNL Adobe Target] 様。
title: マシンラーニングアルゴリズムを構築するために収集されるデータは何ですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
TQID: https://experienceleague.adobe.com/eXEeFKovZmtYqcIe0dNda7f0J-nWgfW5mB1Mxv9Zp6U
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2009
ht-degree: 52%

---

# [!DNL Target]個の機械学習アルゴリズムで使用されるデータ

[!DNL Adobe Target]は、様々なデータを自動的に収集して使用し、[!UICONTROL Automated Personalization] （AP）および[!UICONTROL 自動ターゲット &#x200B;] （AT）アクティビティでパーソナライゼーションアルゴリズムを構築します。 訪問者が[!UICONTROL Automated Personalization]または[!UICONTROL 自動ターゲット &#x200B;] アクティビティにエントリすると、情報のスナップショットが「トレーニングレコード」（パーソナライゼーションアルゴリズムが学習する訪問者データ）のセットに渡されます。

[!DNL Target] パーソナライゼーション アルゴリズムについて詳しくは、[&#x200B; ランダム フォレスト アルゴリズム &#x200B;](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)を参照してください。

## 既定の[!DNL Target]属性カテゴリ

次の表は、[!UICONTROL Automated Personalization]および[!UICONTROL 自動ターゲット &#x200B;] アクティビティによって収集されたデータをデフォルトで示しています。ただし、[!DNL Target]またはその他の[!DNL Adobe] ソリューションは含まれていません。 このテーブルには、[Personalization インサイトレポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)でこれらの属性を示すために使用される命名規則も含まれています。 入力データセットはいつでも増やすことができます。 追加のデータをアップロードする方法について詳しくは、 [!DNL Target]  パーソナライゼーションアルゴリズム [&#128279;](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)の データのアップロードを参照してください。

| データカテゴリ | システム接頭辞 | 説明 | [!UICONTROL &#x200B; インサイト &#x200B;] レポートの表示名 |
| --- | --- | --- | --- |
| 環境パラメーター | ENV | オペレーティングシステム、ブラウザー、時間帯など、ユーザーの環境に関する情報。 | ブラウザー – [属性名]<br> オペレーティングシステム - [値] |
| 地域 | 地域 | IP ルックアップを介して取得されたユーザーの地理情報。 | 地域 – [地理属性] |
| モバイルデバイス | モブ | ユーザーのモバイルデバイスに関する情報。 | デバイス - [ デバイス属性]<br> モバイル - [ モバイル属性] |
| [!DNL Target] レポートセグメント | SEG | [!DNL Target] レポートで設定されたレポートセグメント。 | レポート セグメント - [ セグメント名] |
| セッション動作 | SES | 閲覧されたページ数など、ユーザーの行動に関する情報。 | 訪問者プロファイル - [属性名] |

## カスタム [!DNL Target]属性カテゴリ

次の表は、[!UICONTROL Automated Personalization]および[!UICONTROL 自動ターゲット &#x200B;] アクティビティによって収集されたお客様が提供したデータを示しています。 このデータは、お客様が提供した場合にのみ収集されます。 特定の属性名とサンプル値は、システム設定に固有です。

| データカテゴリ | システム接頭辞 | 説明 | [!UICONTROL &#x200B; インサイト &#x200B;] レポートの表示名 |
| --- | --- | --- | --- |
| ページのパラメーター | ボックス | カスタムページパラメーター（「mbox パラメーター」）が[!DNL Target]への呼び出しに渡されました。 | カスタム - Mbox パラメーター – [ パラメーター名] |
| [!DNL Target] プロファイル | PRO | カスタムプロファイル属性は、APIまたはページパラメーターと[!DNL Target] プロファイルスクリプトを使用して、[!DNL Target] プロファイルに直接アップロードされます。 | カスタム – 訪問者プロファイル - [属性名] |
| 顧客属性 | CRS | 顧客属性が[[!DNL Adobe Experience Cloud Customer Attributes Service]](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=ja){target=_blank}経由で[!DNL Target] プロファイルにアップロードされました。 | カスタム – 訪問者プロファイル - [属性名] |
| URL パラメーター | URL | URLと、現在表示されているページのURL パラメーター。 | カスタム - URL パラメーター – [URL パラメーター] |
| 参照 URL | REF | 参照URLと、参照URLのURL パラメーター。 | カスタム - [参照URL パラメーター] - [ パラメーター値] |
| [!DNL Adobe Experience Cloud]個の共有オーディエンス | AAM | 他の[!DNL Adobe Experience Cloud] ソリューション （[!DNL Adobe Audience Manager]および[!DNL Adobe Analytics]など、[[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank}経由）から[!DNL Target]と共有されたすべてのオーディエンス。 | カスタム - Experience Cloud オーディエンス - [ オーディエンス名] |
| [!DNL Adobe Experience Platform Real-time CDP]人のオーディエンス | UPS | [!UICONTROL 宛先]を介して[!DNL Target]と共有されたPlatform Real-Time CDP オーディエンス。 |  |


## [!DNL Target]個の機械学習アルゴリズムの機能をブロック中

[!DNL Target]個のマシンラーニングアルゴリズムから機能をブロックして、[!UICONTROL Automated Personalization]または[!UICONTROL 自動ターゲット &#x200B;]のモデルまたはアクティビティで使用できないようにすることができます。

詳しくは、*[!DNL Adobe Target]開発者ガイド*&#x200B;の「[&#x200B; モデル API （ブロックリストへの登録）の概要](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html?lang=ja){target=_blank}」を参照してください。

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
| Mobile - Pixel Density (ppi) | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスのピクセル密度。 | 1、2、3など。 | MOB_targeting.mobile.displayPpi |
| モバイル - OS - OS X （[!DNL Android]、[!DNL Windows]など） | ユーザーがOSX （または[!DNL Android]、[!DNL Windows]など）デバイスを使用してアクティビティにアクセスするかどうかを指定します。 | 0 は False、1 は True | MOB_targeting.mobile.os[OS]<br>例：MOB_targeting.mobile.osOSx、MOB_targeting.mobile.osWindows、MOB_targeting.mobile.osAndroid、MOB_targeting.mobile.osLinux |
| Mobile - Screen Height (px) | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスの画面の高さ（ピクセル単位）。 | 1、2、3など。 | MOB_targeting.mobile.displayHeight |
| Mobile - Screen Width (px) | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスの画面の幅（ピクセル単位）。 | 1、2、3など。 | MOB_targeting.mobile.displayWidth |

## 環境データ {#env}

| 属性名 | 属性の説明 | サンプル値 | システム名 |
| --- | --- | --- | -- |
| Browser - Day of Week | 訪問者がアクティビティにアクセスしたときの曜日。 | 0 - 6.<br> （0は日曜日） | ENV_DayOfWeek |
| Browser - Hour of Day | 訪問者がアクティビティにアクセスしたときの時刻。 | 0 - 23<br> （0は午前0時） | ENV_UserHour |
| Browser - Hour of Week | 訪問者がアクティビティにアクセスしたときの週の時間。 | 0 - 168<br> （日曜日の午前0時） | ENV_WeekHour |
| Browser - Language Setting | 訪問者がアクティビティへのアクセスに使用したブラウザーで指定された言語。 | English<br>German | ENV_Language |
| Browser - Time of Day | 訪問者がアクティビティにアクセスしたときのブラウザーの時間。 | 0, 6, 12, 18<br>（0 は夜、6 は朝、<br>12 は午後、18 は夜） | ENV_LocalTimePeriod |
| Browser - Timezone | 訪問者がアクティビティにアクセスしたときのタイムゾーン。 | Pacific Time<br>Eastern Time<br>GMT | ENV_BrowserTimezoneOffsetMinutes |
| Browser - Type | 訪問者がアクティビティへのアクセスに使用したブラウザーのタイプ。 | [!DNL Chrome]<br>[!DNL Firefox]<br>[!DNL Internet Explorer]<br>[!DNL Safari]<br>その他 | ENV_Browser |
| Browser - Weekday/Weekend | 訪問者がアクティビティにアクセスしたときの作業ステータス（週末、勤務時間、平日の自由時間）。 | 土曜日と日曜日は週末です<br>月曜日から金曜日の0900 - 1800は作業時間です<br>1800年以降の月曜日から金曜日の0900までは平日の自由時間です | ENV_UserHourType |
| Browser - Window Height (px) | 訪問者がアクティビティへのアクセスに使用したデバイスのブラウザーウィンドウの高さ（ピクセル単位）。 | 1、2、3など， | ENV_BrowserHeight |
| Browser - Window Width (px) | 訪問者がアクティビティへのアクセスに使用したデバイスのブラウザーウィンドウの幅（ピクセル単位）。 | 1、2、3など， | ENV_BrowserWidth |
| デバイス – 画面の高さ（px） | 訪問者がアクティビティへのアクセスに使用したデバイスの画面の高さ。 | 1、2、3など， | ENV_ScreenHeight |
| デバイス – スクリーン幅（px） | 訪問者がアクティビティへのアクセスに使用したデバイスの画面の幅。 | 1、2、3など， | ENV_ScreenWidth |
| オペレーティングシステム | 訪問者がアクティビティへのアクセスに使用したデバイスのオペレーティングシステム。 | [!DNL Mac OS]<br>[!DNL Windows]<br>[!DNL Linux]<br>検索ボット <br>不明なOS | ENV_OperatingSystem |
| Operating System - Version | 訪問者がアクティビティへのアクセスに使用したオペレーティングシステムのバージョン。 | [!DNL Windows] 10<br>[!DNL Mac OS] 10 | ENV_OperatingSystemVersion |
| トラフィックソース - 参照元ランディングページ URL | サイトにアクセスした際に訪問者が見た最初のページ。 | `https://www.adobe.com/ecloud.html` | ENV_Referrer |

## 地理データ {#geo}

| 属性名 | 属性の説明 | サンプル値 | システム名 |
| --- | --- | --- | --- |
| Geo - City | アクティビティにアクセスした訪問者のいる都市。 | サンフランシスコ | Geo_City |
| Geo - Country | アクティビティにアクセスした訪問者のいる国。 | ドイツ | Geo_Country |
| Geo - DMA | アクティビティにアクセスした訪問者のいる Designated Marketing Area（DMA）。 | Charlottesville | Geo_DMA |
| Geo - Latitude | アクティビティにアクセスした訪問者のいる緯度。 | 47.269<br>小数点以下3桁に丸め（約100 メートルの精度） | GEO_Latitude |
| Geo - Longitude | アクティビティにアクセスした訪問者のいる経度。 | -122.269<br>小数点以下3桁に丸め（約100 メートルの精度） | GEO_Longitude |
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
| Visitor Profile - Average Time per Visit | 訪問／セッションあたりの平均滞在時間を指定します。 これには現在のセッションは含まれません。 | ダブル、ミリ秒 | SES_TIME_PER_SESSION |
| Visitor Profile - First Visit | ユーザーが[!DNL Target]と最初にやり取りした訪問の時刻を指定します。 | ダブル、ミリ秒 | SES_PROFILE_CREATION_TIME |
| Visitor Profile - Hours since Last Visit | このアクティビティへの最後の訪問からの経過時間を指定します。 | Double （整数のみ） 1、2、3など。 | SES_HOURS_SINCE_LAST_VISIT |
| Visitor Profile - Impressions of Location/Content | 特定のアクティビティでの特定の場所／コンテンツの組み合わせに対するインプレッション数を指定します。 | Double （整数のみ） 1、2、3など。 | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| 訪問者プロファイル – 最後の[!DNL Target] インタラクション | [!DNL Target]との最後のやり取りの時間を指定します。 [!DNL Target]の現在の実装では各要求のプロファイルが更新されるため、操作は[!DNL Target]要求ごとに行われます。 | ダブル、ミリ秒 | SES_PROFILE_UPDATE_TIME |
| Visitor Profile - Pages Seen Before Activity | 訪問者がアクティビティに入るまで、現在の訪問/セッションを含む合計ページビュー（インプレッション）の数を指定します。 | Double （整数のみ） 1、2、3など。 | SES_TOTAL_PAGE_VIEWS |
| Visitor Profile - Page Views in Current Visit | 訪問者がアクティビティに入るまで、現在の訪問/セッションのページビュー数を指定します。 もっと正確に言えば、インプレッション数です。 これらのインプレッションは実際のページビューではなく、リクエストが[!DNL Target]に達した回数です。 [!DNL Target]は、タイムアウト、またはユーザーがコンテンツを受信または表示しなかった他の理由を区別できません。 | ダブル（正の整数のみ） | SES_SESSION_POSITION |
| Visitor Profile - Start of Current Visit | [!DNL Target]の現在の訪問/セッションが開始された時間を指定します。 [!DNL Target]の訪問は、アクティビティを入力せずに開始できます。 必要なのは、任意の[!DNL Target] リクエストへの呼び出しだけです。 訪問者がアクティビティに入り、スナップショットが実行されるまでしばらく時間がかかる場合があります。 | ダブル、ミリ秒 | SES_SESSION_START |
| Visitor Profile - Start of Most Recent Visit | [!DNL Target]との最後の訪問/セッションが開始された時刻を指定します。 この属性は、セッションの有効期限が切れると更新されます。<br>これが訪問者の最初のセッションである場合、結果は`LAST_SESSION_START = 0.`になります | ダブル、ミリ秒 | SES_LAST_SESSION_START |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | 以前のセッションとユーザーがアクティビティに入ってスナップショットが実行されたときの間の期間を指定します。 | ダブル、ミリ秒 | SES_RECENCY |
| Visitor Profile - Time in Visit Before Enter Activity | [!DNL Target]との最後のインタラクションと、現在の訪問が開始されたときの違いを指定します。 この属性は、ユーザーがアクティビティに入ってスナップショットが実行されるまでの訪問／セッション期間と考えることができます。<br>負の値は、セッションの開始と前回の更新時間が同じ[!DNL Target]呼び出しによってトリガーされたときに発生します。 負の値は 0（ゼロ）とみなす必要があります。 | ダブル、ミリ秒 | SES_SESSION_TIME |
| 訪問者プロファイル - 合計訪問回数 | 訪問／セッションの合計数を指定します。 現在の訪問／セッションは含まれません。 | Double （整数のみ） 1、2、3など。 | SES_TOTAL_SESSIONS |
| Visitor Profile - Total Visits to Activity | 特定のアクティビティへの訪問数を指定します。 以前の訪問がない場合、0（ゼロ）を返します。 | Double （整数のみ） 1、2、3など。 | SES_PREVIOUS_VISIT_COUNT |
| 訪問者プロファイル - コンバージョンを伴うアクティビティへの総訪問数 | 訪問中に少なくとも 1 つのコンバージョンがある場合の、特定のアクティビティへの訪問／セッションの数を指定します。 | ダブル | SES_CUMULATIVE_SUCCESSES |
| 訪問者プロファイル - コンバージョンに至らなかったアクティビティへの訪問 | 特定のアクティビティに対するコンバージョンがない訪問／セッションの数。 この値は、コンバージョンの後に 0 にリセットされます。または、コンバージョンが発生しなかった場合、-1 になります。 | Double （整数のみ） 1、2、3など。 | SES_SUCCESS_RECENCY |
