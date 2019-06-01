---
description: at. js1. xからat. js2. xへのアップグレード
keywords: at.js リリース;at.js バージョン;シングルページアプリ;SPA
seo-description: Adobe Target at.js 1.x から at.js バージョン 2.0.0 へアップグレードする方法に関する詳細情報
seo-title: 'Adobe Target の at js バージョン 1. x から at.js バージョン 2.0.0 へのアップグレード '
solution: 'Target '
subtopic: 導入
title: at. js1. xからat. js2. xへのアップグレード
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: 4315e6dbec175b22fb7b321719c2f3e2d6729009

---


# at. js1. xからat. js2. xへのアップグレード {#upgrading-from-atjs-1x-to-atjs-200}

最新 [!DNL Adobe Target] バージョンのat. jsでは、ビジネスを均等化する豊富な機能セットを提供して、次世代のクライアントテクノロジーでパーソナライゼーションを実行します。この新しいバージョンは、シングルページアプリケーション（SPA）と調和したインタラクションを実現するための at.js のアップグレードに焦点を当てています。

以前のバージョンでは利用できないat. js2. xを使用する利点を次に示します。

* ページ読み込み時にすべてのオファーをキャッシュし、複数のサーバー呼び出しを単一のサーバー呼び出しに減らす機能。
* 従来のサーバー呼び出しで発生する遅延時間なしで、キャッシュ経由でオファーが即座に表示されるため、サイトでのエンドユーザーのエクスペリエンスが著しく向上します。
* 1 行のシンプルなコードと開発者による 1 回限りのセットアップで、マーケティング担当者は SPA 上で VEC を使用して A/B および XT アクティビティを作成し、実行できます。

## at. js2. xシステムダイアグラム

以下の図では、at. js2. xのワークフローを把握し、これによりSPA統合を強化する方法について説明します。at. js2. xで使用される概念のより優れた紹介を行うには、 [「シングルページアプリケーションの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)」を参照してください。

