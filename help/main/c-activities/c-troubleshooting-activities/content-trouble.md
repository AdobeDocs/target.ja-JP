---
keywords: mboxのデバッグ;mboxのトラブルシューティング;mboxの問題;ちらつき;mboxDebug;mboxTrace;トークン;デバッガー;優先度;アクティビティ優先度;Adobe Experience Cloudデバッガー;orderConfirmPage mbox;SiteCatalystの購入mbox;トップセラー;トップセラー
description: ページに期待した内容が表示されない場合は、問題の修正に役立つ提案を見つけます。 Adobe Target でコンテンツ配信をデバッグする方法について説明します。
title: コンテンツ配信のトラブルシューティング方法を教えてください。
feature: Activities
exl-id: 887b7956-1d61-439a-8339-c150deb9a378
TQID: 'https://experienceleague.adobe.com/nkaoqcuoqMm67AnEjSg6dCnFDy-jvlwvD1a6YeXTkwk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 22dff18ca8369805557788d62c4eaf09f9764494
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 55%
---
# コンテンツ配信のトラブルシューティング {#content-trouble}

>[!BEGINSHADEBOX]

**このページで：** ページに期待されるコンテンツが表示されない場合に[!DNL Adobe Target]でコンテンツ配信をデバッグする方法を説明します。

>[!ENDSHADEBOX]

ページに予想されるコンテンツが表示されない場合、原因は、アクティビティコードのエラー、見つからないか配置されていない[!DNL Target] リクエスト、または別のアクティビティとの競合である可能性があります。 タイプミスやその他のエラーにより、予想されるコンテンツが表示されない可能性があるため、アクティビティやキャンペーンコードを注意深く確認してください。 次に、mboxTrace、mboxDebug、またはAdobe Experience Cloud Debuggerを使用して、[!DNL Target] リクエストを調べます。

**mboxDebug**&#x200B;は、ページに[!DNL Target]を設定する際に特に便利です。[!DNL Target] リクエストが実行され、Cookieが設定されていることを確認します。 ただし、コンテンツ配信をデバッグする際に役立つ詳細には入りません。 ページにアクティビティが表示されない場合や、意図していないコンテンツが表示される場合は、mboxTrace を使用してページの調査とデバッグを詳細におこないます。

## デバッグツール {#debugging-tools}

### 認証トークンの取得 {#section_BED130298E794D1FA229DB7C3358BA54}

mboxTraceとmboxDebugは、キャンペーンデータとプロファイルデータを外部の関係者に公開できるため、認証トークンが必要です。 認証トークンは、[!DNL Target] UI で取得できます。 トークンは 6 時間有効です。

認証トークンを生成するには、次のいずれかのユーザー権限が必要です。

* 少なくとも&#x200B;**[!UICONTROL 編集者]**&#x200B;の権限（または&#x200B;**[!UICONTROL 承認者]**）

  [!DNL Target Standard]ユーザーの詳細については、*ユーザー*&#x200B;の[役割と権限の指定](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)を参照してください。 [!DNL Target Premium]ユーザーの詳細については、[エンタープライズ権限の設定](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)を参照してください。

* ワークスペース／製品プロファイルレベルでの管理者の役割

  Workspaces は[!DNL Target Premium]のお客様のみが利用できます。 詳しくは、 [エンタープライズの権限の設定](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)を参照してください。

* [!DNL Adobe Target]製品レベルの管理者権限（Sysadmin 権限）

認証トークンを取得するには、次の手順に従います。

