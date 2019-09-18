---
description: at.js 1.*x*からat.js 2.*x*へのアップグレード
keywords: at.jsリリース；at.jsバージョン；単一ページアプリ；spa；クロスドメイン；クロスドメイン
seo-description: Adobe Target at.js 1.*x*からat.jsバージョン2.0.0にアップグレードする方法に関する詳細情報
seo-title: Adobe Target at.jsバージョン1からアップグレードします。*x*をat.jsバージョン2に変更します。*x*
solution: 'Target '
subtopic: 導入
title: at.js 1.*x*からat.js 2.*x*へのアップグレード
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Upgrading from at.js 1.*x* to at.js 2.*x* {#upgrading-from-atjs-1x-to-atjs-200}

at.js の最新バージョンは、次世代のクライアント側のテクノロジーで、パーソナライゼーションを実行するための機能セットを提供します。[!DNL Adobe Target]この新しいバージョンは、シングルページアプリケーション（SPA）と調和したインタラクションを実現するための at.js のアップグレードに焦点を当てています。

Here are some benefits of using at.js 2.*x* that are not available in previous versions:

* ページ読み込み時にすべてのオファーをキャッシュし、複数のサーバー呼び出しを単一のサーバー呼び出しに減らす機能。
* 従来のサーバー呼び出しで発生する遅延時間なしで、キャッシュ経由でオファーが即座に表示されるため、サイトでのエンドユーザーのエクスペリエンスが著しく向上します。
* 1 行のシンプルなコードと開発者による 1 回限りのセットアップで、マーケティング担当者は SPA 上で VEC を使用して A/B および XT アクティビティを作成し、実行できます。

## at.js 2.*x* システム図

The following diagrams help you understand the workflow of at.js 2.*x* with Views and how this enhances the SPA integration. To get a better introduction of the concepts used in at.js 2.*x*, see [Single Page Application implementation](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

![at.js 2.*xを使用したTargetのフロー*](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| 呼び出し | 詳細 |
| --- | --- |
| 1 | 呼び出しユーザーが認証されると、呼び出しが [!DNL Experience Cloud ID]を返し、別の呼び出しが顧客 ID を同期します。 |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.js は、ページに実装されているスニペットを非表示にするオプションを使用して非同期で読み込むこともできます。 |
| 3 | すべての設定済みパラメーター（MCID、SDID および顧客 ID）を含む、ページ読み込みリクエストがおこなわれます。 |
| 4 | プロファイルスクリプトが実行されてから、プロファイルストアにフィードされます。ストアは、オーディエンスライブラリから正規のオーディエンスをリクエストします（例えば、Adobe Analytics、Audience Management などから共有されたオーディエンス）。<br>顧客属性がバッチ処理でプロファイルストアに送信されます。 |
| 5 | URL リクエストパラメーターとプロファイルデータに基づいて、[!DNL Target] が現在のページおよび将来のビューでどのアクティビティおよびエクスペリエンスを訪問者に返すかを決定します。 |
| 6 | ターゲットコンテンツが（オプションで、追加のパーソナライゼーションに関するプロファイル値を含めて）ページに送り返されます。<br>デフォルトコンテンツがちらつくことなく、可能な限り迅速に現在のページ上のターゲットコンテンツが表示されます。<br>SPA でのユーザーアクションの結果として表示されるビューのターゲットコンテンツは、ブラウザーにキャッシュされます。そのため、`triggerView()` を介してビューがトリガーされたときに追加のサーバー呼び出しをおこなわずに即座にターゲットコンテンツを適用できます。 |
| 7 | Analytics データがデータ収集サーバーに送信されます。 |
| 8 | ターゲットデータは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。<br>A4T レポートを使用して、Analytics データが Analytics と Target の両方に表示できるようになります。 |

これで、`triggerView()` が SPA のどこに 実装されているかに関わらず、ビューとアクションはキャッシュから取得され、サーバー呼び出しなしでユーザーに表示されるようになります。`triggerView()` は、インプレッション数を増分して記録するために、[!DNL Target] バックエンド に通知リクエストもおこないます。

![Targetのフローat.js 2.** x triggerView](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 呼び出し | 詳細 |
| --- | --- |
| 1 | `triggerView()` は SPA で呼び出され、ビューをレンダリングし、ビジュアル要素を変更ためのアクションを適用します。 |
| 2 | ビューのターゲットコンテンツがキャッシュから読み取られます。 |
| 3 | デフォルトコンテンツがちらつくことなく、可能な限り迅速にターゲットコンテンツが表示されます。 |
| 4 | 通知リクエストが [!DNL Target] プロファイルストア に送信され、アクティビティで訪問者がカウントされ、指標が増分されます。 |
| 5 | Analytics データがデータ収集サーバーに送信されます。 |
| 6 | Target データは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。A4T レポートを使用して、Analytics データが Analytics と Target の両方に表示できるようになります。 |

## at.js 2をデプロイします。*x* {#deploy-atjs-200}

1. at.js 2をデプロイします。*Adobe* Launch [拡張機能](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) 。

   >[!NOTE]
   >
   > Adobe Launch を使用した at.js のデプロイが、推奨される方法です。.

   または

   Manually download at.js 2.*x* using the Target UI and deploy it using the [method of your choice](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md).

## 廃止された at.js 関数

There are several functions that have been deprecated in at.js 2.*x*.

>[!IMPORTANT]
>
>If these deprecated functions are still used on your site when at.js 2.*x* is deployed, you will see console warnings. The recommended approach when upgrading is to test the deployment of at.js 2.*x* in a staging environment and make sure to go through each and every warning that has been logged in the console and translate the deprecated functions to new functions introduced in at.js 2.*x*.

廃止された関数とそれらに対応する関数は、以下のとおりです。関数の完全なリストについては、[at.js 関数](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)を参照してください。

>[!NOTE]
>at.js 2.*x* では、`mboxDefault` としてマークされた要素は自動的に非表示されなくなりました。したがって、サイト上またはタグマネージャーを介して、あらかじめ非表示にするロジックを手動で用意する必要があります。

### mboxCreate(mbox,params)

**説明**：

リクエストを実行し、`mboxDefault` クラス名を持つ最も近い DIV にオファーを適用します。

**例**：

```
<div class="mboxDefault">
  default content to replace by offer
</div>
<script>
  mboxCreate('mboxName','param1=value1','param2=value2');
</script>
```

**at.js 2.*x相当*数**

`mboxCreate(mbox, params)` に代わるものは、`getOffer()` および `applyOffer()` です。

**例**：

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  var el = document.currentScript.previousElementSibling;
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2"
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: el,
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      el.style.visibility = "visible";
    }
  });
</script> 
```

### mboxDefine() と mboxUpdate()

**説明**：

要素と mbox 名の間の内部マッピングを作成しますが、リクエストを実行しません。`mboxUpdate()` と併用します。この mboxUpdate がリクエストを実行し、`mboxDefine()` の nodeId で識別された要素にオファーを適用します。また、`mboxCreate` によって開始された mbox を更新するために使用できます。

**例**：

```
<div id="someId" class="mboxDefault"></div>
<script>
 mboxDefine('someId','mboxName','param1=value1','param2=value2');
 mboxUpdate('mboxName','param3=value3','param4=value4');
</script>
```

**at.js 2.*x相当***:

`mboxDefine()` と `mboxUpdate` に代わるものは、`getOffer()` と `applyOffer()`（`applyOffer()` でセレクターオプションを使用）です。この方法を使用すると、ID を持つ要素だけではなく、CSS セレクターを使用してオファーを要素にマッピングできます。

**例**：

```
<div id="someId" class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2",
      param3: "value3",
      param4: "value4" 
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: "#someId",
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      var el = document.getElementById("someId");
      el.style.visibility = "visible";
    }
  });
