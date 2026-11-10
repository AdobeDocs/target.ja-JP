---
title: Web統合ガイドのフラグ拡張機能
description: Web アプリケーション用のAdobe Experience Platform Web SDK（Alloy）にFlags拡張機能を統合する方法について説明します。
badge: label="Beta" type="Informative"
hide: true
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: c1fafcfcd7d5d22781abdd10e6eb3c2b84136c2d
workflow-type: tm+mt
source-wordcount: '1229'
ht-degree: 7%
---
# Web用フラグ拡張機能 {#web-extension-integration-guide}

このガイドでは、Web アプリケーション用のAdobe Experience Platform Web SDK（Alloy）にFlags拡張機能を統合する方法について説明します。 フラグ拡張機能を使用すると、web エクスペリエンスの機能フラグ管理と制御されたロールアウトが可能になります。

## 前提条件 {#prerequisites}

フラグ拡張機能を実装する前に、次のことを確認してください。

* [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)で設定されたweb プロパティ
* Adobe Experience Platform Web SDK拡張機能のインストール
* Adobe Experience Cloud組織ID
* 組織内のフラグへのアクセス

### 必要な権限 {#required-permissions}

次のプロパティ権限を持っていることを確認します。

* 現像
* 拡張機能を管理

## 拡張機能の依存関係 {#extension-dependencies}

Flags拡張機能には、次のAdobe Experience Platform拡張機能が必要です。

| 拡張子 | 説明 | 必須 |
|---|---|---|
| Adobe Experience Platform Web SDK | Edge NetworkコミュニケーションやID管理などのコア機能を提供 | はい |

フラグ拡張機能をインストールする前に、この拡張機能がデータ収集web プロパティにインストールされていることを確認してください。

## データ収集でのフラグ拡張機能の設定 {#configure}

### 拡張機能のインストール {#install-extension}

1. [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)にログインします。

1. 「**[!UICONTROL タグ]**」タブを選択し、モバイルプロパティを選択します。

1. **[!UICONTROL 拡張機能]** > **[!UICONTROL カタログ]**&#x200B;に移動します。

1. **[!DNL Adobe Flags]**&#x200B;を検索し、**[!UICONTROL インストール]**&#x200B;を選択します。

   ![](../assets/extension-install.png)

1. 拡張機能の設定を行います。

* クライアント ID: フラグ内のアプリケーションの一意のID。

1. **[!UICONTROL 保存]**&#x200B;を選択します。

1. [公開プロセス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview)に従って、設定を更新します。

   1. 拡張機能をライブラリに追加します。

   1. 開発環境に合わせて構築。

   1. [Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html?lang=ja)で検証します。

   1. ステージングと制作へのプロモーション。

## Web サイトへのタグ埋め込みコードの追加 {#embed-code}

タグライブラリを公開したら、埋め込みコードをweb サイトに追加する必要があります。 埋め込みコードは`<script>` タグで、タグライブラリと、フラグ拡張機能を含むすべての設定済み拡張機能が読み込まれます。

### 埋め込みコードをコピー {#copy-embed-code}

1. データ収集で、web プロパティに移動します。

1. **[!UICONTROL 環境]** メニューにアクセスします。

1. 選択した環境の&#x200B;**[!UICONTROL Install]**&#x200B;列でボックスアイコンを選択します。

   ![](../assets/extension-install-2.png)

1. **[!UICONTROL Web インストール手順]** ダイアログでは、タグはデフォルトで非同期埋め込みコードになります。

1. 埋め込みコードをクリップボードにコピーするには、**[!UICONTROL コピー]** アイコンを選択します。

   >[!NOTE]
   >
   >各環境には一意の埋め込みコード URLがあります。 詳しくは、[環境](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=ja) ドキュメントを参照してください。

   ![](../assets/extension-install-4.png)

### 埋め込みコードの実装 {#implement-embed-code}

>[!NOTE]
>
>`src` URLを、環境ページの実際の埋め込みコードに置き換えます。 URLには、会社識別子、プロパティ識別子、および環境識別子（例：`launch-EN123456789abcdef.min.js`）が含まれています。

