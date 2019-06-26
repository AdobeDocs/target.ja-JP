---
description: 電子メールと Recommendations を統合する方法に関する情報をまとめています。
keywords: 電子メール;ESP;電子メールサービスプロバイダー;rawbox;delivery API;ダウンロード専用テンプレート;電子メールテンプレート;バッチ処理;ビルド時の電子メール
seo-description: 電子メールと Recommendations を統合する方法に関する情報をまとめています。
seo-title: Recommendations と電子メールの統合
solution: 'Target '
title: Recommendations と電子メールの統合
title-outputclass: premium
topic: Recommendations
uuid: ae137d7c-58c5-4601-92fc-2dc5548760fd
badge: premium
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![PREMIUM](/help/assets/premium.png) Recommendations と電子メールの統合{#integrate-recommendations-with-email}

電子メールと Recommendations を統合する方法に関する情報をまとめています。

ご使用の電子メールサービスプロバイダーが提供する機能によって、どの方法を使用するかが決まります。アカウントマネージャーまたはコンサルタントが、最適なオプションの選択を支援します。

## オプション 1：Delivery API の使用 {#section_9F00D271BABA4B7390B461F4C44EC319}

Delivery API は、ビルド時の電子メールを操作する POST リクエストです。このオプションは、ビルド時の電子メール用に推奨される方法です。

ほとんどの電子メールクライアントでは POST リクエストが許可されません。したがって、この API は、オープン時の用途には推奨されません。Gmail や Outlook などの一部の電子メールクライアントでは、コンテンツがキャッシュされたり、画像がブロックされたりする場合があり、画像のレンダリングを受信者が事前に許可する必要があります。

Delivery API を使用してデフォルトのコンテンツを返すことはできません。

サンプル API 配信リクエストのコードを次に示します。

```
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

ここで、`clientcode` は Target クライアントコードです。

>[!NOTE]
>
>電子メール受信者（API 呼び出し）ごとに、`sessionId` と `tntId`（または `thirdPartyId`）の両方で一意の値を必ず指定してください。これらのフィールドに一意の値を指定しない場合は、1 つのプロファイル内で多数のイベントが生成されるので、API の応答が遅くなったり失敗したりする可能性があります。

詳しくは、[Delivery API ドキュメント](https://developers.adobetarget.com/api/#server-side-delivery)を参照してください。

## オプション 2：rawbox 電子メールテンプレートの使用 {#section_C0D48A42BCCE45D6A68852F722C7C352}

rawbox は、mbox リクエストに似ていますが、電子メールサービスプロバイダー（ESP）などの非 Web 環境用です。[!DNL mbox.js] または [!DNL at.js] を rawbox リクエストに使用できないので、手動でリクエストを作成する必要があります。次の例で、電子メールでの rawbox リクエストの操作方法を説明します。

この方法を使用すれば、電子メールでのレコメンデーションのパフォーマンスを追跡し、それをレコメンデーションを使用した通常の方法でテストして、さらにサイトでの追跡を継続することが可能になります。

[フォームベースの Experience Composer](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) オプションを使用して、[!DNL Recommendations] アクティビティを [!DNL Adobe Target] で設定します。場所には、ESP から来る rawbox リクエストで使用することにした mbox の名前を選択します。電子メールに使用したいルックアンドフィールを持つデザインを選択します。電子メールの構築時に、ESP は、生成中の各電子メールの各 rawbox に対して、[!DNL Adobe Target] サーバーを呼び出します。ESP には、電子メールを送信する際に、返された HTML を電子メールに含める手段が必要です。

使用する電子メールシステムが、次の状況に対処する機能を持っている必要があります。

**有効な応答を受信したが、レコメンデーションが存在しない。**

* この場合、どんな値でも mboxDefault パラメーター値として設定されたのもが応答になります。このパラメーターに関する後述の説明を参照してください。
* この場合、電子メールプロバイダーは、レコメンデーションのデフォルト HTML ブロックを使用する必要があります。

**Target サーバーがタイムアウトし、データなしで返される。**

* この場合、Target サーバーは、次のコンテンツを返します。

   `//ERROR: application server timeout`

* 電子メールアプリケーションが、このテキストを検索して、このエラーに対処できる必要があります。電子メールプロバイダーには、この事例に対処する複数のオプションがあります。

   * 即座に別のサーバー呼び出しを試す（推奨、試行をカウントする必要がある可能性があります）。
   * 該当する電子メールを捨てて、次の電子メールに移る。
   * 該当する電子メールをキューに入れて、最初の実行の最後に、失敗した電子メールをバッチとして再実行する。

**リクエスト URL の例：**

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

**必須パラメーター:**

>[!NOTE]
>
>電子メールで [!DNL Recommendations] を使用するには、rawbox 呼び出しに通常、レコメンデーション条件のタイプに応じて、`entity.id`、`entity.categoryId` またはその両方を含める必要があります。前述の呼び出しの例では、両方が含まれています。

| パラメーター | 値 | 説明 | 検証 |
|--- |--- |--- |--- |
| `client_code` | *client_code* | Recommendations で使用されるクライアントのコード。この値はアドビコンサルタントから入手できます。 |  |
| `mbox` | *mboxName* | ターゲット設定に使用される mbox 名。 | すべての mbox 呼び出しと同じ検証。<br>上限 250 文字.<br>次の文字を含めることはできません：`', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | 無効 | 非 Web 環境において応答で cookie を設定しないようにします。 |  |
| `entity.id`<br>（特定のタイプの条件が必要：view/view、view/bought、bought/bought） | *entity_id* | 買い物かごで放棄された商品や以前の購入など、レコメンデーションが基にする productId。<br>条件で必須の場合、rawbox 呼び出しには `entity.id` を含める必要があります。 |  |
| `entity.event.detailsOnly` | true | `entity.id` を渡す場合、リクエストがその商品に関して集計されたページビュー数を増加させることを防ぎ、製品表示ベースのアルゴリズムを歪曲しないように、このパラメーターも渡すことを強くお勧めします。 |  |
| `entity.categoryId`<br>（特定のタイプの条件が必要：カテゴリ別で最も多く閲覧されたものおよびカテゴリ別のトップセラー） | *category_id* | あるカテゴリのトップセラーなど、レコメンデーションが基にするカテゴリ。<br>条件で必須の場合、rawbox 呼び出しには `entity.categoryId` を含める必要があります。 |  |
| `mboxDefault` | *`https://www.default.com`* | `mboxNoRedirect` パラメーターがない場合、`mboxDefault` には、レコメンデーションが使用できない場合にデフォルトコンテンツを返す絶対 URL を指定する必要があります。これは、画像または他の静的コンテンツにすることができます。<br>`mboxNoRedirect` パラメーターがある場合、`mboxDefault` には、`no_content` など、レコメンデーションがないことを示す任意のテキストを指定できます。<br>電子メールプロバイダーは、この値が返された場合に対処し、電子メールにデフォルト HTML を挿入する必要があります。 |  |
| `mboxHost` | *mbox_host* | これは、呼び出しが発生する際にデフォルト環境（ホストグループ）に追加されているドメインです。 |  |
| `mboxPC` | 空 | （訪問者のプロファイルを使用するレコメンデーションに必要）<br>「thirdPartyId」を指定しない場合、新しい tntId が生成され、応答の一部として返されます。それ以外の場合は、空です。<br>**注意**：電子メール受信者（API 呼び出し）ごとに、`mboxSession` および `mboxPC` の一意の値を必ず指定してください。これらのフィールドに一意の値を指定しない場合は、1 つのプロファイル内で多数のイベントが生成されるので、API の応答が遅くなったり失敗したりする可能性があります。 | 1 &lt; Length &lt; 128<br>「.」（ドット）を複数含めることはできません。（ドット）.<br>プロファイルのロケーションサフィックスにのみ、ドットを使用できます。 |

**オプションのパラメーター**：

| パラメーター | 値 | 説明 | 検証 |
|--- |--- |--- |--- |
| `mboxPC`<br>（オプション） | *mboxPCId* | Target の訪問者 ID。複数の訪問で元のサイトに戻るユーザーを追跡する場合、またはユーザープロファイルパラメーターを使用する場合に、この値を使用します。<br>この値は、ユーザーの実際の Adobe Target PCID である必要があります（Adobe Target PCID は、Web サイトから CRM にエクスポートされます）。電子メールプロバイダーは、この ID を CRM または Data Ｗarehouse から取得し、このパラメーターの値に使用します。<br>`mboxPC` 値も、レコメンデーションが A/B アクティビティの一部である場合の指標追跡で、複数の訪問での訪問者のサイトでの行動を追跡するのに便利です。<br>**注意**：電子メール受信者（API 呼び出し）ごとに、`mboxSession` および `mboxPC` の一意の値を必ず指定してください。これらのフィールドに一意の値を指定しない場合は、1 つのプロファイル内で多数のイベントが生成されるので、API の応答が遅くなったり失敗したりする可能性があります。 | 1 &lt; Length &lt; 128<br>「.」（ドット）を複数含めることはできません。（ドット）.<br>プロファイルのロケーションサフィックスにのみ、ドットを使用できます。 |
| `mboxNoRedirect`<br>（オプション） | 1 | デフォルトでは、配信可能なコンテンツが見つからない場合、呼び出し元がリダイレクトされます。デフォルトの動作を無効にする場合に使用します。 |  |
| `mbox3rdPartyId` | *xxx* | 独自のカスタム訪問者 ID をプロファイルのターゲット設定に使用する場合、これを使用します。 |  |

**Target サーバーの応答**：

| 応答 | 説明 |
|--- |--- |
| //ERROR: | コンテンツを返すことができない場合にロードバランサーによって生成されます。 |
| success | `mboxNoRedirect` パラメーターが「true」に設定され、サーバーはレコメンデーションを返しません（つまり、mbox に合致しないか、サーバーキャッシュが初期化されません）。 |
| bad request | `mbox` パラメーターがありません。<ul><li>`mboxDefault` または `mboxNoRedirect` パラメーターが指定されていません。</li><li>`mboxTrace` リクエストパラメーターは指定されていますが、`mboxNoRedirect` は指定されていません。</li><li>mbox 名が `-clicked` サフィックスで終わる場合に、`mboxTarget` パラメーターが指定されていません。</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | リクエストに合致するものが存在しない場合に `mboxDefault` が指定されておらず、`mboxNoRedirect` パラメーターが指定されていません。 |
| `Invalid mbox name:= MBOX_NAME` | `mbox` パラメーターに無効な文字が含まれていることを示します。 |
| `Mbox name [MBOX_NAME] is too long` | `mbox` パラメーターが 250 文字より長いことを示します。 |

## オプション 3：ダウンロード専用テンプレートの使用 {#section_518C279AF0094BE780F4EA40A832A164}

通常どおりにレコメンデーションを設定しますが、テンプレートと mbox の組み合わせの代わりに「**ダウンロードのみ**」を「プレゼンテーション」セクションで選択します。次に、作成したレコメンデーション ID を ESP に伝えます。ESP が、API を介してレコメンデーションデータにアクセスします。このデータには、特定のカテゴリまたはキー品目としてレコメンデーションすべき品目（放棄された買い物かごに含まれる品目など）が示されます。ESP はこのデータを保存して、独自の外観と操作性に結び付け、品目ごとの情報を表示してから電子メールで配信します。

このオプションを使用する場合、recommendations サーバーでレコメンデーションのパフォーマンスを直接追跡したり、複数のアルゴリズム／テンプレートの組み合わせ全体でトラフィックを分割したりできません。また、レコメンデーションは、訪問者プロファイルとは結び付けられません。

ダウンロード API について詳しくは、[従来の API／ダウンロード](../../assets/adobe-recommendations-classic.pdf)を参照してください。
