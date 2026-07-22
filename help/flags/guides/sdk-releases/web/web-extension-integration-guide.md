---
title: Web統合ガイドのフラグ拡張機能
description: Web アプリケーション用のAdobe Experience Platform Web SDK（Alloy）にFlags拡張機能を統合する方法について説明します。
badge: label="Beta" type="Informative"
hide: true
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 8%

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

1. Adobe IDの資格情報を使用して[experience.adobe.com](https://experience.adobe.com)にログインします。
1. **データ収集** > **タグ**&#x200B;に移動します。
1. 目的のタグプロパティを選択します。
1. **拡張機能** > **カタログ**&#x200B;に移動します。
1. **フラグ**&#x200B;を検索し、拡張カードを選択します。
1. **インストール**&#x200B;を選択します。

### 拡張機能の設定 {#configure-settings}

Flags拡張機能をインストールすると、設定ページに移動します。 以下の設定を指定します。

| 設定 | 説明 | 必須 |
|---|---|---|
| クライアント ID | フラグ内のアプリケーションの一意のID。 | はい |

### 保存して公開 {#save-publish}

1. 拡張機能の設定を保存するには、**保存**&#x200B;を選択します。
1. 公開フローに従って、変更をデプロイします。
   1. 拡張機能をライブラリに追加します。
   1. 開発環境に合わせて構築。
   1. Adobe Experience Platform Debuggerによる検証。
   1. ステージングと制作へのプロモーション。

## Web サイトへのタグ埋め込みコードの追加 {#embed-code}

タグライブラリを公開したら、埋め込みコードをweb サイトに追加する必要があります。 埋め込みコードは`<script>` タグで、タグライブラリと、フラグ拡張機能を含むすべての設定済み拡張機能が読み込まれます。

### 埋め込みコードをコピー {#copy-embed-code}

1. データ収集で、web プロパティに移動します。
1. 左側のナビゲーションで「**環境**」を選択します。
1. ターゲット環境（開発、ステージング、実稼動）の行で、**インストール**&#x200B;列の下にあるボックスアイコンを選択します。
1. **Web インストール手順** ダイアログでは、タグはデフォルトで非同期埋め込みコードになります。
1. 埋め込みコードをクリップボードにコピーするには、**コピー** アイコンを選択します。
1. モーダルを閉じるには、**閉じる**&#x200B;を選択します。

>[!NOTE]
>
>各環境には一意の埋め込みコード URLがあります。 詳しくは、「環境」を参照してください。

### 埋め込みコードの実装 {#implement-embed-code}

HTML ページの`<head>`要素に埋め込みコードを追加します。 埋め込みコードは、タグライブラリに依存する他のスクリプトの前に配置する必要があります。

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Website</title>

  <!-- Adobe Experience Platform Tags embed code -->
  <script src="https://assets.adobedtm.com/yourcompany/your-property/launchENxxxxxxxxxxx.min.js" async></script>
</head>
<body>
  <!-- Your page content -->
</body>
</html>
```

>[!NOTE]
>
>`src` URLを、環境ページの実際の埋め込みコードに置き換えます。 URLには、会社識別子、プロパティ識別子、および環境識別子（例：`launch-EN123456789abcdef.min.js`）が含まれています。

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

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled`は、指定されたコンテキストに対してフラグ機能がオンかオフかを返します。 `featureKey`と`FeatureEvaluationContext`を渡します。 [評価コンテキスト ](#evaluation-context)を参照してください。 **機能が有効になっています** タグ条件を使用するか、初期化後にカスタムコードから`window._flagClient.isFeatureEnabled(...)`を呼び出します。

**署名**

```javascript
isFeatureEnabled(featureKey: string, context: FeatureEvaluationContext): boolean
```

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | string | フラグで評価する機能キー |
| `context` | FeatureEvaluationContext | ID （必須）とオプションのターゲティング属性。 [評価コンテキスト ](#evaluation-context)を参照してください。 |

### 機能フラグデータ要素の作成 {#create-data-element}

ルールまたはカスタムコードで`%Data Element Name%`として利用可能なフラグ値が必要な場合は、データ要素を使用します。

**手順**

1. プロパティで、**データ要素**&#x200B;に移動し、**データ要素を追加**&#x200B;を選択します。
1. **データ要素を作成**&#x200B;画面で、タグフィールドを設定します。

   | フィールド | 値 |
   |---|---|
   | 名前 | わかりやすい名前（例：`checkout flag`） |
   | 拡張子 | フラグ |
   | データ要素タイプ | 機能フラグ |

1. **フラグ**&#x200B;拡張フィールドを設定します。

   | フィールド | 必須 | 説明 |
   |---|---|---|
   | 機能キー | はい | 一意のフラグキー（例：`checkout_flag`） |
   | 戻り値の型 | はい | **Boolean （true/false）** – 有効/無効、または&#x200B;**機能オブジェクト （詳細）** — `meta`を含む完全なペイロード |

1. **保存**&#x200B;を選択します。

**タイプを返す**

| 戻り値タイプ | 次に解決する |
|---|---|
| ブール値（true／false） | 有効な場合は`true`、それ以外の場合は`false` |
| 機能オブジェクト（詳細） | 完全に評価された機能ペイロード。ルールを満たさない場合は`null` |

### データ要素の使用 {#use-data-element}

ルール内 – 名前で参照（例：`%Test Flag%`）。

カスタムコードでは、`_satellite.getVar`を使用します。 ランタイム属性を使用して、フラット属性マップを2番目の引数として渡して評価します。

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

**機能フラグ** データ要素を&#x200B;**戻り型：機能オブジェクト（詳細）**、[機能フラグデータ要素の作成](#create-data-element)を参照、または`flagClientReady`の解決後にカスタムコードから`window._flagClient.getFeature(...)`を呼び出して使用します。

**署名**

```javascript
getFeature(featureKey: string, context: FeatureEvaluationContext): FeatureResult | null
```

**パラメーター**

| パラメーター | タイプ | 説明 |
|---|---|---|
| `featureKey` | string | フラグで評価する機能キー |
| `context` | FeatureEvaluationContext | ID （必須）とターゲティング属性。 [評価コンテキスト ](#evaluation-context)を参照してください。 |

**応答**

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
| `variantId` | 数値\| null | バリアント ID （`0` コントロール用） |

**コントロール グループの動作**

| シナリオ | isFeatureEnabled | getFeature | Analytics イベント isFeatureEnabled | Analytics イベント getFeature |
|---|---|---|---|---|
| 処理 | `true` | 通常の結果 | ○ | ○ |
| 機能レベルの制御 | `false` | センチネル （`id: -1`, `key: null`） | はい（`variantId: 0`） | はい |
| 条件が一致しない/見つかりません | `false` | `null` | × | × |

**例**

```javascript
var feature = _flagClient.getFeature('new-testflag', {
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
const feature = _flagClient.getFeature('new-testflag', context);

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

<!-- -->