HTML ページの`<head>`要素に埋め込みコードを追加します。 埋め込みコードは、タグライブラリに依存する他のスクリプトの前に配置する必要があります。

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Website</title>

  <!-- Adobe Experience Platform Tags embed code -->
  <script src="https://assets.adobedtm.com/your-company/your-property/launch-ENxxxxxxxxxxx.min.js" async></script>
</head>
<body>
  <!-- Your page content -->
</body>
</html>
```

### タグコンポーネントを使用したフラグの評価 {#tags-components}

Flags拡張機能には、タグネイティブの評価サーフェスが用意されています。

| コンポーネント | タイプ | 説明 |
|---|---|---|
| 機能が有効です | 条件 | 現在のユーザー/コンテキストに対して機能が有効かどうかを返します |
| 機能フラグ | データ要素 | ブール値または完全なフィーチャ オブジェクトを返します |

## SDKの初期化 {#initialize-sdk}

タグ拡張機能は、タグライブラリが読み込まれると自動的に初期化されます。 拡張機能は、次の場所でクライアントを公開します。

```javascript
window._flagClient
```

### クライアントの準備を待つ {#client-readiness}

タグは非同期的に読み込まれます。 カスタムコードからSDK メソッドを呼び出す前に、クライアントが初期化されるまで待ちます。

```javascript
window.flagClientReady
  .then(function () {
    const enabled = window._flagClient.isFeatureEnabled('my-feature', context);
    // Use enabled to select the feature or fallback behavior.
  })
  .catch(function (error) {
    console.error('Flags initialization failed:', error);
  });