![at. js2. xを使用したTargetフロー](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| 呼び出し | 詳細 |
| --- | --- |
| 1 | 呼び出しユーザーが認証されると、呼び出しが [!DNL Experience Cloud ID]を返し、別の呼び出しが顧客 ID を同期します。 |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.js は、ページに実装されているスニペットを非表示にするオプションを使用して非同期で読み込むこともできます。 |
| 3 | すべての設定済みパラメーター（MCID、SDID および顧客 ID）を含む、ページ読み込みリクエストがおこなわれます。 |
| 4 | プロファイルスクリプトが実行されてから、プロファイルストアにフィードされます。ストアは、オーディエンスライブラリから正規のオーディエンスをリクエストします（例えば、Adobe Analytics、Audience Management などから共有されたオーディエンス）。<br>顧客属性がバッチ処理でプロファイルストアに送信されます。 |
| 5 | URL リクエストパラメーターとプロファイルデータに基づいて、[!DNL Target] が現在のページおよび将来のビューでどのアクティビティおよびエクスペリエンスを訪問者に返すかを決定します。 |
| 6 | ターゲットコンテンツが（オプションで、追加のパーソナライゼーションに関するプロファイル値を含めて）ページに送り返されます。<br>デフォルトコンテンツがちらつくことなく、可能な限り迅速に現在のページ上のターゲットコンテンツが表示されます。<br>SPA でのユーザーアクションの結果として表示されるビューのターゲットコンテンツは、ブラウザーにキャッシュされます。そのため、`triggerView()` を介してビューがトリガーされたときに追加のサーバー呼び出しをおこなわずに即座にターゲットコンテンツを適用できます。 |
| 7 | Analytics データがデータ収集サーバーに送信されます。 |
| 8 | ターゲットデータは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。Analytics for Target（A4T）レポートを使用して、<br>Analytics データが Analytics および Target に表示できるようになります。 |

これで、`triggerView()` が SPA のどこに 実装されているかに関わらず、ビューとアクションはキャッシュから取得され、サーバー呼び出しなしでユーザーに表示されるようになります。`triggerView()` は、インプレッション数を増分して記録するために、[!DNL Target] バックエンド に通知リクエストもおこないます。

![Targetのフローat. js2. xのトリガービュー](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 呼び出し | 詳細 |
| --- | --- |
| 1 | `triggerView()` は SPA で呼び出され、ビューをレンダリングし、ビジュアル要素を変更ためのアクションを適用します。 |
| 2 | ビューのターゲットコンテンツがキャッシュから読み取られます。 |
| 3 | デフォルトコンテンツがちらつくことなく、可能な限り迅速にターゲットコンテンツが表示されます。 |
| 4 | 通知リクエストが [!DNL Target] プロファイルストア に送信され、アクティビティで訪問者がカウントされ、指標が増分されます。 |
| 5 | Analytics データがデータ収集サーバーに送信されます。 |
| 6 | Target データは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。A4T レポートを使用して、Analytics データが Analytics および Target に表示できるようになります。 |

## at. js2. xのデプロイ {#deploy-atjs-200}

1. Target UIを使用してat. js2. xをダウンロードします。

   ![実装の詳細ダイアログボックス](/help/c-experiences/assets/imp-200.png)

   >[!NOTE]
   >
   >[Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) 拡張機能を使用したat. js2. xのインストールは、まだサポートされていません。

## 廃止された at.js 関数

at. js2. xで非推奨となった関数がいくつかあります。

>[!IMPORTANT]
>
>at. js2. xがデプロイされているときに、これらの非推奨の関数がサイトで引き続き使用されている場合、コンソール警告が表示されます。アップグレードの際に推奨されるアプローチは、ステージング環境でat. js2. xのデプロイメントをテストし、コンソールに記録されているすべての警告と、非推奨の関数をat. js2. xで導入された新しい関数に変換することです。

廃止された関数とそれらに対応する関数は、以下のとおりです。関数の全リストは、「[at.js 関数](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)」を参照してください。

>[!NOTE]
>at. js2. xは、マークされた要素を自動的に非表示 `mboxDefault` にすることはなくなりました。したがって、サイト上またはタグマネージャーを介して、あらかじめ非表示にするロジックを手動で用意する必要があります。

### mboxCreate(mbox,params)

**説明**:

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

**at. js2. xと同等**

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

**説明**:

要素と mbox 名の間の内部マッピングを作成しますが、リクエストを実行しません。`mboxUpdate()` と併用します。この mboxUpdate がリクエストを実行し、`mboxDefine()` の nodeId で識別された要素にオファーを適用します。また、`mboxCreate` によって開始された mbox を更新するために使用できます。

**例**：

```
<div id="someId" class="mboxDefault"></div>
<script>
 mboxDefine('someId','mboxName','param1=value1','param2=value2');
 mboxUpdate('mboxName','param3=value3','param4=value4');
</script>
```

**at. js2. xと同等**:

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

**説明**:

特定の拡張を登録するための標準的な方法を提供します。

この関数はサポートされなくなったため、使用しないでください。

## 2.0 で廃止、新規追加およびサポートされた at.js functio 関数の概要

| メソッド | 対応? | 新規? | 廃止? <br>（デフォルトコンテンツが表示されます） |
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

**コンバージョントラッキング**

コンバージョントラッキングに `mboxCreate()` を使用している場合、`trackEvent()` または `getOffer()` を使用する必要があります。

**オファーの配信**

`mboxCreate()` を `getOffer()` または `applyOffer()` で置き換えない場合、オファーが配信されない場合があります。

**at. js2. xは、at. js1の間に使用できます。*x*またはmbox. jsは他のページにありますか。**

できます。訪問者プロファイルは、異なるバージョンやライブラリを使用してページ間で保持されます。Cookie の形式は同じです。

**Adobe Experience Cloud Debuggerはat. js2. xで完全にはサポートされていません**

[!DNL Adobe Experience Cloud Debugger] [!UICONROL Summary Tab] features and [!UICONTROL Disable and Console Logging] tools are supported, but Network Requests and mboxTrace are not supported for at.js 2.x.

これは、at. js2. xでは、キーと値のペアの代わりにJSONペイロードが送信されるためです。[!DNL Target] リクエストを検証するには、ブラウザーの開発者ツールの「[!UICONTROL Network]」タブで、「delivery」、「`tt.omtrdc.net`」、またはクライアントコードをフィルタリングします。追跡データは、クエリ文字列パラメーターと認証トークンを使用して引き続き検証できます。詳細については、「[mboxTrace](/help/c-activities/c-troubleshooting-activities/content-trouble.md) 」を参照してください。

**at. js2. xでの新しいAPIの使用**

at. js2. xは、新しいAPIを使用して、配信APIを呼び出します。at.js が [!DNL Target] エッジサーバーを正しく呼び出しているかどうかデバッグするには、ブラウザーの開発者ツールの「ネットワーク」タブで「delivery」、「`tt.omtrdc.net`」、またはクライアントモードをフィルタリングします。また、[!DNL Target] はキーと値のペアの変わりに JSON ペイロードを送信します。

**Target グローバル mbox の廃止**

at. js2. xでは、ネットワーク呼び出しで「`target-global-mbox`」が表示されなくなりました。代わりに、[!DNL Target] サーバーに送信される JSON ペイロードの「`target-global-mbox`」構文を以下のように「`execute > pageLoad`」に置き換えました。

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

**at.js のグローバル mbox 名は重要ではなくなりましたか？**

「[!UICONTROL Target」／「セットアップ」／「実装」／「at.js 設定を編集]」の順に移動して、グローバル mbox 名を指定できます。この設定は [!DNL Target] エッジサーバーによって使用され、execute &gt; pageLoad が [!DNL Target] UI に表示されるグローバル mbox 名に変換されます。これにより、ユーザーはサーバーサイド API、フォームベースのコンポーザー、プロファイルスクリプトの使用、およびグローバル mbox 名を使用したオーディエンスを引き続き作成できます。まだ at.js 1.*x* または mbox.js を使用しているページがある場合、次の図のように「[!UICONTROL セットアップ」／「環境設定]」ページの順に移動して、同じグローバル mbox 名 を設定することを強くお勧めします。

![at.js ダイアログの変更](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

および

![カスタムグローバル mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

**at. js2. xではグローバルmbox設定をオンにする必要がありますか。**

ほとんどの場合では、有効にする必要があります。この設定は、ページ読み込み時に [!DNL Target] エッジサーバーへのリクエストを実行するようにat. js2. xに指示します。グローバル mbox は execute &gt; pageLoad に変換されているため、ページ読み込み時にリクエストを送信する場合、この設定を有効にする必要があります。

**ターゲットのグローバルmbox名がat. js2. xから指定されていない場合でも、既存のVECアクティビティは引き続き動作しますか。**

動作します。execute &gt; pageLoad は、`target-global-mbox` のような [!DNL Target] バックエンドで処理されるためです。

**フォームベースのアクティビティのターゲット設定先が`target-global-mbox`の場合、これらのアクティビティは引き続き機能しますか？**

機能します。execute &gt; pageLoad は、`target-global-mbox` のような [!DNL Target] エッジサーバーで処理されるためです。

**at. js2. xの設定でサポートされ、サポートされていない設定**

| 設定 | 対応? |
| --- | --- |
| X-Domain | × |
| グローバル mbox 自動作成 | ○ |
| グローバル mbox 名 | ○ |

**クロスドメイントラッキングはサポートされて*いません***

クロスドメイントラッキングを使用すると、異なる ドメインを持つ 2 つの関連するサイト上のセッションを、単一のセッションと見なせます。`siteA.com` と `siteB.com` にまたがる [!DNL Target] アクティビティを作成し、訪問者がドメインを移るときに同じエクスペリエンスを維持できます。この機能は、Target のサードパーティおよびファーストパーティ Cookie の動作に結びついています。

[!DNL Target] では、サードパーティ Cookie は `[CLIENTCODE].tt.omtrdc.net` に、ファーストパーティ Cookie は `clientdomain.com` にそれぞれ保存されます。最初のリクエストは、HTTP 応答ヘッダーを返します。このヘッダーによって、`mboxSession` および `mboxPC` という名前のサードパーティ Cookie の設定が試行され、リダイレクトリクエストが追加のパラメーター（`mboxXDomainCheck=true`）と共に返されます。ブラウザーがサードパーティ Cookie を受け入れる場合、リダイレクトリクエストにはそれらの Cookie が含まれており、オファーが返されます。このワークフローは、HTTP GET メソッドの使用により可能になっています。

ただし、at. js2. xでは、HTTP GETは使用されなくなり、代わりにHTTP POSTを使用します。JSON ページロードを [!DNL Target] エッジサーバーに送信するために、at.js を介して HTTP POST が使用されるようになりました。つまり、ブラウザがサードパーティ Cookie をサポートするかどうかを確認するためのリダイレクトリクエストは中断されます。これは、HTTP GET リクエストはべき等トランザクションであるのに対して HTTP POST は非べき等であり、任意の繰り返しを防ぐ必要があるためです。したがって、at. js2. xのクロスドメイントラッキングはサポートされなくなります。

**グローバル mbox 自動作成はサポートされています**

この設定により、at. js2. xによって、ページ読み込み時 [!DNL Target] にエッジサーバーへのリクエストが実行されます。[!DNL Target] エッジサーバーがグローバル mbox を execute&gt; pageLoad に変換します。ページロード時にリクエストを発行する場合、この設定を有効にする必要があります。

**グローバル mbox 名はサポートされています**

[!UICONTROL Target／セットアップ／実装／at.js 設定を編集] を使用して、グローバル mbox 名を指定できます。[!DNL Target] エッジサーバーがこの設定を使用して、execute &gt; pageLoad を入力されたグローバル mbox 名に変換します。これによりユーザーは引き続き、サーバーサイド API、フォームベースのコンポーザー、プロファイルスクリプトの使用、およびグローバル mbox をターゲットにしたオーディエンスの作成ができます。

**以下の at.js カスタムイベントは`triggerView()`に適用できますか？または`applyOffer()`や`applyOffers()`のみですか？**

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

適用できます。at.js カスタムイベントは `triggerView()` にも適用できます。

**`{“page” : “true”}`を使用して`triggerView()`を呼び出すと、通知が[!DNL Target]バックエンドに送信され、インプレッションが増加します。これによりプロファイルスクリプトも実行されますか？**

[!DNL Target] バックエンドに対してプリフェッチ呼び出しが実行されると、プロファイルスクリプトが実行されます。その後、影響を受けたプロファイルデータは暗号化され、クライアント側に返されます。`{"page": "true"}` を使用した `triggerView()` が呼び出されると、通知が暗号化されたプロファイルデータとともに送信されます。このとき、[!DNL Target] バックエンドはプロファイルデータを復号してデータベースに保存します。

**ちらつきに対処するために、`triggerView()`を呼び出す前に、事前に非表示になるコードを追加する必要がありますか？**

不要です。`triggerView()` を呼び出す前に、事前に非表示になるコードを追加する必要はありません。at. js2. xは、ビューが表示および適用される前に、非表示およびちらつきのロジックを管理します。

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
| Automated Personalization | ○ |
| Recommendations | ○ |

>[!NOTE]
>
>自動ターゲットアクティビティは、すべての変更が適用されるときにat. js2. xおよびVEC経由でサポート `Page Load Event`されます。特定のビューに変更が追加された場合、A/Bテスト、自動配分およびエクスペリエンスターゲット設定（XT）アクティビティのみがサポートされます。

### 統合 {#integrations}

| タイプ | 対応? |
| --- | --- |
| Analytics for Target（A4T） | ○ |
| オーディエンス | ○ |
| 顧客属性 | ○ |
| AEM エクスペリエンスフラグメント | ○ |
| Adobe Launch 拡張機能 | 現在未対応 |
| デバッガー | ○ |
| Auditor | ルールはat. js2. x用にまだ更新されていません |
| Dynamic Tag Manager（DTM） | ○ |
| Opt-In | ×の呼び出しの後におこなわれる場合です。[DGPR](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) のオプトインサポートは、at. jsバージョン2.1.0で [サポート](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)されています。 |
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
| マルチアクティビティ配信 | ○ |
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

at.js 2.*x*. js1と同様。*x*は、カスタムイベント `at-request-succeeded` を応答トークンに使用します。`at-request-succeeded` カスタムイベントを使用するコード例については [、応答トークン](/help/administrating-target/response-tokens.md)を参照してください。

## at. js1. xのパラメーター（at. js2. xのペイロードマッピング） {#payload-mapping}

ここでは、at. js1のマッピングについて説明します。*x* およびat. js2. x.

パラメーターマッピングを削除する前に、これらのライブラリバージョンが使用しているエンドポイントが変更されました。

* at.js 1.*x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at. js2. x- `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

もう1つの大きな違いは次のとおりです。

* at.js 1.*x* -クライアントコードがパスの一部
* at. js2. x-クライアントコードは、次のようなクエリ文字列パラメーターとして送信されます。
   `http://<client code>.tt.omtrdc.net/rest/v1/delivery?client=democlient`

以下の節では、各at. js1について説明しています。*x* パラメータ、その説明、および対応する2.0.0JSONペイロード（該当する場合）:

### at_ property

(at.js 1.*x* パラメーター）

[Enterpriseユーザー権限に使用](/help/administrating-target/c-user-management/property-channel/property-channel.md)されます。

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

(at.js 1.*x* パラメーター）

訪問者のブラウザーウィンドウの高さ。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

訪問者のブラウザーウィンドウの幅。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

タイムゾーンのオフセット。

at. js2. x JSONペイロード:

```
{
  "context": {
    "timeOffsetInMinutes": -480
  }
}
```

### screenHeight

(at.js 1.*x* パラメーター）

訪問者の画面の高さ。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

訪問者の画面の幅。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

訪問者の画面の色深度。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

Targetライブラリが実行されるページのドメイン。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

ブラウザーのWEB GLレンダラー機能。これは、訪問者のデバイスがデスクトップ、iPhone、Androidデバイスなどであるかどうかを判断するためにデバイス検出メカニズムで使用されます。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

ページURL。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

ページリファラー。

at. js2. x JSONペイロード:

```
{
  "context": {
    "address": {
       "referringUrl": "http://google.com"
    }
  }
}
```

### mbox（名前）がグローバルmboxと等しい

(at.js 1.*x* パラメーター）

配信APIにグローバルmboxの概念がなくなりました。JSONペイロードでは、使用する必要 `execute > pageLoad`があります。

at. js2. x JSONペイロード:

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

### mbox（名前）が *グローバルmbox* と等しくない

(at.js 1.*x* パラメーター）

mbox名を使用するには、に渡し `execute > mboxes`ます。mboxにはインデックスと名前が必要です。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

廃止。

### mboxCount

(at.js 1.*x* パラメーター）

廃止。

### mboxGrid

(at.js 1.*x* パラメーター）

デバッグに役立つように、ダウンストリームシステムで使用されるリクエストID。

at. js2. x JSONペイロード:

```
{
  "requestId": "2412234442342"
  ....
}
```

### mboxTime

(at.js 1.*x* パラメーター）

廃止。

### mboxSession

(at.js 1.*x* パラメーター）

セッションIDは、クエリ文字列パラメータ（`sessionId`）として配信APIエンドポイントに送信されます。

### mboxPC

(at.js 1.*x* パラメーター）

TNT IDが渡さ `id > tntId`れます。

at. js2. x JSONペイロード:

```
{
  "id": {
    "tntId": "ca5ddd7e33504c58b70d45d0368bcc70.21_3"
  }
  ....
}
```

### mboxMCGVID

(at.js 1.*x* パラメーター）

Marketing Cloud訪問者IDが渡さ `id > marketingCloudVisitorId`れます。

at. js2. x JSONペイロード:

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### vst. aaa. idおよびvst. aaa. authState

(at.js 1.*x* パラメーター）

顧客IDを渡す必要 `id > customerIds`があります。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

異なるTarget IDをリンクするために使用される顧客サードパーティID。

at. js2. x JSONペイロード:

```
{
  "id": {
    "thirdPartyId": "1232312323123"
  }
  ....
}
```

### mboxMCSDID

(at.js 1.*x* パラメーター）

SDID（追加データIDとも呼ばれます）。渡される必要 `experienceCloud > analytics > supplementalDataId`があります。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

Analyticsトラッキングサーバー。渡される必要 `experienceCloud > analytics > trackingServer`があります。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

Analyticsトラッキングサーバーのセキュリティ保護渡される必要 `experienceCloud > analytics > trackingServerSecure`があります。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

Audience Managerのロケーションヒント渡される必要 `experienceCloud > audienceManager > locationHint`があります。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

Audience Manager blob。渡される必要 `experienceCloud > audienceManager > blob`があります。

at. js2. x JSONペイロード:

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

(at.js 1.*x* パラメーター）

バージョンは、versionパラメーターを使用してクエリ文字列パラメーターとして送信されます。

## トレーニングビデオ:at. js2. xアーキテクチャ図

at. js2. xは、Adobe TargetのSPAサポートを強化し、他のExperience Cloudソリューションと統合します。このビデオでは、すべてがどのように結び付いているかを説明します。

>[!VIDEO](https://video.tv.adobe.com/v/26250?captions=jpn)

詳しくは、at. js2. xの仕組み [](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) についてを参照してください。