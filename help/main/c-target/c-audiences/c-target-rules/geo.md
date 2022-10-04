---
keywords: ターゲット設定;a4t;地理;ジオターゲティング;ジオターゲティングの精度;国;都道府県;市区町村;郵便番号;dma;携帯電話会社;cityコード;regionコード;countryコード;metro code;プロファイルスクリプト;ジオターゲティングプロファイルスクリプト;ジオターゲティングモバイル
description: でオーディエンスを作成する方法を説明します。 [!DNL Adobe Target] 地理的な場所に基づいてユーザーをターゲットに設定します。
title: 場所に基づいて訪問者をターゲットに設定することはできますか？
feature: Audiences
solution: Target,Analytics
exl-id: e4a71a4d-e8f3-4f94-a1a7-fd250f4d5095
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 50%

---

# 地域

でのオーディエンスの使用 [!DNL Adobe Target] 地理的な場所に基づいてユーザーをターゲットに設定します。

地域パラメーターを使用すると、訪問者の地域情報に基づいてアクティビティとエクスペリエンスをターゲット設定できます。 国、都道府県、市区町村、郵便番号、緯度、経度、DMA または携帯電話会社に基づいて訪問者を選択または除外することができます。このデータは、 [!DNL Target] リクエストに含まれ、訪問者の IP アドレスに基づいています。 他のターゲット値と同様に、これらのパラメーターを選択します。

## GeoTargeting を使用するオーディエンスの作成 {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. [!DNL Target] インターフェイスで、**[!UICONTROL オーディエンス]**／**[!UICONTROL オーディエンスを作成]**&#x200B;をクリックします。
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. ドラッグ&amp;ドロップ **[!UICONTROL 地域]** を audience builder パネルにドラッグします。

1. 「**[!UICONTROL 選択]**」をクリックし、次のいずれかのオプションを選択します。

   * [!UICONTROL 国 / 地域]
   * [!UICONTROL 都道府県]
   * [!UICONTROL 市区町村]
   * [!UICONTROL 郵便番号]
   * [!UICONTROL 経度]
   * [!UICONTROL 緯度]
   * [!UICONTROL DMA]
   * [!UICONTROL 携帯電話会社]

   mbox リクエストによって訪問者の IP アドレスが訪問（セッション）ごとに 1 回渡され、その訪問者の地域ターゲットパラメーターが解決されます。

   の場合 [!UICONTROL 携帯電話会社], [!DNL Target] は、（IP アドレスのブロックを所有する）IP アドレス登録データを使用して、 [モバイル国コード (MCC) およびモバイルネットワークコード (MNC)](https://www.mcc-mnc.com).

1. 演算子と適切な値を指定します。
1. （オプション）オーディエンス用の追加のルールを設定します。
1. 「 **[!UICONTROL 完了]**」をクリックします。

次の図に、緯度 44°以上、経度 22°未満からアクティビティにアクセスするユーザーをターゲットにするオーディエンスを示します。

![target_geo 画像](assets/target_geo.png)

## 精度 {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

GeoTargeting の精度は、複数の要因に左右されます。WiFi 接続は、携帯電話ネットワークよりも正確です。訪問者がモバイルデータ通信を使用している場合、地域ルックアップの精度は、場所、プロバイダーの [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) とのデータの関係性、およびその他の要因の影響を受ける可能性があります。携帯電話基地局ベースのネットワーク接続では、有線または WiFi 接続に正確性で劣る可能性があります。また、訪問者の IP アドレスは、訪問者の ISP の場所にマッピングされ、訪問者の実際の場所とは異なる可能性があります。 モバイルの位置情報に関するいくつかの問題は、 [位置情報 API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

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

以下を使用できます。 `profile.geolocation` の値は、オファーやプラグインなどでトークンとして直接使用できます。

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

## 地域ターゲット設定に関する FAQ {#section_DD308A53AF0F48FA8C81423580561FE7}

ジオターゲティングに関して、次のよくある質問について説明します。

### 緯度と経度を指定するには、どうすればよいですか？

* 緯度と経度の値は、度単位の数値である必要があります。
* 緯度と経度の値には、小数点以下 5 桁までの精度を指定できます。
* 緯度は -90 から 90 の間の値にする必要があります。
* 経度は -180 から 180 の間の値にする必要があります。

### モバイルデバイスでは GeoTargeting はどのように機能しますか？

ほとんどのモバイルデバイスユーザーは WiFi 経由でコンテンツにアクセスします。つまり、 [!DNL Target]の IP ベースの GeoTargeting は、デスクトップと同様に正確です。 携帯電話基地局ベースの接続では、信号が補足される基地局に基づいて訪問者の IP アドレスが決まるので、正確性に劣る場合があります。モバイルの位置情報に関するいくつかの問題は、 [位置情報 API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

### AOL 経由の訪問者は地域ターゲット設定ではどのように処理されますか?

AOL がトラフィックをプロキシする方法により、 [!DNL Target] は、国レベルでのみターゲットにできます。 例えば、フランスをターゲットにしたキャンペーンで、フランスの AOL ユーザーが正常にターゲットに設定されたとします。 しかし、パリをターゲットにしたキャンペーンでは、パリの AOL ユーザーをターゲットにすることはできません。 AOL ユーザーだけをターゲットにする場合は、地域フィールドに「aol」を設定できます。実際、米国内の AOL ユーザーをターゲットにする場合は、国と地域の 2 つのターゲット条件がそれぞれ「米国」と「aol」に正確に一致するように指定します。

### 地域ターゲット設定には、場所を微調整する機能がありますか?

* 国 - グローバル
* 州/県/地域 - グローバル
* 市区町村 - グローバル
* 郵便番号 - 米国、ドイツ、カナダ
* DMA/ITV（英国） - 米国、英国
* 携帯電話会社 - グローバル

### 別の場所からアクセスするユーザーとして、自分のキャンペーンをテストすることができますか？

* **at.js 1.*x***:IP アドレスを別の場所の IP アドレスで上書きし、 `mboxOverride.browserIp url` パラメーター。 例えば、会社が英国にあり、グローバルキャンペーンがニュージーランドのオークランドの訪問者をターゲットにする場合は、次のような URL を使用します。 `60.234.0.39` はオークランドの IP アドレスです。

   `https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

   アクティビティをテストする前に、Cookie を消去します。

   >[!NOTE]
   >
   >`mboxOverride.browserIp` は at.js 1.*x* のみで使用できます。この機能は、at.js 2.**。

* **at.js 2.*x***:IP アドレスを at.js 2.*x*、ブラウザー拡張機能/プラグイン（Chrome または Firefox 用の X-Forwarded-For ヘッダーなど）をインストールします。 この拡張機能を使用すると、ページリクエストで x-forwarded-for ヘッダーを渡すことができます。

### プエルトリコや香港などの地域はジオターゲティング構造にどのようにマッピングされますか？

プエルトリコや香港などの地域は、個別の「国」として扱われます。

### 実行 [!DNL Target] アクティビティが位置情報ターゲティング機能でターゲット設定される場合に、郵便番号などの情報をキャプチャ（および保存）しますか？

いいえ、 [!DNL Target] では、セッション中にのみ地域データを使用するので、データは破棄されます。

## トレーニングビデオ：オーディエンスの作成 ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