</script>
```

### adobe.target.registerExtension()

**説明**：

特定の拡張を登録するための標準的な方法を提供します。

この関数はサポートされなくなったため、使用しないでください。

## 2.0 で廃止、新規追加およびサポートされている at.js functio 関数の概要

| メソッド | 対応? | 新登場? | 廃止? <br>（デフォルトコンテンツが表示されます） |
| --- | --- | --- | --- |
| `getOffer()` | ○ |  |  |
| `getOffers()` |  | ○ |  |
| `applyOffer()` | ○ |  |  |
| `applyOffers()` |  | ○ |  |
| `triggerView()` |  | ○ |  |
| `trackEvent()` | ○ |  |  |
| `mboxCreate()` |  |  | ○ |
| `mboxDefine()`<br>`mboxUpdate()` |  |  | ○ |
| `targetGlobalSettings()` | ○ |  |  |
| `Data Providers` | ○ |  |  |
| `targetPageParams()` | ○ |  |  |
| `targetPageParamsAll()` | ○ |  |  |
| `registerExtension()` |  |  | ○ |
| `At.js Custom Events` | ○ |  |  |

## 制限事項と注意事項

次の制限事項と注意事項を把握しておいてください。

### コンバージョントラッキング

コンバージョントラッキングに `mboxCreate()` を使用している場合、`trackEvent()` または `getOffer()` を使用する必要があります。

### オファーの配信

`mboxCreate()` を `getOffer()` または `applyOffer()` で置き換えない場合、オファーが配信されない場合があります。

### at.js 2が可能。*at.js* 1の間は、一部のページでxが使用されます。*x* または mbox.js が他のページにあるときに、at.js 2.x をを一部のページで使用できますか？

できます。訪問者プロファイルは、異なるバージョンやライブラリを使用してページ間で保持されます。Cookie の形式は同じです。

### New API use in at.js 2.*x*

at.js 2.*x* は、Delivery API と呼ばれる新しい API を使用します。at.js が [!DNL Target] エッジサーバーを正しく呼び出しているかどうかデバッグするには、ブラウザーの開発者ツールの「ネットワーク」タブで「delivery」、「`tt.omtrdc.net`」、またはクライアントモードをフィルタリングします。また、[!DNL Target] はキーと値のペアの変わりに JSON ペイロードを送信します。

### Target グローバル mbox の廃止

at.js 2.*x,*`target-global-mbox`, the network calls. 代わりに、[!DNL Target] サーバーに送信される JSON ペイロードの「`target-global-mbox`」構文を以下のように「`execute > pageLoad`」に置き換えました。

```
{
  "id": {
    // ...
  },
  "context": {
    "channel": "web",
    // ...
  },
  "execute": {
    "pageLoad": {}
  }
}
```

基本的に、グローバル mbox のコンセプトは、ページ読み込み時にオファーとコンテンツを取得するかについて [!DNL Target] へ通知するために導入されました。そのため、最新バージョンではこれをより明確にしています。

### at.js のグローバル mbox 名は重要ではなくなりましたか？

[!UICONTROL Target／セットアップ／実装／at.js 設定を編集] を使用して、グローバル mbox 名を指定できます。この設定は [!DNL Target] エッジサーバーによって使用され、execute &gt; pageLoad が [!DNL Target] UI に表示されるグローバル mbox 名に変換されます。これにより、ユーザーはサーバーサイド API、フォームベースのコンポーザー、プロファイルスクリプトの使用、およびグローバル mbox 名を使用したオーディエンスを引き続き作成できます。まだ at.js 1.*x* または mbox.js を使用しているページがある場合、次の図のように「[!UICONTROL セットアップ／環境設定]」ページの順に移動して、同じグローバル mbox 名 を設定することを強くお勧めします。

![at.js ダイアログの変更](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

および

![カスタムグローバル mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

### Does the auto-create global mbox setting need to be turned on for at.js 2.*x*?

ほとんどの場合では、有効にする必要があります。This setting tells at.js 2.*x* to fire a request to the [!DNL Target] edge servers upon page load. グローバル mbox は execute &gt; pageLoad に変換されているため、ページ読み込み時にリクエストを送信する場合、この設定を有効にする必要があります。

### Will existing VEC activities continue to work, even though the target global mbox name is not specified from at.js 2.*x*?

動作します。execute &gt; pageLoad は、`target-global-mbox` のような [!DNL Target] バックエンドで処理されるためです。

### フォームベースのアクティビティのターゲット設定先が `target-global-mbox` の場合、これらのアクティビティは引き続き機能しますか？

機能します。execute &gt; pageLoad は、`target-global-mbox` のような [!DNL Target] エッジサーバーで処理されるためです。

### Supported and non-supported at.js 2.*x* Settings

| 設定 | 対応? |
| --- | --- |
| X-Domain | × |
| グローバル mbox 自動作成 | ○ |
| グローバル mbox 名 | ○ |

### at.js 2.xでのクロスドメイントラッキングのサポート {#cross-domain}

クロスドメイントラッキングを使用すると、異なるドメイン間で訪問者を縫い合わせることができます。 ドメインごとに新しいcookieを作成する必要があるので、訪問者がドメイン間を移動する際に、訪問者を追跡するのは困難です。 クロスドメイントラッキングを実現するために、 [!DNL Target] サードパーティcookieを使用してドメイン間で訪問者を追跡します。 これにより、個別のドメイン間を移動した場合に、同じエクスペリエ `siteA.com` ンスにま `siteB.com` たがって訪問者が残るTargetアクティビティを作成できます。 この機能は、Target のサードパーティおよびファーストパーティ Cookie の動作に結びついています。

>[!NOTE]
>
>クロスドメイントラッキングは、at.js 2の初期設定ではサポートされていません。*x* ではサポートされていませんでした。クロスドメイントラッキングはat.js 2でサポートされています。*Experience* Cloud ID(ECID)ライブラリv4.3.0以降を使用して、

Targetでは、サードパーティCookieがに保存されます `<CLIENTCODE>.tt.omtrdc.net`。 ファーストパーティCookieはに保存されま `clientdomain.com`す。 最初のリクエストは、HTTP 応答ヘッダーを返します。このヘッダーによって、`mboxSession` および `mboxPC` という名前のサードパーティ Cookie の設定が試行され、リダイレクトリクエストが追加のパラメーター（`mboxXDomainCheck=true`）と共に返されます。ブラウザーがサードパーティcookieを受け入れる場合、リダイレクトリクエストにはそれらのcookieが含まれ、エクスペリエンスが返されます。 このワークフローは、HTTP GET メソッドの使用により可能になっています。

However, in at.js 2.*x*, HTTP GET is no longer used and instead we use HTTP POST. HTTP POSTがat.js 2を介して使用されるようになりました。*xを指定し* 、JSONペイロードをTarget edgeサーバーに送信します。 つまり、ブラウザがサードパーティ Cookie をサポートするかどうかを確認するためのリダイレクトリクエストは中断されます。これは、HTTP GET要求は等価なトランザクションですが、HTTP POSTは非等価で、任意に繰り返してはいけないからです。 したがって、at.js 2でのクロスドメイントラッキングです。*xは既製* でサポートされなくなりました。 at.js 1のみ。*xには* 、クロスドメイントラッキングの追加設定不要なサポートが含まれています。

クロスドメイントラッキングを使用する場合は、 [ECIDライブラリv4.3.0+をat.js 2と共にインストールする](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) 必要があります。*x* ではサポートされていませんでした。ECIDライブラリは、複数のドメインで訪問者を識別するために使用される永続的なIDを管理するために存在します。 ECIDライブラリv4.3.0以降とat.js 2をインストールした後。*x*、一意のドメインにまたがるアクティビティを作成し、ユーザーを追跡できます。

### グローバル mbox 自動作成はサポートされています

This setting tells at.js 2.*x* to fire a request to the [!DNL Target] edge servers on page-load. [!DNL Target] エッジサーバーがグローバル mbox を execute&gt; pageLoad に変換します。ページロード時にリクエストを発行する場合、この設定を有効にする必要があります。

### グローバル mbox 名はサポートされています

[!UICONTROL Target／セットアップ／実装／at.js 設定を編集] を使用して、グローバル mbox 名を指定できます。[!DNL Target] エッジサーバーがこの設定を使用して、execute &gt; pageLoad を入力されたグローバル mbox 名に変換します。これによりユーザーは引き続き、サーバーサイド API、フォームベースのコンポーザー、プロファイルスクリプトの使用、およびグローバル mbox をターゲットにしたオーディエンスの作成ができます。

### 以下の at.js カスタムイベントは `triggerView()` に適用できますか？または `applyOffer()` や `applyOffers()` のみですか？

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

適用できます。at.js カスタムイベントは `triggerView()` にも適用できます。

### `triggerView()` を使用して `{“page” : “true”}` を呼び出すと、通知が [!DNL Target] バックエンドに送信され、インプレッションが増加します。これによりプロファイルスクリプトも実行されますか？

[!DNL Target] バックエンドに対してプリフェッチ呼び出しが実行されると、プロファイルスクリプトが実行されます。その後、影響を受けたプロファイルデータは暗号化され、クライアント側に返されます。`{"page": "true"}` を使用した `triggerView()` が呼び出されると、通知が暗号化されたプロファイルデータとともに送信されます。このとき、[!DNL Target] バックエンドはプロファイルデータを復号してデータベースに保存します。

### ちらつきに対処するために、`triggerView()` を呼び出す前に、事前に非表示になるコードを追加する必要がありますか？

不要です。`triggerView()` を呼び出す前に、事前に非表示になるコードを追加する必要はありません。at.js 2.*x* は、ビューが表示され適用される前に、事前非表示およびちらつきのロジックを管理します。

## at.js の互換性

次の表は、さまざまなアクティビティのタイプ、統合、機能、および at.js 関数に対する at.js. 2.0.0 の互換性を説明しています。

### アクティビティのタイプ {#types}

| タイプ | 対応? |
| --- | --- |
| A/B テスト | ○ |
| 自動配分 | ○ |
| 自動ターゲット | ○ |
| エクスペリエンスのターゲット設定 | ○ |
| 多変量分析テスト | ○ |
| 自動パーソナライゼーション | ○ |
| Recommendations | ○ |

>[!NOTE]
>
>Auto-Target activities are supported through at.js 2.*x* and the VEC when all modifications are applied to the `Page Load Event`. 特定のビューに変更が追加された場合、A/Bテスト、自動配分およびエクスペリエンスターゲット設定（XT）のアクティビティのみがサポートされます。

### 統合 {#integrations}

| タイプ | 対応? |
| --- | --- |
| Analytics for Target（A4T） | ○ |
| オーディエンス | ○ |
| 顧客属性 | ○ |
| AEM エクスペリエンスフラグメント | ○ |
| Adobe Launch 拡張機能 | [○](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) |
| デバッガー | ○ |
| Auditor | Rules have not yet been updated for at.js 2.*x* |
| Dynamic Tag Manager（DTM） | ○ |
| Opt-In | × [GDPR](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) のための Opt-in サポートは、[at.js バージョン 2.1.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) でサポートされます。 |
| AEM Enhanced Personalization powered by Adobe Target | × |

### 機能

| 機能 | 対応? |
| --- | --- |
| X-Domain | × |
| プロパティ、ワークスペース | ○ |
| QA リンク | ○ |
| フォームベースの Experience Composer | ○ |
| Visual Experience Composer（VEC） | ○ |
| カスタムコード | ○ |
| レスポンストークン | [○](#response-tokens) |
| クリックの追跡 | ○ |
| 複数アクティビティ配信 | ○ |
| targetGlobalSettings | はい（ただし X-Domain は不可） |
| at.js のメソッド | デフォルトコンテンツを表示する<br>`mboxCreate()`<br>`mboxUpdate()`<br>`mboxDefine()`<br>を除いてすべてがサポートされています。 |

### クエリ文字列パラメーター

| パラメーター | 対応? |
| --- | --- |
| `?mboxDisable` | ○ |
| `?mboxDisable` | ○ |
| `?mboxTrace` | ○ |
| `?mboxSession` | × |
| `?mboxOverride.browserIp` | × |

## レスポンストークン {#response-tokens}

at.js 2.*x* は、at.js 1.*x* と同様に、カスタムイベント `at-request-succeeded` を応答トークンに使用します。`at-request-succeeded` カスタムイベントを使用するコード例については「[応答トークン](/help/administrating-target/response-tokens.md)」を参照してください。

## at.js 1.*x* パラメーターをat.js 2に設定します。*xペイロード* ・マッピング {#payload-mapping}

ここでは、at.js 1.*x* およびat.js 2.*x*。

パラメーターマッピングを詳しく調べる前に、これらのライブラリバージョンが使用しているエンドポイントが変更されています。

* at.js 1.*x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at.js 2.*x* - `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

