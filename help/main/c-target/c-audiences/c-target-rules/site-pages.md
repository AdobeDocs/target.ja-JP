---
keywords: サイトページ；Target サイトページ；ターゲティング；現在のページ；Target 現在のページ；前のページ；Target 前のページ；ランディングページ；Target ランディングページ；http ヘッダー
description: サイトの特定のページにいる訪問者を  [!DNL Adobe Target]  を使用してターゲットにする方法を説明します。
title: サイトページに基づいて訪問者をターゲットにできますか？
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 19%

---

# サイトのページ

サイトの特定のページにアクセスする [!DNL Adobe Target] ーザーを使用して、訪問者をターゲットに設定できます。

1. [!DNL Target] インターフェイスで、**[!UICONTROL Audiences]**/**[!UICONTROL Create Audience]** をクリックします。
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. **[!UICONTROL Site Pages]** をオーディエンスビルダーペインにドラッグ&amp;ドロップします。

   ![サイトページオーディエンス](assets/target_site_pages.png)

1. 「**[!UICONTROL Select]**」ドロップダウンリストをクリックして、次のいずれかのオプションを選択し、必要に応じてルールを設定します。

   ルール内の後続のドロップダウンリストで使用できるオプションとエバリュエーターは、選択するオプションによって異なります。 次の図は、[!UICONTROL Current Page] を選択した場合に使用可能なオプションを示しています。

   ![ カレント ページ ](assets/current-page.png)

   [!UICONTROL Select] を選択すると、最初のドロップダウンリストで次のオプションを使用できます。

   * **[!UICONTROL Current Page]:** ユーザーが表示しているページ。

     このオプションを選択した場合、2 番目のドロップダウンリストでは次のオプションを使用できます。

      * [!UICONTROL URL] （[!DNL Target] による URL の評価方法について詳しくは、[ ターゲットとオーディエンスに関する FAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md) を参照してください）。
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]
      * [!UICONTROL Hash (#) fragment]

   * **[!UICONTROL Previous Page]:** 現在のページにクリックする前にユーザーが表示したページ。 ページを追跡するには、ユーザーが前のページから現在のページをクリックする必要があります。 ユーザーがブラウザーに新しい URL を入力しても、前のページはトラッキングされません。 このページの実際のコンテンツはサイトのデザインによって異なります。例えば、現在のページに特定の製品に関する情報が表示されている場合、前のページは訪問者が特定の項目を選択するカテゴリページである可能性があります。 例えば、特定のタイプの複数のカメラを表示するページや、最終的なページにつながるホームページなどがあります。

     このオプションを選択した場合、2 番目のドロップダウンリストでは次のオプションを使用できます。

      * [!UICONTROL URL] （Target による URL の評価方法について詳しくは、[ ターゲットとオーディエンスに関する FAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md) を参照してください。
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]

   * **[!UICONTROL Landing Page]:** ランディングページは、訪問者がサイトにアクセスしたときに最初に表示されるページです。 例えば、訪問者が Google 上のリンクをクリックしてカテゴリページが開いた場合は、そのカテゴリページがランディングページになります。リンクからホームページが表示された場合は、そのホームページがランディングページになります。ランディングページは訪問者のセッション中記憶されます。このセッションで訪問者のランディングページが何であったのかを基に、サイトをより掘り下げてターゲットを定めることができます。

     このオプションを選択した場合、2 番目のドロップダウンリストでは次のオプションを使用できます。

      * [!UICONTROL URL] （Target による URL の評価方法について詳しくは、[ ターゲットとオーディエンスに関する FAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md) を参照してください。
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]
      * [!UICONTROL Hash (#) fragment]

     >[!NOTE]
     >
     >`landing.url` サブドメインの変更またはダイレクトURLの置換時にオブジェクトがリセットされます。

   * **[!UICONTROL HTTP Header]:** このオプションは、[!DNL Target] リクエストの HTTP ヘッダー内の情報を評価します。 例えば、HTTP ヘッダーに言語情報が含まれる場合、ページにスペイン語でアクセスする訪問者をターゲットにする `Accept-Language: es` 条件を含むルールを作成できます。

     このオプションを選択した場合、2 番目のドロップダウンリストでは次のオプションを使用できます。

      * [!UICONTROL Accept]
      * [!UICONTROL Accept-Charset]
      * [!UICONTROL Accept-Encoding]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL Authorization]
      * [!UICONTROL Cache-Control]
      * [!UICONTROL Connection]
      * [!UICONTROL Content-Length]
      * [!UICONTROL Content-MDS]
      * [!UICONTROL Content-Type]
      * [!UICONTROL Date]
      * [!UICONTROL Expect]
      * [!UICONTROL From]
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
      * [!UICONTROL Referrer]
      * [!UICONTROL TE]
      * [!UICONTROL Upgrade]
      * [!UICONTROL User-Agent]
      * [!UICONTROL Via]
      * [!UICONTROL Warning]

   [!UICONTROL Current Page]、[!UICONTROL Previous Page] または [!UICONTROL Landing Page] を選択した場合は、[!UICONTROL Domain] と [!UICONTROL Query] のオプションを使用できます。 これらのオプションを選択する際は、次の点に注意してください。

   * **ドメイン：**&#x200B;ページの完全ドメイン。ドメインを指定する際には、ベストプラクティスとして、「次を含む」を使用することが推奨されます。例えば、「ドメインが facebook.com と等しい」は、`m.facebook.com` または `www.facebook.com` を受け付けません。 「Domain contains facebook.com」は、facebook.comの任意のバリアントを受け入れます。
   * **クエリ：** 最初の疑問符（?）の後の URL のコンテンツ。

     `foo.html?e0a72cb2a2c7`

1. （任意）オーディエンスの追加ルールを設定します。
1. **[!UICONTROL Done]** をクリックします。

独自の「ユーザー定義のクエリパラメーター」または「ユーザー定義のヘッダー」を使用して、サイトページのオーディエンスを作成することもできます。

それぞれの使い分けは次のとおりです。

* ユーザーが選択したルールが [!UICONTROL Current Page]、[!UICONTROL Landing Page] または [!UICONTROL Previous Page] の場合にクエリパラメーター
* ユーザーが選択したルールが HTTP ヘッダーの場合はヘッダー

## トラブルシューティング {#ts}

* ランディングページオーディエンスが正しく機能するには、リクエストに、at.js JavaScript ライブラリが `mboxReferrer` 属性を使用してページから取得する `context.address.referringUrl` パラメーター（配信 API の場合は `document.referrer` パラメーター）を設定する必要があります。 この `HTMLDocument` 属性は、ユーザーがナビゲートしたページの URI を返します。 ユーザーが（リンク経由ではなく、ブックマーク経由などで）ページに直接移動した場合、この属性の値は空の文字列になります。

  この動作が要件に合わない場合は、次のいずれかのアクションの実行を検討します。

   * [mbox パラメーター ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html?lang=ja){target=_blank} をターゲット設定に使用で [!DNL Target] るようにします。
   * ランディングページアクティビティの代わりに [](/help/main/c-activities/t-test-ab/test-ab.md)A/B テスト アクティビティを使用します。 A/B テスト アクティビティでは、同じ訪問者のエクスペリエンスが切り替わることはありません。
   * 代わりに [ 訪問者プロファイル ](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) を使用します。

* コンマを含む文字列に「で始まる/で終わる」評価子を使用する場合、これらの文字列は値の配列として評価され、コンマで区切られた各値が評価されます。 例えば、ヘッダーの値が `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` の場合、次のような条件に該当します。
   * zh で始まる
   * en で開始
   * 0.7 で終わる
   * 0.8 で終わる。

## トレーニングビデオ: オーディエンスの作成

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
