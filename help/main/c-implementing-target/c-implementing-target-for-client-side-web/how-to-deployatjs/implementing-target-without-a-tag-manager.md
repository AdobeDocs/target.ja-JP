---
keywords: target の実装；実装；at.js の実装；タグマネージャー；オンデバイス判定；デバイス判定時
description: 設定（アカウントの詳細、実装方法など）を指定する方法について説明します。 Adobe [!DNL Target] タグマネージャーを使用しない at.js ライブラリ。
title: 実装可能か [!DNL Target] タグマネージャーがない場合、
feature: Implement Server-side
role: Developer
exl-id: cb57f6b8-43cb-485d-a7ea-12db8170013f
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1672'
ht-degree: 51%

---

# 実装方法 [!DNL Target] タグマネージャーなし

実装に関する情報 [!DNL Adobe Target] タグマネージャーやタグを [!DNL Adobe Experience Platform].

>[!NOTE]
>
>タグ [Adobe Experience Platform](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) は、 [!DNL Target] と at.js ライブラリに含まれています。 次の情報は、 [!DNL Adobe Experience Platform] 実装する [!DNL Target].

次の手順で [!UICONTROL 実装] ページ、クリック **[!UICONTROL 管理]** > **[!UICONTROL 実装]**.

このページでは、次の設定を指定できます。

* アカウントの詳細
* 実装方法
* プロファイル API
* デバッガーツール
* プライバシー

>[!NOTE]
>
>設定を上書きする際には、 [!DNL Target Standard/Premium] UI または REST API を使用します。 詳しくは、[targetGlobalSettings()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) を参照してください。

## アカウントの詳細

次のアカウントの詳細を表示できます。 これらの設定は変更できません。

| 設定 | 説明 |
| --- | --- |
| [!UICONTROL クライアントコード] | クライアントコードは、[!DNL Target] API を使用する際に必要になることの多い、クライアント固有の一連の文字です。 |
| [!UICONTROL IMS 組織 ID] | この ID は、実装を [!DNL Adobe Experience Cloud] アカウントと結び付けます。 |
| [!UICONTROL オンデバイス判定] | オンデバイス判定を有効にするには、切り替えを「オン」の位置にスライドします。<br>オンデバイス判定を使用すると、A/B および [!UICONTROL エクスペリエンスのターゲット設定] (XT) キャンペーンをサーバー上で実行し、ほぼゼロの待ち時間でインメモリ判定を実行します。 詳しくは、 [オンデバイス判定の概要](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) 内 *[!DNL Adobe Target]SDK* ガイド。 |
| [!UICONTROL 既存のすべてのオンデバイス判定対象アクティビティをアーティファクトに含めます。] | （条件付き）このオプションは、On-Device Decisioning を有効にした場合に表示されます。<br>オンデバイス判定の対象となるすべてのライブ Target アクティビティをアーティファクトに自動的に含める場合は、切り替えを「オン」の位置にスライドします。<br>この切り替えをオフにした場合、オンデバイス判定アクティビティを生成されたルールアーティファクトに含めるには、そのアクティビティを再作成してアクティブ化する必要があります。 |

## 実装方法

以下の設定は、実装方法パネルで設定できます。

### グローバル設定

>[!NOTE]
>
>これらの設定は、すべての [!DNL Target] .js ライブラリ。 「実装方法」セクションの変更を実行した後、ライブラリをダウンロードし、実装で更新する必要があります。