もう 1 つの大きな違いは次のとおりです。

* at.js 1.*x* - クライアントコードはパスの一部です
* at.js 2.*x* - クライアントコードは、次のようなクエリ文字列パラメーターとして送信されます
   `http://<client code>.tt.omtrdc.net/rest/v1/delivery?client=democlient`

以下のセクションでは、各 at.js 1.*x* パラメーター、その説明および対応する 2.0.0 JSON ペイロード（該当する場合）について説明しています。

### at_property

（at.js 1.*x* パラメーター）

[Enterprise ユーザー権限](/help/administrating-target/c-user-management/property-channel/property-channel.md)に使用されます。

```
{
  ....
  "property": {
    "token": "1213213123122313121"
  }
  ....
}
```

### browserHeight

（at.js 1.*x* パラメーター）

訪問者のブラウザーウィンドウの高さです。

at.js 2.*x* JSONペイロード：

```
{
  "context": {
    "window": {
       "height": 200
    }
  }
}
```

### browserWidth

（at.js 1.*x* パラメーター）

訪問者のブラウザーウィンドウの幅です。

at.js 2.*x* JSONペイロード：

```
{
  "context": {
    "window": {
       "width": 200
    }
  }
}
```

### browserTimeOffset

（at.js 1.*X* パラメーター）

