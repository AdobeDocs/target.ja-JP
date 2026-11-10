---
title: Android統合ガイドのフラグ拡張機能
description: Flags拡張機能をAndroid上のAdobe Experience Platform Mobile SDKと統合する方法について説明します。
badge: label="Beta" type="Informative"
hide: true
exl-id: 683ef4d4-e637-4b7b-b694-689c7e65a99e
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: c1fafcfcd7d5d22781abdd10e6eb3c2b84136c2d
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 4%
---
# Androidのフラグ拡張機能 {#android-extension-integration-guide}

このガイドでは、Android上のAdobe Experience Platform Mobile SDKにFlags拡張機能を統合する方法について説明します。

## 前提条件 {#prerequisites}

フラグ拡張機能を実装する前に、次のことを確認してください。

* [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)で設定されたモバイルプロパティ
* モバイルプロパティにインストールおよび設定されたAdobe Flags拡張機能
* Adobe Experience Cloud組織ID
* 露出の分析を受け取るように、モバイルプロパティで設定されたEdge Network データストリーム
* Android API 21 （Android 5.0 Lollipop）以降
* Mobile Core 3.6.0以降（`sdk-bom` 3.17.0以降に含まれる）

## 拡張機能の依存関係 {#extension-dependencies}

Flags拡張機能には、次のAdobe Experience Platform拡張機能が必要です。

| 拡張子 | 説明 | 必須 |
|---|---|---|
| [ モバイルコア ](https://developer.adobe.com/client-sdks/home/base/mobile-core/) | 設定、イベント処理、SDKの初期化を提供 | はい |
| [ライフサイクル](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/) | アプリが前景または背景に移動する際のレポート | はい |
| [Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/) | Adobe Experience Platformに露出分析を送信します | はい |
| Edge Network](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/)の[ID | ユーザーをバリアントに割り当てるために使用するIDを提供します | はい |

これらの拡張機能がデータ収集モバイルプロパティにインストールされ、アプリの依存関係に含まれていることを確認します。

## データ収集でのフラグ拡張機能の設定 {#configure}

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

1. [公開プロセス ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)に従って、設定を更新します。

### 環境ファイル IDの取得 {#environment-file-id}

1. モバイルプロパティで、**[!UICONTROL 環境]**&#x200B;に移動します。

1. 選択した環境の&#x200B;**[!UICONTROL Install]**&#x200B;列でボックスアイコンを選択します。

   ![](../assets/extension-install-2.png)

1. **[!UICONTROL モバイルインストール手順]** ダイアログで、**[!UICONTROL 環境ファイル ID]**&#x200B;をコピーします。

   ![](../assets/extension-install-3.png)

## アプリにフラグ拡張機能を追加 {#add-to-app}

### 依存関係を追加 {#add-dependencies}

>[!IMPORTANT]
>
>Flags拡張機能は、Mobile SDK BOMの一部ではありません。 `<latest-version>`をMaven Centralの最新バージョンに置き換えます。 バージョンがなければ、Gradleは依存関係を解決できません。
>
></br>
実稼動アプリケーションの場合、Adobeでは、「3.+」などの動的バージョンではなく、明示的なバージョン番号を使用することをお勧めします。 詳しくは、[Gradle依存関係の管理] （https://docs.gradle.org/current/userguide/dependency_management.html）を参照してください。

アプリの`build.gradle.kts` （Kotlin）または`build.gradle` （Groovy）ファイルに次の依存関係を追加します。

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM (3.17.0 or later)
    implementation(platform("com.adobe.marketing.mobile:sdk-bom:3.+"))

    // Required extensions (versions managed by the BOM)
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")

    // Flags extension (not managed by the BOM; specify the version)
    implementation("com.adobe.marketing.mobile:flags:<latest-version>")
}
```

>[!TAB Groovy]

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM (3.17.0 or later)
    implementation platform('com.adobe.marketing.mobile:sdk-bom:3.+')

    // Required extensions (versions managed by the BOM)
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'

    // Flags extension (not managed by the BOM; specify the version)
    implementation 'com.adobe.marketing.mobile:flags:<latest-version>'
}
```

>[!ENDTABS]

### SDKの初期化 {#initialize-sdk}

>[!IMPORTANT]
>
>実稼動アプリの場合は、`LoggingMode.ERROR`のみを使用してください。 リリースビルドで`DEBUG`または`VERBOSE`を使用しないでください。

