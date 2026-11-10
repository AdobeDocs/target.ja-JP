---
title: IOS統合ガイドのフラグ拡張機能
description: Flags拡張機能をiOS上のAdobe Experience Platform Mobile SDKと統合する方法について説明します。
badge: label="Beta" type="Informative"
hide: true
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: c1fafcfcd7d5d22781abdd10e6eb3c2b84136c2d
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 3%
---
# IOSのフラグ拡張機能 {#ios-extension-integration-guide}

このガイドでは、iOS上のAdobe Experience Platform Mobile SDKにFlags拡張機能を統合する方法について説明します。 ソースコードは、[aepsdk-flags-ios](https://github.com/adobe/aepsdk-flags-ios) リポジトリで入手できます。

## 前提条件 {#prerequisites}

まず、次の項目を確認してください。

* iOS 12.0以降、およびSwift 5.7以降
* [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)のモバイルプロパティ
* 次の拡張機能がモバイルプロパティにインストールされ、設定されています。

  | 拡張子 | 説明 | SDKの最小バージョン |
  |---|---|---|
  | [&#x200B; モバイルコア &#x200B;](https://developer.adobe.com/client-sdks/home/base/mobile-core/) | 設定とイベント処理 | AEPCore 5.8.0 |
  | [ライフサイクル](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/) | アプリケーションライフサイクルデータ | AEPCoreと同じ |
  | [Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/) | Adobe Experience Platform Edge Networkとの連携。 データストリームが必要です。 | AEPEdge 5.0.2 |
  | Edge Network[&#128279;](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/)のID | Edge NetworkのID管理 | AEPEdgeIdentity 5.0.0 |
  | [&#x200B; フラグ &#x200B;](https://experienceleague.adobe.com/ja/docs/target/flags/home) | 機能フラグの評価 | [&#x200B; インストール &#x200B;](#installation)を参照 |

## データ収集でのフラグの設定 {#configure}

### 拡張機能のインストール {#install-extension}

1. [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)にログインします。

1. 「**[!UICONTROL タグ]**」メニューを選択し、モバイルプロパティを選択します。

1. **[!UICONTROL 拡張機能]** > **[!UICONTROL カタログ]**&#x200B;に移動します。

1. **[!DNL Adobe Flags]**&#x200B;を検索し、**[!UICONTROL インストール]**&#x200B;を選択します。

   ![](../assets/extension-install.png)

1. 拡張機能の設定を行います。

   * **[!UICONTROL Sandbox]**: フラグ設定を含むAdobe Experience Platform サンドボックス。
   * **[!UICONTROL アプリケーション ID]**: フラグ内のアプリケーションの識別子。

1. **[!UICONTROL 保存]**&#x200B;を選択します。

1. [公開プロセス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview)に従って、設定を更新します。

### 環境ファイル IDの取得 {#environment-file-id}

1. モバイルプロパティで、**[!UICONTROL 環境]**&#x200B;に移動します。

1. 選択した環境の&#x200B;**[!UICONTROL Install]**&#x200B;列でボックスアイコンを選択します。

   ![](../assets/extension-install-2.png)

1. **[!UICONTROL モバイルインストール手順]** ダイアログで、**[!UICONTROL 環境ファイル ID]**&#x200B;をコピーします。

   ![](../assets/extension-install-3.png)

## インストール {#installation}

Swift パッケージマネージャーまたはXCFrameworkを使用して拡張機能を追加します。 アプリターゲットごとに1つのメソッドを使用します。

### Swift パッケージマネージャー {#swift-package-manager}

Xcodeの場合：

1. 「**ファイル**」 > 「**パッケージ依存関係を追加**」を選択します。

1. パッケージ URLを入力してください：`https://github.com/adobe/aepsdk-flags-ios.git`

1. バージョンルールの場合、**正確なバージョン**&#x200B;を選択し、[&#x200B; リリースページ &#x200B;](https://github.com/adobe/aepsdk-flags-ios/releases)から最新バージョンを入力します。

1. `AEPFlags` ライブラリをアプリターゲットに追加します。

1. 拡張機能が依存するAdobe パッケージを追加し、そのライブラリをアプリターゲットに追加します。

   * `https://github.com/adobe/aepsdk-core-ios.git`: `AEPCore`、`AEPLifecycle`、`AEPServices`
   * `https://github.com/adobe/aepsdk-edge-ios.git`: `AEPEdge`
   * `https://github.com/adobe/aepsdk-edgeidentity-ios.git`: `AEPEdgeIdentity`

プロジェクトで`Package.swift` ファイルを使用している場合は、代わりにそこに依存関係を追加します。 `<latest-version>`をリリースページの最新バージョンに置き換えます。

```swift
dependencies: [
    .package(url: "https://github.com/adobe/aepsdk-flags-ios.git", exact: "<latest-version>"),
    .package(url: "https://github.com/adobe/aepsdk-core-ios.git", .upToNextMajor(from: "5.8.0")),
    .package(url: "https://github.com/adobe/aepsdk-edge-ios.git", .upToNextMajor(from: "5.0.2")),
    .package(url: "https://github.com/adobe/aepsdk-edgeidentity-ios.git", .upToNextMajor(from: "5.0.0"))
],
targets: [
    .target(
        name: "YourTarget",
        dependencies: [
            .product(name: "AEPFlags", package: "aepsdk-flags-ios"),
            .product(name: "AEPCore", package: "aepsdk-core-ios"),
            .product(name: "AEPLifecycle", package: "aepsdk-core-ios"),
            .product(name: "AEPServices", package: "aepsdk-core-ios"),
            .product(name: "AEPEdge", package: "aepsdk-edge-ios"),
            .product(name: "AEPEdgeIdentity", package: "aepsdk-edgeidentity-ios")
        ]
    )
]
```

### XCFramework {#xcframework}

1. [&#x200B; リリースページ &#x200B;](https://github.com/adobe/aepsdk-flags-ios/releases)から、`AEPFlags-<version>.xcframework.zip`をダウンロードして解凍します。

1. 各リポジトリのリリースページから、拡張機能が依存するXCFrameworksをダウンロードします。

   * [aepsdk-core-ios リリース &#x200B;](https://github.com/adobe/aepsdk-core-ios/releases): `AEPCore`、`AEPServices`、`AEPLifecycle`および`AEPRulesEngine`
   * [aepsdk-edge-ios リリース &#x200B;](https://github.com/adobe/aepsdk-edge-ios/releases): `AEPEdge`
   * [aepsdk-edgeidentity-ios リリース &#x200B;](https://github.com/adobe/aepsdk-edgeidentity-ios/releases): `AEPEdgeIdentity`

1. Xcodeで、アプリターゲットを選択し、**一般** > **フレームワーク、ライブラリ、および埋め込みコンテンツ**&#x200B;を開きます。

1. `AEPFlags.xcframework`とすべての依存XCFrameworksを追加します。

1. 各フレームワークを&#x200B;**Embed &amp; Sign**&#x200B;に設定します。

## SDKの初期化 {#initialize-sdk}

Flags拡張機能を登録し、モバイルプロパティからEnvironment File IDを使用してSDKを初期化します。 `MobileCore.initialize`はフラグ拡張機能を登録しません。最初に登録してください。

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPCore
import AEPFlags
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        MobileCore.registerExtensions([Flag.self])
        MobileCore.initialize(appId: "<your-environment-file-id>")
        return true
    }
}
```

>[!TAB Objective-C]

```objc
@import AEPCore;
@import AEPFlags;

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [AEPMobileCore registerExtensions:@[AEPMobileFlag.class] completion:nil];
    [AEPMobileCore initializeWithAppId:@"<your-environment-file-id>" completion:nil];
    return YES;
}
```

>[!ENDTABS]

### 拡張機能を手動で登録 {#register-manually}

拡張機能を登録する場合は、それらをすべて登録します。 アプリがフォアグラウンドに入ったときに`MobileCore.lifecycleStart`を呼び出し、バックグラウンドに入ったときに`MobileCore.lifecyclePause`を呼び出します。

アプリでシーンを使用する場合は、代わりに`sceneWillEnterForeground(_:)`と`sceneDidEnterBackground(_:)`でこれらの呼び出しを行います。

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPCore
import AEPEdge
import AEPEdgeIdentity
import AEPFlags
import AEPLifecycle
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        MobileCore.registerExtensions([
            Lifecycle.self,
            Edge.self,
            AEPEdgeIdentity.Identity.self,
            Flag.self
        ]) {
            MobileCore.configureWith(appId: "<your-environment-file-id>")
            DispatchQueue.main.async {
                if application.applicationState != .background {
                    MobileCore.lifecycleStart(additionalContextData: nil)
                }
            }
        }
        return true
    }

    func applicationWillEnterForeground(_ application: UIApplication) {
        MobileCore.lifecycleStart(additionalContextData: nil)
    }

    func applicationDidEnterBackground(_ application: UIApplication) {
        MobileCore.lifecyclePause()
    }
}
```

>[!TAB Objective-C]

```objc
@import AEPCore;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPFlags;
@import AEPLifecycle;

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [AEPMobileCore registerExtensions:@[
        AEPMobileLifecycle.class,
        AEPMobileEdge.class,
        AEPMobileEdgeIdentity.class,
        AEPMobileFlag.class
    ] completion:^{
        [AEPMobileCore configureWithAppId:@"<your-environment-file-id>"];
        dispatch_async(dispatch_get_main_queue(), ^{
            if (application.applicationState != UIApplicationStateBackground) {
                [AEPMobileCore lifecycleStart:nil];
            }
        });
    }];
    return YES;
}

- (void)applicationWillEnterForeground:(UIApplication *)application {
    [AEPMobileCore lifecycleStart:nil];
}

- (void)applicationDidEnterBackground:(UIApplication *)application {
    [AEPMobileCore lifecyclePause];
}
```

>[!ENDTABS]

## 評価コンテキスト {#evaluation-context}

すべての評価呼び出しには`FeatureEvaluationContext`が必要です。 フラグのターゲティングルールが使用する属性を保持します。

| パラメーター | 必須 | 説明 |
|---|---|---|
| `attributes` | × | `[String: [String]]`. 各キーは、フラグターゲティングルールで使用される属性名です。 各値は、現在のユーザーの値のリストです。 |

* フラグで定義したターゲティングルールに一致する属性名と値を使用します。
* ビルダーごとに1回まで`withAttributes`を呼び出します。 2回目の呼び出しはアプリを終了します。
* 属性なしで評価するには、`withAttributes`を呼び出さずに`build()`を呼び出します。

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPFlags

let context = FeatureEvaluationContext.builder()
    .withAttributes([
        "locale": ["en_US"],
        "appVersion": ["3.0.0"]
    ])
    .build()
```

>[!TAB Objective-C]

```objc
@import AEPFlags;

AEPFeatureEvaluationContext *context = [[[AEPFeatureEvaluationContext builder]
    withAttributes:@{
        @"locale": @[@"en_US"],
        @"appVersion": @[@"3.0.0"]
    }]
    build];
```

>[!ENDTABS]

## カスタム ID {#custom-identity}

Flags拡張機能は、ID解決にIdentity for Edge Network拡張機能を使用します。 機能フラグをカスタム ID （CRM IDやロイヤルティ IDなど）でコホートできるため、バリエーションの分割と分析を、アプリケーションにとって重要なIDに結び付けることができます。

機能フラグの作成時に、フラグ UIでカスタム ID名前空間を選択する必要があります。 そのIDに対してフラグを評価するには、一致する名前空間を使用して、デバイス上のEdge ID `identityMap`に同じIDが存在する必要があります。 Edge Network `updateIdentities` APIのIDを実行時に指定します。

### ID マップへのカスタム IDの追加 {#add-identity}

機能フラグで設定された同じ名前空間の下にIDを追加します。

次の動作に注意してください。

* 名前空間は、大文字と小文字を含め、フラグに設定されている名前空間と正確に一致する必要があります。
* 名前空間に複数のIDがある場合は、プライマリとしてマークされたものが使用されます。 プライマリとしてマークされていない場合は、最初のものを使用します。
* IDが見つからない場合、呼び出しは失敗しません。 ユーザーは、現在のアプリセッションに対してのみランダムにバリアントに割り当てられ、アプリの再起動後に別のバリアントに割り当てることができます。 IDを使用するフラグを評価する前に、IDを設定します。

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPEdgeIdentity

let identityMap = IdentityMap()
identityMap.add(
    item: IdentityItem(id: "1111", authenticatedState: .authenticated, primary: true),
    withNamespace: "userCRMId" // must match the namespace configured on the feature flag
)
Identity.updateIdentities(with: identityMap)
```

>[!TAB Objective-C]

```objc
@import AEPEdgeIdentity;

AEPIdentityItem *item = [[AEPIdentityItem alloc] initWithId:@"1111"
                                         authenticatedState:AEPAuthenticatedStateAuthenticated
                                                    primary:YES];
AEPIdentityMap *identityMap = [[AEPIdentityMap alloc] init];
[identityMap addItem:item withNamespace:@"userCRMId"]; // must match the namespace configured on the feature flag
[AEPMobileEdgeIdentity updateIdentities:identityMap];
```

>[!ENDTABS]


## API リファレンス {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

現在のユーザーに対して機能が有効になっているかどうかを確認します。 機能が存在し、ユーザーがターゲティングルールと一致し、ユーザーがコントロールグループに属していない場合、結果は`true`になります。 それ以外の場合、結果は`false`です。

>[!BEGINTABS]

>[!TAB Swift]

```swift
static func isFeatureEnabled(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void,
    errorCallback: ((AEPError) -> Void)?
)
```

>[!TAB Objective-C]

```objc
+ (void)isFeatureEnabled:(NSString *)featureKey
       evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
              completion:(void (^)(BOOL))completion
           errorCallback:(void (^ _Nullable)(enum AEPError))errorCallback;
```

>[!ENDTABS]

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | 文字列 | フラグで評価する機能キー |
| `evaluationContext` | FeatureEvaluationContext | 必要に応じてターゲティング属性を含めます。空のコンテキストには`FeatureEvaluationContext.builder().build()`を使用します。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。 |
| `completion` | `(Bool) -> Void` | 機能が有効になっている場合は`true`で呼び出され、それ以外の場合は`false`です。 |
| `errorCallback` | `((AEPError) -> Void)?` | オプション。 空のキー、設定の欠落、評価の失敗、タイムアウトなど、実際のエラーに対してのみ呼び出されます。 |

**例**

>[!BEGINTABS]

>[!TAB Swift]

```swift
Flag.isFeatureEnabled("new-flag", evaluationContext: context) { isEnabled in
    DispatchQueue.main.async {
        if isEnabled {
            // Run the feature-specific behavior
        } else {
            // Run the default behavior
        }
    }
} errorCallback: { _ in
    DispatchQueue.main.async {
        // Run the default behavior
    }
}
```

>[!TAB Objective-C]

```objc
[AEPMobileFlag isFeatureEnabled:@"new-flag"
              evaluationContext:context
                     completion:^(BOOL isEnabled) {
    dispatch_async(dispatch_get_main_queue(), ^{
        if (isEnabled) {
            // Run the feature-specific behavior
        } else {
            // Run the default behavior
        }
    });
} errorCallback:^(enum AEPError error) {
    dispatch_async(dispatch_get_main_queue(), ^{
        // Run the default behavior
    });
}];
```

>[!ENDTABS]

### getFeature {#get-feature}

>[!IMPORTANT]
>
>以前のバージョンでは、機能が提供されなかった場合、`AEPError.unexpected`を含むエラーコールバックが呼び出されていました。 アプリがそのエラーを「機能が見つかりません」と扱った場合は、代わりに`nil`を完了処理してください。

現在のユーザーの機能の詳細（メタデータとユーザーが割り当てられているバリアントなど）を返します。 有効または無効を超える必要がある場合に使用します。

補完は、機能がユーザーに提供されたときにのみ結果として呼び出されます。 機能が提供されない場合、完了は`nil`で呼び出されます。 これは通常の結果であり、エラーではなく、エラーコールバックは呼び出されません。 次の場合、完了は`nil`で呼び出されます。

* このキーを持つ機能はありません。
* ユーザーがターゲティングルールと一致しません。
* ユーザーはコントロール グループに属しています。

エラーコールバックは、何か問題が発生した場合にのみ`AEPError.unexpected` （または別の`AEPError`）で呼び出されます。機能キーが空であるか、必要な設定値が欠落しているか、評価が失敗しているか、応答を読み取ることができないか、リクエストがタイムアウトします。

>[!BEGINTABS]

>[!TAB Swift]

```swift
static func getFeature(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void,
    errorCallback: ((AEPError) -> Void)?
)
```

>[!TAB Objective-C]

```objc
+ (void)getFeature:(NSString *)featureKey
 evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
        completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion
     errorCallback:(void (^ _Nullable)(enum AEPError))errorCallback;
```

>[!ENDTABS]

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | 文字列 | フラグで評価する機能キー |
| `evaluationContext` | FeatureEvaluationContext | 必要に応じてターゲティング属性を含めます。空のコンテキストには`FeatureEvaluationContext.builder().build()`を使用します。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。 |
| `completion` | `(FeatureEvaluationResult?) -> Void` | 評価された機能ペイロードで呼び出されます。 機能がユーザーに提供されない場合（不明なキー、ターゲティングが一致しない、またはコントロール グループ）に`nil`で呼び出されます。 `nil`はエラーではありません。 |
| `errorCallback` | `((AEPError) -> Void)?` | オプション。 空のキー、設定の欠落、評価の失敗、タイムアウトなど、実際のエラーに対してのみ呼び出されます。 機能が提供されない場合は呼び出されません。 |

**応答**

*FeatureEvaluationResult*

| フィールド | タイプ | 説明 |
|---|---|---|
| `id` | 整数 | 機能ID |
| `key` | 文字列 | 機能キー |
| `featureGroupKey` | 文字列？ | フィーチャを含むフィーチャ グループのキー |
| `meta` | 文字列？ | 機能に設定されたメタデータをテキストとして指定します。 メタデータがJSONの場合は、アプリでデコードします。 |
| `analyticsParam` | AnalyticsParam? | 機能とユーザーのバリエーションの識別子 |

**例**

>[!BEGINTABS]

>[!TAB Swift]

```swift
Flag.getFeature("new-flag", evaluationContext: context) { feature in
    DispatchQueue.main.async {
        guard let meta = feature?.meta, !meta.isEmpty else {
            // The feature is not served to this user (feature is nil), or it has no metadata.
            // Run the default behavior
            return
        }
        // Use the metadata to drive the feature behavior
    }
} errorCallback: { _ in
    DispatchQueue.main.async {
        // A genuine failure occurred. Run the default behavior
    }
}
```

>[!TAB Objective-C]

```objc
[AEPMobileFlag getFeature:@"new-flag"
        evaluationContext:context
               completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    dispatch_async(dispatch_get_main_queue(), ^{
        if (feature.meta.length > 0) {
            // Use the metadata to drive the feature behavior
        } else {
            // Run the default behavior
        }
    });
} errorCallback:^(enum AEPError error) {
    dispatch_async(dispatch_get_main_queue(), ^{
        // Run the default behavior
    });
}];
```

>[!ENDTABS]

### extensionVersion {#extension-version}

Flags拡張機能のバージョンを返します。

*Swift*

```swift
let version = Flag.extensionVersion
```

*Objective-C*

```objc
NSString *version = [AEPMobileFlag flagExtensionVersion];
```

## API サマリー {#api-summary}

| API | 返品 |
|---|---|
| `isFeatureEnabled(_:evaluationContext:completion:errorCallback:)` | 完了を通してブールする |
| `getFeature(_:evaluationContext:completion:errorCallback:)` | FeatureEvaluationResult? 完了するまで |
| `extensionVersion` | 文字列 |
