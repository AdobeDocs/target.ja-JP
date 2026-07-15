---
title: Android用エクスペリエンスロールアウト拡張機能の統合ガイド
description: Experience Rollout拡張機能をAndroid上のAdobe Experience Platform Mobile SDKと統合する方法について説明します。
hide: true
exl-id: 683ef4d4-e637-4b7b-b694-689c7e65a99e
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 7%

---

# Androidのエクスペリエンスロールアウト拡張機能 {#android-extension-integration-guide}

このガイドでは、Experience Rollout拡張機能をAndroid上のAdobe Experience Platform Mobile SDKと統合する方法について説明します。

## 前提条件 {#prerequisites}

エクスペリエンスのロールアウト拡張機能を実装する前に、次のことを確認してください。

* [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)で設定されたモバイルプロパティ
* Experience Rollout拡張機能がモバイルプロパティにインストールされ、設定されている
* Adobe Experience Cloud組織ID
* 最小SDK:API 21 （Android 5.0 Lollipop）

## 拡張機能の依存関係 {#extension-dependencies}

Experience Rollout拡張機能には、次のAdobe Experience Platform拡張機能が必要です。

| 拡張子 | 説明 | 必須 |
|---|---|---|
| モバイルコア | 設定やイベント処理などのコア機能を提供 | はい |
| ライフサイクル | Mobile SDKのアプリケーションライフサイクルおよびセッションデータを収集します | はい |
| Edge Network | Adobe Experience Platform Edge Networkとの通信が可能 | はい |
| Edge Identity | Edge NetworkのユーザーIDを管理します | はい |

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
1. [公開プロセス ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)に従って、設定を更新します。

### 環境ファイル IDの取得 {#environment-file-id}

1. モバイルプロパティで、**環境**&#x200B;に移動します。
1. 環境の&#x200B;**Install**&#x200B;列の下にあるボックスアイコンを選択します。
1. **モバイルインストール手順** ダイアログで、**環境ファイル ID**&#x200B;をコピーします。

>[!IMPORTANT]
>
>**ステージング**&#x200B;環境では、環境ファイル IDの先頭に`staging/`を付けます。つまり、`staging/<environmentId>`を使用します。 **本番**&#x200B;で、環境ファイル IDを直接使用します。

## エクスペリエンスのロールアウト拡張機能をアプリに追加 {#add-to-app}

### 依存関係を追加 {#add-dependencies}

Mobile SDKの依存関係をプロジェクトに追加します。 Experience Rollout拡張機能には、Mobile Coreと以下に示すEdge関連の拡張機能が必要です。

#### BOMでのGradleの使用（推奨） {#gradle-bom}

アプリの`build.gradle.kts` ファイルに次の依存関係を追加します。

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation(platform("com.adobe.marketing.mobile:sdk-bom:3.+"))

    // Required extensions
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")

    // Experience Rollout extension
    implementation("com.adobe.marketing.mobile:rollout")
}
```

#### Gradleの使用（Groovy） {#gradle-groovy}

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation platform('com.adobe.marketing.mobile:sdk-bom:3.+')

    // Required extensions
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'

    // Experience Rollout extension
    implementation 'com.adobe.marketing.mobile:rollout'
}
```

