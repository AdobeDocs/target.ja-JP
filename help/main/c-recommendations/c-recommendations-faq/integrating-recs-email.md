---
keywords: 電子メール;ESP;電子メールサービスプロバイダー;rawbox;delivery API;ダウンロード専用テンプレート;電子メールテンプレート;バッチ処理;ビルド時の電子メール
description: '[!DNL Target]配信API、rawbox テンプレート、およびダウンロード専用テンプレートの使用を含め、メールをAdobe [!DNL Target Recommendations]と統合する方法について説明します。'
title: レコメンデーションとメールの統合方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
TQID: 'https://experienceleague.adobe.com/ZyeOl6ysM03a0mMiNgHuicOLPfgpXnrdqXJE1gHRRvE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1741'
ht-degree: 27%
---
# [!DNL Recommendations]をメールと統合 {#integrate-recs-email}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、メール内のレコメンデーションを送信時にパーソナライズするために、[!DNL Target Recommendations]をメールサービスプロバイダー（ESP）と統合する方法について説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target] は、メールでのレコメンデーションの送信時パーソナライゼーションをサポートします。 レコメンデーションのオープン時のパーソナライズはサポートされていません。

[!DNL Target Recommendations]をESPと統合するには、3つの方法があります。 ESPの能力によって使用する方法が決まり、アカウントマネージャーやコンサルタントが最適なオプションを選択するのに役立ちます。