フラグ拡張機能APIを呼び出す前に、`Application` クラスでMobile SDKを初期化します。 モバイルプロパティから環境ファイル IDを使用して、アプリがデータ収集で公開したフラグ設定を取得します。

`MobileCore.initialize`は、Flags拡張機能を含め、Gradle依存関係に含まれるすべてのAdobe拡張機能を登録します。

`MobileCore.initialize`を使用する場合は、`MobileCore.registerExtensions`、`MobileCore.lifecycleStart`、または`MobileCore.lifecyclePause`も呼び出さないでください。 これらはあなたのために取り扱われます。

>[!BEGINTABS]

>[!TAB Kotlin]

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

>[!TAB Java]

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
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID");
    }
}
```

>[!ENDTABS]

### アプリケーションクラスを登録 {#register-application}

`Application` クラスを`AndroidManifest.xml`に登録します：

```xml
<application
    android:name=".MainApplication"
    ... >
</application>
```

### 拡張機能を手動で登録する場合 {#register-manually}

アプリで`MobileCore.initialize`を使用できず、`MobileCore.registerExtensions`に拡張機能を登録する場合は、`Flag.EXTENSION`をリストに追加してください。 従来の`com.adobe.marketing.mobile.Identity`ではなく、Edge Network クラス `com.adobe.marketing.mobile.edge.identity.Identity`のIDを使用してください。

```kotlin
import com.adobe.marketing.mobile.Edge
import com.adobe.marketing.mobile.Lifecycle
import com.adobe.marketing.mobile.MobileCore
import com.adobe.marketing.mobile.edge.identity.Identity
import com.adobe.marketing.mobile.flags.Flag

MobileCore.setApplication(this)
MobileCore.configureWithAppID("YOUR_ENVIRONMENT_FILE_ID")
MobileCore.registerExtensions(
    listOf(Lifecycle.EXTENSION, Identity.EXTENSION, Edge.EXTENSION, Flag.EXTENSION)
) { }
```

この設定では、ライフサイクルは自動的に追跡されません。 すべてのアクティビティの`onResume`の`MobileCore.lifecycleStart(null)`と、その`onPause`の`MobileCore.lifecyclePause()`を呼び出します。 これらの呼び出しがなければ、アプリがバックグラウンド中でも拡張機能はフラグを更新し続け、露出の分析は後で送信されます。

## 評価コンテキスト {#evaluation-context}

`FeatureEvaluationContext`には、フラグルールが使用するターゲティング属性が保持されます。 IDを渡しません。拡張機能は、評価のたびにIdentity for Edge NetworkからIDを読み取ります。 [ カスタム ID](#custom-identity)を参照してください。

| メソッド | 必須 | 説明 |
|---|---|---|
| `withAttributes(map)` | × | `Map<String, List<String>>`. 各キーは、フラグルールで使用される属性名（`locale`や`appVersion`など）です。 各値は、現在のユーザーの値のリストです（例：`["en_US"]`）。 |

* すべての評価にはコンテキストが必要です。 属性がない場合は、`FeatureEvaluationContext.builder().build()`を渡します。
* ビルダーごとに1回まで`withAttributes`を呼び出します。
* 構築されたコンテキストは変更できないので、評価間で再利用できます。

### 使用方法 {#evaluation-context-usage}

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext

val ctx = FeatureEvaluationContext.builder()
    .withAttributes(
        mapOf(
            "locale" to listOf("en_US"),
            "platform" to listOf("ANDROID")
        )
    )
    .build()
```

>[!TAB Java]

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

>[!ENDTABS]

### ターゲティング属性の例 {#sample-attributes}

| 属性 | 説明 | 値の例 |
|---|---|---|
| `locale` | ユーザーのロケール | `["en_US"]`, `["fr_FR"]` |
| `platform` | プラットフォーム | `["ANDROID"]` |
| `appVersion` | アプリバージョン | `["3.0.0"]` |
| `deviceType` | デバイスタイプ | `["phone"]`, `["tablet"]` |

属性名と値は、フラグルールで使用される名前と値と一致する必要があります。

## カスタム ID {#custom-identity}

Flags拡張機能は、ID解決に[Edge Network拡張機能](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/)のIDを使用します。 機能フラグは、CRM IDやロイヤルティ IDなどのカスタム IDでコホートできるため、バリエーションの分割と分析を、アプリケーションにとって重要なIDに結び付けることができます。