>[!IMPORTANT]
>
>実稼動アプリケーションの場合は、動的バージョンではなく明示的なバージョン番号を使用することをお勧めします。 詳しくは、[Gradle依存関係の管理](https://docs.gradle.org/current/userguide/dependency_management.html)を参照してください。

### 権限の追加 {#add-permissions}

次の権限を`AndroidManifest.xml` ファイルに追加します。

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### SDKの初期化 {#initialize-sdk}

Experience Rollout拡張機能APIを呼び出す前に、`Application` クラスでMobile SDKを初期化します。 モバイルプロパティの環境ファイル IDを`MobileCore.initialize`で使用すると、アプリはデータ収集で公開したロールアウト設定を取得します。

#### MobileCore.initializeの使用 {#mobile-core-initialize}

Android BOM バージョン 3.8.0以降で使用可能なこのAPIは、拡張機能を自動的に登録し、ライフサイクルトラッキングを有効にします。

>[!IMPORTANT]
>
>実稼動アプリの場合は、`LoggingMode.ERROR`のみを使用してください。 リリースビルドで`DEBUG`または`VERBOSE`を使用しないでください。

**Kotlin**

```kotlin
import android.app.Application
import com.adobe.marketing.mobile.LoggingMode
import com.adobe.marketing.mobile.MobileCore

class MainApplication : Application() {

    override fun onCreate() {
        super.onCreate()

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

`FeatureEvaluationContext`には、ターゲット属性（ロールアウト ルールの照合に使用）とオプション ID （分析に使用）が含まれます。

| メソッド | 必須 | 説明 |
|---|---|---|
| `withIdentity(namespace, id)` | × | 最初の引数：ID名前空間（[Adobe ID名前空間](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces)を参照）。 2つ目の引数：ID値 この評価のためにAnalyticsで名前空間とIDを表す場合に、これを含めます。 指定しない場合、AnalyticsはデフォルトでECIDを使用します。 これは、機能の有効化に関する意思決定の推進には使用されません。 |
| `withAttributes(map)` | × | `Map<String, List<String>>`. キーは、ロールアウト ルールで使用されるコンテキスト属性名です（例：`locale`、`platform`、`appVersion`、`deviceType`）。 値は、現在のユーザー/セッションのキーの候補属性値のリストです（例：`["en_US"]`または`["phone"]`）。 |

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.rollout.FeatureEvaluationContext

val attrs = mapOf(
    "locale" to listOf("en_US"),
    "platform" to listOf("ANDROID"),
    "appVersion" to listOf("3.0.0")
)

val ctx = FeatureEvaluationContext.builder()
    .withIdentity("Email", "customer@example.com")
    .withAttributes(attrs)
    .build()
```

**Java**

```java
import com.adobe.marketing.mobile.rollout.FeatureEvaluationContext;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

Map<String, List<String>> attrs = new HashMap<>();
attrs.put("locale", Arrays.asList("en_US"));
attrs.put("platform", Arrays.asList("ANDROID"));
attrs.put("appVersion", Arrays.asList("3.0.0"));

FeatureEvaluationContext ctx = FeatureEvaluationContext.builder()
        .withIdentity("Email", "customer@example.com")
        .withAttributes(attrs)
        .build();
```

### ターゲティング属性の例 {#sample-attributes}

| 属性 | 説明 | 値の例 |
|---|---|---|
| `locale` | ユーザーのロケール/言語 | `["en_US"]`, `["fr_FR"]` |
| `platform` | プラットフォーム識別子 | `["ANDROID"]` |
| `appVersion` | アプリケーションバージョン | `["3.0.0"]` |
| `deviceType` | デバイスタイプ | `["phone"]`, `["tablet"]` |

## 機能評価の主要な概念 {#key-concepts}

アプリに機能ゲートを実装する際には、次の点に注意してください。

* **属性値を渡します。ラベルは表示されません。** コンテキスト属性値は&#x200B;**大文字と小文字を区別**&#x200B;します。 コンソールに表示されるラベルではなく、アプリまたはweb サイトが送信する生の値（例：`"en_US"`または`"ANDROID"`）を渡します。
* **機能（フラグ）レベルで評価します。** フラグが機能グループに属している場合でも、個々の&#x200B;**機能キー**&#x200B;を使用してAPIを常に呼び出します。 グループレベルの評価はありません。 応答は、ユーザーが入力したバリエーションを返します。
* **IDは、プロファイルにリンクする必要はありません。** 評価は実行時に行われます。 IDが既知のプロファイルにリンクされているかどうかに関係なく、評価イベントがCustomer Journey Analyticsに送信されます。
* **新しいフラグごとにコードを変更する必要があります。** コード内の各フラグキーのゲートを追加します。 `isFeatureEnabled()`を使用してブール値のオン/オフ状態を確認するか、`getFeature()`を使用してバリアントを含む完全な機能ペイロードを取得します。

## API リファレンス {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled`は、特定のコンテキストに対してエクスペリエンスのロールアウト機能がオンかオフかを返します。 `featureKey`、`FeatureEvaluationContext` （オプションのターゲティング属性およびAnalytics用のオプション ID）、およびコールバックを渡します。 [評価コンテキスト ](#evaluation-context)を参照してください。

**署名**

*Kotlin*

```kotlin
Rollout.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

*Java*

```java
Rollout.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | 文字列 | エクスペリエンスロールアウトで評価する機能キー |
| `evaluationContext` | FeatureEvaluationContext | 必要に応じて、Analyticsのターゲティング属性とオプション IDを含めます。空のコンテキストには`FeatureEvaluationContext.builder().build()`を使用します。 [評価コンテキスト ](#evaluation-context)を参照してください。 |
| `callback` | AdobeCallback&lt;Boolean> | 機能が有効になっている場合は`true`で呼び出され、それ以外の場合は`false`です。 `AdobeCallbackWithError<Boolean>`を渡して`fail(...)`を処理することもできます。 |

**例**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.rollout.Rollout

Rollout.isFeatureEnabled(
    "new-checkout-experience",
    ctx,
    object : AdobeCallback<Boolean> {
        override fun call(isEnabled: Boolean?) {
            if (isEnabled == true) {
                showNewCheckout()
            } else {
                showDefaultCheckout()
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.rollout.Rollout;

Rollout.isFeatureEnabled(
    "new-checkout-experience",
    ctx,
    new AdobeCallback<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            if (Boolean.TRUE.equals(isEnabled)) {
                showNewCheckout();
            } else {
                showDefaultCheckout();
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
Rollout.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

*Java*

```java
Rollout.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | 文字列 | エクスペリエンスロールアウトで評価する機能キー |
| `evaluationContext` | FeatureEvaluationContext | 必要に応じて、Analyticsのターゲティング属性とオプション IDを含めます。空のコンテキストには`FeatureEvaluationContext.builder().build()`を使用します。 [評価コンテキスト ](#evaluation-context)を参照してください。 |
| `callback` | AdobeCallback&lt;FeatureEvaluationResult> | 評価された機能ペイロードで呼び出されます。機能が見つからない場合は`null`になる可能性があります。 `AdobeCallbackWithError<FeatureEvaluationResult>`を渡して`fail(...)`を処理することもできます。 |

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

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.rollout.FeatureEvaluationResult
import com.adobe.marketing.mobile.rollout.Rollout

Rollout.getFeature(
    "new-checkout-experience",
    ctx,
    object : AdobeCallback<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            if (!meta.isNullOrEmpty()) {
                applyMetaDrivenExperience(meta)
            } else {
                showFallbackExperience()
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.rollout.FeatureEvaluationResult;
import com.adobe.marketing.mobile.rollout.Rollout;

Rollout.getFeature(
    "new-checkout-experience",
    ctx,
    new AdobeCallback<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            String meta = feature != null ? feature.getMeta() : null;
            if (meta != null && !meta.isEmpty()) {
                applyMetaDrivenExperience(meta);
            } else {
                showFallbackExperience();
            }
        }
    }
);
```

### refreshCache {#refresh-cache}

デフォルトでは、Experience Rollout拡張機能は、設定可能なスケジュールで、サーバーの最新のロールアウトルールと機能を定期的に同期します。 次回のスケジュールされた同期よりも早く更新が必要な場合は、`refreshCache`に電話して強制的に更新します。 一般的なケースには、ログイン後や、アプリの状態がターゲティングに影響を与える影響を与えるような変化が発生した場合などがあります。

**構文**

*Kotlin*

```kotlin
Rollout.refreshCache()
```

*Java*

```java
Rollout.refreshCache();
```

### extensionVersion {#extension-version}

エクスペリエンスのロールアウト拡張機能のバージョン文字列を返します。

**構文**

```kotlin
Rollout.extensionVersion(): String
```

**例**

*Kotlin*

```kotlin
val version = Rollout.extensionVersion()
```

*Java*

```java
String version = Rollout.extensionVersion();
```

## API サマリー {#api-summary}

| API | 返品 |
|---|---|
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. `FeatureEvaluationContext`は、ルールのターゲティング属性と分析のオプション IDを保持します。 [機能評価](#is-feature-enabled)を参照してください。 | コールバックを使用したブーリアン |
| `getFeature(featureKey, evaluationContext, callback)`. 指定されたコンテキストの評価された機能ペイロードを返します。 [getFeature](#get-feature)を参照してください。 | コールバックによるFeatureEvaluationResult |
| `refreshCache()` | 無効 |
| `extensionVersion()` | 文字列 |

## 詳細については、 {#see-also}

* [モバイルアプリケーション](../../integrate/mobile-applications.md)
* [統合ステップ](../../integrate/integration-steps.md)
* [SDK](../../integrate/sdks.md)

<!-- -->