タイムゾーンのオフセットです。

at.js 2.*x* JSONペイロード：

```
{
  "context": {
    "timeOffsetInMinutes": -480
  }
}
```

### screenHeight

（at.js 1.*x* パラメーター）

訪問者の画面の高さです。

at.js 2.*x* JSONペイロード：

```
{
  "context": {
    "screen": {
       "height": 200
    }
  }
}
```

### screenWidth

（at.js 1.*x* パラメーター）

訪問者の画面の幅です。

at.js 2.*x* JSONペイロード：

```
{
  "context": {
    "screen": {
       "width": 200
    }
  }
}
```

### colorDepth

（at.js 1.*x* パラメーター）

訪問者の画面の色深度です。

at.js 2.*x* JSONペイロード：

```
{
  "context": {
    "screen": {
       "colorDepth": 24
    }
  }
}
```

### mboxHost

（at.js 1.*x* パラメーター）

Target ライブラリが実行されるページのドメインです。

at.js 2.*x* JSONペイロード：

```
{
  "context": {
    "browser": {
       "host": "test.com"
    }
  }
}
```

### webGLRenderer

（at.js 1.*x* パラメーター）

ブラウザーの WEB GL レンダラー機能です。これは、訪問者のデバイスがデスクトップ、iPhone、Android デバイスなどであるかどうかを判断するためにデバイス検出メカニズムで使用されます。