```

## 評価コンテキスト {#evaluation-context}

`FeatureEvaluationContext`には、ID （評価、A/B バケット、分析に必要）とオプションのターゲティング属性（ルールの照合に使用）が含まれます。

| プロパティ | 必須 | 説明 |
|---|---|---|
| `identityNamespace` | ○ | ID名前空間（[Adobe ID名前空間](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces)を参照）。 共通の値：`ECID`、`Email`、`CRMId`。 |
| `identityId` | はい | 現在のユーザーのID値。 |
| `attributes` | × | `Record<string, string[]>`. キーは、フラグルールで使用されるコンテキスト属性名です（例：`locale`、`platform`）。 値は、そのキーの候補属性値のリストです。 |

タグコンポーネントでは、条件またはデータ要素UIでIDのデフォルトを設定します。 機能フラグデータ要素は、2番目の引数がフラット属性マップの場合、`getVar(name, attributes)`を介してランタイム属性も受け入れます。

### 使用方法 {#usage}

```javascript
const context = {
  identityNamespace: 'ECID',
  identityId: 'your-visitor-ecid',
  attributes: {
    locale: ['en-US'],
    platform: ['web']
  }
};
```

## API リファレンス {#api-reference}

### 機能の評価 {#is-feature-enabled}

`isFeatureEnabled`は、指定されたコンテキストに対してフラグ機能がオンかオフかを返します。 `featureKey`と`FeatureEvaluationContext`を渡します。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。 **機能が有効になっています** タグ条件を使用するか、初期化後にカスタムコードから`window._flagClient.isFeatureEnabled(...)`を呼び出します。

**署名**

```javascript
isFeatureEnabled(featureKey: string, context: FeatureEvaluationContext): boolean
```

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | string | フラグで評価する機能キー |
| `context` | FeatureEvaluationContext | ID （必須）とオプションのターゲティング属性。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。 |

## 機能フラグデータ要素の作成 {#create-data-element}

ルールまたはカスタムコードで`%Data Element Name%`として利用可能なフラグ値が必要な場合は、データ要素を使用します。

1. プロパティで、**[!UICONTROL データ要素]** メニューにアクセスし、**[!UICONTROL データ要素を追加]**&#x200B;を選択します。

   ![](../assets/extension-install-5.png)

1. **データ要素を作成**&#x200B;画面で、タグフィールドを設定します。

   * **[!UICONTROL 名前]**：わかりやすい名前（例：`checkout flag`）
   * **[!UICONTROL 拡張機能]**: フラグ
   * **[!UICONTROL データ要素タイプ]**：機能フラグ

1. **フラグ**&#x200B;拡張フィールドを設定します。

   * **[!UICONTROL 機能キー]**：一意のフラグキー（例：`checkout_flag`）、必須。
   * **[!UICONTROL Return Type]**: **ブール値（true/false）** – 有効/無効、または&#x200B;**機能オブジェクト（詳細）** – 完全なペイロード （必須：`meta`を含む）。

     | 戻り値タイプ | 次に解決する |
     |---|---|
     | ブール値（true／false） | 有効な場合は`true`、それ以外の場合は`false` |
     | 機能オブジェクト（詳細） | フラグが有効で、コンテキストがそのオーディエンスと一致する場合、機能ペイロードを評価しました。フラグが無効になっている場合、見つからない場合、またはコンテキストが一致しない場合、`null` |

1. **保存**&#x200B;を選択します。

### データ要素の使用 {#use-data-element}

ルールでは、名前で参照します（例：`%Test Flag%`）。

カスタムコードでは、`_satellite.getVar`を使用します。 ランタイム属性を使用して、フラット属性マップを2番目の引数として渡して評価します。

```javascript
var isEnabled = _satellite.getVar('Test Flag', {
  locale: ['en-US'],
  platform: ['web']
});
```

**カスタムコード**

```javascript
var isEnabled = _satellite.getVar('Test Flag', {
  locale: ['en-US'],
  platform: ['web']
});
if (isEnabled) {
  // your custom code
} else {
  // your default code
}
```

### getFeature {#get-feature}

`getFeature`は、有効/無効を超えるメタデータが必要な場合に、評価された機能ペイロードを返します。

**機能フラグ** データ要素を&#x200B;**戻り型：機能オブジェクト（詳細）**&#x200B;で使用するか、[機能フラグデータ要素の作成](#create-data-element)を参照するか、`flagClientReady`の解決後にカスタムコードから`window._flagClient.getFeature(...)`を呼び出します。

**署名**

```javascript
getFeature(featureKey: string, context: FeatureEvaluationContext): FeatureResult | null
```

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | string | フラグで評価する機能キー |
| `context` | FeatureEvaluationContext | ID （必須）とターゲティング属性。 [評価コンテキスト &#x200B;](#evaluation-context)を参照してください。 |

**応答**

`getFeature`は、フラグが有効になっていて、指定されたコンテキストがフラグオーディエンス条件に一致する場合にのみフラグを評価します。 その場合は結果オブジェクトを返し、それ以外の場合は`null`を返します。

*FeatureResult*

| フィールド | タイプ | 説明 |
|---|---|---|
| `id` | 数値 | 数値特徴識別子。 機能レベルのコントロール センチネルの`-1`。 |
| `key` | 文字列\| null | 機能キー。 機能レベルのコントロール センチネルの`null`。 |
| `featureGroupKey` | 文字列\| null | 機能グループキー（使用可能な場合） |
| `meta` | 文字列\| null | 機能メタデータ（利用可能な場合） |
| `analyticsParam` | AnalyticsParam \| null | 評価済み機能の分析の詳細 |

*AnalyticsParam*

| フィールド | タイプ | 説明 |
|---|---|---|
| `featureGroupId` | 数値 | 数値フィーチャ グループ ID |
| `featureId` | 数値 | 数値特徴識別子 |
| `variantId` | 数値\| null | バリアント ID （ユーザーがコントロール グループ内にある場合は`0`） |

**コントロール グループの動作**

| シナリオ | isFeatureEnabled | getFeature | Analytics イベント isFeatureEnabled | Analytics イベント getFeature |
|---|---|---|---|---|
| 処理 | `true` | 通常の結果 | ○ | ○ |
| 機能レベルの制御 | `false` | センチネル （`id: -1`, `key: null`） | はい（`variantId: 0`） | はい |
| 条件が一致しない/見つかりません | `false` | `null` | × | × |

**例**

*タグ データ要素*

ルール内のデータ要素（例：`%Test Feature%`）を参照し、`_satellite.getVar`を介して取得します。

*カスタムコード*

```javascript
var feature = _flagClient.getFeature('new-test-flag', {
  identityNamespace: 'ECID',
  identityId: visitorEcid,
  attributes: {
    locale: ['en-US']
  }
});