| メソッド | 詳細 |
| --- | --- |
| [メソッド 1： [!DNL Adobe Target Delivery API]](#delivery-api)（推奨） | [!DNL Adobe Target Delivery API]を使用して、お客様ごとに、メールごとにレコメンデーションのリクエストを行います。 |
| [メソッド 2： [!DNL Adobe Rawbox API]](#rawbox) | [!DNL Adobe Target Rawbox API]を使用して、お客様ごとに、メールごとにレコメンデーションのリクエストを行います。 |
| [メソッド 3： [!DNL Recommendations Download API]](#download-api) | [!DNL Recommendations Download API]を使用して、CSV形式の製品またはカテゴリのリストに対する一括レコメンデーションをリクエストします。 |

メソッド 1および2では、ESPが顧客ごとに、メールごとに外部APIを呼び出し、コンテンツが返されるのを待つ必要があります。 すべてのESPがこれらの方法をサポートしているわけではないので、ESPに連絡して、この統合パターンに対応しているかどうかを判断する必要があります。

方法3では、ESPが商品IDまたはカテゴリ ID別のレコメンデーションのリストをメールのリストに結合する必要があります。 この結合は、顧客の最後に閲覧された製品、最後に購入された製品、最も閲覧されたカテゴリなどの属性に基づいて行うことができます。 ESPは、結合を実行するために顧客プロファイル内のこのデータにアクセスできる必要があります。そのため、ESPに連絡して、このデータにアクセスできるかどうか、またこの統合パターンと互換性があるかどうかを判断する必要があります。

>[!IMPORTANT]
>
>次のキャパシティガイドラインは、配信APIおよびrawbox メールテンプレートメソッド（メソッド 1および2）に適用されます。
>
>* リクエストは、1秒あたり1,000件のリクエストのうち、ピーク時の1日のトラフィックの25倍に制限する必要があります。
>* トラフィックは、毎分200 リクエスト/秒のステップで傾斜させる必要があります。
>
>より高いレート制限を使用するには、アカウントマネージャーにお問い合わせください。

## 方法1：配信APIを使用する（推奨） {#delivery-api}

配信APIは、ビルドタイムメールで動作するPOST リクエストです。 このオプションは、ビルド時の電子メール用に推奨される方法です。

ほとんどのメールクライアントはPOST リクエストを許可しないため、このAPIはオープンタイムのユースケースには推奨されません。 GmailやOutlookなどの一部のメールクライアントでは、コンテンツをキャッシュしたり画像をブロックしたりすることができ、受信者は画像のレンダリングを積極的に許可する必要があります。

デフォルトのコンテンツは、配信APIでは返すことができません。

次のコードはサンプル API配信リクエストです。`clientcode`は[!DNL Target] クライアント コードです。

```javascript
curl -X POST \ 
  'https://clientcode.tt.omtrdc.net/rest/v1/mbox/?client=clientcode' \ 
  -H 'authorization: Bearer 3423614b-4843-4664-83c4-c6c3f6c8869b' \ 
  -H 'cache-control: no-cache' \ 
  -H 'content-type: application/json' \ 
  -d '{ 
  "mbox" : "email-mbox", 
  "tntId" : "111499796294071-449025.28_44", 
  "requestLocation" : { 
    "host" : "prod" 
  }, 
   "profileParameters" : { 
   }, 
  "mboxParameters" : { 
    "at_property": "b468a242-64a4-32a0-ca0c-890bddd78789", 
    "entity.id": "article-123", 
    "entity.event.detailsOnly" : "true" 
  } 
  "contentAsJson":  true 
}'
```

>[!NOTE]
>
>各電子メール受信者（API呼び出しごとに）に、`sessionId`と`tntId`または`thirdPartyId`の両方に一意の値を指定します。 これらのフィールドに一意の値がないと、1つのプロファイル内で生成される多くのイベントが原因で、API応答が遅くなったり失敗したりする可能性があります。

詳しくは、[配信API ドキュメント &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html?lang=ja){target=_blank}を参照してください。

## オプション 2：rawbox メールテンプレートの使用 {#rawbox}

rawboxはmbox リクエストと似ていますが、メールサービスプロバイダー（ESP）などのweb以外の環境に対しては使用できます。 [!DNL Adobe Experience Platform Web SDK]と[!DNL at.js]はrawbox リクエストに使用できないため、リクエストは手動で作成する必要があります。 次の例では、メールでrawbox リクエストを操作する方法を説明します。

このアプローチにより、電子メールのレコメンデーションのパフォーマンスを追跡し、レコメンデーションを通じて通常の方法でテストを実施して、サイトでトラッキングを継続できます。

>[!NOTE]
>
>rawboxと[!DNL Target]を使用する場合は、[&#x200B; に mbox 呼び出しを送信する権限のあるホストを指定する許可リストの作成 [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist)の重要なセキュリティ通知を参照してください。

1. [&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md) オプションを使用して、[!DNL Target]で[!DNL Recommendations] アクティビティを設定します。

1. 場所として、ESPからのrawbox リクエストで使用されるmboxの名前を選択します。

1. 電子メールに求められているルック&amp;フィールのデザインを選択します。

電子メールの構築時に、ESP は、生成中の各電子メールの各 rawbox に対して、[!DNL Target] サーバーを呼び出します。 ESPは、返されたHTMLを送信時にメールに含める方法を持っている必要があります。

メールシステムは、次のシナリオを処理できる必要があります。

### 有効な応答を受信したが、レコメンデーションが存在しない

* 応答は、`mboxDefault` パラメーターで設定された値です。 必要なパラメーターの表に、このパラメーターの説明を示します。
* この場合、電子メールプロバイダーは、レコメンデーションのデフォルト HTML ブロックを使用する必要があります。

### [!DNL Target] サーバーがタイムアウトし、返されるデータがない

* [!DNL Target] サーバーは次のコンテンツを返します。

  `//ERROR: application server timeout`

* メールアプリケーションは、そのテキストを検索し、エラーを処理できる必要があります。 電子メールプロバイダーには、この事例に対処する複数のオプションがあります。

  * 即座に別のサーバー呼び出しを試す（推奨、試行をカウントする必要がある可能性があります）。
  * その特定のメールを破棄して、次のメールに進みます。
  * その特定の電子メールをキューに入れ、最初の実行の最後に、失敗した電子メールをバッチとして再実行します。

### リクエスト URL の例

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### 必須パラメーター {#reqparams}

>[!NOTE]
>
>メールで[!DNL Recommendations]を使用するには、推奨条件の種類に応じて、通常、`entity.id`または`entity.categoryId`のいずれか、またはその両方をrawbox呼び出しに含める必要があります。 前述の呼び出しの例では、両方が含まれています。

| パラメーター | 値 | 説明 | 検証 |
|--- |--- |--- |--- |
| `client_code` | *client_code* | [!DNL Recommendations]で使用されているクライアント コード。 Adobeコンサルタントは、この価値を提供します。 |  |
| `mbox` | *mboxName* | ターゲット設定に使用される mbox 名。 | すべてのmbox呼び出しと同じ検証です。<br>250文字の制限があります。<br>次の文字を含めることはできません：`', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | 無効 | 非 Web 環境において応答で cookie を設定しないようにします。 |  |
| `entity.id`<br>（特定のタイプの条件が必要：view/view、view/bought、bought/bought） | *entity_id* | 買い物かご内の放棄された商品や過去の購入履歴など、レコメンデーションの基になる商品ID。<br>条件で必須の場合、rawbox 呼び出しには `entity.id` を含める必要があります。 |  |
| `entity.event.detailsOnly` | true | `entity.id`が渡された場合は、製品ビューベースのアルゴリズムをゆがませないように、リクエストがアイテムの集計ページビュー数を増やさないようにするために、このパラメーターを渡すことを強くお勧めします。 |  |
| `entity.categoryId`<br>（特定のタイプの条件が必要：カテゴリ別で最も多く閲覧されたものおよびカテゴリ別のトップセラー） | *category_id* | カテゴリ内の上位の販売者など、レコメンデーションの基になるカテゴリ。<br>条件で必須の場合、rawbox 呼び出しには `entity.categoryId` を含める必要があります。 |  |
| `mboxDefault` | *`https://www.default.com`* | `mboxNoRedirect` パラメーターがない場合、`mboxDefault` は、レコメンデーションが使用できない場合にデフォルトコンテンツを返す絶対 URL である必要があります。 この URL は、画像またはその他の静的コンテンツにすることができます。<br> パラメーター`mboxNoRedirect`が存在する場合、`mboxDefault`は、推奨事項がないことを示す任意のテキストにできます（例：`no_content`）。<br>この値が返される場合は、電子メールプロバイダーが処理し、デフォルトのHTMLを電子メールに挿入する必要があります。<br>表の下にあるセキュリティのベストプラクティスを参照してください。 |  |
| `mboxHost` | *mbox_host* | 呼び出しが発生したときにデフォルト環境（ホストグループ）に追加されるドメインです。 |  |
| `mboxPC` | 空 | （訪問者のプロファイルを使用するレコメンデーションには必須です。） <br> 「thirdPartyId」が指定されていない場合、応答の一部として新しいtntIdが生成され、返されます。 それ以外の場合、値は空のままです。<br> テーブルの下の一意の値に関するメモを参照してください。 | 1 &lt; Length &lt; 128<br>「.」（ドット）を複数含めることはできません。 （ドット）。<br>許可されるドットは、プロファイルの場所のサフィックスのみです。 |

### オプションのパラメーター：

| パラメーター | 値 | 説明 | 検証 |
|--- |--- |--- |--- |
| `mboxPC`<br>（オプション） | *mboxPCId* | [!DNL Target]訪問者ID。 この値を使用すると、複数の訪問でサイトに戻るユーザーのフルサークルを追跡したり、ユーザープロファイルパラメーターを使用したりする場合に使用します。<br>この値は、Web サイトからCRMに書き出されるユーザーの実際の[!DNL Adobe Target] PCIDである必要があります。 メールプロバイダーは、CRMまたはデータウェアハウスからこのIDを取得し、このパラメーターの値として使用します。<br> レコメンデーションがA/B アクティビティの一部である場合、指標トラッキング用に複数訪問にわたる訪問者サイトの動作を追跡する場合にも`mboxPC`値が役立ちます。<br> テーブルの下の一意の値に関するメモを参照してください。 | 1 &lt; Length &lt; 128<br>「.」（ドット）を複数含めることはできません。 （ドット）。<br>許可されるドットは、プロファイルの場所のサフィックスのみです。 |
| `mboxNoRedirect`<br>（オプション） | 1 | デフォルトでは、配信可能なコンテンツが見つからない場合、呼び出し元がリダイレクトされます。 このパラメーターを使用して、デフォルトの動作を無効にします。 |  |
| `mbox3rdPartyId` | *xxx* | このオプションを使用して、プロファイルターゲティング用のカスタム訪問者IDを指定します。 |  |

`mboxSession`と`mboxPC`の場合、メール受信者ごとに一意の値を指定します（API呼び出しごとに）。 これらのフィールドに一意の値がないと、1つのプロファイル内で生成されるイベントの数が多いため、API応答が遅くなったり失敗したりする可能性があります。

`mboxDefault`のセキュリティのベストプラクティスとして、承認済みホストを使用して、デフォルトのリダイレクト URL ドメインを許可リストに加えるします。 `mboxDefault` URLで使用されているドメインが許可リストに加えるされていない場合、オープンリダイレクトの脆弱性のリスクが公開される可能性があります。 許可されたホストは、第三者によるリダイレクトリンクまたは`mboxDefault`の不正使用を回避します。 [!DNL Target]はホストを使用して、リダイレクトが許可されるドメインを許可リストに加えるします。 詳しくは、この節の先頭にあるセキュリティ通知を参照してください。

### 考えられる[!DNL Target] サーバーの応答

| 応答 | 説明 |
|--- |--- |
| //ERROR: | コンテンツを返すことができない場合にロードバランサーによって生成されます。 |
| 成功 | `mboxNoRedirect` パラメーターが&#39;true&#39;に設定されており、サーバーは推奨事項を返しません（mboxに一致しないか、サーバーキャッシュが初期化されていません）。 |
| bad request | `mbox` パラメーターがありません。<ul><li>`mboxDefault` または `mboxNoRedirect` パラメーターが指定されていません。</li><li>`mboxTrace` リクエストパラメーターが指定されていますが、`mboxNoRedirect`は指定されていません。</li><li>mbox名が`-clicked`接尾辞で終わる場合、`mboxTarget` パラメーターが指定されていません。</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | リクエストに一致するリクエストが存在せず、`mboxNoRedirect` パラメーターが指定されていない場合、`mboxDefault`は指定されません。 |
| `Invalid mbox name:= MBOX_NAME` | `mbox` パラメーターに無効な文字が含まれています。 |
| `Mbox name [MBOX_NAME] is too long` | `mbox` パラメーターが250文字を超えています。 |

## メソッド 3：Recommendations Download API の使用 {#download-api}

通常どおりにレコメンデーションを設定しますが、テンプレートと mbox の組み合わせの代わりに「**ダウンロードのみ**」を「プレゼンテーション」セクションで選択します。 次に、作成されたレコメンデーションのIDをESPに入力します。 ESPはAPIを介してレコメンデーションデータにアクセスします。 このデータには、特定のカテゴリまたはキー品目としてレコメンデーションすべき品目（放棄された買い物かごに含まれる品目など）が示されます。 ESPは、このデータを保存し、独自のルックアンドフィールでつなぎ合わせ、各商品に関する情報を表示し、メールで配信します。

このオプションを使用すると、レコメンデーションサーバーは、複数のアルゴリズムとテンプレートの組み合わせをまたいで、レコメンデーションまたは分割トラフィックのパフォーマンスを直接追跡できません。 また、レコメンデーションは、訪問者プロファイルとは結び付けられません。

ダウンロード API について詳しくは、[従来の API／ダウンロード](/help/main/assets/adobe-recommendations-classic.pdf)を参照してください。
