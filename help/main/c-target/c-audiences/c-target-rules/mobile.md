---
keywords: ターゲティング;mobile;target mobile;deviceAtlas;iPhone;iPhoneモデル;device Atlas;displaywidth;display width;display height;デバイスの種類;displayHeight;phone;タブレット;デバイスモデル
description: ターゲットモバイルデバイスに [!DNL Adobe Target] でオーディエンスを作成する方法について説明します。
title: モバイルオプションに基づいて訪問者をターゲティングできますか？
feature: Audiences
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
TQID: https://experienceleague.adobe.com/oCyCtd21XayR3G4ClrQwyqcrgyxS4nmUONE-iIwavOY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 707
ht-degree: 39%

---

# モバイル

モバイルデバイス、デバイスの種類、デバイスベンダー、画面サイズなどのパラメーターにもとづいて、ターゲットモバイルデバイスに[!DNL Adobe Target]でオーディエンスを作成します。

例えば、PCを使用して自社ページにアクセスしたオーディエンスとは異なるコンテンツを表示したい場合があります。 その場合、[!UICONTROL Mobile] オーディエンスを選択してから、**[!UICONTROL Is Mobile Phone]** オプションを選択できます。 次に、電話の種類、画面のサイズ（ピクセル単位）など、重要な特定の詳細を追加できます。

モバイルターゲットは、DotMobi 社のサービスである [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) から提供されます。 DeviceAtlas は、メーカーやネットワーク通信業者を含む非常に多くのソースから収集したデータに基づいて構築された、モバイルデバイスの包括的なデータベースです。 このデータには、大規模で正確なモバイルデバイスデータベースを構築するための検証、相互参照、妥当性確認が実施されます。

デバイス検出は、ユーザーエージェント文字列を分析することで実行されます。 Apple などの一部のデバイス製造業者は、UA に十分な情報を提供しないことで、この機能を無効にしています。

例えば、Apple デバイスは、デバイスモデル専用のトークンを UA で共有しません。 その結果、iPhone モデル（iPhone 12 Pro、iPhone 12、iPhone 11 Pro Maxなど）を簡単なキーワードベースの方法で検出できなくなります。

この問題を解決するために、[!DNL Target]は次のパラメーターを使用して、iPhoneやその他のApple デバイスを正確に検出するための追加データを収集します。

| パラメーター | タイプ | 説明 |
|--- |--- |--- |
| devicePixelRatio | 文字列 | ブラウザー上の物理的なピクセルとデバイスに依存しないピクセル（dips）の比率。 例えば、「1.5」や「2」などです |
| screenOrientation | 文字列 | デバイスとブラウザーの JavaScript エンジンは、デバイスオリエンテーションに対応します。 横または縦にすることができます。 |
| webGLRenderer | 文字列 | グラフィックドライバーのブラウザーレンダラーです。 |

>[!NOTE]
>
>Mobile SDKをご利用のお客様は、この機能を適用するために何もする必要はありません。 at.jsを使用する顧客は、[at.js バージョン 1.5.0](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} （以降）にアップグレードする必要があります。

複数のモバイルデバイスプロパティを選択できます。 複数の選択範囲は、OR演算子で結合されます。

（at.js または Mobile SDK を使用していない）カスタム統合を使用しているユーザーは、これらのパラメーターを手動で収集して mbox パラメーターとして渡すことができます。

1. [!DNL Target] インターフェイスで、「**[!UICONTROL オーディエンス]**」 > 「**[!UICONTROL オーディエンスを作成]**」をクリックします。
1. オーディエンスに名前を付け、オプションの説明を追加します。
1. **[!UICONTROL Mobile]**&#x200B;をオーディエンスビルダーペインにドラッグ&amp;ドロップします。
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

1. （オプション）オーディエンスの追加ルールを設定します。
1. 「**[!UICONTROL Done]**」をクリックします。

次の図は、Googleで製造されたモバイルデバイスを使用する訪問者をターゲットとするオーディエンスを示しています。

![モバイルデバイスをターゲット設定](assets/target_mobile.png)

## 注意点

モバイルデバイスをターゲティングする場合は、次の情報を考慮してください。

### IOS 12.2以降を実行しているデバイスをターゲットにする

IOS 12.2で導入された新しい変更により、[!UICONTROL Device Marketing Name]および[!UICONTROL Device Model]によって定義されたルールを使用して、iPhone モデルを指定するオーディエンスを作成することが影響を受けます。 [!DNL Target]は、iOS 12.2以降がインストールされたiPhoneを持つユーザーをターゲットにできなくなりました。 ただし、これらのユーザーがiOS 12.2 （またはそれ以降）を持っていない場合、iPhone モデルのターゲティングは引き続き正しく機能します。

IOS 12.2 （以降）のアップデートは、以下のモデルの識別には影響しません。これらのモデルは、iPhone、iPhone 3G、iPhone 3GS、iPhone 4、iPhone 4s、iPhone 5、iPhone 5c、iPad、iPad 2、iPad / Retina display、iPad Retina （第4世代）、iPod Touch 4、およびiPod Touch 5へのアップグレードをサポートしていないためです。

### Safari 14.0.2以降を実行しているデバイスをターゲットにする

MacOSでSafari バージョン 14.0.2 （またはそれ以降）を実行しているデバイスにモバイルルールを使用する場合、AppleのユーザーエージェントとDeviceAtlasに関する既知の問題により、[!DNL Target]はMacおよびiPad デバイスでSafariを誤って識別します。 この問題は将来対処されるだろう。

## トレーニングビデオ: オーディエンスの作成

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