at.js 2.*x* JSONペイロード：

```
{
  "context": {
    "browser": {
       "webGLRenderer": "AMD Radeon Pro 560X OpenGL Engine"
    }
  }
}
```

### mboxURL

（at.js 1.*x* パラメーター）

ページ URL です。

at.js 2.*x* JSONペイロード：

```
{
  "context": {
    "address": {
       "url": "http://test.com"
    }
  }
}
```

### mboxReferrer

（at.js 1.*x* パラメーター）

ページリファラーです。

at.js 2.*x* JSONペイロード：

```
{
  "context": {
    "address": {
       "referringUrl": "http://google.com"
    }
  }
}
```

### Mbox（名前）がグローバル mbox と等しい

（at.js 1.*x* パラメーター）

配信 API にグローバル mbox の概念がなくなりました。JSON ペイロードでは、`execute > pageLoad` を使用する必要があります。

at.js 2.*x* JSONペイロード：

```
{
  "execute": {
    "pageLoad": {
       "parameters": ....
       "profileParameters": ...
       .....
    }
  }
}
```

### Mbox（名前）が *グローバル mbox* と等しくない

（at.js 1.*x* パラメーター）

mbox 名を使用するには、`execute > mboxes` に渡します。mbox にはインデックスと名前が必要です。

