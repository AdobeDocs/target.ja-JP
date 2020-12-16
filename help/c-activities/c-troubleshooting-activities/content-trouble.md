---
keywords: debug mbox;troubleshoot mbox;mbox issues;flicker;mboxDebug;mboxTrace;token;debugger;priority;activity priority;Adobe Experience Cloud Debugger;orderConfirmPage mbox;SiteCatalyst  purchase mbox;top selling;top seller
description: ページに期待したコンテンツが表示されない場合は、Adobe Targetでコンテンツの配信をデバッグするためにいくつかの手順を実行できます。
title: Adobe Targetでのコンテンツ配信のトラブルシューティング
feature: activities
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1386'
ht-degree: 60%

---


# コンテンツ配信のトラブルシューティング{#troubleshoot-content-delivery}

ページに意図するコンテンツが表示されない場合は、コンテンツ配信をデバッグするためにいくつかの手順をおこないます。

* アクティビティやキャンペーンコードを慎重に確認します。タイポやその他のエラーがあると、意図するコンテンツが表示されない場合があります。
* mboxTraceまたはmboxDebugを使用して[!DNL Target]リクエストのトラブルシューティングを行います。
* Adobe Experience Cloudデバッガは、mboxDebugとほとんど同じ情報を提供する使いやすいツールで、[!DNL Target]リクエストのトラブルシューティングに使用します。

mboxDebugは、ページに[!DNL Target]を設定して、[!DNL Target]リクエストが実行され、cookieが設定されていることを確認する場合に特に便利です。 ただし、mboxDebug は、コンテンツ配信のデバッグに役立つ詳細までは調べません。ページにアクティビティが表示されない場合や、意図していないコンテンツが表示される場合は、mboxTrace を使用してページの調査とデバッグを詳細におこないます。

## デバッグツールで使用する認証トークンを取得{#section_BED130298E794D1FA229DB7C3358BA54}

mboxTrace と mboxDebug は、外部パーティにキャンペーンデータとプロファイルデータを公開するので、認証トークンが必要です。認証トークンは、[!DNL Target] UI で取得できます。トークンは 6 時間有効です。

認証トークンを生成するには、次のいずれかのユーザー権限が必要です。

* [!UICONTROL エディター]権限（または[!UICONTROL 承認者]）以上

   [!DNL Target Standard]ユーザーの詳細については、*ユーザー*&#x200B;の[役割と権限の指定](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)を参照してください。 [!DNL Target Premium]ユーザーの詳細については、[エンタープライズ権限の設定](/help/administrating-target/c-user-management/property-channel/properties-overview.md)を参照してください。

* ワークスペース/製品プロファイルレベルの管理者ロール

   ワークスペースは[!DNL Target Premium]のお客様のみ利用できます。 詳しくは、[エンタープライズ権限の設定](/help/administrating-target/c-user-management/property-channel/properties-overview.md)を参照してください。

* [!DNL Adobe Target]製品レベルの管理権限（Sysadmin権限）

認証トークンを取得するには、次の手順に従います。

