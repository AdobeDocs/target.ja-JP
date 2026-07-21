---
title: IOS統合ガイドのフラグ拡張機能
description: Flags拡張機能をiOS上のAdobe Experience Platform Mobile SDKと統合する方法について説明します。
hide: true
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 5%

---

# IOSのフラグ拡張機能 {#ios-extension-integration-guide}

このガイドでは、iOS上のAdobe Experience Platform Mobile SDKにFlags拡張機能を統合する方法について説明します。

## 前提条件 {#prerequisites}

フラグ拡張機能を実装する前に、次のことを確認してください。

* [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)で設定されたモバイルプロパティ
* Flags拡張機能がインストールされ、モバイルプロパティに設定されている
* Adobe Experience Cloud組織ID
* 最小デプロイメントターゲット：iOS 12.0

## 拡張機能の依存関係 {#extension-dependencies}

Flags拡張機能には、次のAdobe Experience Platform拡張機能が必要です。

| 拡張子 | 説明 | 必須 |
|---|---|---|
| モバイルコア | 設定やイベント処理などのコア機能を提供 | はい |
| ライフサイクル | Mobile SDKのアプリケーションライフサイクルおよびセッションデータを収集します | はい |
| Edge Network | Adobe Experience Platform Edge Networkとの通信が可能 | はい |
| Edge Identity | Edge Network拡張機能を使用する場合に、モバイルアプリからのID管理を有効にします | はい |

これらの拡張機能がデータ収集モバイルプロパティにインストールされ、アプリの依存関係に含まれていることを確認します。

## データ収集でのフラグ拡張機能の設定 {#configure}

### 拡張機能のインストール {#install-extension}

1. [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)にログインします。
1. 「**タグ**」タブを選択し、モバイルプロパティを選択します。
1. **拡張機能** > **カタログ**&#x200B;に移動します。
1. **フラグ拡張機能**&#x200B;を検索し、**インストール**&#x200B;を選択します。
1. 拡張機能の設定を行います。

   | 設定 | 説明 |
   |---|---|
   | アプリケーション ID | フラグ内のアプリケーションの一意のID |

1. **保存**&#x200B;を選択します。
1. [公開プロセス &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)に従って、設定を更新します。

### 環境ファイル IDの取得 {#environment-file-id}

1. モバイルプロパティで、**環境**&#x200B;に移動します。
1. 環境の&#x200B;**Install**&#x200B;列の下にあるボックスアイコンを選択します。
1. **モバイルインストール手順** ダイアログで、**環境ファイル ID**&#x200B;をコピーします。

## アプリにフラグ拡張機能を追加 {#add-to-app}

### 依存関係を追加 {#add-dependencies}

Mobile SDKの依存関係をプロジェクトに追加します。 Flags拡張機能には、Mobile Coreと以下に示すEdge関連の拡張機能が必要です。

#### Swift パッケージマネージャーの使用 {#swift-package-manager}

Xcodeで、**ファイル**/**パッケージを追加**&#x200B;を選択し、次のAdobe Experience Platform Mobile SDK パッケージ URLを追加します。

| パッケージ | URL |
|---|---|
| AEPCore | `https://github.com/adobe/aepsdk-core-ios.git` |
| AEPEdge | `https://github.com/adobe/aepsdk-edge-ios.git` |
| AEPEdgeIdentity | `https://github.com/adobe/aepsdk-edgeidentity-ios.git` |

プロンプトが表示されたら、次のライブラリを選択してターゲットに追加します。

* `AEPCore`, `AEPLifecycle` （`aepsdk-core-ios`から）
* `AEPEdge` （`aepsdk-edge-ios`から）
* `AEPEdgeIdentity` （`aepsdk-edgeidentity-ios`から）

AEPCore 5.8.0以降を使用します。

>[!NOTE]
>
>Xcodeでパッケージを追加する際に、各パッケージの依存関係ルールを選択します（例：**次のメジャーバージョン**&#x200B;まで）。これにより、次のメジャーバージョンを除外しながら、新しいマイナーリリースとパッチリリースが自動的に取得されます。 最新のリリース済みバージョンについては、GitHubの各拡張機能のリリースページを確認してください。

### Flags パッケージを追加する {#add-flags-package}

アプリターゲットに対しては、Swift パッケージまたはXCFramework統合方法のいずれかを使用します。両方を使用しないでください。

#### Package.swift ファイルのないXcode プロジェクトの場合 {#xcode-project}

1. Xcodeで、**ファイル**/**パッケージを追加**&#x200B;を選択します。
1. 「**ローカルを追加**」を選択します。
1. `Package.swift`を含む指定された`Packages/AEPFlags` ディレクトリを選択します。
1. アプリケーションターゲットに`AEPFlags` ライブラリを追加します。

