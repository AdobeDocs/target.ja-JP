---
keywords: site pages;target site pages;targeting;current page;target current page;previous page;target previous page;landing page;target landing page;http header
description: サイトの特定のページにいるターゲット訪問者を訪問できます。
title: Adobe Targetのサイトページ
feature: null
topic: Standard
uuid: 1cf9fa94-dbec-4719-9a0a-79c1eb91a233
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 44%

---


# サイトのページ{#site-pages}

サイトの特定のページにいるターゲット訪問者を訪問できます。

1. [!DNL Target] インターフェイスで、**[!UICONTROL オーディエンス]**／**[!UICONTROL オーディエンスを作成]**&#x200B;をクリックします。
1. オーディエンスに名前を付けます。
1. **[!UICONTROL ルールを追加]**／**[!UICONTROL サイトページ]**&#x200B;をクリックします。

   ![サイトページオーディエンス](assets/target_site_pages.png)

1. 「 **[!UICONTROL 選択]** 」ドロップダウンリストをクリックし、次のオプションのいずれかを選択して、必要に応じてルールを設定します。

   ルール内の後続のドロップダウンリストで使用できるオプションと評価演算子は、選択したオプションによって異なります。 次の図に、「 [!UICONTROL 現在のページ」を選択した場合に使用できるオプションを示します]。

   ![現在のページ](/help/c-target/c-audiences/c-target-rules/assets/current-page.png)

   「 [!UICONTROL 選択」を選択した場合は、初期ドロップダウンリストで次のオプションを使用でき]ます。

   * **現在のページ：** ユーザーが現在閲覧しているページ。

      このオプションを選択した場合は、2番目のドロップダウンリストで次のオプションを使用できます。

      * URL(ターゲットがURLを評価する方法について詳しくは、 [ターゲットとオーディエンスに関するFAQ](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md))
      * ドメイン
      * クエリ
      * サブドメイン
      * トップレベルドメイン
      * パス
      * ハッシュ（#）フラグメント
   * **前のページ：**&#x200B;クリックして現在のページに移動する前に閲覧していたページ（ユーザーが前のページからクリックして現在のページを開いた場合は、前のページが追跡されますが、ブラウザーで新しく URL を入力した場合は、前のページは追跡されません）。このページの実際のコンテンツはサイトのデザインによって異なります。例えば、現在のページに特定の商品に関する情報が表示されている場合、その直前のページは、訪問者が特定のアイテムを選択するカテゴリページ（あるタイプのカメラが数種類掲載されたページなど）になっているか、最終ページへ案内するホームページになっていることがあります。

      このオプションを選択した場合は、2番目のドロップダウンリストで次のオプションを使用できます。

      * URL(ターゲットがURLを評価する方法について詳しくは、 [ターゲットとオーディエンスに関するFAQ](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md))
      * ドメイン
      * クエリ
      * サブドメイン
      * トップレベルドメイン
      * パス
   * **ランディングページ：**&#x200B;ランディングページは、サイトにアクセスする訪問者が最初に目にするページです。例えば、訪問者が Google 上のリンクをクリックしてカテゴリページが開いた場合は、そのカテゴリページがランディングページになります。リンクからホームページが表示された場合は、そのホームページがランディングページになります。ランディングページは訪問者のセッション中記憶されます。このセッションで訪問者のランディングページが何であったのかを基に、サイトをより掘り下げてターゲットを定めることができます。

      このオプションを選択した場合は、2番目のドロップダウンリストで次のオプションを使用できます。

      * URL(ターゲットがURLを評価する方法について詳しくは、 [ターゲットとオーディエンスに関するFAQ](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md))
      * ドメイン
      * クエリ
      * サブドメイン
      * トップレベルドメイン
      * パス
      * ハッシュ（#）フラグメント

      >[!NOTE]
      >
      >`landing.url` サブドメインの変更またはダイレクトURLの置換時にオブジェクトがリセットされます。

   * **HTTPヘッダー：** このオプションは、ターゲット要求のHTTPヘッダー内の情報を評価します。 例えば、HTTPヘッダーに言語情報が含まれる場合、スペイン語でページにアクセスするターゲット訪問者に対する `Accept-Language: es` 条件を含むルールを作成できます。

      このオプションを選択した場合は、2番目のドロップダウンリストで次のオプションを使用できます。

      * Accept
      * Accept-Charset
      * Accept-Encoding
      * Accept-Language
      * 承認
      * Cache-Control
      * 接続
      * Content-Length
      * Content-MDS
      * Content-Type
      * 日付
      * 期待する
      * 送信元
      * ホスト
      * 一致する場合
      * If-Modified-Since
      * If-None-Match
      * if-Range
      * If-Unmodified-Since
      * 最大転送数
      * Pragma
      * Proxy-Authorization
      * Range
      * 参照元
      * TE
      * アップグレード
      * User-Agent
      * 経由
      * 警告

   「現在のページ [!UICONTROL 」、「]前のページ [!UICONTROL 」]、または「ランディングページ [!UICONTROL 」を選択した場合は、「ドメインクエリ]」および「ドメインドメイン」オプションが使用  可能です。 これらのオプションを選択する際は、次の点を考慮してください。

   * **ドメイン：**&#x200B;ページの完全ドメイン。ドメインを指定する際には、ベストプラクティスとして、「次を含む」を使用することが推奨されます。例えば、「ドメインがfacebook.comに等しい」は受け入れ `m.facebook.com` られ `www.facebook.com` ません。「facebook.com を含むドメイン」では、facebook.com のあらゆるバリエーションが含まれます。
   * **クエリ：**&#x200B;最初の疑問符（?）後の URL のコンテンツ。

      `foo.html?e0a72cb2a2c7`