| 設定 | 説明 |
| --- | --- |
| ページ読み込みが有効（グローバル mbox を自動作成） | 各ページが読み込まれると自動的に実行されるように、グローバル mbox 呼び出しを at.js ファイルに埋め込むかどうかを選択します。 |
| グローバル mbox | global mbox の名前を選択します。デフォルトでは、この名前は target-global-mbox です。<br>at.js を使用した mbox 名には、アンパサンド（&amp;）を含む特殊文字を使用できます。 |
| タイムアウト（秒） | [!DNL Target] が定義された期間内にコンテンツの応答をしない場合、サーバー呼び出しはタイムアウトし、デフォルトコンテンツが表示されます。訪問者のセッション中、追加の呼び出しが引き続き試行されます。デフォルト値は 5 秒です。<br>at.js ライブラリは、`XMLHttpRequest` のタイムアウト設定を使用します。タイムアウトは、リクエストが実行されると開始され、[!DNL Target] がサーバーから応答を受け取ると停止します。詳しくは、Mozilla Developer Network の [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout) を参照してください。<br>応答を受け取る前に指定されたタイムアウトが発生すると、デフォルトのコンテンツが表示され、訪問者はアクティビティの参加者としてカウントされる可能性があります。これは、[!DNL Target] エッジですべてのデータ収集がおこなわれるためです。リクエストが [!DNL Target] エッジに到達すると、訪問者はカウントされます。<br>タイムアウト設定を構成する際は、次の点を考慮してください。<ul><li>値が低すぎると、訪問者はアクティビティの参加者としてカウントされるものの、ほとんどの時間デフォルトのコンテンツが表示される可能性があります。</li><li>値が高すぎると、Web ページに空白の領域が表示されるか、長時間の本文の非表示を使用している場合は空白のページが表示される可能性があります。</li></ul>mbox の応答時間をよりよく把握するには、ブラウザーの開発者ツールの「ネットワーク」タブを確認してください。また、Catchpoint など、サードパーティの Web パフォーマンス監視ツールを使用することもできます。<br>**注意：**[visitorApiTimeout](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) 設定では、[!DNL Target] が訪問者 API の応答を長時間待たないようにします。この設定と、ここで説明している at.js のタイムアウト設定は相互に影響しません。 |
| プロファイルの有効期間 | この設定は、訪問者プロファイルが保存される期間を決定します。デフォルトでは、プロファイルは 2 週間保存されます。この設定は、最大 90 日まで延長できます。<br>プロファイルの有効期間設定を変更するには、[ClientCare](https://helpx.adobe.com/jp/contact/enterprise-support.ec.html) にお問い合わせください。 |

### 主な実装方法

>[!IMPORTANT]
>
>Target チームは at.js 1.*x* と at.js 2.*x* 間のマッピングについて説明します。at.js のメジャーバージョンのいずれかの最新の更新にアップグレードして、サポート対象のバージョンを実行していることを確認してください。

目的の at.js バージョンをダウンロードするには、 **[!UICONTROL ダウンロード]** 」ボタンをクリックします。

at.js の設定を編集するには、 **[!UICONTROL 編集]** をクリックします。

>[!IMPORTANT]
>
>これらのデフォルト設定を変更する前に、 [ClientCare](/help/main/cmp-resources-and-contact-information.md) したがって、現在の実装に影響を与えません。

上記の設定に加えて、次の at.js 固有の設定も使用できます。

| 設定 | 説明 |
|--- |--- |
| カスタムライブラリヘッダー | ライブラリの最上部に含めるカスタム JavaScript を追加します。 |
| カスタムライブラリのフッター | ライブラリの最下部に含めるカスタム JavaScript を追加します。 |

### プロファイル API

API による一括更新の認証を有効または無効にし、プロファイル認証トークンを生成します。

詳しくは、 [プロファイル API 設定](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/profile-api-settings.md).

### デバッガーツール

詳細を使用するための認証トークンを生成 [!DNL Target] デバッグツールを使用します。 クリック **[!UICONTROL 新しい認証トークンを生成]**.

![新しい認証トークンの生成](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

### プライバシー

これらの設定を使用すると、 [!DNL Target] 該当するデータプライバシー法に準拠する

「訪問者の IP アドレスを難読化」ドロップダウンリストから目的の設定を選択します。

* 最終オクテットの難読化
* IP 全体の難読化
* None

詳しくは、[プライバシー](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md)を参照してください。

>[!NOTE]
>
>「レガシーブラウザーのサポート」オプションは、at.js バージョン 0.9.3 以前で使用できました。 このオプションは、at.js バージョン 0.9.4 で削除されました。at.js でサポートされているブラウザーのリストについては、 [サポートされているブラウザー](/help/main/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).<br>レガシーブラウザーは、CORS（クロスオリジンリソース共有）を完全にはサポートしない古いブラウザーです。こうしたブラウザーには、バージョン 11 より前の Internet Explorer およびバージョン 6 以下の Safari が含まれます。「レガシーブラウザーのサポート」を無効にした場合、Target はコンテンツを配信しなかったか、これらのブラウザーのレポートで訪問者をカウントしました。 このオプションを有効にした場合、古いブラウザーで品質保証をおこない、優れた顧客体験を得ることをお勧めします。

## at.js のダウンロード {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

を使用したライブラリのダウンロード手順 [!DNL Target] インターフェイスまたはダウンロード API を使用して、

>[!NOTE]
>
>* [[!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) は、 [!DNL Target] と at.js ライブラリに含まれています。 次の情報は、 [!DNL Adobe Experience Platform] 実装する [!DNL Target].
>
>* この [!DNL Target] チームは at.js 1.*x* と at.js 2.*x* 間のマッピングについて説明します。サポート対象のバージョンを実行していることを確認するには、at.js のいずれかのメジャーバージョンの最新の更新にアップグレードしてください。 各バージョンについて詳しくは、 [at.js のバージョンの詳細](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)を参照してください。


### を使用して at.js をダウンロードします。 [!DNL Target] インターフェイス {#section_1F5EE401C2314338910FC57F9592894E}

[!DNL at.js] インターフェイスから [!DNL Target] をダウンロードするには：

1. **[!UICONTROL 管理]**／**[!UICONTROL 実装]**&#x200B;をクリックします。
1. 次の [!UICONTROL 実装方法] セクションで、 **[!UICONTROL ダウンロード]** ボタンをクリックします。

### を使用して at.js をダウンロードします。 [!DNL Target] ダウンロード API {#section_C0D9D2A9068144708D08526BA5CA10D0}

API を使用して [!DNL at.js] をダウンロードするには：

1. クライアントコードを取得します。

   クライアントコードは **[!UICONTROL 管理]** > **[!UICONTROL 実装]** ページ [!DNL Target] インターフェイス。

1. 管理番号を取得します。

   次の URL を読み込みます。

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   置換 `client code` を手順 1 のクライアントコードと共に使用します。

   この URL を読み込んだ結果は、次の例のようになります。

   ```
   { 
     "api": "https://admin6.testandtarget.omniture.com/admin/rest/v1" 
   }
   ```

   この例では、「6」が管理番号です。

1. ダウンロード [!DNL at.js].

   この URL を次の構造で読み込みます。

   ```
   https://admin<varname>admin number</varname>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code</varname>&version=<version number>
   ```

   * 置換 `admin number` 管理番号を入力します。
   * 置換 `client code` を手順 1 のクライアントコードと共に使用します。
   * 置換 `version number` を適切な at.js バージョン番号（例：2.2）に置き換えます。

   >[!IMPORTANT]
   >
   >Target チームがサポートを提供しているのは、[!DNL at.js] の最新バージョンとその 1 つ前のバージョンの 2 つのみです。必要に応じて [!DNL at.js] をアップグレードし、サポート対象のバージョンを使用するようにしてください。各バージョンについて詳しくは、 [at.js のバージョンの詳細](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)を参照してください。

   この URL を読み込むと、カスタマイズされた [!DNL at.js] ファイルのダウンロードが開始されます。

## at.js の実装 {#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js は、Web サイトのすべてのページの `<head>` 要素で実装する必要があります。

タグマネージャーを使用しない Target の一般的な実装 ( 例： [[!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 次のようになります。

```
<!doctype html> 
<html> 
<head> 
    <meta charset="utf-8"> 
    <title>Title of the Page</title> 
    <!--Preconnect and DNS-Prefetch to improve page load time--> 
    <link rel="preconnect" href="//<client code>.tt.omtrdc.net"> 
    <link rel="dns-prefetch" href="//<client code>.tt.omtrdc.net"> 
    <!--/Preconnect and DNS-Prefetch--> 
    <!--Data Layer to enable rich data collection and targeting--> 
    <script> 
        var digitalData = { 
            "page": { 
                "pageInfo": { 
                    "pageName": "Home" 
                } 
            } 
        }; 
    </script> 
    <!--/Data Layer--> 
    <!-- targetPageParams(), targetPageParamsAll(), Data Providers or targetGlobalSettings() functions to enrich the visitor profile or modify the library settings--> 
    <script> 
        targetPageParams = function() { 
            return { 
                "a": 1, 
                "b": 2, 
                "pageName": digitalData.page.pageInfo.pageName, 
                "profile": { 
                    "age": 26, 
                    "country": { 
                        "city": "San Francisco" 
                    } 
                } 
            }; 
        }; 
    </script> 
    <!--/targetPageParams()--> 
 
    <!--jQuery or other helper libraries should be implemented before at.js if you would like to use their methods in Target--> 
    <script src="jquery-3.3.1.min.js"></script> 
    <!--/jQuery--> 
    <!--Target's JavaScript SDK, at.js--> 
    <script src="at.js"></script> 
    <!--/at.js--> 
</head>
<body> 
    The default content of the page 
</body> 
</html>
```

次の重要な注意点を考慮してください。

* HTML5 の Doctype( 例： `<!doctype html>`) を使用する必要があります。 サポートされていない doctype や古い doctype を使用すると、Target がリクエストを送信できなくなる可能性があります。
* 事前接続とプリフェッチのオプションは、Web ページの読み込みを高速化するのに役立ちます。これらの設定を使用する場合は、 `<client code>` 独自のクライアントコードを使用して、 **[!UICONTROL 管理]** > **[!UICONTROL 実装] ページ。
* データレイヤーがある場合、at.js が読み込まれる前にページの `<head>` でデータレイヤーについてできるだけ多く定義することが最適です。この場所に、この情報を Target でパーソナライゼーションに最大限に使用できます。
* 特殊な Target 関数（`targetPageParams()`、`targetPageParamsAll()`、データプロバイダー、および `targetGlobalSettings()` など）は、データレイヤーの後で、at.js が読み込まれる前に定義する必要があります。または、これらの関数を [!UICONTROL ライブラリヘッダー] セクション [!UICONTROL at.js 設定の編集] ページに保存され、at.js ライブラリ自体の一部として保存されます。 これらの関数について詳しくは、[at.js 関数](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).
* jQuery などの JavaScript ヘルパーライブラリを使用する場合は、Target の前にそれらをインクルードして、Target エクスペリエンスの構築時に構文とメソッドを使用できるようにします。
* at.js はページの `<head>` に含めます。

## コンバージョンの追跡 {#task_E85D2F64FEB84201A594F2288FABF053}

注文の確認 mbox では、サイトでの注文に関する詳細が記録され、売上高および注文に基づくレポートが可能になります。また、注文の確認 mbox は、「商品 x および商品 y を購入した人」などのレコメンデーションアルゴリズムを駆動できます。

>[!NOTE]
>
>Adobeが Web サイトで買い物をする場合、レポートに Analytics for Target(A4T) を使用している場合でも、注文の確認 mbox を実装することをお勧めします。

1. 注文の詳細ページで、以下のモデルに示す mbox スクリプトを挿入します。
1. 大文字のテキストを、カタログの動的値または静的値に置き換えます。

   >[!NOTE]
   >
   >複数の製品 ID を区切るには、コンマを使用してください。

   **ヒント：**&#x200B;任意の mbox に注文情報を渡すこともできます（`orderConfirmPage` という名前にする必要はありません）。また、同じキャンペーン内の複数の mbox に注文情報を渡すこともできます。

   ```
   <script type="text/javascript"> 
   adobe.target.trackEvent({ 
       "mbox": "orderConfirmPage", 
       "params":{  
           "orderId": "ORDER ID FROM YOUR ORDER PAGE",  
           "orderTotal": "ORDER TOTAL FROM YOUR ORDER PAGE",  
           "productPurchasedId": "PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3"  
       } 
   }); 
   </script> 
   ```

注文の確認 mbox では、次のパラメーターを使用します。

| パラメーター | 説明 |
|--- |--- |
| orderId | 注文を識別する一意の値（コンバージョンのカウントに使用）。<br>`orderId` は一意である必要があります。重複する注文はレポートで無視されます。 |
| orderTotal | 購入金額。<br>通貨記号を渡さないでください。（コンマではなく）小数点を使用して、10 進数値を示します。 |
| productPurchasedId（オプション） | この注文で購入された製品 ID のコンマ区切りのリスト。<br>これらの製品 ID は監査レポートに表示され、さらに詳細なレポート分析ができます。 |
