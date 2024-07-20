---
keywords: ターゲット設定;mobile;target mobile;deviceAtlas;iPhone;iPhoneモデル;device Atlas;displaywidth;display width;display height;デバイスの種類;displayHeight;phone;タブレット;デバイスモデル
description: でオーディエンスを作成してモバイルデバイス  [!DNL Adobe Target]  ターゲットにする方法を説明します。
title: モバイルオプションに基づいて訪問者をターゲットにできますか？
feature: Audiences
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 34%

---

# モバイル

モバイルデバイス、デバイスのタイプ、デバイスのベンダー、画面の寸法などのパラメーターに基づいてモバイルデバイスをターゲティングするた [!DNL Adobe Target] に、オーディエンスを作成します。

例えば、電話を使用してページを訪問したユーザーには、コンピューターを使用して訪問したユーザーとは異なるコンテンツを表示する場合があります。 この場合は、[!UICONTROL Mobile] オーディエンスを選択してから、「**[!UICONTROL Is Mobile Phone]**」オプションを選択します。 その後、電話の種類、画面のサイズ（ピクセル単位）など、重要な特定の詳細を追加できます。

モバイルターゲットは、DotMobi 社のサービスである [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) から提供されます。DeviceAtlas は、メーカーやネットワーク通信業者を含む非常に多くのソースから収集したデータに基づいて構築された、モバイルデバイスの包括的なデータベースです。このデータには、大規模で正確なモバイルデバイスデータベースを構築するための検証、相互参照、妥当性確認が実施されます。

デバイス検出は、ユーザーエージェント文字列を分析することで実行されます。Apple などの一部のデバイス製造業者は、UA に十分な情報を提供しないことで、この機能を無効にしています。

例えば、Apple デバイスは、デバイスモデル専用のトークンを UA で共有しません。その結果、単純なキーワードベースの手法では、iPhone モデル（iPhone 12 Pro、iPhone 12、iPhone 11 Pro Max など）を検出できません。

この問題を解決するために、[!DNL Target] では、iPhone やその他のApple デバイスを次のパラメーターを使用して正確に検出するための追加データを収集します。

| パラメーター | タイプ | 説明 |
|--- |--- |--- |
| devicePixelRatio | 文字列 | ブラウザー上の物理ピクセルとデバイスに依存しないピクセル（dip）の比率。 例えば、「1.5」や「2」です |
| screenOrientation | 文字列 | デバイスとブラウザーの JavaScript エンジンは、デバイスオリエンテーションに対応します。横または縦にすることができます。 |
| webGLRenderer | 文字列 | グラフィックドライバーのブラウザーレンダラーです。 |

>[!NOTE]
>
>Mobile SDK を使用しているお客様は、この機能を適用するために何もする必要はありません。 at.js を使用しているお客様は、[at.js バージョン 1.5.0 以降にアップグレード ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} する必要があります。

複数のモバイルデバイスプロパティを選択できます。複数の選択項目は、OR 演算子で結合されます。

（at.js または Mobile SDK を使用していない）カスタム統合を使用しているユーザーは、これらのパラメーターを手動で収集して mbox パラメーターとして渡すことができます。

1. [!DNL Target] インターフェイスで、**[!UICONTROL Audiences]**/**[!UICONTROL Create Audience]** をクリックします。
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. **[!UICONTROL Mobile]** をオーディエンスビルダーペインにドラッグ&amp;ドロップします。
1. 「**[!UICONTROL Select]**」をクリックして、次のいずれかのオプションを選択します。

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

1. （任意）オーディエンスの追加ルールを設定します。
1. **[!UICONTROL Done]** をクリックします。

次の図は、Googleが製造するモバイルデバイスを使用して、訪問者をターゲティングするオーディエンスを示しています。

![モバイルデバイスをターゲット設定](assets/target_mobile.png)

## 注意点

モバイルデバイスをターゲティングする際は、次の情報を考慮してください。

### iOS 12.2 以降を実行するデバイスのターゲティング

iOS 12.2 で導入された新しい変更により、[!UICONTROL Device Marketing Name] と [!UICONTROL Device Model] で定義され、iPhone モデルを指定するルールを含むオーディエンスの作成に影響が及びます。 iOS 12.2 （[!DNL Target] 降）がインストールされた iPhone を使用しているユーザーをターゲットに設定できなくなりました。 ただし、これらのユーザーがiOS 12.2 （またはそれ以降）を持っていない場合、iPhone モデルのターゲット設定は引き続き正しく機能します。

iOS 12.2 （以降）のアップデートは、iOS 12.2 へのアップグレードをサポートしていないので、次のモデルの ID には影響しません。これらのモデル：iPhone、iPhone 3G、iPhone 3GS、iPhone 4、iPhone 4s、iPhone 5、iPhone 5c、iPad、iPad 2、iPad/Retina ディスプレイ、iPad Retina （第 4 世代）、iPod Touch 4、iPod Touch 5

### Safari 14.0.2 以降を実行するデバイスのターゲティング

macOSで Safari バージョン 14.0.2 （またはそれ以降）が稼働しているデバイスをモバイルルールを使用してターゲティングする場合、Appleのユーザーエージェントと DeviceAtlas に関する既知の問題が原因で、[!DNL Target] ではMacおよびiPad デバイス上の Safari を誤って識別します。 この問題は今後対処される予定です。

## トレーニングビデオ: オーディエンスの作成

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
