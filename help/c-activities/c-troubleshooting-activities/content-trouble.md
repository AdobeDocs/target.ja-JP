---
keywords: debug mbox;troubleshoot mbox;mbox issues;flicker;mboxDebug;mboxTrace;token;debugger;priority;activity priority;Adobe Experience Cloud Debugger;orderConfirmPage mbox;SiteCatalyst  purchase mbox;top selling;top seller
description: ページに期待したコンテンツが表示されない場合は、Adobe Targetでコンテンツの配信をデバッグするためにいくつかの手順を実行できます。
title: Adobe Targetでのコンテンツ配信のトラブルシューティング
feature: null
subtopic: Multivariate Test
topic: Standard
uuid: 8837d07a-f793-495e-a6c1-b9c35fbe18b1
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 67%

---


# コンテンツ配信のトラブルシューティング{#troubleshoot-content-delivery}

ページに意図するコンテンツが表示されない場合は、コンテンツ配信をデバッグするためにいくつかの手順をおこないます。

* アクティビティやキャンペーンコードを慎重に確認します。タイポやその他のエラーがあると、意図するコンテンツが表示されない場合があります。
* Use mboxTrace or mboxDebug to troubleshoot the [!DNL Target] request.
* Use the Adobe Experience Cloud Debugger, an easy-to-use tool that provides much of the same information as mboxDebug, to troubleshoot the [!DNL Target] request.

mboxDebug is especially useful when you are setting up [!DNL Target] on your page to make sure the [!DNL Target] request is firing and the cookie is being set. ただし、mboxDebug は、コンテンツ配信のデバッグに役立つ詳細までは調べません。ページにアクティビティが表示されない場合や、意図していないコンテンツが表示される場合は、mboxTrace を使用してページの調査とデバッグを詳細におこないます。

## デバッグツールで使用するための認証トークンの取得 {#section_BED130298E794D1FA229DB7C3358BA54}

mboxTrace と mboxDebug は、外部パーティにキャンペーンデータとプロファイルデータを公開するので、認証トークンが必要です。認証トークンは、[!DNL Target] UI で取得できます。トークンは 6 時間有効です。

認証トークンを取得するには、次の手順に従います。