Xcodeはプロジェクト内のローカルパッケージ参照を保存するので、アプリケーションに独自の`Package.swift` ファイルは必要ありません。

#### Package.swift ファイルを含むプロジェクトの場合 {#package-swift-project}

既存のマニフェストで、アプリケーションターゲットの依存関係に`AEPFlags`を追加し、指定されたマニフェストのURLとチェックサムを使用してバイナリターゲットを追加します。

```swift
targets: [
    .target(
        name: "YourApp",
        dependencies: [
            "AEPFlags"
        ]
    ),
    .binaryTarget(
        name: "AEPFlags",
        url: "<AEPFlags binary URL>",
        checksum: "<AEPFlags binary checksum>"
    )
]
```

Swift Package Managerは、ローカル Xcode、CI、およびアーカイブ ビルドのバイナリ ターゲットを解決します。

#### XCFrameworkを直接追加する {#xcframework}

または、指定された`AEPFlags.xcframework`をXcode プロジェクトナビゲーターにドラッグして、アプリケーションターゲットに追加します。 **General** > **Frameworks, Libraries, and Embedded Content**&#x200B;で、フレームワークを&#x200B;**Embed &amp; Sign**&#x200B;に設定します。

### SDKの初期化 {#initialize-sdk}

フラグ APIを呼び出す前に、`AppDelegate`にMobile SDK拡張機能を登録してください。 ID、Edge、およびライフサイクルの後に`Flag`を登録し、モバイルプロパティのEnvironment File IDを使用してSDKを設定します。

#### 拡張機能の登録と設定 {#register-configure}

>[!IMPORTANT]
>
>実稼動アプリの場合は、`.error` ログレベルのみを使用します。リリースビルドで`.debug`または`.trace`を使用しないでください。

**Swift**

```swift
// AppDelegate.swift
import AEPCore
import AEPLifecycle
import AEPEdge
import AEPEdgeIdentity
import AEPFlags
import UIKit

final class AppDelegate: NSObject, UIApplicationDelegate {

    func application(_: UIApplication,
                      didFinishLaunchingWithOptions _: [UIApplication.LaunchOptionsKey: Any]? = nil) -> Bool {
        // Production: use .error only. Do not use .debug or .trace in release builds.
        MobileCore.setLogLevel(.error)

        MobileCore.registerExtensions([
            Identity.self,
            Edge.self,
            Lifecycle.self,
            Flag.self
        ]) {
            MobileCore.configureWith(appId: "YOUR_ENVIRONMENT_FILE_ID")
            MobileCore.lifecycleStart(additionalContextData: nil)
        }

        return true
    }
}
```

**Objective-C**

```objc
// AppDelegate.m
#import "AppDelegate.h"
@import AEPCore;
@import AEPLifecycle;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPFlags;

@implementation AppDelegate

- (BOOL)application:(UIApplication *)application
    didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

    // Production: use AEPLogLevelError only. Do not use Debug or Trace in release builds.
    [AEPMobileCore setLogLevel:AEPLogLevelError];

    [AEPMobileCore registerExtensions:@[
        AEPMobileEdgeIdentity.class,
        AEPMobileEdge.class,
        AEPMobileLifecycle.class,
        AEPMobileFlag.class
    ] completion:^{
        [AEPMobileCore configureWithAppId:@"YOUR_ENVIRONMENT_FILE_ID"];
        [AEPMobileCore lifecycleStart:nil];
    }];

    return YES;
}

@end
```

## 評価コンテキスト {#evaluation-context}