at.js 2.*x* JSONペイロード：

```
{
  "execute": {
    "mboxes": [{
       "index": 0,
       "name": "some-mbox",
       "parameters": ....
       "profileParameters": ...
       .....
    }]
  }
}
```

### mboxId

（at.js 1.*x* パラメーター）

廃止。

### mboxCount

（at.js 1.*x* パラメーター）

廃止。

### mboxRid

（at.js 1.*x* パラメーター）

デバッグに役立つように、ダウンストリームシステムで使用されるリクエスト ID です。

at.js 2.*x* JSONペイロード：

```
{
  "requestId": "2412234442342"
  ....
}
```

### mboxTime

（at.js 1.*x* パラメーター）

廃止。

### mboxSession

（at.js 1.*x* パラメーター）

セッション ID は、クエリ文字列パラメーター（`sessionId`）として配信 API エンドポイントに送信されます。

### mboxPC

（at.js 1.*x* パラメーター）

`id > tntId` に TNT ID が渡されます。

at.js 2.*x* JSONペイロード：

```
{
  "id": {
    "tntId": "ca5ddd7e33504c58b70d45d0368bcc70.21_3"
  }
  ....
}
```

### mboxMCGVID

（at.js 1.*x* パラメーター）

`id > marketingCloudVisitorId` に Experience Cloud Visitor ID が渡されます。

