---
keywords: ターゲット設定;mobile;target mobile;deviceAtlas;iPhone;iPhoneモデル;device Atlas;displaywidth;display width;display height;デバイスの種類;displayHeight;phone;タブレット;デバイスモデル
description: モバイルデバイス、Adobeの種類、デバイスのベンダー、画面の寸法（ピクセル単位）などのパラメーターに基づいて、ターゲット [!DNL Target] からモバイルデバイスをオーディエンスするデバイスを作成する方法を説明します。
title: モバイルオプションに基づいて訪問者を [!DNL Target] 設定できますか。
feature: オーディエンス
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 93%

---

# モバイル

オーディエンスを作成して、モバイルデバイス、デバイスの種類、デバイスのベンダー、画面の寸法（ピクセル単位）などのパラメーターに基づいてモバイルデバイスをターゲット設定します。

例えば、携帯電話からページに訪問するユーザーに対しては、コンピューターから訪問するユーザーとは別のコンテンツを表示するとします。この場合、モバイルオーディエンスを選択して「**[!UICONTROL 携帯電話]**」オプションを選択し、携帯電話の種類や画面のサイズ（ピクセル単位）など重要となる特定の詳細を追加します。

モバイルターゲットは、DotMobi 社のサービスである [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) から提供されます。DeviceAtlas は、メーカーやネットワーク通信業者を含む非常に多くのソースから収集したデータに基づいて構築された、モバイルデバイスの包括的なデータベースです。このデータには、大規模で正確なモバイルデバイスデータベースを構築するための検証、相互参照、妥当性確認が実施されます。

デバイス検出は、ユーザーエージェント文字列を分析することで実行されます。Apple などの一部のデバイス製造業者は、UA に十分な情報を提供しないことで、この機能を無効にしています。

例えば、Apple デバイスは、デバイスモデル専用のトークンを UA で共有しません。その結果、シンプルなキーワードベースの方法を使用して iPhone のモデル（iPhone 5S、iPhone SE、iPhone 6 など）を検出することはできません。

この問題を解決するために、Target では、次のパラメーターを使用して追加のデータを収集し、iPhone などの Apple デバイスを正確に検出します。

| パラメーター | タイプ | 説明 |
|--- |--- |--- |
| devicePixelRatio | 文字列 | ブラウザー上の物理的なピクセルとデバイスに依存しないピクセル（dips）の比率。例：「1.5」または「2」 |
| screenOrientation | 文字列 | デバイスとブラウザーの JavaScript エンジンは、デバイスオリエンテーションに対応します。横または縦にすることができます。 |
| webGLRenderer | 文字列 | グラフィックドライバーのブラウザーレンダラーです。 |

>[!NOTE]
>
>Mobile SDK を使用しているお客様は、この機能を利用するために必要なことは何もありません。at.jsを使用する顧客は、[at.js バージョン 1.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) （以降）にアップグレードする必要があります。

複数のモバイルデバイスプロパティを選択できます。OR を使用して複数の選択肢を結合できます。

（at.js または Mobile SDK を使用していない）カスタム統合を使用しているユーザーは、これらのパラメーターを手動で収集して mbox パラメーターとして渡すことができます。

1. [!DNL Target] インターフェイスで、**[!UICONTROL オーディエンス]**／**[!UICONTROL オーディエンスを作成]**&#x200B;をクリックします。
1. オーディエンスに名前を付けます。
1. **[!UICONTROL ルールを追加]**／**[!UICONTROL モバイル]**&#x200B;をクリックします。
1. 「**[!UICONTROL 選択]**」をクリックし、次のいずれかのオプションを選択します。

   * デバイスのマーケティング名
   * デバイスモデル
   * デバイスのベンダー
   * モバイルデバイス
   * 携帯電話
   * タブレット
   * OS
   * 画面の高さ（px）
   * 画面の幅 (px)

   >[!NOTE]
   >
   >iOS 12.2 で導入された新しい変更により、iPhone モデルを指定する、デバイスのマーケティング名およびデバイスモデルで定義されたルールを持つオーディエンスの作成が影響を受けます。iOS 12.2 がインストールされた iPhones を持つユーザーをターゲットにすることはできなくなりました。ただし、ユーザーが iOS 12.2 をインストールしていない場合、その iPhone モデルのターゲット設定は引き続き正常に機能します。
   >
   >以下のモデルは iOS 12.2 へのアップグレードをサポートしていないので、iOS 12.2 アップデートは、これらのモデルの識別には影響しません：iPhone、iPhone 3G、iPhone 3GS、iPhone 4、iPhone 4s、iPhone 5、iPhone 5c、iPad、iPad 2、iPad / Retina display、iPad Retina（4th Gen）、iPod Touch 4 および iPod Touch 5。

   >[!NOTE]
   >
   >[地域設定](/help/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670)を使用してモバイルデバイスの通信事業者にターゲット設定できます。

1. （オプション）「**[!UICONTROL ルールを追加]**」をクリックして、オーディエンス用の追加のルールを設定します。
1. 「**[!UICONTROL 保存]**」をクリックします。

以下の図に、Google 製のモバイルデバイスを使用する訪問者をターゲットにするオーディエンスを示します。

![モバイルデバイスをターゲット設定](assets/target_mobile.png)

## トレーニングビデオ：オーディエンスの作成

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