`FeatureEvaluationContext`にはターゲティング属性が含まれています（フラグルールの照合に使用）。

| パラメーター | 必須 | 説明 |
|---|---|---|
| `attributes` | × | `[String: [String]]`. キーは、フラグルールで使用されるコンテキスト属性名です（例：`locale`、`platform`、`appVersion`、`deviceType`）。 値は、現在のユーザー/セッションのキーの候補属性値のリストです（例：`["en_US"]`または`["phone"]`）。 |

**Swift**

```swift
import AEPFlags

let attrs: [String: [String]] = [
    "locale": ["en_US"],
    "platform": ["IOS"],
    "appVersion": ["3.0.0"]
]

let ctx = FeatureEvaluationContext.builder()
    .withAttributes(attrs)
    .build()
```

**Objective-C**

```objc
@import AEPFlags;

NSDictionary<NSString *, NSArray<NSString *> *> *attrs = @{
    @"locale": @[@"en_US"],
    @"platform": @[@"IOS"],
    @"appVersion": @[@"3.0.0"]
};

AEPFeatureEvaluationContextBuilder *builder = [AEPFeatureEvaluationContext builder];
AEPFeatureEvaluationContext *ctx = [[builder withAttributes:attrs] build];
```

### ターゲティング属性の例 {#sample-attributes}

| 属性 | 説明 | 値の例 |
|---|---|---|
| `locale` | ユーザーのロケール/言語 | `["en_US"]`, `["fr_FR"]` |
| `platform` | プラットフォーム識別子 | `["IOS"]` |
| `appVersion` | アプリケーションバージョン | `["3.0.0"]` |
| `deviceType` | デバイスタイプ | `["phone"]`, `["tablet"]` |

### カスタム ID {#custom-identity}

Flags拡張機能は、ID解決にIdentity for Edge Network拡張機能を使用します。 機能フラグをカスタム ID （CRM IDやロイヤルティ IDなど）でコホートできるため、バリエーションの分割と分析を、アプリケーションにとって重要なIDに結び付けることができます。

機能フラグの作成時に、フラグ UIでカスタム ID名前空間を選択する必要があります。 そのIDに対してフラグを評価するには、一致する名前空間を使用して、デバイス上のEdge ID `identityMap`に同じIDが存在する必要があります。 Edge Network `updateIdentities` APIのIDを実行時に指定します。

#### ID マップへのカスタム IDの追加 {#add-identity}

機能フラグで設定された同じ名前空間の下にIDを追加します。

**Swift**

```swift
import AEPEdgeIdentity

let identityMap = IdentityMap()
identityMap.add(item: IdentityItem(id: "1111", authenticatedState: .authenticated, primary: true),
                 withNamespace: "userCRMId") // must match the namespace configured on the feature flag
Identity.updateIdentities(with: identityMap)
```

**Objective-C**

```objc
@import AEPEdgeIdentity;

AEPIdentityItem *item = [[AEPIdentityItem alloc]
    initWithId:@"1111"
    authenticatedState:AEPAuthenticatedStateAuthenticated
    primary:YES];
AEPIdentityMap *identityMap = [[AEPIdentityMap alloc] init];
[identityMap addItem:item withNamespace:@"userCRMId"]; // must match the namespace configured on the feature flag
[AEPMobileEdgeIdentity updateIdentities:identityMap];
```

## API リファレンス {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled`は、指定されたコンテキストに対してフラグ機能がオンかオフかを返します。 `featureKey`、`FeatureEvaluationContext` （オプションのターゲット属性）、および完了クロージャを渡します。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。

**署名**

*Swift*

```swift
static func isFeatureEnabled(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void
)
```

*Objective-C*

```objc
+ (void)isFeatureEnabled:(NSString *)featureKey
       evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
               completion:(void (^)(BOOL))completion;
```

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | 文字列 | フラグで評価する機能キー |
| `evaluationContext` | FeatureEvaluationContext | 必要に応じてターゲティング属性を含めます。空のコンテキストには`FeatureEvaluationContext.builder().build()`を使用します。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。 |
| `completion` | `(Bool) -> Void` | 機能が有効になっている場合は`true`で呼び出され、それ以外の場合は`false`です。 |

