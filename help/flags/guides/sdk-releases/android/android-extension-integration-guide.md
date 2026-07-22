---
title: Android統合ガイドのフラグ拡張機能
description: Flags拡張機能をAndroid上のAdobe Experience Platform Mobile SDKと統合する方法について説明します。
badge: label="Beta" type="Informative"
hide: true
exl-id: 683ef4d4-e637-4b7b-b694-689c7e65a99e
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 5%

---

# Androidのフラグ拡張機能 {#android-extension-integration-guide}

このガイドでは、Android上のAdobe Experience Platform Mobile SDKにFlags拡張機能を統合する方法について説明します。

## 前提条件 {#prerequisites}

フラグ拡張機能を実装する前に、次のことを確認してください。

* [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)で設定されたモバイルプロパティ
* Flags拡張機能がインストールされ、モバイルプロパティに設定されている
* Adobe Experience Cloud組織ID
* 最小SDK:API 21 （Android 5.0 Lollipop）

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
1. [公開プロセス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview)に従って、設定を更新します。

### 環境ファイル IDの取得 {#environment-file-id}

1. モバイルプロパティで、**環境**&#x200B;に移動します。
1. 環境の&#x200B;**Install**&#x200B;列の下にあるボックスアイコンを選択します。
1. **モバイルインストール手順** ダイアログで、**環境ファイル ID**&#x200B;をコピーします。

## アプリにフラグ拡張機能を追加 {#add-to-app}

### 依存関係を追加 {#add-dependencies}

Mobile SDKの依存関係をプロジェクトに追加します。 Flags拡張機能には、Mobile Coreと以下に示すEdge関連の拡張機能が必要です。

#### BOMでのGradleの使用（推奨） {#gradle-bom}

アプリの`build.gradle.kts` ファイルに次の依存関係を追加します。

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation(platform("com.adobe.marketing.mobile:sdkbom:3.+"))

    // Required extensions
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")
}
```

#### Gradleの使用（Groovy） {#gradle-groovy}

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation platform('com.adobe.marketing.mobile:sdkbom:3.+')

    // Required extensions
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'
}
```

