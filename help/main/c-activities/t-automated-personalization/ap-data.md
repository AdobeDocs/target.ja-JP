---
keywords: 環境データ；セッションデータ；地域データ；地理的データ；デバイスデータ；モバイルデータ；属性；プロファイル属性；パーソナライゼーションアルゴリズム；機械学習アルゴリズム
description: どのデータを収集し  [!DNL Adobe Target]  を使用して、機械学習アルゴリズムを構築するかを説明します。
title: 機械学習アルゴリズムを構築するために収集されるデータには何がありますか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: fe6a7addd3854c430798fc339741c9ae6a4efc7d
workflow-type: tm+mt
source-wordcount: '1958'
ht-degree: 52%

---

# 機械学習アルゴリズム [!DNL Target] 使用するデータ

[!DNL Adobe Target] は、様々なデータを自動的に収集し、それを基に [!UICONTROL Automated Personalization] （AP）と [!UICONTROL Auto-Target] （AT）アクティビティのパーソナライゼーションアルゴリズムを構築します。 訪問者が [!UICONTROL Automated Personalization] または [!UICONTROL Auto-Target] アクティビティに入ると、情報のスナップショットが一連の「トレーニングレコード」（パーソナライゼーションアルゴリズムが学習する訪問者データ）に渡されます。

[!DNL Target] のパーソナライゼーションアルゴリズムについて詳しくは、[ ランダムフォレストアルゴリズム ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) を参照してください。

## デフォルトの [!DNL Target] 属性カテゴリ

次の表に、[!UICONTROL Automated Personalization] やその他の [!UICONTROL Auto-Target] ソリューションの設定を行わずに、デフォルトで [!DNL Target] および [!DNL Adobe] アクティビティによって収集されるデータを示します。 この表には、[Personalization Insights レポート ](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) でこれらの属性を示すために使用される命名規則も含まれています。 入力データセットはいつでも増やすことができます。追加データのアップロード方法について詳しくは、[ パーソナライゼーションアルゴリズム用のデータ  [!DNL Target]  アップロード ](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md) を参照してください。

| データカテゴリ | システムプレフィックス | 説明 | [!UICONTROL Insights] レポートの表示名 |
| --- | --- | --- | --- |
| 環境パラメーター | 環境 | オペレーティングシステム、ブラウザー、時間帯など、ユーザーの環境に関する情報。 | ブラウザー – [ 属性名 ]<br> オペレーティングシステム - [ 値 ] |
| 地域 | 地域 | ユーザーの地域に関する情報で、IP ルックアップを通じて取得されます。 | 地域 – [ 地域属性 ] |
| モバイルデバイス | 暴徒 | ユーザーのモバイルデバイスに関する情報。 | デバイス - [device 属性 ]<br>Mobile - [mobile 属性 ] |
| [!DNL Target] レポートセグメント | セグメント | [!DNL Target] レポートで設定されたレポートセグメント。 | レポートセグメント [ セグメント名 ] |
| セッションの動作 | セス | ユーザーの行動に関する情報（表示されたページ数など）。 | 訪問者プロファイル - [ 属性名 ] |

## カスタム [!DNL Target] 属性のカテゴリ

次の表に、[!UICONTROL Automated Personalization] および [!UICONTROL Auto-Target] アクティビティによって収集されたお客様データを示します。 このデータは、お客様から提供された場合にのみ収集されます。 特定の属性名とサンプル値は、システム設定に固有です。