at.js 2.*x* JSONペイロード：

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### `vst.aaaa.id` および `vst.aaaa.authState`

（at.js 1.*x* パラメーター）

`id > customerIds` に顧客 ID を渡す必要があります。

at.js 2.*x* JSONペイロード：

```
{
  "id": {
    "customerIds": [{
       "id": "1232131",
       "integrationCode": "aaaa",
       "authenticatedState": "....."
     }]
  }
  ....
}
```

### mbox3rdPartyId

（at.js 1.*x* パラメーター）

異なる Target ID をリンクするために使用される顧客サードパーティ ID です。

at.js 2.*x* JSONペイロード：

```
{
  "id": {
    "thirdPartyId": "1232312323123"
  }
  ....
}
```

### mboxMCSDID

（at.js 1.*x* パラメーター）

SDID です（追加データ ID とも呼ばれます）。`experienceCloud > analytics > supplementalDataId` に渡される必要があります。

at.js 2.*x* JSONペイロード：

```
{
  "experienceCloud": {
    "analytics": {
      "supplementalDataId": "1212321132123131"
    }
  }
  ....
}
```

### vst. trk

（at.js 1.*x* パラメーター）

Analytics トラッキングサーバーです。`experienceCloud > analytics > trackingServer` に渡される必要があります。

at.js 2.*x* JSONペイロード：

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServer": "analytics.test.com"
    }
  }
  ....
}
```

### vst. trks

（at.js 1.*x* パラメーター）

Analytics トラッキングサーバーのセキュリティ保護`experienceCloud > analytics > trackingServerSecure` に渡される必要があります。

at.js 2.*x* JSONペイロード：

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServerSecure": "secure-analytics.test.com"
    }
  }
  ....
}
```

### mboxMCGLH

（at.js 1.*x* パラメーター）

Audience Manager のロケーションヒント`experienceCloud > audienceManager > locationHint` に渡される必要があります。

at.js 2.*x* JSONペイロード：

```
{
  "experienceCloud": {
    "audienceManager": {
      "locationHint": 9
    }
  }
  ....
}
```

### mboxAAMB

（at.js 1.*x* パラメーター）

Audience Manager BLOB です。`experienceCloud > audienceManager > blob` に渡される必要があります。

at.js 2.*x* JSONペイロード：

```
{
  "experienceCloud": {
    "audienceManager": {
      "blob": "2142342343242342"
    }
  }
  ....
}
```

### mboxVersion

（at.js 1.*x* パラメーター）

バージョンは、version パラメーターを使用して、クエリ文字列パラメーターとして送信されます。

## Training video: at.js 2.*x* architectural diagram

at.js 2.*x* は、Adobe Target の SAP のサポートを強化し、Adobe Target と他の Experience Cloud を統合します。このビデオでは、すべてがどのように結び付いているかを説明します。

>[!VIDEO](https://video.tv.adobe.com/v/26250?captions=jpn)

at.js [2の仕組みについてを参照してください。*xは*](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) 、詳細を表示します。