1. （オプション）「**[!UICONTROL ルールを追加]**」をクリックして、オーディエンス用の追加のルールを設定します。
1. 「**[!UICONTROL 保存]**」をクリックします。

独自の「ユーザー定義のクエリパラメーター」または「ユーザー定義のヘッダー」を使用して、サイトページのオーディエンスを作成することもできます。

それぞれの使い分けは次のとおりです。

* ユーザーが選択したルールが現在のページ、ランディングページ、前のページの場合はクエリパラメーターを使用します。
* ユーザーが選択したルールがHTTPヘッダーの場合は、ヘッダー。

次の図を参照してください。

![](assets/site_pages.png)

## トラブルシューティング {#ts}

* ランディングページオーディエンスが正しく機能するためには、at.js JavaScriptライブラリが `mboxReferrer` 属性を使用してページから取得するパラメーターセット(配信APIの `context.address.referringUrl``document.referrer` パラメーター)がリクエストに含まれている必要があります。 この `HTMLDocument` 属性は、ユーザーがナビゲーションしたページのURIを返します。 この属性の値は、ユーザーがページに直接移動したとき（リンクを介さずに、ブックマークを介して移動した場合など）に空の文字列になります。

   この動作が要件を満たさない場合は、次のいずれかの操作を行うことを検討してください。

   * ターゲット設定の目的で使用する [mboxパラメーター](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md)[!DNL Target] を渡します。
   * ランディングページアクティビティの [代わりに](/help/c-activities/t-test-ab/test-ab.md) 、A/Bテストアクティビティを使用します。 A/Bテストアクティビティは、同じ訪問者のエクスペリエンスを切り替えません。
   * 代わりに、 [訪問者プロファイルを使用します](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) 。

* コンマを含む文字列で「開始/次で終わる」評価演算子を使用する場合、これらの評価は値の配列として行われ、コンマで区切られた各値が評価されることに注意してください。 例えば、ヘッダーの値がある場合： `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` 次のような条件を満たします。
   * zhの開始、
   * enの開始
   * 0.7で終わる
   * 0.8で終わります。

## トレーニングビデオ：オーディエンスの作成

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
