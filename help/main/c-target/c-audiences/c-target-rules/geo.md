---
keywords: ターゲット設定;a4t;地理;ジオターゲティング;ジオターゲティングの精度;国;都道府県;市区町村;郵便番号;dma;携帯電話会社;cityコード;regionコード;countryコード;metro code;プロファイルスクリプト;ジオターゲティングプロファイルスクリプト;ジオターゲティングモバイル
description: でのオーディエンスを作成し、地理的な場所  [!DNL Adobe Target]  基づいてユーザーをターゲットにする方法を説明します。
title: 場所に基づいて訪問者をターゲットにできますか？
feature: Audiences
solution: Target,Analytics
exl-id: e4a71a4d-e8f3-4f94-a1a7-fd250f4d5095
source-git-commit: 195028613dec0294c816703b9145e720e3209d74
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 41%

---

# 地域

のオーディエンスを使用 [!DNL Adobe Target] て、地理的な場所に基づいてユーザーをターゲットに設定します。

ジオロケーションパラメーターを使用すると、訪問者の地域に基づいてアクティビティとエクスペリエンスをターゲット設定できます。 国、都道府県、市区町村、郵便番号、緯度、経度、DMA または携帯電話会社に基づいて訪問者を選択または除外することができます。このデータは [!DNL Target] リクエストのたびに送信され、訪問者の IP アドレスに基づいています。 他のターゲット値と同様に、これらのパラメーターを選択します。

## ジオターゲティングを使用したオーディエンスの作成 {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. [!DNL Target] インターフェイスで、**[!UICONTROL Audiences]**/**[!UICONTROL Create Audience]** をクリックします。
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. **[!UICONTROL Geo]** をオーディエンスビルダーペインにドラッグ&amp;ドロップします。

