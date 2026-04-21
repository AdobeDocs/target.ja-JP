---
title: IOS用エクスペリエンスロールアウト拡張機能の統合ガイド
description: Experience Rollout拡張機能をiOS上のAdobe Experience Platform Mobile SDKと統合する方法について説明します。
hide: true
source-git-commit: fea4d9e87ad8417de9d820ee3556796fba112dc1
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 7%

---

# IOSのエクスペリエンスロールアウト拡張機能 {#ios-extension-integration-guide}

このガイドでは、Experience Rollout拡張機能をiOS上のAdobe Experience Platform Mobile SDKと統合する方法について説明します。

## 前提条件 {#prerequisites}

エクスペリエンスのロールアウト拡張機能を実装する前に、次のことを確認してください。

* [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)で設定されたモバイルプロパティ
* Experience Rollout拡張機能がモバイルプロパティにインストールされ、設定されている
* Adobe Experience Cloud組織ID
* 最小デプロイメントターゲット：iOS 12.0
* Xcode 14.1以降

## 拡張機能の依存関係 {#extension-dependencies}

Experience Rollout拡張機能には、次のAdobe Experience Platform拡張機能が必要です。

| 拡張 | 説明 | 必須 |
|---|---|---|
| モバイルコア | 設定やイベント処理などのコア機能を提供 | ○ |
| ライフサイクル | Mobile SDKのアプリケーションライフサイクルおよびセッションデータを収集します | ○ |
| Edge Network | Adobe Experience Platform Edge Networkとの通信が可能 | ○ |
| Edge Identity | Edge NetworkのユーザーIDを管理します | ○ |

これらの拡張機能がデータ収集モバイルプロパティにインストールされ、アプリの依存関係に含まれていることを確認します。

## データ収集でのExperience Rollout拡張機能の設定 {#configure}

### 拡張機能のインストール {#install-extension}

1. [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)にログインします。
1. 「**タグ**」タブを選択し、モバイルプロパティを選択します。
1. **拡張機能** > **カタログ**&#x200B;に移動します。
1. **Experience Rollout extension**&#x200B;を検索し、**Install**&#x200B;を選択します。
1. 拡張機能の設定を行います。

   | 設定 | 説明 |
   |---|---|
   | サンドボックス | Experience Rollout設定を含むAdobe Experience Platform サンドボックス |
   | アプリケーション ID | Experience Rolloutでのアプリケーションの一意のID |
   | データセット ID | Analytics イベントデータのAdobe Experience Platform データセット ID |

1. **保存**&#x200B;を選択します。
1. [公開プロセス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview)に従って、設定を更新します。

### 環境ファイル IDの取得 {#environment-file-id}

1. モバイルプロパティで、**環境**&#x200B;に移動します。
1. 環境の&#x200B;**Install**&#x200B;列の下にあるボックスアイコンを選択します。
1. **モバイルインストール手順** ダイアログで、**環境ファイル ID**&#x200B;をコピーします。

## エクスペリエンスのロールアウト拡張機能をアプリに追加 {#add-to-app}

### 依存関係の追加 {#add-dependencies}

Mobile SDKの依存関係をプロジェクトに追加します。 Experience Rollout拡張機能には、Mobile Coreと以下に示すEdge関連の拡張機能が必要です。

#### Swift パッケージマネージャーの使用（推奨） {#swift-package-manager}

