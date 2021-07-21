---
keywords: サイトページ；targetサイトページ；ターゲット設定；現在のページ；target現在のページ；前のページ；target前のページ；ランディングページ；targetランディングページ；httpヘッダー
description: サイト上の特定のページにいるユーザー [!DNL Adobe Target] を使用して訪問者をターゲットにする方法を説明します。
title: サイトページに基づいて訪問者をターゲットに設定できますか。
feature: オーディエンス
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 25%

---

# サイトのページ

[!DNL Adobe Target]を使用して、サイトの特定のページにアクセスする訪問者をターゲットに設定できます。

1. [!DNL Target] インターフェイスで、**[!UICONTROL オーディエンス]**／**[!UICONTROL オーディエンスを作成]**&#x200B;をクリックします。
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. **[!UICONTROL サイトページ]**&#x200B;をAudience Builderウィンドウにドラッグ&amp;ドロップします。

   ![サイトページオーディエンス](assets/target_site_pages.png)

1. **[!UICONTROL 選択]**&#x200B;ドロップダウンリストをクリックし、次のいずれかのオプションを選択して、必要に応じてルールを設定します。

   ルール内の後続のドロップダウンリストで使用可能なオプションと評価演算子は、選択したオプションによって異なります。 次の図に、「[!UICONTROL 現在のページ]」を選択した場合に使用可能なオプションを示します。

   ![現在のページ](assets/current-page.png)

   「[!UICONTROL 選択]」を選択すると、最初のドロップダウンリストで次のオプションを使用できます。

   * **[!UICONTROL 現在のページ]:** ユーザーが表示しているページ。

      このオプションを選択した場合、2番目のドロップダウンリストでは次のオプションを使用できます。

      * [!UICONTROL URL] (URLの評価方法について詳しく [!DNL Target] は、ターゲットとオーディエ [ンスに関するFAQ](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)を参照してください)。
      * [!UICONTROL ドメイン]
      * [!UICONTROL クエリ]
      * [!UICONTROL サブドメイン]
      * [!UICONTROL トップレベルドメイン]
      * [!UICONTROL パス]
      * [!UICONTROL ハッシュ（#）フラグメント]
   * **[!UICONTROL 前のページ]:** クリックして現在のページに移動する前に表示されたページ。ページを追跡するには、前のページから現在のページまでをクリックする必要があります。 ユーザーがブラウザーに新しいURLを入力した場合、前のページは追跡されません。 このページの実際のコンテンツはサイトのデザインによって異なります。例えば、現在のページに特定の製品に関する情報が表示されている場合、前のページは、訪問者が特定の品目を選択するカテゴリページになる可能性があります。 例えば、特定のタイプの複数のカメラを表示するページや、最終ページに導くホームページなどがあります。

      このオプションを選択した場合、2番目のドロップダウンリストでは次のオプションを使用できます。

      * [!UICONTROL URL] (TargetがURLを評価する方法について詳しくは、ターゲットとオーディエ [ンスに関するFAQ](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)を参照してください)
      * [!UICONTROL ドメイン]
      * [!UICONTROL クエリ]
      * [!UICONTROL サブドメイン]
      * [!UICONTROL トップレベルドメイン]
      * [!UICONTROL パス]
   * **ランディングページ：**&#x200B;ランディングページは、サイトにアクセスする訪問者が最初に目にするページです。例えば、訪問者が Google 上のリンクをクリックしてカテゴリページが開いた場合は、そのカテゴリページがランディングページになります。リンクからホームページが表示された場合は、そのホームページがランディングページになります。ランディングページは訪問者のセッション中記憶されます。このセッションで訪問者のランディングページが何であったのかを基に、サイトをより掘り下げてターゲットを定めることができます。

      このオプションを選択した場合、2番目のドロップダウンリストでは次のオプションを使用できます。

      * [!UICONTROL URL] (TargetがURLを評価する方法について詳しくは、ターゲットとオーディエ [ンスに関するFAQ](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)を参照してください)
      * [!UICONTROL ドメイン]
      * [!UICONTROL クエリ]
      * [!UICONTROL サブドメイン]
      * [!UICONTROL トップレベルドメイン]
      * [!UICONTROL パス]
      * [!UICONTROL ハッシュ（#）フラグメント]

      >[!NOTE]
      >
      >`landing.url` サブドメインの変更またはダイレクトURLの置換時にオブジェクトがリセットされます。

   * **[!UICONTROL HTTPヘッダー]:** このオプションは、リクエストのHTTPヘッダーの情報を評価 [!DNL Target] します。例えば、HTTPヘッダーに言語情報が含まれる場合、スペイン語でページにアクセスする訪問者をターゲットにする`Accept-Language: es`条件を含むルールを作成できます。

      このオプションを選択した場合、2番目のドロップダウンリストでは次のオプションを使用できます。

      * [!UICONTROL Accept]
      * [!UICONTROL Accept-Charset]
      * [!UICONTROL Accept-Encoding]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL Authorization]
      * [!UICONTROL Cache-Control]
      * [!UICONTROL 接続]
      * [!UICONTROL Content-Length]
      * [!UICONTROL Content-MDS]
      * [!UICONTROL Content-Type]
      * [!UICONTROL Date]
      * [!UICONTROL Expect]
      * [!UICONTROL 送信元]
      * [!UICONTROL ホスト]
      * [!UICONTROL If-Match]
      * [!UICONTROL If-Modified-Since]
      * [!UICONTROL If-None-Match]
      * [!UICONTROL If-Range]
      * [!UICONTROL If-Unmodified-Since]
      * [!UICONTROL Max-Forwards]
      * [!UICONTROL Pragma]
      * [!UICONTROL Proxy-Authorization]
      * [!UICONTROL Range]
      * [!UICONTROL リファラー]
      * [!UICONTROL TE]
      * [!UICONTROL アップグレード]
      * [!UICONTROL User-Agent]
      * [!UICONTROL 経由]
      * [!UICONTROL Warning]

   「[!UICONTROL 現在のページ]」、「[!UICONTROL 前のページ]」、または「[!UICONTROL ランディングページ]」を選択した場合は、「[!UICONTROL ドメイン]」と「[!UICONTROL クエリ]」オプションを使用できます。 これらのオプションを選択する際は、次の点を考慮してください。

   * **ドメイン：**&#x200B;ページの完全ドメイン。ドメインを指定する際には、ベストプラクティスとして、「次を含む」を使用することが推奨されます。例えば、「facebook.comと等しいドメイン」には、`m.facebook.com`や`www.facebook.com`を指定できません。 「facebook.comを含むドメイン」は、facebook.comの任意のバリアントを受け入れます。
   * **クエリ：**&#x200B;最初の疑問符（?）後の URL のコンテンツ。

      `foo.html?e0a72cb2a2c7`





1. （オプション）オーディエンス用の追加のルールを設定します。
1. 「 **[!UICONTROL 完了]**」をクリックします。

独自の「ユーザー定義のクエリパラメーター」または「ユーザー定義のヘッダー」を使用して、サイトページのオーディエンスを作成することもできます。

それぞれの使い分けは次のとおりです。

* ユーザーが選択したルールが「[!UICONTROL 現在のページ]」、「[!UICONTROL ランディングページ]」、「[!UICONTROL 前のページ]」の場合のクエリパラメーター
* ユーザーが選択したルールがHTTPヘッダーの場合のヘッダー

## トラブルシューティング {#ts}

* ランディングページのオーディエンスが正しく機能するには、`document.referrer`属性を使用してat.js JavaScriptライブラリがページから取得する`mboxReferrer`パラメーターを（Delivery APIの`context.address.referringUrl`パラメーターに）リクエストに設定する必要があります。 この`HTMLDocument`属性は、ユーザーが移動したページのURIを返します。 この属性の値は、ユーザーが（リンクを介さずに）ページに直接移動する場合に空の文字列になります。たとえば、ブックマークを介して移動する場合などです。

   この動作が要件を満たさない場合は、次のいずれかの操作を実行することを検討してください。

   * ターゲット設定に使用する[mboxパラメーター](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md)を[!DNL Target]に渡します。
   * ランディングページアクティビティの代わりに、[A/Bテストアクティビティ](/help/c-activities/t-test-ab/test-ab.md)を使用します。 A/Bテストアクティビティは、同じ訪問者のエクスペリエンスを切り替えません。
   * 代わりに、[訪問者プロファイル](/help/c-target/c-audiences/c-target-rules/visitor-profile.md)を使用します。

* コンマを含む文字列に対して「次の語句で始まる/次の語句で終わる」評価演算子を使用する場合、これらの文字列は値の配列として評価され、値内でコンマで区切られた各値が評価されます。 例えば、ヘッダーの値がある場合：`Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7`次の条件に該当します。
   * zhで始まる。
   * 「en」で始まる
   * は0.7で終わる。
   * は0.8で終わります。

## トレーニングビデオ：オーディエンスの作成

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