1. **[!UICONTROL 管理]**/**[!UICONTROL 実装]**&#x200B;をクリックします。
1. 「Debugger Tools」セクションで、「**[!UICONTROL Generate New Authentication Token]**」をクリックします。

   ![新しい認証トークンの生成](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. 生成されたトークンをパラメーターとして URL に追加して、高度なデバッグツールの 1 つを有効にします。

   ![認証トークン](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTraceを使用すると、[!DNL Target]応答に添付されたトレース情報を受信できます。 トレース情報は、[!DNL Target]呼び出しの結果（コンバージョンやインプレッションなど）と、キャンペーンで選択された分岐のセットなど、この特定の結果が発生した理由を判断するのに役立つ追加データを反映します。 この情報を使用してコンテンツ配信をデバッグします。

次のパラメーターを使用できます。

| mboxTrace のオプション | 結果 |
|--- |--- |
| `?mboxTrace=console` | コンソールログにオブジェクトとして出力します。<br>at.js の場合は、mbox.js のように新しいブラウザーウィンドウをポップアップしたりコンソールに出力したりする代わりに、ネットワークリクエストを調べて、プレビュー（Chrome）または応答（Firefox）を確認する必要があります。 |
| `?mboxTrace=json` | コンソールログにリテラル JSON 文字列として出力します。 |
| `?mboxTrace=window` | ポップアップウィンドウに JSON 文字列として出力します。 |
| `?mboxTrace=disable` | セッションモードのトレースをオフにします。 |

**mboxTrace呼び出しの例**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

出力に、コンテンツに関するきわめて詳しい情報が表示されます。mboxTrace は、キャンペーンまたはアクティビティとプロファイルの詳細を表示します。また、実行前のプロファイルのスナップショットと、実行後の変化を示すスナップショットも提供します。さらに、各場所で評価されたキャンペーンやアクティビティも表示します。

情報によっては、一致するセグメント、一致しないセグメントおよびターゲット ID が含まれる場合もあります。

* **SegmentId**：セグメントの ID。再利用可能なセグメントライブラリか、特定のキャンペーン用に作成された匿名セグメントのいずれかのものです。
* **TargetId**：ターゲットの ID。ターゲットエクスプレッションライブラリか、キャンペーンの任意のセグメント用の匿名ターゲットのものです。
* **Unmatched**：リクエストは、この呼び出しで、セグメントまたはターゲットに適していませんでした。
* **Matched**：リクエストは、指定されたセグメントまたはターゲットに適していました。

**レコメンデーションページでのmboxTraceの使用**:ページにmboxTraceをクエリパラメーターとしてレコメンデーションと共に追加すると、ページ上のRecommendationsデザインがmboxTrace詳細ウィンドウに置き換えられます。このウィンドウには、レコメンデーションに関する次のような詳細情報が表示されます。

* 返されたレコメンデーションと要求されたレコメンデーション
* 使用されたキーと、それがレコメンデーションを生成するかどうか
* 条件によって生成されたレコメンデーションとバックアップレコメンデーション
* 条件の設定
* 適用される除外とインクルージョン
* 収集ルール

クエリパラメーターには、`=console`、`=json`、または `=window` を含める必要はありません。mboxTrace の詳細が完了したら、`=disable` を追加して、**[!UICONTROL Enter]** キーを押すと、通常の表示モードに戻ります。

サイトの通常の機能や外見は、mboxTrace の影響を受けません。訪問者には、通常のレコメンデーションのデザインが表示されます。

## mboxDebug {#mboxdebug}

mboxDebug を使用するには、URL の末尾に mboxDebug パラメーターを追加します。次の表に、[!DNL Target]応答関連のURLパラメーターに関する情報を示します。

>[!NOTE]
>
>mboxDebug パラメーターによっては、使用するのに認証を必要とするものと、認証を必要としないものがあります。

| URL パラメーター | 目的 |
|--- |--- |
| `mboxDebug=1` | デバッガー<br>ターゲットリクエストが定義された任意のURLにこのパラメーターを追加すると、ポップアップウィンドウが開き、貴重なデバッグの詳細が表示されます。 Cookie 情報、PCID およびセッション ID の値が記述され、 URL がすべて表示されます。ターゲットリクエストURLをクリックすると、その[!DNL Target]リクエストの応答が表示されます。 詳しくは、[mbox_debug.pdf](/help/assets/mbox_debug.pdf) を参照してください。 |
| `mboxDebug=x-cookie` | cookie の変更 |
| `mboxDisable=1` | ページ上の mbox を無効化 |
| `mboxDebug=x-profile` | プロファイルセットを表示 |
| `mboxDebug=x-time` | 各[!DNL Target]リクエストの応答時間を表示 |
| `mboxOverride.browserIp=<Insert IP address>` | Geotargeting のテスト<br>Geotargeting をこの URL パラメーターでテストします。この属性の値に IP アドレスを入力すると、Test&amp;Target のジオターゲティングがこの IP アドレスを評価し、キャンペーン内のジオターゲティングまたはセグメント化セットに一致させます。 |

>[!NOTE]
>
>URLフラグメントがクエリ文字列パラメーターの後にあることを確認します。 最初の`#`の後はすべてフラグメント識別子で、デバッグパラメーターが正しく機能しません。

## Adobe Experience Cloud デバッガー {#section_A2798ED3A431409690A4BE08A1BFCF17}

Adobe Experience Cloud デバッガーを使用すると、Target の実装をすばやく簡単に理解できます。ライブラリ設定をすばやく表示し、リクエストを検証してカスタムパラメーターが正しく渡されたことを確認し、コンソールのログを有効にして、Target のすべてのリクエストを無効にすることができます。Experience Cloudを認証し、強力なMboxTraceツールを使用して、アクティビティとオーディエンスの資格、および訪問者プロファイルを調査できます。

詳しくは、以下のトレーニングビデオを参照してください。

詳しくは、[Adobe Experience Cloudデバッガーを使用したat.jsのデバッグ](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md)を参照してください。

## 配信中に target.js を読み込めなかった場合 {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

配信中に target.js の読み込みに失敗した場合は、mbox.js から訪問者に対して「em-disabled」という cookie が送信されます。この cookie は、Visual Experience Composer を使用して作成されたオファーがサイトに表示されないようにします。この cookie が設定された訪問者には、テストコンテンツが表示されず、それらのアクティビティレポートでもカウントされません。その他すべてのオファーコンテンツ（例えば Target Classic のキャンペーンのコンテンツ）は引き続き読み込まれます。この cookie の有効期間は、読み込み失敗時から 30 分です。

## レコメンデーションにトップセラーが表示されない {#section_3920C857270A406C80BE6CBAC8221ECD}

*`SiteCatalyst: purchase`*&#x200B;呼び出しは、購入アルゴリズムのトラフィックデータには使用できません。 代わりに&#x200B;*`orderConfirmPage`*&#x200B;呼び出しを使用します。

## アクティビティの優先度を確認{#section_3D0DD07240F0465BAF655D0804100AED}

[!DNL Target Standard/Premium]で作成されたフォームベースのアクティビティは、[!DNL Target Classic] UIで作成されたアクティビティと競合し、同じ[!DNL Target]リクエストを使用します。

## Internet Explorer 8 でカスタムコードが期待どおりの結果を返さない{#section_FAC3651F19144D12A37A3E4F14C06945}

Target は、IE 8 をサポートしていません。

## グローバル[!DNL Target]リクエストによって配信されるJavaScriptコンテンツが、mbox.jsの使用時に読み込まれません。{#section_03EC9B9C410B4F52A7FCD81840311709}

[!DNL mbox.js] のバージョンを 58 以降にアップグレードしてください。

mbox.jsバージョン58以降では、HTML `BODY`タグの直後に、グローバル[!DNL Target]リクエストの非JavaScriptコンテンツを実行します。 グローバル[!DNL Target]リクエストの`<script>`タグ内のJavaScriptコンテンツは、`DOMContentLoaded`イベントの起動後に実行されます。 このコンテンツ配信の順序によって、グローバル[!DNL Target]リクエストのJavaScriptコンテンツが適切に配信およびレンダリングされます。

## ターゲットCookieが{#section_77AFEB541C0B495EB67E29A4475DF960}設定されていません

サイトにサブドメイン（[!DNL us.domain.com] など）がある場合で Target の cookie を（[!DNL domain.com] ではなく）[!DNL us.domain.com] に設定する必要がある場合、`cookieDomain` 設定を上書きする必要があります。詳しくは、「[targetGlobalSettings（）](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)」を参照してください。。

## 要素が AEM パーソナライゼーションにも含まれていると、Target のコンテンツがちらつく、または表示されない{#section_9E1DABEB75AB431FB9F09887E6DD07D3}

DOM 要素が Adobe Experience Manager（AEM）パーソナライゼーションのターゲット設定と Target アクティビティの両方に含まれていると、Target コンテンツがちらついたり表示されなかったりする場合があります。

これを修正するには、Target が実行されているページで AEM パーソナライゼーションを無効にします。

## URL が無効なのでリダイレクトおよびリモートオファーを配信できない  {#section_7D09043B687F43B39DAEDF17D00375AC}

リダイレクトまたはリモートオファーで無効な URL が使用されていると、配信できない可能性があります。

リダイレクトオファーの場合、[!DNL Target]応答には`/* invalid redirect offer URL */`を含めることができます

または

リモートオファーの場合、[!DNL Target]応答には`/* invalid remote offer URL */`を含めることができます

ブラウザーで[!DNL Target]応答を確認するか、mboxTraceを使用します。 有効な URL について詳しくは、[https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) を参照してください。

## サイトでターゲット要求が実行されていない。

at.jsは、無効なdoctypeを使用している場合、ターゲットリクエストを実行しません。 a.js には HTML5 の doctype が必要です。

## トレーニングビデオ

以下のビデオは、この記事で説明する概念についてさらに詳しく説明しています。

### 拡張機能の追加  ![チュートリアルバッジ](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### 基本的なターゲットのデバッグ![チュートリアルバッジ](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### mboxトレース![チュートリアルバッジ](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)