>[!IMPORTANT]
>
>実稼動アプリケーションの場合は、動的バージョンではなく明示的なバージョン番号を使用することをお勧めします。 詳しくは、[Gradle依存関係の管理](https://docs.gradle.org/current/userguide/dependency_management.html)を参照してください。

### フラグの依存関係を追加 {#add-flags-dependency}

#### ホストされたMaven リポジトリの使用（推奨） {#hosted-maven}

Flags Maven リポジトリを`settings.gradle.kts`の`repositories` ブロックに追加します。

```kotlin
maven {
    url = uri("<HTTPS Flags Maven repository URL>")
}
```

Groovy `settings.gradle` ファイル：

```groovy
maven {
    url = uri('<HTTPS Flags Maven repository URL>')
}
```

`<HTTPS Flags Maven repository URL>`を、フラグ拡張機能に指定されたセキュアなリポジトリ URLに置き換えます。

次に、バージョン管理されたフラグの依存関係をアプリの`build.gradle.kts`に追加します。

```kotlin
implementation("com.adobe.marketing.mobile:flags:<version>")
```

Groovy `build.gradle` ファイル：

```groovy
implementation 'com.adobe.marketing.mobile:flags:<version>'
```

`<version>`を、リリースに提供されたFlags拡張機能のバージョンと完全に置き換えます。

#### フラグ配布パッケージの使用 {#distribution-package}

Flags拡張機能の配布パッケージには、次のものが含まれます。

* `flags-3.x.aar`
* `flags-3.x.module`
* `flags-3.x.pom`

次のいずれかの方法を使用して、この拡張機能をAndroid プロジェクトで使用できるようにします。

* 配布パッケージからすべてのファイルをローカルまたはプライベートのMaven リポジトリに公開し、そのリポジトリを使用するようにプロジェクトを設定します。
* プロジェクトに`flags-3.x.aar`を直接追加し、`flags-3.x.pom`で指定された推移的依存関係を宣言します。

### 権限の追加 {#add-permissions}

次の権限を`AndroidManifest.xml` ファイルに追加します。

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### SDKの初期化 {#initialize-sdk}

フラグ拡張機能APIを呼び出す前に、`Application` クラスでMobile SDKを初期化します。 モバイルプロパティの環境ファイル IDを`MobileCore.initialize`で使用すると、アプリはデータ収集で公開したフラグ設定を取得します。

#### MobileCore.initializeの使用 {#mobile-core-initialize}

Android BOM バージョン 3.8.0以降で使用可能なこのAPIは、Data Collection環境ファイルを使用してSDKを初期化します。

>[!IMPORTANT]
>
>実稼動アプリの場合は、`LoggingMode.ERROR`のみを使用します。リリースビルドで`DEBUG`または`VERBOSE`を使用しないでください。

**Kotlin**

```kotlin
import android.app.Application
import com.adobe.marketing.mobile.LoggingMode
import com.adobe.marketing.mobile.MobileCore

class MainApplication : Application() {

    override fun onCreate() {
        super.onCreate()

        // Production: use LoggingMode.ERROR only. Do not use DEBUG or VERBOSE in release builds.
        MobileCore.setLogLevel(LoggingMode.ERROR)

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID")
    }
}
```

**Java**

```java
import android.app.Application;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        // Production: use LoggingMode.ERROR only. Do not use DEBUG or VERBOSE in release builds.
        MobileCore.setLogLevel(LoggingMode.ERROR);

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID", null);
    }
}
```

### アプリケーションクラスを登録 {#register-application}

`Application` クラスを`AndroidManifest.xml`に登録します：

```xml
<application
    android:name=".MainApplication"
    ... >
</application>
```

## 評価コンテキスト {#evaluation-context}

`FeatureEvaluationContext` クラスには、ターゲティング属性が含まれています（フラグルールの照合に使用）。

| メソッド | 必須 | 説明 |
|---|---|---|
| `withAttributes(map)` | × | `Map<String, List<String>>`. キーは、フラグルールで使用されるコンテキスト属性名です（例：`locale`、`platform`、`appVersion`、`deviceType`）。 値は、現在のユーザー/セッションのキーの候補属性値のリストです（例：`["en_US"]`または`["phone"]`）。 |

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext

val attrs = mapOf(
    "locale" to listOf("en_US"),
    "platform" to listOf("ANDROID")
)

val ctx = FeatureEvaluationContext.builder()
    .withAttributes(attrs)
    .build()
```

**Java**

```java
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

Map<String, List<String>> attrs = new HashMap<>();
attrs.put("locale", Arrays.asList("en_US"));
attrs.put("platform", Arrays.asList("ANDROID"));

FeatureEvaluationContext ctx = FeatureEvaluationContext.builder()
        .withAttributes(attrs)
        .build();
```

### カスタム ID {#custom-identity}

Flags拡張機能は、ID解決にIdentity for Edge Network拡張機能を使用します。 機能フラグをカスタム ID （CRM IDやロイヤルティ IDなど）でコホートできるため、バリエーションの分割と分析を、アプリケーションにとって重要なIDに結び付けることができます。

機能フラグの作成時に、フラグ UIでカスタム ID名前空間を選択する必要があります。 そのIDに対してフラグを評価するには、一致する名前空間を使用して、デバイス上のEdge ID `identityMap`に同じIDが存在する必要があります。 Edge Network `updateIdentities` APIのIDを実行時に指定します。

#### ID マップへのカスタム IDの追加 {#add-identity}

機能フラグで設定された同じ名前空間の下にIDを追加します。

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState
import com.adobe.marketing.mobile.edge.identity.Identity
import com.adobe.marketing.mobile.edge.identity.IdentityItem
import com.adobe.marketing.mobile.edge.identity.IdentityMap

val identityMap = IdentityMap()
identityMap.addItem(
    IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true),
    "userCRMId" // must match the namespace configured on the feature flag
)
Identity.updateIdentities(identityMap)
```

**Java**

```java
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState;
import com.adobe.marketing.mobile.edge.identity.Identity;
import com.adobe.marketing.mobile.edge.identity.IdentityItem;
import com.adobe.marketing.mobile.edge.identity.IdentityMap;

final IdentityItem item = new IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true);
final IdentityMap identityMap = new IdentityMap();
identityMap.addItem(item, "userCRMId"); // must match the namespace configured on the feature flag
Identity.updateIdentities(identityMap);
```

## API リファレンス {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled`は、指定されたコンテキストに対してフラグ機能がオンかオフかを返します。 `featureKey`、`FeatureEvaluationContext` （オプションのターゲット属性）、およびコールバックを渡します。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。

**署名**

*Kotlin*

```kotlin
Flag.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

*Java*

```java
Flag.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | 文字列 | フラグで評価する機能キー |
| `evaluationContext` | FeatureEvaluationContext | 必要に応じてターゲティング属性を含めます。空のコンテキストには`FeatureEvaluationContext.builder().build()`を使用します。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。 |
| `callback` | AdobeCallback&lt;Boolean> | 機能が有効になっている場合は`true`で呼び出され、それ以外の場合は`false`です。 `AdobeCallbackWithError<Boolean>`を渡して`fail(...)`を処理することもできます。 |

**例**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.flags.Flag

Flag.isFeatureEnabled(
    "new-flag",
    ctx,
    object : AdobeCallback<Boolean> {
        override fun call(isEnabled: Boolean?) {
            if (isEnabled == true) {
                // run the feature-specific behavior
            } else {
                // fall back to the default behavior
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.flags.Flag;

Flag.isFeatureEnabled(
    "new-flag",
    ctx,
    new AdobeCallback<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            if (Boolean.TRUE.equals(isEnabled)) {
                // run the feature-specific behavior
            } else {
                // fall back to the default behavior
            }
        }
    }
);
```

### getFeature {#get-feature}

`getFeature`は、指定されたコンテキストの評価済み機能ペイロードを返します。 このAPIは、有効/無効を超える必要があり、機能のメタデータまたは値が必要な場合に使用します。

**署名**

*Kotlin*

```kotlin
Flag.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

*Java*

```java
Flag.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | 文字列 | フラグで評価する機能キー |
| `evaluationContext` | FeatureEvaluationContext | 必要に応じてターゲティング属性を含めます。空のコンテキストには`FeatureEvaluationContext.builder().build()`を使用します。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。 |
| `callback` | AdobeCallback&lt;FeatureEvaluationResult> | 評価された機能ペイロードで呼び出されます。機能が見つからない場合は`null`になる可能性があります。 `AdobeCallbackWithError<FeatureEvaluationResult>`を渡して`fail(...)`を処理することもできます。 |

**応答**

*FeatureEvaluationResult*

| フィールド | タイプ | 説明 |
|---|---|---|
| `id` | 整数 | 数値特徴識別子 |
| `key` | 文字列 | 機能キー |
| `featureGroupKey` | 文字列？ | 機能グループキー（使用可能な場合） |
| `meta` | 文字列？ | 利用可能な場合、メタデータをJSON文字列として機能する |
| `analyticsParam` | AnalyticsParam? | 評価済み機能の分析の詳細 |

*AnalyticsParam*

| フィールド | タイプ | 説明 |
|---|---|---|
| `featureGroupId` | 整数 | 数値フィーチャ グループ ID |
| `featureId` | 整数 | 数値特徴識別子 |
| `variantId` | 文字列？ | バリアント ID |

**例**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult
import com.adobe.marketing.mobile.flags.Flag

Flag.getFeature(
    "new-flag",
    ctx,
    object : AdobeCallback<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            if (!meta.isNullOrEmpty()) {
                // Feature metadata is available: use it to drive the feature behavior
            } else {
                // No metadata available: fall back to the default behavior
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult;
import com.adobe.marketing.mobile.flags.Flag;

Flag.getFeature(
    "new-flag",
    ctx,
    new AdobeCallback<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            String meta = feature != null ? feature.getMeta() : null;
            if (meta != null && !meta.isEmpty()) {
                // Feature metadata is available: use it to drive the feature behavior
            } else {
                // No metadata available: fall back to the default behavior
            }
        }
    }
);
```

### extensionVersion {#extension-version}

Flags拡張機能のバージョン文字列を返します。

**構文**

```kotlin
Flag.extensionVersion(): String
```

**例**

*Kotlin*

```kotlin
val version = Flag.extensionVersion()
```

*Java*

```java
String version = Flag.extensionVersion();
```

## API サマリー {#api-summary}

| API | 返品 |
|---|---|
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. `FeatureEvaluationContext`には、ルールのターゲット属性が含まれています。 [機能評価](#is-feature-enabled)を参照してください。 | コールバックを使用したブーリアン |
| `getFeature(featureKey, evaluationContext, callback)`. 指定されたコンテキストの評価された機能ペイロードを返します。 [getFeature](#get-feature)を参照してください。 | コールバックによるFeatureEvaluationResult |
| `extensionVersion()` | 文字列 |

## 詳細については、 {#see-also}

* [モバイルアプリケーション](../../integrate/mobile-applications.md)
* [SDK](../../integrate/sdks.md)

<!-- -->