1. Xcodeで、**ファイル**/**パッケージ依存関係の追加**&#x200B;に移動します。
1. Adobe Experience Platform Mobile SDK リポジトリ URLを入力します。

   ```
   https://github.com/adobe/aepsdk-core-ios
   ```

1. 次のパッケージを追加します。

   | パッケージ | リポジトリ |
   |---|---|
   | AEPCore、AEPLifecycle | `https://github.com/adobe/aepsdk-core-ios` |
   | AEPEdge | `https://github.com/adobe/aepsdk-edge-ios` |
   | AEPEdgeIdentity | `https://github.com/adobe/aepsdk-edgeidentity-ios` |
   | AEPRollout | `https://github.com/adobe/aepsdk-rollout-ios` |

#### CocoaPodsの使用 {#cocoapods}

次のポッドを`Podfile`に追加します。

```ruby
pod 'AEPCore'
pod 'AEPLifecycle'
pod 'AEPEdge'
pod 'AEPEdgeIdentity'
pod 'AEPRollout'
```

次に実行：

```bash
pod install
```

>[!IMPORTANT]
>
>実稼動アプリケーションの場合、Adobeでは、`~>`またはオープンレンジを使用する代わりに、明示的なバージョン番号にピン留めすることをお勧めします。 詳しくは、[CocoaPods バージョン管理ガイド &#x200B;](https://guides.cocoapods.org/using/the-podfile.html)を参照してください。

### SDKの初期化 {#initialize-sdk}

Experience Rollout拡張機能APIを呼び出す前に、`AppDelegate` （または`SceneDelegate`）でMobile SDKを初期化します。 モバイルプロパティから環境ファイル IDを使用して、アプリがデータ収集で公開したロールアウト設定を取得します。

**Swift**

```swift
import AEPCore
import AEPLifecycle
import AEPEdge
import AEPEdgeIdentity
import AEPRollout

@main
class AppDelegate: UIResponder, UIApplicationDelegate {

    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {

        MobileCore.setLogLevel(.error)

        MobileCore.registerExtensions(
            [Lifecycle.self, Edge.self, Identity.self, Rollout.self]
        ) {
            // Initialize with your Environment File ID from Data Collection
            MobileCore.configureWith(appId: "YOUR_ENVIRONMENT_FILE_ID")
        }

        return true
    }
}
```

**Objective-C**

```objc
@import AEPCore;
@import AEPLifecycle;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPRollout;

@implementation AppDelegate

- (BOOL)application:(UIApplication *)application
    didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

    [AEPMobileCore setLogLevel:AEPLogLevelError];

    NSArray *extensions = @[
        AEPMobileLifecycle.class,
        AEPMobileEdge.class,
        AEPMobileEdgeIdentity.class,
        AEPMobileRollout.class
    ];

    [AEPMobileCore registerExtensions:extensions completion:^{
        // Initialize with your Environment File ID from Data Collection
        [AEPMobileCore configureWithAppId:@"YOUR_ENVIRONMENT_FILE_ID"];
    }];

    return YES;
}

@end
```

>[!IMPORTANT]
>
>実稼動アプリの場合は、`LogLevel.error`のみを使用してください。 リリースビルドで`.debug`または`.verbose`を使用しないでください。

## 評価コンテキスト {#evaluation-context}

`FeatureEvaluationContext`には、ターゲット属性（ロールアウト ルールの照合に使用）とオプション ID （分析に使用）が含まれます。

| メソッド | 必須 | 説明 |
|---|---|---|
| `withIdentity(namespace:id:)` | × | 最初の引数：ID名前空間（[Adobe ID名前空間](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces)を参照）。 2つ目の引数：ID値 この評価のためにAnalyticsで名前空間とIDを表す場合に、これを含めます。 指定しない場合、AnalyticsはデフォルトでECIDを使用します。 これは、機能の有効化に関する意思決定の推進には使用されません。 |
| `withAttributes(_:)` | × | `[String: [String]]`キーは、ロールアウト ルールで使用されるコンテキスト属性名です（例：`locale`、`platform`、`appVersion`、`deviceType`）。 値は、現在のユーザー/セッションのキーの候補属性値のリストです（例：`["en_US"]`または`["phone"]`）。 |

**Swift**

```swift
import AEPRollout

let attrs: [String: [String]] = [
    "locale": ["en_US"],
    "platform": ["IOS"],
    "appVersion": ["3.0.0"]
]

let ctx = FeatureEvaluationContext.builder()
    .withIdentity(namespace: "Email", id: "customer@example.com")
    .withAttributes(attrs)
    .build()
```

**Objective-C**

```objc
@import AEPRollout;

NSDictionary<NSString *, NSArray<NSString *> *> *attrs = @{
    @"locale": @[@"en_US"],
    @"platform": @[@"IOS"],
    @"appVersion": @[@"3.0.0"]
};

AEPFeatureEvaluationContext *ctx = [[[AEPFeatureEvaluationContextBuilder builder]
    withIdentityNamespace:@"Email" id:@"customer@example.com"]
    withAttributes:attrs]
    .build;
```

### ターゲティング属性の例 {#sample-attributes}

| 属性 | 説明 | 値の例 |
|---|---|---|
| `locale` | ユーザーのロケール/言語 | `["en_US"]`, `["fr_FR"]` |
| `platform` | プラットフォーム識別子 | `["IOS"]` |
| `appVersion` | アプリケーションバージョン | `["3.0.0"]` |
| `deviceType` | デバイスタイプ | `["phone"]`, `["tablet"]` |

## API リファレンス {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled`は、特定のコンテキストに対してエクスペリエンスのロールアウト機能がオンかオフかを返します。 `featureKey`、`FeatureEvaluationContext` （オプションのターゲティング属性およびAnalytics用のオプション ID）、および完了ハンドラーを渡します。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。

**署名**

*Swift*

```swift
Rollout.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void
)
```

*Objective-C*

```objc
[AEPMobileRollout isFeatureEnabled:(NSString *)featureKey
               evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
                      completion:(void (^)(BOOL))completion];
```

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | 文字列 | エクスペリエンスロールアウトで評価する機能キー |
| `evaluationContext` | FeatureEvaluationContext | 必要に応じて、Analyticsのターゲティング属性とオプション IDを含めます。空のコンテキストには`FeatureEvaluationContext.builder().build()`を使用します。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。 |
| `completion` | `(Bool) -> Void` | 機能が有効になっている場合は`true`で呼び出され、それ以外の場合は`false`です。 |

**例**

*Swift*

```swift
import AEPRollout

Rollout.isFeatureEnabled(
    featureKey: "new-checkout-experience",
    evaluationContext: ctx
) { isEnabled in
    if isEnabled {
        showNewCheckout()
    } else {
        showDefaultCheckout()
    }
}
```

*Objective-C*

```objc
@import AEPRollout;

[AEPMobileRollout isFeatureEnabled:@"new-checkout-experience"
               evaluationContext:ctx
                      completion:^(BOOL isEnabled) {
    if (isEnabled) {
        [self showNewCheckout];
    } else {
        [self showDefaultCheckout];
    }
}];
```

### getFeature {#get-feature}

`getFeature`は、指定されたコンテキストの評価済み機能ペイロードを返します。 このAPIは、有効/無効を超える必要があり、機能のメタデータまたは値が必要な場合に使用します。

**署名**

*Swift*

```swift
Rollout.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void
)
```

*Objective-C*

```objc
[AEPMobileRollout getFeature:(NSString *)featureKey
         evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
                completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion];
```

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | 文字列 | エクスペリエンスロールアウトで評価する機能キー |
| `evaluationContext` | FeatureEvaluationContext | 必要に応じて、Analyticsのターゲティング属性とオプション IDを含めます。空のコンテキストには`FeatureEvaluationContext.builder().build()`を使用します。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。 |
| `completion` | `(FeatureEvaluationResult?) -> Void` | 評価された機能ペイロードで呼び出されます。機能が見つからない場合は`nil`になる可能性があります。 |

**応答**

*FeatureEvaluationResult*

| フィールド | タイプ | 説明 |
|---|---|---|
| `id` | 整数 | 数値特徴識別子 |
| `key` | 文字列 | 機能キー |
| `releaseKey` | 文字列？ | この機能のリリースキーが利用可能な場合 |
| `meta` | 文字列？ | 利用可能な場合、メタデータをJSON文字列として機能する |
| `analyticsParam` | AnalyticsParam? | 評価済み機能の分析の詳細 |

*AnalyticsParam*

| フィールド | タイプ | 説明 |
|---|---|---|
| `releaseId` | 整数 | 数値リリース ID |
| `featureId` | 整数 | 数値特徴識別子 |
| `variantId` | 文字列？ | バリアント ID |

**例**

*Swift*

```swift
import AEPRollout

Rollout.getFeature(
    featureKey: "new-checkout-experience",
    evaluationContext: ctx
) { feature in
    if let meta = feature?.meta, !meta.isEmpty {
        applyMetaDrivenExperience(meta)
    } else {
        showFallbackExperience()
    }
}
```

*Objective-C*

```objc
@import AEPRollout;

[AEPMobileRollout getFeature:@"new-checkout-experience"
         evaluationContext:ctx
                completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    NSString *meta = feature.meta;
    if (meta != nil && meta.length > 0) {
        [self applyMetaDrivenExperience:meta];
    } else {
        [self showFallbackExperience];
    }
}];
```

### refreshCache {#refresh-cache}

デフォルトでは、Experience Rollout拡張機能は、設定可能なスケジュールで、サーバーの最新のロールアウトルールと機能を定期的に同期します。 次回のスケジュールされた同期よりも早く更新が必要な場合は、`refreshCache`に電話して強制的に更新します。 一般的なケースには、ログイン後や、アプリの状態がターゲティングに影響を与える影響を与えるような変化が発生した場合などがあります。

**構文**

*Swift*

```swift
Rollout.refreshCache()
```

*Objective-C*

```objc
[AEPMobileRollout refreshCache];
```

### extensionVersion {#extension-version}

エクスペリエンスのロールアウト拡張機能のバージョン文字列を返します。

**構文**

```swift
Rollout.extensionVersion(): String
```

**例**

*Swift*

```swift
let version = Rollout.extensionVersion()
```

*Objective-C*

```objc
NSString *version = [AEPMobileRollout extensionVersion];
```

## API サマリー {#api-summary}

| API | Returns |
|---|---|
| `isFeatureEnabled(featureKey:evaluationContext:completion:)` `FeatureEvaluationContext`は、ルールのターゲティング属性と分析のオプション IDを保持します。 [isFeatureEnabled](#is-feature-enabled)を参照してください。 | 完了ハンドラーを使用したブール |
| `getFeature(featureKey:evaluationContext:completion:)`指定されたコンテキストの評価された機能ペイロードを返します。 [getFeature](#get-feature)を参照してください。 | FeatureEvaluationResult? 完了ハンドラーを使用 |
| `refreshCache()` | ボイド |
| `extensionVersion()` | 文字列 |

## 詳しくは、 {#see-also}

* [モバイルアプリ](../../integrate/mobile-applications.md)
* [統合ステップ](../../integrate/integration-steps.md)
* [SDK](../../integrate/sdks.md)
* [Android拡張機能の統合ガイド](../android/android-extension-integration-guide.md)

<!-- -->