| データカテゴリ | システムプレフィックス | 説明 | [!UICONTROL Insights] レポートの表示名 |
| --- | --- | --- | --- |
| ページのパラメーター | BOX | [!DNL Target] への呼び出しで渡されるカスタムページパラメーター（「mbox パラメーター」）。 | カスタム - mbox パラメーター – [ パラメーター名 ] |
| [!DNL Target] profile | PRO | カスタムプロファイル属性は、API またはページパラメーターと [!DNL Target] プロファイルスクリプトを介して、[!DNL Target] プロファイルに直接アップロードされます。 | カスタム – 訪問者プロファイル - [ 属性名 ] |
| 顧客属性 | CRS | [!DNL Target][[!DNL Adobe Experience Cloud Customer Attributes Service] 経由で ](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=ja){target=_blank} プロファイルにアップロードされた顧客属性。 | カスタム – 訪問者プロファイル - [ 属性名 ] |
| URL パラメーター | URL | 現在表示されているページの URL および URL パラメーター。 | カスタム - URL パラメーター – [URL パラメーター ] |
| 参照 URL | 参照 | 参照 URL と参照 URL の任意の URL パラメーター。 | カスタム - [ 参照 URL パラメーター ] - [ パラメーター値 ] |
| [!DNL Adobe Experience Cloud] 共有オーディエンス | AAM | 他の [!DNL Target] ソリューションの [!DNL Adobe Experience Cloud] と共有されるすべてのオーディエンス（[!DNL Adobe Audience Manager][!DNL Adobe Analytics] を介した [[!DNL Experience Cloud Audience Library] や ](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=ja){target=_blank} など）。 | カスタム - Experience Cloud オーディエンス - [ オーディエンス名 ] |
| [!DNL Adobe Experience Platform Real-time CDP] オーディエンス | UPS | [!DNL Target] を介して [!UICONTROL Destinations] と共有される Platform Real-time CDP オーディエンス。 |  |


## [!DNL Target] 機械学習アルゴリズムのブロック機能

機能は機械学習アルゴリズム [!DNL Target] ブロックし、[!UICONTROL Automated Personalization] ーザーや [!UICONTROL Auto-Target] のモデルまたはアクティビティで使用されないようにすることができます。

詳しくは、[ 開発者ガイドの ](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html?lang=ja){target=_blank}Models API （ブロックリストへの登録）の概要 *[!DNL Adobe Target]を参照してください*。

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
| モバイル - OS - OS X （[!DNL Android]、[!DNL Windows] など） | ユーザーがアクティビティへのアクセスに OSX （または [!DNL Android]、[!DNL Windows] など）デバイスを使用したかどうかを指定します。 | 0 は False、1 は True | MOB_targeting.mobile.os[OS]<br> 例：MOB_targeting.mobile.osOSx、MOB_targeting.mobile.osWindows、MOB_targeting.mobile.osAndroid、MOB_targeting.mobile.osLinux |
| Mobile - Screen Height (px) | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスの画面の高さ（ピクセル単位）。 | 1、2、3 など。 | MOB_targeting.mobile.displayHeight |
| Mobile - Screen Width (px) | 訪問者がアクティビティへのアクセスに使用したモバイルデバイスの画面の幅（ピクセル単位）。 | 1、2、3 など。 | MOB_targeting.mobile.displayWidth |

## 環境データ {#env}

