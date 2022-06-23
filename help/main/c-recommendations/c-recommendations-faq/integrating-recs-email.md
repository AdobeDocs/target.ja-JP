---
keywords: 電子メール;ESP;電子メールサービスプロバイダー;rawbox;delivery API;ダウンロード専用テンプレート;電子メールテンプレート;バッチ処理;ビルド時の電子メール
description: 電子メールを Adobe [!DNL Target Recommendations], including using the [!DNL Target] 配信 API、rawbox テンプレート、ダウンロード専用テンプレートと統合する方法について説明します。
title: レコメンデーションとメールの統合方法
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '1715'
ht-degree: 99%

---

# ![PREMIUM](/help/main/assets/premium.png) [!DNL Recommendations] とメールの統合

[!DNL Adobe Target] は、メールでのレコメンデーションの送信時パーソナライゼーションをサポートします。

[!DNL Target Recommendations] をメールサービスプロバイダー（ESP）統合するには、3 つの方法があります。ESP の機能によって、どの方法を使用するかが決まります。アカウントマネージャーまたはコンサルタントが、お客様が最適なオプションを選択できるよう支援します。

| メソッド | 詳細 |
| --- | --- |
| [メソッド 1： [!DNL Adobe Target Delivery API]](#delivery-api)（推奨） | [!DNL Adobe Target Delivery API] を使用して、顧客ごと／メールごとにレコメンデーションをリクエストします。 |
| [メソッド 2： [!DNL Adobe Rawbox API]](#rawbox) | [!DNL Adobe Target Rawbox API] を使用して、顧客ごと／電子メールごとにレコメンデーションをリクエストします。 |
| [メソッド 3： [!DNL Recommendations Download API]](#download-api) | Recommendations Download API を使用して、CSV 形式の製品またはカテゴリのリストに関する一括レコメンデーションをリクエストします。 |

メソッド 1 またはメソッド 2 を使用する場合は、ESP が顧客ごと／メールごとに外部 API を呼び出し、コンテンツが返されるのを待つ必要があります。これらのメソッドは、すべての ESP でサポートされているわけではありません。ESP に問い合わせて、この統合パターンと互換性があるかどうかを確認してください。

メソッド 3 を使用する場合は、ESP が製品 ID またはカテゴリ ID ごとのレコメンデーションのリストをメールのリストに結合する必要があります。このメソッドは、顧客が最後に閲覧した製品、最後に購入した製品、最も多く閲覧したカテゴリなどの属性に基づくことができます。 ただし、結合を行うためには、ESP が顧客プロファイルのこのデータにアクセスできる必要があります。ESP に問い合わせて、このデータへのアクセス権があり、この統合パターンと互換性があるかどうかを確認します。

オープンタイムでのレコメンデーションのパーソナライゼーションは、[!DNL Adobe Target] ではサポートされていません。

>[!IMPORTANT]
>
>次の容量ガイドラインは、以下で説明する Delivery API および rawbox メールテンプレートメソッド（メソッド 1 および 2）に適用されます。
>
>* リクエストのレートは、1 秒あたり 1,000 リクエスト、または 1 日のピークトラフィックの 25 倍のいずれか低い方に制限する必要があります。
>* 毎分 200 リクエスト/秒のステップでトラフィックを傾斜させます。
> 
>レート制限を高くしたい場合は、アカウントマネージャーに連絡してください。

## メソッド 1：配信 API の使用（推奨） {#delivery-api}

Delivery API は、ビルド時の電子メールを操作する POST リクエストです。このオプションは、ビルド時の電子メール用に推奨される方法です。

ほとんどの電子メールクライアントでは POST リクエストが許可されません。したがって、この API は、オープンタイムの使用例には推奨されません。 Gmail や Outlook などの一部の電子メールクライアントは、コンテンツをキャッシュしたり、画像をブロックしたりして、受信者に画像のレンダリングを事前に許可するように要求することができます。

Delivery API を使用してデフォルトのコンテンツを返すことはできません。

サンプル API 配信リクエストのコードを次に示します。

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

ここで、`clientcode` は クライアントコードです。[!DNL Target]

>[!NOTE]
>
>電子メール受信者（API 呼び出し）ごとに、`sessionId` と `tntId`（または `thirdPartyId`）の両方で一意の値を必ず指定してください。これらのフィールドに一意の値を指定しないと、単一のプロファイル内で多くのイベントが生成されるので、API 応答が遅くなったり失敗したりする可能性があります。

詳しくは、 [Delivery API ドキュメント](https://developer.adobe.com/target/implement/delivery-api/){target=_blank} を参照してください。

## オプション 2：rawbox メールテンプレートの使用 {#rawbox}

rawbox は、mbox リクエストに似ていますが、メールサービスプロバイダー（ESP）などの非 web 環境用です。rawbox リクエストで使用する [!DNL Adobe Experience Platform Web SDK] または [!DNL at.js] がないため、リクエストを手動で作成する必要があります。以下の例では、メールで rawbox リクエストを処理する方法を説明しています。

>[!NOTE]
>
>rawboxと[!DNL Target]を使用する場合は、[ に mbox 呼び出しを送信する権限のあるホストを指定する許可リストの作成 [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist)の重要なセキュリティ通知を参照してください。

この方法を使用すれば、電子メールでのレコメンデーションのパフォーマンスを追跡し、それをレコメンデーションを使用した通常の方法でテストして、さらにサイトでの追跡を継続することが可能になります。

[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) オプションを使用して、[!DNL Recommendations] アクティビティを [!DNL Target] で設定します。場所には、ESP から来る rawbox リクエストで使用することにした mbox の名前を選択します。電子メールに使用したいルックアンドフィールを持つデザインを選択します。電子メールの構築時に、ESP は、生成中の各電子メールの各 rawbox に対して、[!DNL Target] サーバーを呼び出します。ESP には、電子メールを送信する際に、返された HTML を電子メールに含める手段が必要です。

使用するメールシステムは、次のシナリオに対応できる必要があります。

### 有効な応答を受信したが、レコメンデーションが存在しない

* この場合、応答は `mboxDefault` パラメーター値として設定されたものになります。 このパラメーターに関する後述の説明を参照してください。
* この場合、電子メールプロバイダーは、レコメンデーションのデフォルト HTML ブロックを使用する必要があります。

### [!DNL Target] サーバーがタイムアウトし、返されるデータがない

* この場合、[!DNL Target] サーバーは次のコンテンツを返します。

   `//ERROR: application server timeout`

* メールアプリケーションは、そのテキストを検索し、エラーを処理できる必要があります。電子メールプロバイダーには、この事例に対処する複数のオプションがあります。

   * 即座に別のサーバー呼び出しを試す（推奨、試行をカウントする必要がある可能性があります）。
   * 該当する電子メールを捨てて、次の電子メールに移る。
   * 該当する電子メールをキューに入れて、最初の実行の最後に、失敗した電子メールをバッチとして再実行します。

### リクエスト URL の例

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### 必須パラメーター： {#reqparams}

>[!NOTE]
>
>電子メールで [!DNL Recommendations] を使用するには、レコメンデーション条件のタイプに応じて、rawbox 呼び出しに通常、`entity.id` または `entity.categoryId`、あるいはその両方を含める必要があります。 前述の呼び出しの例では、両方が含まれています。

| パラメーター | 値 | 説明 | 検証 |
|--- |--- |--- |--- |
| `client_code` | *client_code* | Recommendations で使用されるクライアントのコード。この値はアドビコンサルタントから入手できます。 |  |
| `mbox` | *mboxName* | ターゲット設定に使用される mbox 名。 | すべての mbox 呼び出しと同じ検証。<br>上限 250 文字.<br>次の文字を含めることはできません：`', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | 無効 | 非 Web 環境において応答で cookie を設定しないようにします。 |  |
| `entity.id`<br>（特定のタイプの条件が必要：view/view、view/bought、bought/bought） | *entity_id* | 買い物かごで放棄された商品や以前の購入など、レコメンデーションが基にする productId。<br>条件で必須の場合、rawbox 呼び出しには `entity.id` を含める必要があります。 |  |
| `entity.event.detailsOnly` | true | `entity.id` を渡す場合、リクエストがその商品に関して集計されたページビュー数を増加させることを防ぎ、製品表示ベースのアルゴリズムを歪曲しないように、このパラメーターも渡すことを強くお勧めします。 |  |
| `entity.categoryId`<br>（特定のタイプの条件が必要：カテゴリ別で最も多く閲覧されたものおよびカテゴリ別のトップセラー） | *category_id* | あるカテゴリのトップセラーなど、レコメンデーションが基にするカテゴリ。<br>条件で必須の場合、rawbox 呼び出しには `entity.categoryId` を含める必要があります。 |  |
| `mboxDefault` | *`https://www.default.com`* | `mboxNoRedirect` パラメーターがない場合、`mboxDefault` は、レコメンデーションが使用できない場合にデフォルトコンテンツを返す絶対 URL である必要があります。 この URL は、画像またはその他の静的コンテンツにすることができます。<br>`mboxNoRedirect` パラメーターがある場合、`mboxDefault` には、`no_content` など、レコメンデーションがないことを示す任意のテキストを指定できます。<br>メールプロバイダーは、この値が返された場合に対処し、メールにデフォルトの HTML を挿入する必要があります。<br> **セキュリティのベストプラクティス**：`mboxDefault` URL で使用されるドメインが許可リストに含まれていない場合は、オープンリダイレクトの脆弱性のリスクにさらされる可能性があります。 サードパーティによるリダイレクターリンクまたは `mboxDefault` の不正使用を回避するために、アドビは「承認済みホスト」を使用してデフォルトのリダイレクト URL ドメインを許可リストに加えるすることをお勧めします。 Target は、ホストを使用して、リダイレクトを許可するドメインを許可リストに登録します。詳しくは、[ホスト [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist)の&#x200B;*に mbox 呼び出しを送信する権限のあるホストを指定する許可リストの作成*&#x200B;を参照してください。 |  |
| `mboxHost` | *mbox_host* | 呼び出しが発生したときにデフォルト環境（ホストグループ）に追加されるドメインです。 |  |
| `mboxPC` | 空 | （訪問者のプロファイルを使用するレコメンデーションに必要）<br>「thirdPartyId」を指定しない場合、新しい tntId が生成され、応答の一部として返されます。それ以外の場合は、空です。<br>**注意**：電子メール受信者（API 呼び出し）ごとに、`mboxSession` および `mboxPC` の一意の値を必ず指定してください。これらのフィールドに一意の値を指定しないと、単一のプロファイル内で多くのイベントが生成されるため、API の応答が遅くなったり失敗したりする可能性があります。 | 1 &lt; Length &lt; 128<br>「.」（ドット）を複数含めることはできません。 <br>プロファイルのロケーションサフィックスにのみ、ドットを使用できます。 |

### オプションのパラメーター：

| パラメーター | 値 | 説明 | 検証 |
|--- |--- |--- |--- |
| `mboxPC`<br>（オプション） | *mboxPCId* | Target の訪問者 ID。複数の訪問で元のサイトに戻るユーザーを追跡する場合、またはユーザープロファイルパラメーターを使用する場合に、この値を使用します。<br>この値は、ユーザーの実際の [!DNL Adobe Target] PCID である必要があります。この値は、Web サイトから CRM に書き出されます。 E メールプロバイダーは、この ID を CRM または Data Warehouse から取得し、このパラメーターの値に使用します。<br>`mboxPC` 値も、レコメンデーションが A/B アクティビティの一部である場合の指標追跡で、複数の訪問での訪問者のサイトでの行動を追跡するのに便利です。<br>**注意**：電子メール受信者（API 呼び出し）ごとに、`mboxSession` および `mboxPC` の一意の値を必ず指定してください。これらのフィールドに一意の値を指定しないと、単一のプロファイル内で多くのイベントが生成されるため、API の応答が遅くなったり失敗したりする可能性があります。 | 1 &lt; Length &lt; 128<br>「.」（ドット）を複数含めることはできません。 <br>プロファイルのロケーションサフィックスにのみ、ドットを使用できます。 |
| `mboxNoRedirect`<br>（オプション） | 1 | デフォルトでは、配信可能なコンテンツが見つからない場合、呼び出し元がリダイレクトされます。デフォルトの動作を無効にする場合に使用します。 |  |
| `mbox3rdPartyId` | *xxx* | プロファイルターゲット設定に使用する独自のカスタム訪問者 ID がある場合は、このオプションを使用します。 |  |

### 考えられる[!DNL Target] サーバーの応答

| 応答 | 説明 |
|--- |--- |
| //ERROR: | コンテンツを返すことができない場合にロードバランサーによって生成されます。 |
| 成功 | `mboxNoRedirect` パラメーターが「true」に設定され、サーバーはレコメンデーションを返しません（つまり、mbox に合致しないか、サーバーキャッシュが初期化されません）。 |
| bad request | `mbox` パラメーターがありません。<ul><li>`mboxDefault` または `mboxNoRedirect` パラメーターが指定されていません。</li><li>`mboxTrace` リクエストパラメーターは指定されていますが、`mboxNoRedirect` は指定されていません。</li><li>`mboxTarget`mbox 名が `-clicked` サフィックスで終わる場合、パラメーターは指定されません。</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | リクエストに合致するものが存在しない場合に `mboxDefault` が指定されておらず、`mboxNoRedirect` パラメーターが指定されていません。 |
| `Invalid mbox name:= MBOX_NAME` | `mbox` パラメーターに無効な文字が含まれていることを示します。 |
| `Mbox name [MBOX_NAME] is too long` | `mbox` パラメーターが 250 文字より長いことを示します。 |

## メソッド 3：Recommendations Download API の使用 {#download-api}

通常どおりにレコメンデーションを設定しますが、テンプレートと mbox の組み合わせの代わりに「**ダウンロードのみ**」を「プレゼンテーション」セクションで選択します。次に、作成したレコメンデーション ID を ESP に伝えます。ESP が、API を介してレコメンデーションデータにアクセスします。このデータには、特定のカテゴリまたはキー品目としてレコメンデーションすべき品目（放棄された買い物かごに含まれる品目など）が示されます。ESP はこのデータを保存して、独自の外観と操作性に結び付け、品目ごとの情報を表示してから電子メールで配信します。

このオプションを使用する場合、recommendations サーバーでレコメンデーションのパフォーマンスを直接追跡したり、複数のアルゴリズム／テンプレートの組み合わせ全体でトラフィックを分割したりできません。また、レコメンデーションは、訪問者プロファイルとは結び付けられません。

ダウンロード API について詳しくは、[従来の API／ダウンロード](/help/main/assets/adobe-recommendations-classic.pdf)を参照してください。