1. **[!UICONTROL 管理]** > **[!UICONTROL 実装]**&#x200B;にアクセスします。
1. 「デバッガーツール」セクションで、「**[!UICONTROL 新しい認証トークンを生成]**」をクリックします。

   ![新しい認証トークンの生成](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. 生成されたトークンをパラメーターとして URL に追加して、高度なデバッグツールの 1 つを有効にします。

   ![認証トークン](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

### mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace を使用すると、[!DNL Target] 応答に付属する追跡情報を受信できます。 トレース情報は、[!DNL Target] 呼び出し（コンバージョンやインプレッションなど）の結果と、この特定の結果の発生理由を判断するのに役立つことがある追加データ（キャンペーンで選択肢となった使用可能な分岐のセットなど）を反映します。 この情報を使用してコンテンツ配信をデバッグします。

次のパラメーターを使用できます。

| mboxTrace のオプション | 結果 |
|--- |--- |
| `?mboxTrace=console` | コンソールログにオブジェクトとして出力します。<br>at.js の場合、mbox.js（現在は非推奨）のように新しいブラウザーウィンドウを開いたりコンソールに出力したりする代わりに、ネットワークリクエストを調べて、「プレビュー」（Chrome）または「レスポンス」（Firefox）を確認する必要があります。 |
| `?mboxTrace=json` | コンソールログにリテラル JSON 文字列として出力します。 |
| `?mboxTrace=window` | ポップアップウィンドウに JSON 文字列として出力します。 |
| `?mboxTrace=disable` | セッションモードのトレースをオフにします。 |

**mboxTrace 呼び出しの例**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

出力には、コンテンツに関する詳細情報が表示されます。 mboxTraceは、キャンペーンまたはアクティビティとプロファイルに関する詳細を表示します。 また、実行前のプロファイルのスナップショットと、実行後に変更された内容のスナップショットも提供されます。 さらに、各場所で評価されたキャンペーンやアクティビティも表示します。

情報によっては、一致するセグメント、一致しないセグメントおよびターゲット ID が含まれる場合もあります。

* **SegmentId**：セグメントの ID。再利用可能なセグメントライブラリか、特定のキャンペーン用に作成された匿名セグメントのいずれかのものです。
* **TargetId**：ターゲットの ID。ターゲットエクスプレッションライブラリか、キャンペーンの任意のセグメント用の匿名ターゲットのものです。
* **Unmatched**：リクエストは、この呼び出しで、セグメントまたはターゲットに適していませんでした。
* **Matched**：リクエストは、指定されたセグメントまたはターゲットに適していました。

**レコメンデーションページでの mboxTrace の使用**：レコメンデーションを使用したページに mboxTrace をクエリーパラメーターとして追加すると、ページ上の Recommendation のデザインが、mboxTrace の詳細ウィンドウに置き換わり、以下を含むレコメンデーションに関する詳細が表示されます。

* 返されたレコメンデーションと要求されたレコメンデーション
* 使用されたキーと、それがレコメンデーションを生成するかどうか
* 条件によって生成されたレコメンデーションとバックアップレコメンデーション
* 条件の設定
* 適用される除外とインクルージョン
* 収集ルール

クエリパラメーターに`=console`、`=json`または`=window`を含める必要はありません。 mboxTraceの詳細が完了したら、`=disable`を追加し、**[!UICONTROL Enter]**&#x200B;を押して、通常の表示モードに戻ります。

サイトの通常の機能や外見は、mboxTrace の影響を受けません。 訪問者には、通常のレコメンデーションデザインが表示されます。

### mboxDebug {#mboxdebug}

mboxDebug を使用するには、URL の末尾に mboxDebug パラメーターを追加します。 [!DNL Target] 応答に関連する URL パラメーターについての情報を次の表に示します。

一部のmboxDebug パラメーターは、認証の有無に関わらず使用できます。

| URL パラメーター | 目的 |
|--- |--- |
| `mboxDebug=1` | デバッガー<br>Target リクエストが定義された任意の URL にこのパラメーターを追加すると、ポップアップウィンドウが開き、有用なデバッグ詳細情報が表示されます。 Cookie 情報、PCID およびセッション ID の値が記述され、 URL がすべて表示されます。 Targe リクエストの URL をクリックすると、その [!DNL Target] リクエストに対する応答を表示できます。 詳しくは、[mbox_debug.pdf](/help/main/assets/mbox_debug.pdf) を参照してください。 |
| `mboxDisable=1` | ページ上の mbox を無効化 |
| `mboxOverride.browserIp=<Insert IP address>` | 地域ターゲティングのテスト<br>地域ターゲティングをこの URL パラメーターでテストします。 この属性の値としてIP アドレスを入力すると、[!DNL Target] ジオターゲティングはそのIP アドレスをキャンペーンで設定されているジオターゲティングまたはセグメント化と一致するように評価します。 |

>[!NOTE]
>
>URLフラグメントがクエリ文字列パラメーターの後にあることを確認します。 最初の `#` の後はすべてフラグメント識別子となり、デバッグパラメーターが正しく機能しません。

### Adobe Experience Cloud デバッガー {#section_A2798ED3A431409690A4BE08A1BFCF17}

Adobe Experience Cloud Debuggerは、[!DNL Target]の実装を理解するのに役立ちます。 ライブラリ設定を表示し、カスタムパラメーターが正しく渡されていることを確認し、コンソールのログ記録をオンにして、すべての[!DNL Target]要求を無効にすることができます。 Experience Cloudに認証した後は、mboxTraceを使用して、アクティビティとオーディエンスの条件だけでなく、訪問者プロファイルを調べることができます。

詳しくは、このページの最後にある[&#x200B; トレーニングビデオ &#x200B;](#training-videos)および[Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/target-debugging-atjs.html){target=_blank}を使用したat.jsのデバッグを参照してください。

## 一般的な問題 {#common-problems}

+++ レコメンデーションにトップセラーが表示されない

*`SiteCatalyst: purchase`*&#x200B;呼び出しは、購入アルゴリズムのトラフィックデータに使用できません。 代わりに、*`orderConfirmPage`* 呼び出しを使用します。

+++

</br>

+++ フォームベースのアクティビティとTarget Classic アクティビティの競合

[!DNL Target Standard/Premium] で作成されたフォームベースのアクティビティは、優先度が同じで、同じ [!DNL Target] リクエスト使用している [!DNL Target Classic] UI で作成されたアクティビティと競合する場合があります。 詳しくは、[&#x200B; アクティビティの優先度](/help/main/c-activities/priority.md)を参照してください。

+++

</br>

+++ [!DNL Target] Cookieが設定されません

サイトに[!DNL us.domain.com]などのサブドメインがありますが、[!DNL domain.com]に[!DNL Target] Cookieを設定する必要がある場合（[!DNL us.domain.com]ではなく）は、`cookieDomain`設定を上書きする必要があります。 詳しくは、[targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html?lang=ja){target=_blank} を参照してください。

+++

</br>

+++ 要素がAdobe Experience Manager パーソナライゼーションの一部でもある場合、コンテンツのちらつきが表示されるか、表示されません

DOM要素がAdobe Experience Manager（AEM）のパーソナライゼーションターゲティングおよび[!DNL Target] アクティビティの一部である場合、[!DNL Target]のコンテンツが表示されないことがあります。

この問題を解決するには、[!DNL Target]が実行中のページでAEM パーソナライゼーションを無効にすることができます。

+++

</br>

+++ 無効なURLが原因で、リダイレクトとリモートのオファーを配信できない

リダイレクトまたはリモートオファーで無効な URL が使用されていると、配信できない可能性があります。

* リダイレクトオファーの場合、[!DNL Target]応答に`/* invalid redirect offer URL */`を含めることができます。
* リモートオファーの場合、[!DNL Target]応答に`/* invalid remote offer URL */`を含めることができます。

ブラウザーまたはmboxTraceを使用して、[!DNL Target]応答を確認できます。 有効な URL について詳しくは、[https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) を参照してください。

+++

</br>

+++ [!DNL Target]件のリクエストが自分のサイトで実行されていません

無効なdoctypeを使用している場合、at.jsは[!DNL Target] リクエストを実行しません。 a.js には HTML5 の doctype が必要です。

+++

## URLにクエリ文字列パラメーターを含むアクティビティ {#query-strings}

**[!UICONTROL アクティビティ URL]**&#x200B;は、アクティビティの訪問者を認定し、アクティビティエクスペリエンスをユーザーにレンダリングするページを決定します。 アクティビティの作成中にプロンプトが表示された場合、特にクエリ文字列パラメーターを含む URL の場合、完全な URL を入力してもコンテンツがそのサイトページに配信されるとは限りません。

デフォルトでは、[!UICONTROL Visual Experience Composer] （VEC）は[Visual Experience Composer設定](/help/main/administrating-target/visual-experience-composer-set-up.md)で指定されたページを開きます。 アクティビティ作成中に、別のページを指定することもできます。

VECが開いた後に別のページを表示するには、**[!UICONTROL ギアアイコン]**&#x200B;を設定/**[!UICONTROL ページ配信]**&#x200B;を選択をクリックし、**[!UICONTROL アクティビティ URL]** フィールドに目的のURLを指定します。

![ページ配信設定 UI の設定](assets/configure-page-delivery.png)

URLにクエリ文字列パラメーターが含まれている場合、ページがアクティビティに適格でない場合や、パーソナライズされたコンテンツが表示されない場合があります。 ターゲットオーディエンスに関係なく、ベース URLに加えてテンプレートルールを含めて、クエリパラメーターを定義できます。

追加のテンプレートルールを含めるには、次のオプションを使用できます。

* **オプション 1:** URLを複製し、「contains」オプションを使用してテンプレートルールに保持します

  +++ テンプレートルール設定の表示

  このオプションを使用すると、その URL がアクティビティに適格であることは保証できますが、ベース URL を含む URL にレコードが追加されることで、レポートデータに影響を与える可能性があるコーナーケースが伴うことに注意が必要です。

  このシナリオでは、URL は `https://shopping.mycart.com?type=Summers%20Offers` であり、追加のテンプレートルールには同じ URL が含まれ（contains）、OR 演算子で区切られます。

  ![テンプレートルールに URL を複製](assets/option1.png)

  +++

* **オプション 2:** URLの「contains」条件をクエリ文字列のみで制限する

  +++ テンプレートルール設定の表示

  前のオプションで説明したコーナーケースはこのオプションでも当てはまりますが、ここでは、条件付き設定はクエリ文字列にのみに限られます。

  このシナリオでは、URL は `https://shopping.mycart.com?type=Summers%20Offers` であり、追加のテンプレートルールにはクエリ文字列のみが含まれ（contains）、OR 演算子で区切られます。

  ![テンプレートルールにクエリ文字列のみを含める](assets/option2.png)

  +++

* **オプション 3:**&#x200B;完全なURLをターゲットにするのではなく、URLの特定の部分を活用します

  +++ テンプレートルール設定の表示

  このシナリオでは、URLは`https://shopping.mycart.com?type=Summers%20Offers`で、追加のテンプレートルールは&#x200B;**[!UICONTROL type]** > **[!UICONTROL is （大文字と小文字が区別されます）]** > type=Summers%20Offersで&#x200B;**[!UICONTROL クエリ]**&#x200B;を指定し、OR演算子で区切ります。

  ![URL の特定の部分を活用するテンプレートルール](assets/option3.png)

  +++

## プロファイル属性値の二重引用符のエスケープ {#escape}

[!DNL Target] プロファイル属性に二重引用符を含む値を送信する場合は、次に示すように、二重引用符をエスケープする必要があります。

```
adobe.target.trackEvent({
    "mbox": "data-collection",
    "params":    {
        "profile.tagLine": "Escape \\\"Double Quotes\\\" like this."
    }
});
```

## トレーニングビデオ {#training-videos}

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### 拡張機能![&#x200B; チュートリアルバッジ &#x200B;](/help/main/assets/tutorial.png)を追加

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### Adobe Target の基本的なデバッグ ![チュートリアルバッジ](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Mbox Trace ![チュートリアルバッジ](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)