| 属性名 | 属性の説明 | サンプル値 | システム名 |
| --- | --- | --- | -- |
| Browser - Day of Week | 訪問者がアクティビティにアクセスしたときの曜日。 | 0 ～ 6。<br>（0 は日曜日） | ENV_DayOfWeek |
| Browser - Hour of Day | 訪問者がアクティビティにアクセスしたときの時刻。 | 0 ～ 23<br> （0 は午前 0 時） | ENV_UserHour |
| Browser - Hour of Week | 訪問者がアクティビティにアクセスしたときの週の時間。 | 0～168<br> （日曜日の午前 0 時） | ENV_WeekHour |
| Browser - Language Setting | 訪問者がアクティビティへのアクセスに使用したブラウザーで指定された言語。 | English<br>German | ENV_Language |
| Browser - Time of Day | 訪問者がアクティビティにアクセスしたときのブラウザーの時間。 | 0, 6, 12, 18<br>（0 は夜、6 は朝、<br>12 は午後、18 は夜） | ENV_LocalTimePeriod |
| Browser - Timezone | 訪問者がアクティビティにアクセスしたときのタイムゾーン。 | Pacific Time<br>Eastern Time<br>GMT | ENV_BrowserTimezoneOffsetMinutes |
| Browser - Type | 訪問者がアクティビティへのアクセスに使用したブラウザーのタイプ。 | [!DNL Chrome]<br>[!DNL Firefox]<br>[!DNL Internet Explorer]<br>[!DNL Safari]<br> その他 | ENV_Browser |
| Browser - Weekday/Weekend | 訪問者がアクティビティにアクセスしたときの作業ステータス（週末、勤務時間、平日の自由時間）。 | 土曜日と日曜日は週末です <br> 月曜日から金曜日 0900 - 1800 は営業時間 <br> 月曜日から金曜日 1800 の後 0900 は平日の自由時間です | ENV_UserHourType |
| Browser - Window Height (px) | 訪問者がアクティビティへのアクセスに使用したデバイスのブラウザーウィンドウの高さ（ピクセル単位）。 | 1、2、3 など、 | ENV_BrowserHeight |
| Browser - Window Width (px) | 訪問者がアクティビティへのアクセスに使用したデバイスのブラウザーウィンドウの幅（ピクセル単位）。 | 1、2、3 など、 | ENV_BrowserWidth |
| デバイス – 画面の高さ（px） | 訪問者がアクティビティへのアクセスに使用したデバイスの画面の高さ。 | 1、2、3 など、 | ENV_ScreenHeight |
| デバイス – 画面の幅（px） | 訪問者がアクティビティへのアクセスに使用したデバイスの画面の幅。 | 1、2、3 など、 | ENV_ScreenWidth |
| オペレーティングシステム | 訪問者がアクティビティへのアクセスに使用したデバイスのオペレーティングシステム。 | [!DNL Mac OS]<br>[!DNL Windows]<br>[!DNL Linux]<br> 検索ボット <br> 不明な OS | ENV_OperatingSystem |
| Operating System - Version | 訪問者がアクティビティへのアクセスに使用したオペレーティングシステムのバージョン。 | [!DNL Windows] 10<br>[!DNL Mac OS] 10 | ENV_OperatingSystemVersion |
| Traffic Sources - Referring Landing Page URL | サイトにアクセスした際に訪問者が見た最初のページ。 | `https://www.adobe.com/ecloud.html` | ENV_Referler |

## 地理的データ {#geo}

