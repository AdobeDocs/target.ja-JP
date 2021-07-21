---
keywords: ターゲット設定;mobile;target mobile;deviceAtlas;iPhone;iPhoneモデル;device Atlas;displaywidth;display width;display height;デバイスの種類;displayHeight;phone;タブレット;デバイスモデル
description: ' [!DNL Adobe Target] でオーディエンスを作成し、モバイルデバイス、デバイスの種類、デバイスのベンダー、画面の寸法（ピクセル単位）などのパラメーターに基づいてモバイルデバイスをターゲットにする方法を説明します。'
title: モバイルオプションに基づいて訪問者をターゲットに設定することはできますか？
feature: オーディエンス
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 43%

---

# モバイル

[!DNL Adobe Target]でオーディエンスを作成し、モバイルデバイス、デバイスの種類、デバイスのベンダー、画面の寸法などのパラメーターに基づいてモバイルデバイスをターゲット設定します。

例えば、電話を使用してページにアクセスするユーザーに対しては、コンピューターを使用して訪問するユーザーとは異なるコンテンツを表示したい場合があります。 その場合、[!UICONTROL モバイル]オーディエンスを選択し、「**[!UICONTROL 携帯電話]**」オプションを選択します。 その後、電話の種類、画面のサイズ（ピクセル単位）など、重要な特定の詳細を追加できます。

モバイルターゲットは、DotMobi 社のサービスである [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) から提供されます。DeviceAtlas は、メーカーやネットワーク通信業者を含む非常に多くのソースから収集したデータに基づいて構築された、モバイルデバイスの包括的なデータベースです。このデータには、大規模で正確なモバイルデバイスデータベースを構築するための検証、相互参照、妥当性確認が実施されます。

デバイス検出は、ユーザーエージェント文字列を分析することで実行されます。Apple などの一部のデバイス製造業者は、UA に十分な情報を提供しないことで、この機能を無効にしています。

例えば、Apple デバイスは、デバイスモデル専用のトークンを UA で共有しません。その結果、簡単なキーワードベースの方法でiPhoneモデル（iPhone 12 Pro、iPhone 12、iPhone 11 Pro Maxなど）を検出できなくなります。

この問題を解決するために、[!DNL Target]は追加のデータを収集し、次のパラメーターを使用してiPhoneやその他のAppleデバイスを正確に検出します。

| パラメーター | タイプ | 説明 |
|--- |--- |--- |
| devicePixelRatio | 文字列 | ブラウザー上の物理的なピクセルとデバイスに依存しないピクセル（dips）の比率。例：「1.5」または「2」 |
| screenOrientation | 文字列 | デバイスとブラウザーの JavaScript エンジンは、デバイスオリエンテーションに対応します。横または縦にすることができます。 |
| webGLRenderer | 文字列 | グラフィックドライバーのブラウザーレンダラーです。 |

>[!NOTE]
>
>Mobile SDKを使用しているお客様は、この機能を適用するために何もする必要はありません。 at.jsを使用する顧客は、[at.js バージョン 1.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) （以降）にアップグレードする必要があります。

複数のモバイルデバイスプロパティを選択できます。複数の選択はOR演算子で結合されます。

（at.js または Mobile SDK を使用していない）カスタム統合を使用しているユーザーは、これらのパラメーターを手動で収集して mbox パラメーターとして渡すことができます。

1. [!DNL Target] インターフェイスで、**[!UICONTROL オーディエンス]**／**[!UICONTROL オーディエンスを作成]**&#x200B;をクリックします。
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. **[!UICONTROL Mobile]**&#x200B;をAudience Builderウィンドウにドラッグ&amp;ドロップします。
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
   >iOS 12.2で導入された新しい変更により、iPhoneモデルを指定する[!UICONTROL Device Marketing Name]および[!UICONTROL Device Model]で定義されるルールを使用したオーディエンスの作成が影響を受けます。 [!DNL Target] iOS 12.2（以降）がインストールされたiPhoneを持つユーザーをターゲットにすることはできなくなりました。ただし、iOS 12.2以降を持たないユーザーの場合、iPhoneモデルのターゲット設定は引き続き正しく機能します。
   >
   >iOS 12.2（以降）の更新は、次のモデルの識別に影響を与えません。これらのモデルはiOS 12.2へのアップグレードをサポートしていません。iPhone、iPhone 3G、iPhone 3GS、iPhone 4、iPhone 4s、iPhone 5、iPhone 5c、iPad、iPad 2、iPad / Retinaディスプレイ、iPad Retina（第4世代）、iPod Touch 4、iPod Touch 5。

   >[!NOTE]
   >
   >[地域設定](/help/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670)を使用してモバイルデバイスの通信事業者にターゲット設定できます。

1. （オプション）オーディエンス用の追加のルールを設定します。
1. 「 **[!UICONTROL 完了]**」をクリックします。

次の図に、Google製のモバイルデバイスを使用する訪問者をターゲットにするオーディエンスを示します。

![モバイルデバイスをターゲット設定](assets/target_mobile.png)

## トレーニングビデオ：オーディエンスの作成

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