var meta = feature && feature.meta;
if (meta) {
  // your custom code
} else {
  // your default code
}
```

### extensionVersion {#extension-version}

Flags拡張機能のバージョン文字列を返します。

**署名**

```javascript
_flagClient.extensionVersion(): string
```

**例**

```javascript
const version = _flagClient.extensionVersion();
console.log(`Flags extension version: ${version}`);
```

## API サマリー {#api-summary}

| API | 返品 |
|---|---|
| 機能フラグ （タグデータ要素、ブール値） | ブール型 |
| 機能フラグ （タグデータ要素、オブジェクト） | 機能オブジェクトまたは`null` |
| `window.flagClientReady` | Promise – 拡張機能の初期化を待つ |
| `window._flagClient.isFeatureEnabled(featureKey, context)` | ブール型 |
| `window._flagClient.getFeature(featureKey, context)` | 機能オブジェクトまたは`null` |
| `window._flagClient.extensionVersion()` | 拡張機能バージョン文字列 |

## エラー処理 {#error-handling}

拡張機能はエラーを適切に処理します。

| シナリオ | 動作 |
|---|---|
| 初期化時にネットワークを利用できません | SDKは、バックオフで最初のフェッチを3回再試行し、初期化が失敗します。 `window.flagClientReady`と`_satellite.getVar(...)`は`Failed to initialize Flag`で拒否し、`window._flagClient`は`undefined`のままです。 |
| コンテキスト内にIDがありません | 評価でエラーがスローされます。`identityNamespace`と`identityId`の両方を指定してください |
| 機能が見つかりません | `getFeature`さんが`null`を返し、`isFeatureEnabled`さんが`false`を返します |

**例**

```javascript
try {
  const isEnabled = _flagClient.isFeatureEnabled('my-feature', context);
  // Use the result
} catch (error) {
  console.error('Evaluation failed:', error.message);
  // Use default value
}
```

## ベストプラクティス {#best-practices}

### 一貫したIDを提供 {#consistent-identity}

複数の評価で同じID名前空間とIDを使用し、パーセンテージのロールアウトで一貫したグループ化を実現します。

**例**

```javascript
const context = {
  identityNamespace: 'ECID',
  identityId: identity,
  attributes: {
    locale: ['en-US'],
    platform: ['web']
  }
};

const isEnabled = _flagClient.isFeatureEnabled('my-feature', context);
```

### 欠けている機能を適切に処理 {#handle-missing}

機能が見つからなかったり、評価が失敗したりすると、常にフォールバック動作を提供します。

```javascript
const feature = _flagClient.getFeature('new-test-flag', context);

if (feature && feature.meta) {
  // your custom code
} else {
  // Feature not enabled - use default code
}
```

### ページ読み込み後に評価 {#evaluate-after-load}

APIを呼び出す前に、タグライブラリとフラグ拡張機能が初期化されていることを確認します。 ルールの&#x200B;**Library Loaded** イベント、**機能フラグ** データ要素を使用するか、`flagClientReady`を待ちます。

```javascript
window.flagClientReady.then(function () {
  var isEnabled = window._flagClient.isFeatureEnabled('my-feature', context);
  // Use the result
});
```

## 詳細については、 {#see-also}

* [最初の機能フラグを作成](../../feature-flags/create-your-first-feature-flag.md)
* [機能フラグと機能グループのオーディエンス](../../audience/audience-in-feature-flags-and-feature-groups.md)
* [レポート](../../feature-flags/reporting.md)