機能フラグの作成時に、フラグ UIでカスタム ID名前空間を選択する必要があります。 そのIDに対してフラグを評価するには、一致する名前空間を使用して、デバイス上のEdge ID `identityMap`に同じIDが存在する必要があります。 Edge Network `updateIdentities` APIのIDを実行時に指定します。

### ID マップにカスタム IDを追加する {#add-identity}

フラグを評価する前に、機能フラグで設定された同じ名前空間の下にIDを追加します。

IDを追加する場合は、次の点に注意してください。

* 名前空間は、大文字と小文字を含めて正確に一致する必要があります。
* 名前空間に複数のIDがある場合は、プライマリとしてマークされたIDが使用されます。 それ以外の場合は、最初のものが使用されます。
* フラグが評価されたときにIDが見つからない場合、ユーザーはアプリの起動時に毎回変更される一時的なIDで割り当てられます。 次に、ユーザーのバリエーションをアプリのローンチ間で変更できます。 IDを使用するフラグを評価する前に、必ずIDを設定してください。

>[!BEGINTABS]

>[!TAB Kotlin]

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

>[!TAB Java]

```java
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState;
import com.adobe.marketing.mobile.edge.identity.Identity;
import com.adobe.marketing.mobile.edge.identity.IdentityItem;
import com.adobe.marketing.mobile.edge.identity.IdentityMap;

IdentityMap identityMap = new IdentityMap();
identityMap.addItem(
        new IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true),
        "userCRMId"); // must match the namespace configured on the feature flag
Identity.updateIdentities(identityMap);
```

>[!ENDTABS]

## API リファレンス {#api-reference}

### コールバックとエラー処理 {#callbacks-errors}

次のルールは`isFeatureEnabled`と`getFeature`に適用されます：

* 常にデフォルトのエクスペリエンスを提供する： `AdobeCallbackWithError`を渡し、`fail`でデフォルトのエクスペリエンスを表示します。 プレーン `AdobeCallback`では、エラーが発生したときに呼び出されることはありません。

* 拡張機能は、アプリの起動時にフラグ定義をプリロードします。 その後、フラグはデバイス上で評価されます。

* その他のエラー：`fail`は次の場合に`AdobeError.UNEXPECTED_ERROR`で呼び出されます：

  * 機能キーが空です，
  * 公開された設定にフラグ設定またはExperience Cloud組織IDが見つからない、または
  * アプリの起動時にフラグ定義をダウンロードできませんでした（デバイスがオフラインだったなど）。 拡張機能は、次の設定の更新時（通常は次のアプリ起動時）に再試行します。

### isFeatureEnabled {#is-feature-enabled}

現在のユーザーに対して機能が有効になっているかどうかを返します。

**署名**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
Flag.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

>[!TAB Java]

```java
Flag.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

>[!ENDTABS]

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | 文字列 | 評価する機能のキー |
| `evaluationContext` | FeatureEvaluationContext | ターゲティング属性： `FeatureEvaluationContext.builder().build()`がない場合は使用します。 [評価コンテキスト ](#evaluation-context)を参照してください。 |
| `callback` | AdobeCallback&lt;Boolean> | この機能がユーザーに対して有効になっている場合、`true`で呼び出されます。 機能が見つからない場合、ターゲティングルールが一致しない場合、またはユーザーがコントロールグループ内にある場合に、`false`で呼び出されます。 `AdobeCallbackWithError<Boolean>`を渡してエラーも受信します。 |

**例**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.AdobeCallbackWithError
import com.adobe.marketing.mobile.AdobeError
import com.adobe.marketing.mobile.flags.Flag

Flag.isFeatureEnabled(
    "new-checkout",
    ctx,
    object : AdobeCallbackWithError<Boolean> {
        override fun call(isEnabled: Boolean?) {
            runOnUiThread {
                if (isEnabled == true) showNewCheckout() else showDefaultCheckout()
            }
        }

        override fun fail(error: AdobeError?) {
            runOnUiThread { showDefaultCheckout() }
        }
    }
)
```

>[!TAB Java]

```java
import com.adobe.marketing.mobile.AdobeCallbackWithError;
import com.adobe.marketing.mobile.AdobeError;
import com.adobe.marketing.mobile.flags.Flag;

Flag.isFeatureEnabled(
    "new-checkout",
    ctx,
    new AdobeCallbackWithError<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            runOnUiThread(() -> {
                if (Boolean.TRUE.equals(isEnabled)) {
                    showNewCheckout();
                } else {
                    showDefaultCheckout();
                }
            });
        }

        @Override
        public void fail(AdobeError error) {
            runOnUiThread(() -> showDefaultCheckout());
        }
    }
);
```