**例**

*Swift*

```swift
import AEPFlags

Flag.isFeatureEnabled(
    "new-flag",
    evaluationContext: ctx
) { isEnabled in
    if isEnabled {
        // Feature is enabled: run the feature-specific behavior
    } else {
        // Feature is disabled: fall back to the default behavior
    }
}
```

*Objective-C*

```objc
@import AEPFlags;

[AEPMobileFlag isFeatureEnabled:@"new-flag"
              evaluationContext:ctx
                      completion:^(BOOL isEnabled) {
    if (isEnabled) {
        // Feature is enabled: run the feature-specific behavior
    } else {
        // Feature is disabled: fall back to the default behavior
    }
}];
```

### getFeature {#get-feature}

`getFeature`は、指定されたコンテキストの評価済み機能ペイロードを返します。 このAPIは、有効/無効を超える必要があり、機能のメタデータまたは値が必要な場合に使用します。

**署名**

*Swift*

```swift
static func getFeature(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void
)
```

*Objective-C*

```objc
+ (void)getFeature:(NSString *)featureKey
 evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
        completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion;
```

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | 文字列 | フラグで評価する機能キー |
| `evaluationContext` | FeatureEvaluationContext | 必要に応じてターゲティング属性を含めます。空のコンテキストには`FeatureEvaluationContext.builder().build()`を使用します。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。 |
| `completion` | `(FeatureEvaluationResult?) -> Void` | 評価された機能ペイロードで呼び出されます。機能が見つからない場合は`nil`。 |

**応答**

*FeatureEvaluationResult*

| フィールド | タイプ | 説明 |
|---|---|---|
| `id` | 整数 | 数値特徴識別子 |
| `key` | 文字列 | 機能キー |
| `featureGroupKey` | 文字列？ | 機能グループキー（使用可能な場合） |
| `meta` | 文字列？ | 不透明な機能メタデータ（使用可能な場合） |
| `analyticsParam` | AnalyticsParam? | 評価済み機能の分析の詳細 |

*AnalyticsParam*

| フィールド | タイプ | 説明 |
|---|---|---|
| `featureGroupId` | 整数 | 数値フィーチャ グループ ID |
| `featureId` | 整数 | 数値特徴識別子 |
| `variantId` | 文字列？ | バリアント ID |

**例**

*Swift*

```swift
import AEPFlags

Flag.getFeature(
    "new-flag",
    evaluationContext: ctx
) { feature in
    guard let meta = feature?.meta, !meta.isEmpty else {
        // No metadata available: fall back to the default behavior
        return
    }
    // Feature metadata is available: use it to drive the feature behavior
}
```

*Objective-C*

```objc
@import AEPFlags;

[AEPMobileFlag getFeature:@"new-flag"
        evaluationContext:ctx
                completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    NSString *meta = feature.meta;
    if (meta.length > 0) {
        // Feature metadata is available: use it to drive the feature behavior
    } else {
        // No metadata available: fall back to the default behavior
    }
}];
```

### extensionVersion {#extension-version}

Flags拡張機能のバージョン文字列を返します。

**構文**

*Swift*

```swift
static var extensionVersion: String
```

*Objective-C*

```objc
+ (nonnull NSString *)flagExtensionVersion;
```

**例**

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
| `isFeatureEnabled(_:evaluationContext:completion:)`. `FeatureEvaluationContext`には、ルールのターゲット属性が含まれています。 [isFeatureEnabled](#is-feature-enabled)を参照してください。 | 完了閉鎖を介した排便 |
| `getFeature(_:evaluationContext:completion:)`. 指定されたコンテキストの評価された機能ペイロードを返します。 [getFeature](#get-feature)を参照してください。 | FeatureEvaluationResult? クロージャを使用 |
| `extensionVersion` | 文字列 |

## 詳細については、 {#see-also}

* [モバイルアプリケーション](../../integrate/mobile-applications.md)
* [SDK](../../integrate/sdks.md)
* [Android拡張機能の統合ガイド](../android/android-extension-integration-guide.md)

<!-- -->