1. [ **[!UICONTROL 管理]** ] > [ **[!UICONTROL 実装]**]の順にクリックします。
1. 「Debugger Tools」セクションで、「 **[!UICONTROL Generate New Authentication Token]**」をクリックします。

   ![新しい認証トークンの生成](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. 生成されたトークンをパラメーターとして URL に追加して、高度なデバッグツールの 1 つを有効にします。

   ![認証トークン](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace enables you to receive trace information attached to [!DNL Target] responses. Trace information reflects the outcome of a [!DNL Target] call (for example, a conversion or an impression) and any additional data that may help in determining why this particular outcome happened, such as a set of available branches among which the selection was made in a campaign. この情報を使用してコンテンツ配信をデバッグします。

次のパラメーターを使用できます。

| mboxTrace のオプション | 結果 |
|--- |--- |
| `?mboxTrace=console` | コンソールログにオブジェクトとして出力します。<br>at.js の場合は、mbox.js のように新しいブラウザーウィンドウをポップアップしたりコンソールに出力したりする代わりに、ネットワークリクエストを調べて、プレビュー（Chrome）または応答（Firefox）を確認する必要があります。 |
| `?mboxTrace=json` | コンソールログにリテラル JSON 文字列として出力します。 |
| `?mboxTrace=window` | ポップアップウィンドウに JSON 文字列として出力します。 |
| `?mboxTrace=disable` | セッションモードのトレースをオフにします。 |

**mboxTrace 呼び出しの例**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

出力に、コンテンツに関するきわめて詳しい情報が表示されます。mboxTrace は、キャンペーンまたはアクティビティとプロファイルの詳細を表示します。また、実行前のプロファイルのスナップショットと、実行後の変化を示すスナップショットも提供します。さらに、各場所で評価されたキャンペーンやアクティビティも表示します。

情報によっては、一致するセグメント、一致しないセグメントおよびターゲット ID が含まれる場合もあります。

* **SegmentId**：セグメントの ID。再利用可能なセグメントライブラリか、特定のキャンペーン用に作成された匿名セグメントのいずれかのものです。
* **TargetId**：ターゲットの ID。ターゲットエクスプレッションライブラリか、キャンペーンの任意のセグメント用の匿名ターゲットのものです。
* **Unmatched**：リクエストは、この呼び出しで、セグメントまたはターゲットに適していませんでした。
* **Matched**：リクエストは、指定されたセグメントまたはターゲットに適していました。

**レコメンデーションページでの mboxTrace の使用**：レコメンデーションを含むページに mboxTrace をクエリパラメーターとして追加すると、ページ上のレコメンデーションのデザインが、mboxTrace の詳細ウィンドウに置き換わり、以下を含むレコメンデーションに関する詳細が表示されます。

* 返されたレコメンデーションと要求されたレコメンデーション
* 使用されたキーと、それがレコメンデーションを生成するかどうか
* 条件によって生成されたレコメンデーションとバックアップレコメンデーション
* 条件の設定
* 適用される除外とインクルージョン
* 収集ルール

クエリパラメーターには、`=console`、`=json`、または `=window` を含める必要はありません。mboxTrace の詳細が完了したら、`=disable` を追加して、**[!UICONTROL Enter]** キーを押すと、通常の表示モードに戻ります。

サイトの通常の機能や外見は、mboxTrace の影響を受けません。訪問者には、通常のレコメンデーションのデザインが表示されます。

## mboxDebug {#mboxdebug}

mboxDebug を使用するには、URL の末尾に mboxDebug パラメーターを追加します。The following table contains information about [!DNL Target] response-related URL parameters.

>[!NOTE]
>
>mboxDebug パラメーターによっては、使用するのに認証を必要とするものと、認証を必要としないものがあります。

| URL パラメーター | 目的 |
|--- |--- |
| `mboxDebug=1` | <br>デバッガターゲットリクエストが定義された任意のURLにこのパラメータを追加すると、ポップアップウィンドウが開き、デバッグに役立つ詳細情報が表示されます。 Cookie 情報、PCID およびセッション ID の値が記述され、 URL がすべて表示されます。Click on a Target request URL to show the response for that [!DNL Target] request. 詳しくは、[mbox_debug.pdf](/help/assets/mbox_debug.pdf) を参照してください。 |
| `mboxDebug=x-cookie` | cookie の変更 |
| `mboxDisable=1` | ページ上の mbox を無効化 |
| `mboxDebug=x-profile` | プロファイルセットを表示 |
| `mboxDebug=x-time` | Show response time for each [!DNL Target] request |
| `mboxOverride.browserIp=<Insert IP address>` | Geotargeting のテスト<br>Geotargeting をこの URL パラメーターでテストします。この属性の値に IP アドレスを入力すると、Test&amp;Target のジオターゲティングがこの IP アドレスを評価し、キャンペーン内のジオターゲティングまたはセグメント化セットに一致させます。 |

>[!NOTE]
>
>URLフラグメントがクエリ文字列パラメーターの後にあることを確認します。 最初の値の後にあ `#` るものはフラグメント識別子で、デバッグパラメーターが正しく機能しない原因となります。

## Adobe Experience Cloud デバッガー {#section_A2798ED3A431409690A4BE08A1BFCF17}

Adobe Experience Cloud デバッガーを使用すると、Target の実装をすばやく簡単に理解できます。ライブラリ設定をすばやく表示し、リクエストを検証してカスタムパラメーターが正しく渡されたことを確認し、コンソールのログを有効にして、Target のすべてのリクエストを無効にすることができます。Experience Cloudを認証し、強力なMboxTraceツールを使用して、アクティビティとオーディエンスの資格、および訪問者プロファイルを調査できます。

詳しくは、以下のトレーニングビデオを参照してください。

詳しくは、「Adobe Experience Cloudデバッガーを使用したat.jsの [デバッグ](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md)」を参照してください。

## 配信中に target.js を読み込めなかった場合 {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

配信中に target.js の読み込みに失敗した場合は、mbox.js から訪問者に対して「em-disabled」という cookie が送信されます。この cookie は、Visual Experience Composer を使用して作成されたオファーがサイトに表示されないようにします。この cookie が設定された訪問者には、テストコンテンツが表示されず、それらのアクティビティレポートでもカウントされません。その他すべてのオファーコンテンツ（例えば Target Classic のキャンペーンのコンテンツ）は引き続き読み込まれます。この cookie の有効期間は、読み込み失敗時から 30 分です。

## レコメンデーションにトップセラーが表示されない {#section_3920C857270A406C80BE6CBAC8221ECD}

The *`SiteCatalyst: purchase`* call can&#39;t be used for Purchase algorithm traffic data. 代わりに、 *`orderConfirmPage`* 呼び出しを使用します。

## アクティビティの優先度を確認 {#section_3D0DD07240F0465BAF655D0804100AED}

Form-based activities created with [!DNL Target Standard/Premium] might collide with activities created in the [!DNL Target Classic] UI that have the same priority and use the same [!DNL Target] request.

## Internet Explorer 8 でカスタムコードが期待どおりの結果を返さない{#section_FAC3651F19144D12A37A3E4F14C06945}

Target は、IE 8 をサポートしていません。

## JavaScript content delivered by the global [!DNL Target] request doesn&#39;t load when using mbox.js. {#section_03EC9B9C410B4F52A7FCD81840311709}

[!DNL mbox.js] のバージョンを 58 以降にアップグレードしてください。

mbox.js version 58 and later executes non-JavaScript content for the global [!DNL Target] request immediately after the HTML `BODY` tag is present. JavaScript content inside `<script>` tags for the global [!DNL Target] request executes after the `DOMContentLoaded` event is fired. This order of content delivery ensures that JavaScript content for the global [!DNL Target] request is delivered and rendered properly.

## Target の Cookie が設定されない {#section_77AFEB541C0B495EB67E29A4475DF960}

サイトにサブドメイン（[!DNL us.domain.com] など）がある場合で Target の cookie を（[!DNL domain.com] ではなく）[!DNL us.domain.com] に設定する必要がある場合、`cookieDomain` 設定を上書きする必要があります。詳しくは、「[targetGlobalSettings（）](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)」を参照してください。.

## 要素が AEM パーソナライゼーションにも含まれていると、Target のコンテンツがちらつく、または表示されない{#section_9E1DABEB75AB431FB9F09887E6DD07D3}

DOM 要素が Adobe Experience Manager（AEM）パーソナライゼーションのターゲット設定と Target アクティビティの両方に含まれていると、Target コンテンツがちらついたり表示されなかったりする場合があります。

これを修正するには、Target が実行されているページで AEM パーソナライゼーションを無効にします。

## URL が無効なのでリダイレクトおよびリモートオファーを配信できない {#section_7D09043B687F43B39DAEDF17D00375AC}

リダイレクトまたはリモートオファーで無効な URL が使用されていると、配信できない可能性があります。

For redirect offers, the [!DNL Target] response can contain `/* invalid redirect offer URL */`

または

For remote offers, the [!DNL Target] response can contain `/* invalid remote offer URL */`

You can check the [!DNL Target] response in the browser or using mboxTrace. 有効な URL について詳しくは、[https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) を参照してください。

## サイトでターゲット要求が実行されていない。

at.jsは、無効なdoctypeを使用している場合、ターゲットリクエストを実行しません。 a.js には HTML5 の doctype が必要です。

## トレーニングビデオ

以下のビデオは、この記事で説明する概念についてさらに詳しく説明しています。

### 拡張機能の追加 ![チュートリアルバッジ](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### 基本的なターゲットデバッグ ![チュートリアルバッジ](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### mboxトレース ![チュートリアルバッジ](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)