>[!ENDTABS]

### getFeature {#get-feature}

現在のユーザーの評価済み機能（メタデータを含む）を返します。 このAPIは、有効または無効を超える必要がある場合に使用します。

**署名**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
Flag.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

>[!TAB Java]

```java
Flag.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

>[!ENDTABS]

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | 文字列 | 評価する機能のキー |
| `evaluationContext` | FeatureEvaluationContext | ターゲティング属性： `FeatureEvaluationContext.builder().build()`がない場合は使用します。 [評価コンテキスト ](#evaluation-context)を参照してください。 |
| `callback` | AdobeCallback&lt;FeatureEvaluationResult> | 評価済み機能で呼び出されるか、機能がユーザーに提供されない場合は`null`で呼び出されます。キーが不明であるか、ターゲティング条件が満たされていないか、ユーザーがコントロール コホート内にあります。 `null`は正常な結果であり、エラーではありません。 コントロールコホートのエクスポージャーは、引き続きAnalyticsに報告されます。 `AdobeCallbackWithError<FeatureEvaluationResult>`を渡して、タイムアウトなどの実際のエラーの`fail(...)`を受け取ります。 |

`null`の結果を「機能オフ」として扱い、デフォルトのエクスペリエンスを表示します。 `fail`が呼び出されたときのデフォルトのエクスペリエンスも表示します。これは、タイムアウトなどの実際のエラーでのみ発生します。

**応答**

*FeatureEvaluationResult*

| フィールド | タイプ | 説明 |
|---|---|---|
| `id` | 整数 | 機能ID |
| `key` | 文字列 | 機能キー |
| `featureGroupKey` | 文字列？ | 機能がグループに属している場合は、機能グループキー |
| `meta` | 文字列？ | 機能に設定されたメタデータ （プレーンテキスト、または設定されていない場合は`null`）。 JSONを保存した場合は、アプリ内の文字列を解析します。 |
| `analyticsParam` | AnalyticsParam? | 評価の分析の詳細 |

*AnalyticsParam*

| フィールド | タイプ | 説明 |
|---|---|---|
| `featureGroupId` | 整数 | 機能グループ ID |
| `featureId` | 整数 | 機能ID |
| `variantId` | 文字列？ | ユーザーが割り当てられたバリアントのID |

**例**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.AdobeCallbackWithError
import com.adobe.marketing.mobile.AdobeError
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult
import com.adobe.marketing.mobile.flags.Flag

Flag.getFeature(
    "new-checkout",
    ctx,
    object : AdobeCallbackWithError<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            runOnUiThread {
                if (!meta.isNullOrEmpty()) applyExperience(meta) else showDefaultExperience()
            }
        }

        override fun fail(error: AdobeError?) {
            runOnUiThread { showDefaultExperience() }
        }
    }
)
```

>[!TAB Java]

```java
import com.adobe.marketing.mobile.AdobeCallbackWithError;
import com.adobe.marketing.mobile.AdobeError;
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult;
import com.adobe.marketing.mobile.flags.Flag;

Flag.getFeature(
    "new-checkout",
    ctx,
    new AdobeCallbackWithError<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            final String meta = feature != null ? feature.getMeta() : null;
            runOnUiThread(() -> {
                if (meta != null && !meta.isEmpty()) {
                    applyExperience(meta);
                } else {
                    showDefaultExperience();
                }
            });
        }

        @Override
        public void fail(AdobeError error) {
            runOnUiThread(() -> showDefaultExperience());
        }
    }
);
```

>[!ENDTABS]

### extensionVersion {#extension-version}

Flags拡張機能のバージョンを返します。

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
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. [isFeatureEnabled](#is-feature-enabled)を参照してください。 | コールバックを使用したブーリアン |
| `getFeature(featureKey, evaluationContext, callback)`. [getFeature](#get-feature)を参照してください。 | コールバックによるFeatureEvaluationResult |
| `extensionVersion()` | 文字列 |

## デバッグ {#debugging}

デバッグするには、デバッグビルドで`MobileCore.setLogLevel(LoggingMode.DEBUG)`を設定し、`Flags`でLogcatをフィルタリングします。 `com.adobe.marketing.mobile.flags.FlagExtension`のMobileCoreから`Discovered extension` メッセージが表示されます。