1. 「**[!UICONTROL Select]**」をクリックして、次のいずれかのオプションを選択します。

   * [!UICONTROL Country/Region]
   * [!UICONTROL State]
   * [!UICONTROL City]
   * [!UICONTROL Zip Code]
   * [!UICONTROL Longitude]
   * [!UICONTROL Latitude]
   * [!UICONTROL DMA]
   * [!UICONTROL Mobile Carrier]

   訪問者の地域情報は、[!DNL Target] 場所リクエスト（mbox リクエスト）の発信元 IP アドレスから決定されます。IP-to-geo 解決は、新しいセッションの最初の呼び出しに対して行われます。つまり、訪問者の IP アドレスが訪問のセッション中に変更された場合でも、地域情報は最初の呼び出しの IP アドレスに基づきます。

   [!UICONTROL Mobile Carrier] えば、[!DNL Target] は IP アドレス登録データ（IP アドレスのブロックを所有する人）を使用して、[ モバイルカントリーコード（MCC）およびモバイルネットワークコード MNC） ](https://www.mcc-mnc.com) を使用して適切な携帯電話会社を決定します。

1. 演算子と適切な値を指定します。
1. （任意）オーディエンスの追加ルールを設定します。
1. **[!UICONTROL Done]** をクリックします。

次の図に、緯度 44 度より大きく、経度 22 度未満からアクティビティにアクセスするユーザーをターゲットにするオーディエンスを示します。

![target_geo 画像 ](assets/target_geo.png)

## 精度 {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

GeoTargeting の精度は、複数の要因に左右されます。WiFi 接続は、携帯電話ネットワークよりも正確です。訪問者が携帯データネットワーク接続を使用している場合、位置情報の検索精度は、場所、プロバイダーと [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) とのデータ関係などの要因に影響を受ける可能性があります。 携帯電話基地局ベースのネットワーク接続では、有線または WiFi 接続に正確性で劣る可能性があります。また、訪問者の IP アドレスが訪問者の ISP の場所にマッピングされる場合がありますが、これは訪問者の実際の場所とは異なる場合があります。 モバイルの位置情報の問題には、[Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API) を使用して解決できるものもあります。

以下の表に、[DigitalEnvoy](https://www.digitalelement.com/solutions/) が有線または WiFi インターネット接続用に提供する IP ベースの地理情報の精度を示します。DigitalEnvoy は、業界で最も正確なデータを提供します。グローバルな精度は、国レベルで 99.9％を超え、市レベルでは最大 97％の正確性です。精度情報は、携帯電話基地局ベースのネットワークには適用されません。

| 国 | 都道府県 | 市区町村 | 地域 |
|--- |--- |--- |--- |
| 米国 | 99.99％ | 96％ | 94％ |
| カナダ | 99.99％ | 96％ | 94％ |
| ヨーロッパ | 99.99％ |  |  |
| 英国 | 99.99％ |  | 87％ |
| ドイツ | 99.99％ | 95％ | 93％ |
| スカンジナビア | 99％ | 90 ％代前半 | 80 ％代半ば |
| スペイン | 99.99％ | 90％前後 | 90 ％代半ばから後半 |
| アジア | 99％ | 90％代半ば | 90 ％代前半 |
| 日本 | 99.99％ | 90％代半ば | 90 ％代前半 |
| オーストラリア | 99.99％ | 94％ | 91％ |

## プロファイルスクリプトでのジオターゲティングの使用 {#section_92C93138542C4A94997E3F4BE3F5DA28}

プロファイルスクリプトで地域情報を使用できます。

例えば、次のものを使用できます。

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`

次のコードで「From North America」というターゲット式を記述することができます。

`return profile.geolocation.country == 'united states' || profile.geolocation.country == 'canada' || profile.geolocation.country == 'mexico';`

## ジオターゲティング値をトークンとして使用 {#section_E7F7FDF62C3B4934A6565D04B24655F6}

オファーやプラグインなどで、トークンとして直接 `profile.geolocation` 値を使用できます。

例えば、次のものを使用できます。

* `${profile.geolocation.country}`
* `${profile.geolocation.state}`
* `${profile.geolocation.city}`
* `${profile.geolocation.zip}`
* `${profile.geolocation.dma}`
* `${profile.geolocation.domainName}`
* `${profile.geolocation.ispName}`
* `${profile.geolocation.connectionSpeed}`
* `${profile.geolocation.mobileCarrier}`
* `${profile.geolocation.latitude}`
* `${profile.geolocation.longitude}`

## ジオターゲティングに関するよくある質問 {#section_DD308A53AF0F48FA8C81423580561FE7}

ジオターゲティングに関するよくある質問を以下に示します。

### 緯度と経度の指定方法を教えてください。

+++詳細を見る
* 緯度と経度の値は、度の数値にする必要があります。
* 緯度と経度の値の精度は、小数点以下 5 桁まで指定できます。
* 緯度は -90 から 90 の間の値にする必要があります。
* 経度は -180 から 180 の間の値にする必要があります。

+++

### ジオターゲティングはモバイルデバイスでどのように機能しますか？

+++詳細を表示
ほとんどのモバイルデバイスユーザーは、WiFi を介してコンテンツにアクセスします。つまり、[!DNL Target] の IP ベースのジオターゲティングは、デスクトップ上と同じくらい正確です。 携帯電話基地局ベースの接続では、信号が補足される基地局に基づいて訪問者の IP アドレスが決まるので、正確性に劣る場合があります。モバイルの位置情報の問題には、[Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API) を使用して解決できるものもあります。

+++

### Geo 機能は AOL からの訪問者をどのように処理しますか？

+++詳細を表示
AOL がそのトラフィックをプロキシする方法により、[!DNL Target] れらをターゲットにできるのは国レベルのみです。 例えば、フランスをターゲットにしたキャンペーンは、フランスの AOL ユーザーを正常にターゲットにします。 ただし、パリをターゲットとしたキャンペーンで、パリの AOL ユーザーが正常にターゲットとされない。 AOL ユーザーだけをターゲットにする場合は、地域フィールドに「aol」を設定できます。実際、米国内の AOL ユーザーをターゲットにする場合は、国と地域の 2 つのターゲット条件がそれぞれ「米国」と「aol」に正確に一致するように指定します。

+++

### ジオターゲティングでは、どのような場所の精度を提供しますか？

+++詳細を見る
* 国 - グローバル
* 州/県/地域 - グローバル
* 市区町村 - グローバル
* 郵便番号 - 米国、ドイツ、カナダ
* DMA/ITV（英国） - 米国、英国
* 携帯電話会社 - グローバル

+++

### 別の場所から来たユーザーであるかのようにアクティビティをテストするにはどうすればよいですか？

+++詳細を見る
* **at.js 1.*x***：別の場所の IP アドレスで IP アドレスを上書きし、`mboxOverride.browserIp url` パラメーターを使用できます。 例えば、会社が英国にあり、グローバルキャンペーンがニュージーランドのオークランドで訪問者をターゲットにしている場合、オークランドの IP アドレスが `60.234.0.39` であると仮定して、次のスタイルの URL を使用します。

  `https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

  アクティビティのテストを実行する前に、Cookie をクリアします。

  >[!NOTE]
  >
  >`mboxOverride.browserIp` は at.js 1 でサポートされています。*x* のみで使用できます。この機能は at.js 2 ではサポートされていません。**。

* **at.js 2.*x***:at.js 2 で IP アドレスを上書きします。*x*、ブラウザー拡張機能/プラグイン（Chromeまたは Firefox 用の X-Forwarded-For Header など）をインストールします。 この拡張機能を使用すると、ページリクエストで x-forwarded-for ヘッダーを渡すことができます。

+++

### プエルトリコや香港などの地域はどのようにジオターゲティング構造にマッピングされますか？

+++詳細を表示
プエルトリコ、香港およびその他の地域は、別々の「国」値として扱われます。

+++

### ジオロケーションターゲティング機能 [!DNL Target] ターゲット設定されたアクティビティの場合、郵便番号などの情報を取得（および保存）しますか？

+++詳細を表示
いいえ、セッション中だけ [!DNL Target] 地域データを使用し、データは破棄されます。

+++

## トレーニングビデオ：オーディエンスの作成 ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
