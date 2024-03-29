---
keywords: site pages;target サイトページ；ターゲット設定；現在のページ；target 現在のページ；前のページ；target 前のページ；ランディングページ；target ランディングページ；http ヘッダー
description: 訪問者をターゲットにする方法については、 [!DNL Adobe Target] サイトの特定のページにいるユーザー
title: サイトページに基づいて訪問者をターゲットに設定することはできますか？
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 18%

---

# サイトのページ

訪問者をターゲットに設定するには、 [!DNL Adobe Target] サイトの特定のページにアクセスするユーザー。

1. Adobe Analytics の [!DNL Target] インタフェース、クリック **[!UICONTROL オーディエンス]** > **[!UICONTROL オーディエンスを作成]**.
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. ドラッグ&amp;ドロップ **[!UICONTROL サイトのページ]** を audience builder パネルにドラッグします。

   ![サイトページオーディエンス](assets/target_site_pages.png)

1. 次をクリック： **[!UICONTROL 選択]** 」ドロップダウンリストから、次のいずれかのオプションを選択し、必要に応じてルールを設定します。

   ルール内の後続のドロップダウンリストで使用可能なオプションと評価演算子は、選択したオプションによって異なります。 次の図に、 [!UICONTROL 現在のページ]:

   ![現在のページ](assets/current-page.png)

   最初のドロップダウンリストでは、以下のオプションを選択できます。 [!UICONTROL 選択].

   * **[!UICONTROL 現在のページ]:** ユーザーが表示しているページ。

     このオプションを選択した場合、2 番目のドロップダウンリストでは、次のオプションを使用できます。

      * [!UICONTROL URL] ( 詳しくは、 [!DNL Target] URL を評価する場合は、 [ターゲットとオーディエンスに関する FAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL ドメイン]
      * [!UICONTROL クエリ]
      * [!UICONTROL サブドメイン]
      * [!UICONTROL トップレベルドメイン]
      * [!UICONTROL パス]
      * [!UICONTROL ハッシュ (#) フラグメント]

   * **[!UICONTROL 前のページ]:** クリックして現在のページに移動する前にユーザーが閲覧したページ。 ページを追跡するには、前のページから現在のページまでクリックする必要があります。 ユーザーがブラウザーに新しい URL を入力した場合、前のページは追跡されません。 このページの実際のコンテンツはサイトのデザインによって異なります。例えば、現在のページに特定の製品に関する情報が表示されている場合、前のページは、訪問者が特定の品目を選択するカテゴリページになることがあります。 例えば、特定のタイプの複数のカメラを表示しているページや、最後のページに移動するホームページなどがあります。

     このオプションを選択した場合、2 番目のドロップダウンリストでは、次のオプションを使用できます。

      * [!UICONTROL URL] (Target での URL の評価方法について詳しくは、 [ターゲットとオーディエンスに関する FAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL ドメイン]
      * [!UICONTROL クエリ]
      * [!UICONTROL サブドメイン]
      * [!UICONTROL トップレベルドメイン]
      * [!UICONTROL パス]

   * **[!UICONTROL ランディングページ]:** ランディングページは、サイトにアクセスする訪問者が最初に目にするページです。 例えば、訪問者が Google 上のリンクをクリックしてカテゴリページが開いた場合は、そのカテゴリページがランディングページになります。リンクからホームページが表示された場合は、そのホームページがランディングページになります。ランディングページは訪問者のセッション中記憶されます。このセッションで訪問者のランディングページが何であったのかを基に、サイトをより掘り下げてターゲットを定めることができます。

     このオプションを選択した場合、2 番目のドロップダウンリストでは、次のオプションを使用できます。

      * [!UICONTROL URL] (Target での URL の評価方法について詳しくは、 [ターゲットとオーディエンスに関する FAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL ドメイン]
      * [!UICONTROL クエリ]
      * [!UICONTROL サブドメイン]
      * [!UICONTROL トップレベルドメイン]
      * [!UICONTROL パス]
      * [!UICONTROL ハッシュ (#) フラグメント]

     >[!NOTE]
     >
     >`landing.url` サブドメインの変更またはダイレクトURLの置換時にオブジェクトがリセットされます。

   * **[!UICONTROL HTTP ヘッダー]:** このオプションは、 [!DNL Target] リクエスト。 例えば、HTTP ヘッダーに言語情報が含まれている場合、 `Accept-Language: es` 条件を使用して、スペイン語でページにアクセスする訪問者をターゲットに設定します。

     このオプションを選択した場合、2 番目のドロップダウンリストでは、次のオプションを使用できます。

      * [!UICONTROL 確定]
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
      * [!UICONTROL Host]
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
      * [!UICONTROL 警告]

   次を選択した場合： [!UICONTROL 現在のページ], [!UICONTROL 前のページ]または [!UICONTROL ランディングページ]、 [!UICONTROL ドメイン] および [!UICONTROL クエリ] オプションを使用できます。 これらのオプションを選択する際は、次の点を考慮してください。

   * **ドメイン：**&#x200B;ページの完全ドメイン。ドメインを指定する際には、ベストプラクティスとして、「次を含む」を使用することが推奨されます。例えば、「ドメインがfacebook.com に等しい」は受け入れられません。 `m.facebook.com` または `www.facebook.com`. 「facebook.com を含むドメイン」は、facebook.comの任意のバリアントを受け入れます。
   * **クエリ：** 最初の疑問符 (?) 後の URL のコンテンツ。

     `foo.html?e0a72cb2a2c7`

1. （オプション）オーディエンス用の追加のルールを設定します。
1. 「**[!UICONTROL Done]**」をクリックします。

独自の「ユーザー定義のクエリパラメーター」または「ユーザー定義のヘッダー」を使用して、サイトページのオーディエンスを作成することもできます。

それぞれの使い分けは次のとおりです。

* ユーザーが選択したルールが次の場合のクエリパラメーター [!UICONTROL 現在のページ], [!UICONTROL ランディングページ]または [!UICONTROL 前のページ]
* ユーザーが選択したルールが HTTP ヘッダーの場合のヘッダー

## トラブルシューティング {#ts}

* ランディングページのオーディエンスが正しく機能するには、リクエストに `mboxReferrer` パラメーターセット (Delivery API の場合は `context.address.referringUrl` パラメーター ) を使用して、at.js JavaScript ライブラリが `document.referrer` 属性。 この `HTMLDocument` 属性は、ユーザーが移動したページの URI を返します。 この属性の値は、ユーザーがリンクを通じて（たとえば、ブックマークを通じて）ページに直接移動したときの空の文字列になります。

  この動作が要件を満たさない場合は、次のいずれかの操作を実行することを検討してください。

   * 合格 [mbox パラメーター](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html){target=_blank} から [!DNL Target] を使用して、ターゲティングの目的で使用します。
   * を使用します。 [A/B テストアクティビティ](/help/main/c-activities/t-test-ab/test-ab.md) ランディングページアクティビティの代わりに使用します。 A/B テストアクティビティは、同じ訪問者のエクスペリエンスを切り替えません。
   * の使用 [訪問者プロファイル](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) 代わりに、

* コンマを含む文字列に対して「次の語句で始まる/次の語句で終わる」エバリュエーターを使用する場合、これらの文字列は値の配列として評価され、コンマで区切られた各値が評価されます。 ヘッダーの値がある場合の例を次に示します。 `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` 次のような条件に該当します。
   * zh で始まる
   * en から始まる
   * 0.7 で終わる
   * は 0.8 で終わります。

## トレーニングビデオ: オーディエンスの作成

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