| 属性名 | 属性の説明 | サンプル値 | システム名 |
| --- | --- | --- | --- |
| Geo - City | アクティビティにアクセスした訪問者のいる都市。 | サンフランシスコ | Geo_City |
| Geo - Country | アクティビティにアクセスした訪問者のいる国。 | ドイツ | Geo_Country |
| Geo - DMA | アクティビティにアクセスした訪問者のいる Designated Marketing Area（DMA）。 | Charlottesville | Geo_DMA |
| Geo - Latitude | アクティビティにアクセスした訪問者のいる緯度。 | 47.269<br> 小数点以下 3 桁まで四捨五入（精度：約 100 メートル） | GEO_Latitude |
| Geo - Longitude | アクティビティにアクセスした訪問者のいる経度。 | -122.269<br> 小数点第 3 位に四捨五入（精度：約 100 メートル） | GEO_Longitue |
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
| Visitor Profile - First Visit | ユーザーが最初に訪問したときに [!DNL Target] の操作を行った時間を指定します。 | ダブル、ミリ秒 | SES_PROFILE_CREATION_TIME |
| Visitor Profile - Hours since Last Visit | このアクティビティへの最後の訪問からの経過時間を指定します。 | 倍精度浮動小数点数（正の整数のみ） 1、2、3 など。 | SES_HOURS_SINCE_LAST_VISIT |
| Visitor Profile - Impressions of Location/Content | 特定のアクティビティでの特定の場所／コンテンツの組み合わせに対するインプレッション数を指定します。 | 倍精度浮動小数点数（正の整数のみ） 1、2、3 など。 | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| 訪問者プロファイル – 前回の [!DNL Target] インタラクション | [!DNL Target] との最後のインタラクションの時間を指定します。 インタラクションは [!DNL Target] リクエストのたびに発生します。これは、[!DNL Target] の現在の実装がリクエストごとにプロファイルを更新するからです。 | ダブル、ミリ秒 | SES_PROFILE_UPDATE_TIME |
| Visitor Profile - Pages Seen Before Activity | 訪問者がアクティビティに入るまで、現在の訪問/セッションを含む、合計ページビュー（インプレッション）数を指定します。 | 倍精度浮動小数点数（正の整数のみ） 1、2、3 など。 | SES_TOTAL_PAGE_VIEWS |
| Visitor Profile - Page Views in Current Visit | 訪問者がアクティビティに入るまで、現在の訪問/セッションのページビュー数を指定します。 もっと正確に言えば、インプレッション数です。これらのインプレッションは実際のページビューではなく、リクエストが [!DNL Target] に到達した回数になります。 [!DNL Target] は、ユーザーがコンテンツを受信または表示しなかったタイムアウトやその他の理由を区別できません。 | ダブル（正の整数のみ） | SES_SESSION_POSITION |
| Visitor Profile - Start of Current Visit | [!DNL Target] を含む現在の訪問/セッションが開始した時刻を指定します。 [!DNL Target] を使用した訪問は、アクティビティを入力せずに開始できます。 必要なのは、[!DNL Target] リクエストを呼び出すことだけです。 訪問者がアクティビティに入ってスナップショットが作成されるまでしばらく時間がかかる場合があります。 | ダブル、ミリ秒 | SES_SESSION_START |
| Visitor Profile - Start of Most Recent Visit | [!DNL Target] との最後の訪問/セッションが開始された時刻を指定します。 この属性は、セッションの有効期限が切れると更新されます。<br> 訪問者が初めてのセッションの場合は、`LAST_SESSION_START = 0.` が発生します | ダブル、ミリ秒 | SES_LAST_SESSION_START |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | 以前のセッションとユーザーがアクティビティに入ってスナップショットが実行されたときの間の期間を指定します。 | ダブル、ミリ秒 | SES_RECENCY |
| Visitor Profile - Time in Visit Before Enter Activity | [!DNL Target] との最後のインタラクションと、現在の訪問がいつ開始されたかの違いを指定します。 この属性は、ユーザーがアクティビティに入ってスナップショットが実行されるまでの訪問／セッション期間と考えることができます。<br> 負の値は、セッションの開始と最後の更新時間が同じ [!DNL Target] 呼び出しでトリガーされた場合に発生します。 負の値は 0（ゼロ）とみなす必要があります。 | ダブル、ミリ秒 | SES_SESSION_TIME |
| 訪問者プロファイル - 合計訪問回数 | 訪問／セッションの合計数を指定します。現在の訪問／セッションは含まれません。 | 倍精度浮動小数点数（正の整数のみ） 1、2、3 など。 | SES_TOTAL_SESSIONS |
| Visitor Profile - Total Visits to Activity | 特定のアクティビティへの訪問数を指定します。以前の訪問がない場合、0（ゼロ）を返します。 | 倍精度浮動小数点数（正の整数のみ） 1、2、3 など。 | SES_PREVIOUS_VISIT_COUNT |
| 訪問者プロファイル - コンバージョンを伴うアクティビティへの総訪問数 | 訪問中に少なくとも 1 つのコンバージョンがある場合の、特定のアクティビティへの訪問／セッションの数を指定します。 | ダブル | SES_CUMULATIVE_SUCCESSES |
| 訪問者プロファイル - コンバージョンに至らなかったアクティビティへの訪問 | 特定のアクティビティに対するコンバージョンがない訪問／セッションの数。この値は、コンバージョンの後に 0 にリセットされます。または、コンバージョンが発生しなかった場合、-1 になります。 | 倍精度浮動小数点数（正の整数のみ） 1、2、3 など。 | SES_SUCCESS_RECENCY |
