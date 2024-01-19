---
keywords: ターゲット設定;mobile;target mobile;deviceAtlas;iPhone;iPhoneモデル;device Atlas;displaywidth;display width;display height;デバイスの種類;displayHeight;phone;タブレット;デバイスモデル
description: でオーディエンスを作成する方法を説明します。 [!DNL Adobe Target] モバイルデバイスをターゲットに設定します。
title: モバイルオプションに基づいて訪問者をターゲットに設定することはできますか？
feature: Audiences
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 34%

---

# モバイル

でのオーディエンスの作成 [!DNL Adobe Target] を使用して、モバイルデバイス、デバイスの種類、デバイスのベンダー、画面の寸法などのパラメーターに基づいてモバイルデバイスをターゲット設定します。

例えば、電話を使用してページにアクセスするユーザーに対しては、コンピューターを使用して訪問した場合とは異なるコンテンツを表示したい場合があります。 この場合、 [!UICONTROL モバイル] オーディエンスを選択し、 **[!UICONTROL 携帯電話]** オプション。 その後、電話の種類、画面のサイズ（ピクセル単位）など、重要な特定の詳細を追加できます。

モバイルターゲットは、DotMobi 社のサービスである [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) から提供されます。DeviceAtlas は、メーカーやネットワーク通信業者を含む非常に多くのソースから収集したデータに基づいて構築された、モバイルデバイスの包括的なデータベースです。このデータには、大規模で正確なモバイルデバイスデータベースを構築するための検証、相互参照、妥当性確認が実施されます。

デバイス検出は、ユーザーエージェント文字列を分析することで実行されます。Apple などの一部のデバイス製造業者は、UA に十分な情報を提供しないことで、この機能を無効にしています。

例えば、Apple デバイスは、デバイスモデル専用のトークンを UA で共有しません。その結果、単純なキーワードベースの方法ではiPhoneモデル (iPhone 12 Pro、iPhone 12、iPhone 11 Pro Max など ) を検出できなくなります。

この問題を解決するには、 [!DNL Target] は、次のパラメーターを使用して、追加のデータを収集し、iPhone やその他のAppleデバイスを正確に検出します。

| パラメーター | タイプ | 説明 |
|--- |--- |--- |
| devicePixelRatio | 文字列 | ブラウザー上の物理ピクセルとデバイスに依存しないピクセル (dips) の比率です。 例：「1.5」や「2」 |
| screenOrientation | 文字列 | デバイスとブラウザーの JavaScript エンジンは、デバイスオリエンテーションに対応します。横または縦にすることができます。 |
| webGLRenderer | 文字列 | グラフィックドライバーのブラウザーレンダラーです。 |

>[!NOTE]
>
>Mobile SDK を使用しているお客様は、この機能を適用するために何もする必要はありません。 at.js を使用するお客様は、 [at.js バージョン 1.5.0 へのアップグレード](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} （またはそれ以降）。

複数のモバイルデバイスプロパティを選択できます。複数の選択は、OR 演算子で結合されます。

（at.js または Mobile SDK を使用していない）カスタム統合を使用しているユーザーは、これらのパラメーターを手動で収集して mbox パラメーターとして渡すことができます。

1. Adobe Analytics の [!DNL Target] インタフェース、クリック **[!UICONTROL オーディエンス]** > **[!UICONTROL オーディエンスを作成]**.
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. ドラッグ&amp;ドロップ **[!UICONTROL モバイル]** を audience builder パネルにドラッグします。
1. 「**[!UICONTROL 選択]**」をクリックして、次のいずれかのオプションを選択します。

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
   >[地域設定](/help/main/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670)を使用してモバイルデバイスの通信事業者にターゲット設定できます。

1. （オプション）オーディエンス用の追加のルールを設定します。
1. 「**[!UICONTROL Done]**」をクリックします。

以下の図に、Google製のモバイルデバイスを使用する訪問者をターゲティングするオーディエンスを示します。

![モバイルデバイスをターゲット設定](assets/target_mobile.png)

## 注意点

モバイルデバイスをターゲット設定する際には、次の情報を考慮してください。

### iOS 12.2 以降を実行しているデバイスのターゲティング

iOS 12.2 で導入された新しい変更により、で定義されたルールを使用したオーディエンスの作成 [!UICONTROL デバイスのマーケティング名] および [!UICONTROL デバイスモデル] 「 iPhone Models 」を指定する処理が影響を受けます。 [!DNL Target] は、iOS 12.2（以降）がインストールされた iPhones を持つユーザーをターゲットにできなくなりました。 ただし、ユーザーがiOS 12.2（またはそれ以降）を持っていない場合、iPhoneモデルのターゲティングは引き続き正しく機能します。

iOS 12.2（またはそれ以降）の更新は、iOS 12.2 へのアップグレードをサポートしていないので、次のモデルの識別に影響しません。 iPhone、iPhone 3G、iPhone 3GS、iPhone 4、iPhone 4s、iPhone 5、iPhone 5c、iPad 2、iPad/Retina ディスプレイ、iPad（第 4 世代）、iPodTouch 4、iPodPodTouch5.

### Safari 14.0.2 以降を実行するデバイスのターゲティング

モバイルルールを使用して、macOS上で Safari バージョン 14.0.2（またはそれ以降）を実行しているデバイスをターゲットにする場合、Appleのユーザーエージェントと DeviceAtlas に関する既知の問題が原因で、 [!DNL Target] は、MacおよびiPadデバイス上の Safari を誤って識別します。 この問題は、今後対応する予定です。

## トレーニングビデオ: オーディエンスの作成

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
