---
keywords: recommendations フィード；フィード；SAINT;ftp;csv；分類；analytics 分類
description: CSV ファイル  [!DNL Adobe Target] [!DNL Recommendations]Google Product Search フィード形式、および商品分類を使用して、にエンティティをインポートする方法について説  [!DNL Analytics]  します。
title: '[!UICONTROL Feeds] の使用方法  [!DNL Target Recommendations]'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 7b336a9e-23f4-4b09-9c8f-b9cb68162b1b
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '2463'
ht-degree: 44%

---

# フィード

フィードを使用して、[!DNL Adobe Target] [!DNL Recommendations] にエンティティを読み込みます。 エンティティは、CSV ファイル、Google Product Search フィード形式および [!DNL Adobe Analytics] の商品分類を使用して送信できます。

## フィードの概要 {#concept_D1E9C7347C5D4583AA69B02E79607890}

フィードを使用すると、ページ上で利用できない情報や、ページから直接送信することが安全でない情報（余白や COGS など）を使用して mbox データを [ エンティティ ](/help/main/c-recommendations/c-products/products.md) 渡したり補強したりできます。

フィードを使用すると、製品 ID、カテゴリ、名前、メッセージ、その他の属性など、詳細な項目情報を [!DNL Recommendations] に渡すことができます。

[!DNL Target] Product Classifications ファイルまたはGoogle Product Search ファイルから、[!DNL Recommendations] サーバーに送信する列を選択できます。

各項目に関するこれらのデータは、次の目的で使用できます。

* デザインでの値の表示
* 条件の包含ルールの定義
* 異なるコレクションへの項目の並べ替え
* 推奨事項への除外の適用

項目の説明は、フィードまたは mbox を使用して [!DNL Target] に渡すことができます。 エンティティフィードと mbox の両方でデータが収集される場合、どちらか最新のほうが使用されます。通常、mbox のほうが頻繁に閲覧されるので、mbox のデータが最新になります。まれにエンティティフィードのデータと mbox のデータが同時に収集されたものである場合、mbox のデータが使用されます。

[!UICONTROL Feeds] リスト（**[!UICONTROL Recommendations]**/**[!UICONTROL Feeds]**）には、作成したフィードに関する情報が表示されます。

![フィードページ](/help/main/c-recommendations/c-products/assets/feeds-page.png)

[!UICONTROL Feeds] ページには、次の列が含まれます。

* **名前**：作成中に指定されたフィードの名前。フィードの名前を編集するには、フィード自体を編集する必要があります。新しい名前でフィードを保存すると、フィードが更新されます。
* **タイプ**：タイプには、[CSV](/help/main/c-recommendations/c-products/feeds.md#section_65CC1148C7DD448FB213FDF499D35FCA)、[Google 製品フィード](/help/main/c-recommendations/c-products/feeds.md#section_8EFA98B5BC064140B3F74534AA93AFFF)および [Analytics 分類](/help/main/c-recommendations/c-products/feeds.md#section_79E430D2C75443BEBC9AA0916A337E0A)が含まれます。
* **ステータス**：フィードの現在の[ステータス](/help/main/c-recommendations/c-products/feeds.md#concept_E475986720D1400999868B3DFD14A7A0)。
* **スケジュール**：フィードの更新スケジュール（[!UICONTROL Daily]、[!UICONTROL Weekly]、[!DNL Every 2 Weeks] または [!UICONTROL Never]）を表示します。
* **項目**：フィード内の項目数を表示します。
* **最終更新日**：フィードが最後に更新された日時とフィードを更新した人物の名前を表示します。[!UICONTROL Last Updated] フィードに「未定義」と表示される場合、フィードは [!DNL Recommendations Classic] から受信されるので、[!DNL Target Premium Recommendations] 内から変更することはできません。

情報アイコンをクリックして、最終アップロード日とフィードの URL を表示するカードを表示します。

省略記号アイコンをクリックして、[!UICONTROL Deactivate]、[!DNL Edit]、[!UICONTROL Copy] および [!UICONTROL Delete] のアクションにアクセスします。

>[!IMPORTANT]
>
>アップロードされたエンティティとエンティティ属性は 61 日後に有効期限が切れます。 つまり、以下のとおりです。
>
>* カタログのコンテンツの有効期限が切れないように、フィードは少なくとも月に 1 回実行する必要があります。
>* フィードファイルから項目を削除しても、カタログからその項目が削除されるわけではありません。 カタログから項目を削除するには、[!DNL Target] UI または API を使用して手動で項目を削除します。 または、品目の属性（在庫など）を変更して、品目が検討対象から除外されるようにします。

## Sourceタイプ

エンティティは、CSV ファイル、Google Product Search フィード形式および [!DNL Adobe Analytics] の商品分類を使用して送信できます。

### CSV {#section_65CC1148C7DD448FB213FDF499D35FCA}

[!DNL Adobe] 独自の CSV アップロード形式を使用して.csv ファイルを作成できます。 このファイルには、製品の予約済み属性とカスタム属性に関する表示情報が含まれています。個々の環境に合った属性をアップロードするためには、ヘッダー行の `CustomN` を、使用する属性名に変更します。以下の例では、`entity.Custom1` が `entity.availability` に変更されています。このファイルを [!DNL Recommendations] サーバーに一括アップロードできます。

.csv 形式は、Google フィード形式よりも次の点で優れています。

* .csv 形式では、フィールドマッピングは必要ありません。
* .csv 形式は、複数値の属性をサポートします（以下の例を参照）。
* .csv 形式では、最大 100 個のカスタム属性をサポートします。 必要なカスタム属性が 100 個を超える場合は、2 つ目のフィードファイルを作成し、カスタム属性の別のセットを指定できます。

ページに mbox がない場合や、サイトで利用できない項目を含む表示情報を追加する場合は、バルクアップロード方法を使用して表示情報を送信します。 例えば、サイトに公開されていない可能性のある在庫情報の送信などができます。

.csv ファイル、Google製品フィード、または [!DNL Analytics] Product 分類フィードを使用してアップロードされたデータは、データベース内の既存のエンティティ属性値を上書きします。 Mbox リクエストで価格情報を送信し、ファイルで異なる価格値を送信した場合、mbox リクエストで送信された値は、ファイル内の値で上書きされます。この例外は、`categoryId` エンティティの属性で、この場合、カテゴリの値は上書きされる代わりに 250 文字制限まで追加されます。

>[!IMPORTANT]
>
>意図的でない限り、.csv ファイルで値を二重引用符（&quot;）で囲まないでください。値を二重引用符で囲む場合は、別の二重引用符で囲んでエスケープする必要があります。 エスケープしていない二重引用符は、レコメンデーションフィードの適切な読み込みを妨げます。

例えば、以下の構文は間違っています。

```
"Apples "Bananas" Grapes"",
```

以下の構文は、正しいです。

```
"Apples ""Bananas"" Grapes""",
```

>[!NOTE]
>
>既存の値を空白の値で上書きできません。その場所に別の値を渡して、上書きします。 セール価格の場合、一般的な解決策は、実際の「NULL」または他のメッセージを渡すことです。 次に、テンプレートルールを記述して、その値の品目を除外します。

商品のエンティティが正常にアップロードされてから約 2 時間後に、この商品が管理者インターフェイスで使用できるようになります。

.csv ファイルのコードのサンプルは次のとおりです。

```
## RECSRecommendations Upload File 
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines. 
## RECS 
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left. 
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'. 
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations. 
## RECSentity.id,entity.name,entity.categoryId,entity.message,entity.thumbnailUrl,entity.value,entity.pageUrl,entity.inventory,entity.margin,entity.last_updated_by,entity.multi_english,entity.availability,entity.tax_country,entity.tax_region,entity.tax_rate,entity.product_type,entity.item_group_id,entity.color,entity.size,entity.brand,entity.gtin 
na3456,RipCurl Watch with Titanium Dial,Watches & Sport,Cutting edge titanium with round case,https://example.com/s7/na3456_Viewer,425,https://example.com/shop/en-us/na3456_RipCurl,24,0.25,csv,"[""New"",""Web"",""Sales"",""[1,2,34,5]""]",in stock,US,CA,9.25,Shop by Category > Watches,dz1,Titanium,44mm,RipCurl,"075380 01050 5" 
na3457,RipCurl Watch with Black Dial,Watches & Sport,Cutting edge matte black with round case,https://example.com/s7/na3457_Viewer,275,https://example.com/shop/en-us/na3457_RipCurl,24,0.27,csv,"[""New"",""Web"",""Sales"",""[1,2,34,5]""]",in stock,US,CA,9.25,Shop by Category > Watches,dz1,Black,44mm,RipCurl,"075340 01060 7"
```

### Google {#section_8EFA98B5BC064140B3F74534AA93AFFF}

フィードのタイプが Google による製品検索の場合は、Google の形式が使用されます。これは、[!DNL Adobe] 独自の CSV アップロード形式とは異なります。

Google 製品フィードを利用している場合は、それをインポートファイルとして使用できます。

>[!NOTE]
>
>Google データを使用する必要はありません。[!DNL Recommendations] では、Googleと同じフォーマットを使用します。 この方法を使用して、あらゆるデータをアップロードしたり、スケジューリング機能を使用したりできます。ただし、ファイルをセットアップする際に、Google によってあらかじめ定義された属性名を保持する必要があります。

ほとんどの小売業者は商品をGoogleにアップロードするので、訪問者がGoogleの商品検索を使用すると、商品が表示されます。 [!DNL Recommendations] では、Google の仕様に厳密に従ったエンティティフィードを使用します。エンティティフィードは、.xml、.txt または.tsv 経由で [!DNL Recommendations] に送信でき、[Googleで定義された属性 ](https://support.google.com/merchants/answer/188494?hl=en&topic=2473824&ctx=topic#US) を使用できます。 結果は [Google のショッピングページ](https://www.google.com/prdhp)で検索できます。

>[!NOTE]
>
>Google フィードコンテンツをホストするサーバーで POST メソッドを有効にする必要があります。

URL または FTP 経由でGoogleに送信する.xml または.txt フィードを既に設定しているた [!DNL Recommendations]、エンティティフィードはその商品データを受け入れ、それを使用して Recommendations カタログを構築します。 フィードの場所を指定すると、recommendations サーバーでデータが取得されます。

エンティティフィードのアップロードにGoogle製品検索を使用する場合、レコメンデーションをページに表示したり、表示に基づいてアルゴリズム配信のために製品ビューを追跡したりするには、ページに製品ページ mbox が必要です。

Google フィードは、カスタム属性での複数の値には対応していません。

フィードは、保存して有効化した時点で実行されます。 フィードを保存した時点で実行され、その後 1 時間後に毎日が実行されます。

Google Product Search フィードの .xml ファイルのコードのサンプルは次のとおりです。

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?> 
<feed xmlns="https://www.w3.org/2005/Atom" xmlns:ns2="https://base.google.com/ns/1.0" xmlns:ns3="https://base.google.com/cns/1.0"> 
    <title>Product Feed</title> 
    <link href="https://example.com"/> 
    <updated>2017-12-13T08:45:04.918-08:00</updated> 
    <author> 
        <name>Product Feed Author</name> 
    </author> 
    <id>https://example.com</id> 
    <entry> 
        <title>RipCurl Watch with Titanium Dial</title> 
        <description>Cutting edge Titanium with Round case</description> 
        <ns2:id>na3452</ns2:id> 
        <ns2:link>https://example.com/shop/en-us/na3452_RipCurl</ns2:link> 
        <ns2:availability>in stock</ns2:availability> 
        <ns2:condition>NEW</ns2:condition> 
        <ns2:google_product_category>Watches &amp; Sport</ns2:google_product_category> 
        <ns2:gtin>075380 01050 5</ns2:gtin> 
        <ns2:image_link>https://example.com/s7/na3452_Viewer</ns2:image_link> 
        <ns2:mobile_link>https://m.example.com/s7/na3452_Viewer</ns2:mobile_link> 
        <ns2:mpn>71050</ns2:mpn> 
        <ns2:price>425</ns2:price> 
        <ns2:product_review_average>5.0</ns2:product_review_average> 
        <ns2:product_review_count>30</ns2:product_review_count> 
        <ns2:product_type>Shop by Category > Watches </ns2:product_type> 
        <ns2:brand>RipCurl</ns2:brand> 
        <ns2:sale_price>375</ns2:sale_price> 
        <ns2:tax> 
          <ns2:country>US</ns2:country> 
          <ns2:region>CA</ns2:region> 
          <ns2:rate>9.25</ns2:rate> 
          <ns2:tax_ship>y</ns2:tax_ship> 
        </ns2:tax> 
        <ns2:is_bundle>N</ns2:is_bundle> 
    </entry> 
    <entry> 
        <title>RipCurl Watch with Black Dial</title> 
        <description>Cutting edge matte black with Round case</description> 
        <ns2:id>na3453</ns2:id> 
        <ns2:link>https://example.com/shop/en-us/na3453_RipCurl</ns2:link> 
        <ns2:availability>in stock</ns2:availability> 
        <ns2:condition>NEW</ns2:condition> 
        <ns2:google_product_category>Watches &amp; Sport</ns2:google_product_category> 
        <ns2:gtin>075380 013450 5</ns2:gtin> 
        <ns2:image_link>https://example.com/s7/na3453_Viewer</ns2:image_link> 
        <ns2:mobile_link>https://m.example.com/s7/na3453_Viewer</ns2:mobile_link> 
        <ns2:mpn>71050</ns2:mpn> 
        <ns2:price>275</ns2:price> 
        <ns2:product_review_average>4.8</ns2:product_review_average> 
        <ns2:product_review_count>23</ns2:product_review_count> 
        <ns2:product_type>Shop by Category > Watches </ns2:product_type> 
        <ns2:brand>RipCurl</ns2:brand> 
        <ns2:sale_price>249</ns2:sale_price> 
        <ns2:tax> 
          <ns2:country>US</ns2:country> 
          <ns2:region>CA</ns2:region> 
          <ns2:rate>9.25</ns2:rate> 
          <ns2:tax_ship>y</ns2:tax_ship> 
        </ns2:tax> 
        <ns2:is_bundle>N</ns2:is_bundle> 
    </entry> 
</feed> 
```

Google Product Search フィードの .tsv ファイルのコードのサンプルは次のとおりです。

```
id    title    description    link    price    condition    availability    image_link    tax    shipping_weight    shipping    google_product_category    product_type    item_group_id    color    size    gender    age_group    pattern    brand    gtin    mpn 
na3454    RipCurl Watch with Titanium Dial    Cutting edge titanium with round case    https://example.com/shop/en-us/na3454_RipCurl    425    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075380 01050 5    DZ1437 
na3455    RipCurl Watch with Black Dial    Cutting edge matte black with round case    https://example.com/shop/en-us/na3455_RipCurl    275    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075340 01060 7    DZ1446
```

### [!DNL Analytics] 製品の分類 {#section_79E430D2C75443BEBC9AA0916A337E0A}

[!DNL Analytics] 製品の分類は、レコメンデーションに使用できる唯一の分類です。 この分類ファイルについて詳しくは、[Analytics コンポーネント ](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html) ガイドの *分類について* を参照してください。 レコメンデーションに必要な情報の一部が現在の実装で利用できない場合があるので、分類ファイルに追加する場合は、このユーザーガイドに従ってください。

>[!IMPORTANT]
>
>[!DNL Recommendations] の製品分類を使用して [!DNL Analytics] にエンティティデータをインポートする前に、この方法は推奨されないことに注意してください。
>
> その際は次の点にご注意ください。
>
>* エンティティ属性を更新すると、最大で 24 時間の遅延が生じます。
>* [!DNL Target] は [!UICONTROL Product Classifications] のみをサポートします。 [!DNL Analytics] の製品 SKU は、[!DNL Recommendations] の `entity.id` と同じレベルにマッピングする必要があります。 カスタム [!DNL Analytics] 分類は、[!UICONTROL Adobe Consulting Services] を使用してエンジニアリングできます。 アカウントマネージャーにお問い合わせください。

## フィードの作成 {#steps}

フィードを作成して、製品やサービスについての情報を [!DNL Recommendations] に挿入します。

1. Target インターフェイス内で、**[!UICONTROL Recommendations]**/**[!UICONTROL Feeds]**/**[!UICONTROL Create Feed]** をクリックします。

   ![フィードを作成ダイアログボックス](assets/CreateFeed.png)

1. フィードにわかりやすい名前を指定します。
1. **[!UICONTROL Source Type]** を選択します。

   * [!UICONTROL CSV]
   * [!UICONTROL Google Product Feed]
   * [!UICONTROL Analytics Classifications]

   [!UICONTROL CSV] および [!UICONTROL Google Product Feed] フィードのタイプについて詳しくは、[ フィードの概要 ](/help/main/c-recommendations/c-products/feeds.md#concept_D1E9C7347C5D4583AA69B02E79607890) を参照してください。 また、フィードを正しく書式設定するのに役立つ [ モデル CSV ガイドをダウンロード ](/help/main/c-recommendations/c-products/assets/EntityFileUploadTemplate.csv) することもできます。

1. （条件付き） **[!UICONTROL CSV]** または **[!UICONTROL Google Product Feed]** を選択した場合、フィードにアクセスできる場所を指定します。

   * **FTP**：FTP を選択した場合は、FTP サーバー情報、ログイン資格情報、ファイル名、FTP ディレクトリを指定します。FTP を SSL （FTPS）と共に使用すると、より安全なアップロードが可能になります。

     サポートされる FTP サーバー設定：

      * FTP および FTPS は、パッシブ FTP を使用するように設定する必要があります。
      * FTPS の場合は、明示的な FTPS 接続を受け入れるようにサーバを設定します。
      * SFTP はサポートされていません。
      * 接続を開始するポート（`ftp://ftp.yoursite.com:2121` など）を手動で指定できます。 ポートを指定しない場合、デフォルト FTP または FTPS ポートが使用されます。

   * **URL**:[!UICONTROL URL] を選択した場合は、URL を指定します。

1. （条件付き） **[!UICONTROL Analytics Classifications]** を選択した場合は、ドロップダウンリストからレポートスイートを選択します。

1. **[!UICONTROL Next]** 矢印をクリックして [!UICONTROL Schedule] のオプションを表示します。

   ![ステップの結果](assets/CreateFeedSchedule.png)

1. 更新オプションを選択します。

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 Weeks]
   * [!UICONTROL Never]：更新をスケジュールしません。 このフィードを実行したくない場合に、これを選択します。

1. フィードを実行する時間を指定します。

   このオプションは、ブラウザーで使用されるタイムゾーンに基づいています。別のタイムゾーンの時間を使用したい場合、タイムゾーンに応じて時間を計算する必要があります。

1. **[!UICONTROL Next]** 矢印をクリックして [!UICONTROL Mapping] のオプションを表示し、データを [!DNL Target] 定義にマッピングする方法を指定します。

   ![ステップの結果](assets/CreatFeedMapping.png)

1. （オプション）フィードを環境（ホストグループ）に所属させたい場合、ホストグループを選択します。

   デフォルトでは、フィードはすべてのホストグループに所属しています。これで、このフィードの品目はどの環境でも利用できるようになります。詳しくは、[ホスト](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)を参照してください。

1. **[!UICONTROL Save]** をクリックします。

フィードを作成または編集すると、フィードは直ちに実行されます。 設定したパラメーターに従ってフィードが更新されます。 情報が使用可能になるまで、ある程度の時間がかかります。 まず、フィードの同期が実行され、処理をおこなってインデックスが構築された上で、発行されて使用可能になります。現在のステータスは、フィード リストの [ フィードのステータス ](/help/main/c-recommendations/c-products/feeds.md#status) に表示されます。 処理が終了する前に [!DNL Target] を閉じても構いません。処理は継続されます。

インデックス構築中は、個々の値のインデックスが作成されるまでは、製品とフィードのヘッダーが表示されます。これにより、製品を検索および表示して、インデックス作成が完了する前にコレクション、除外、デザインおよびアクティビティを作成できるようになります。

「ステータス」に表示される「成功」は、ファイルが見つかり、正しく解析されたことを示します。ファイルのインデックスが作成されるまで、[!DNL Recommendations] 内で情報は使用できません。インデックスの作成には時間がかかります。かかる時間はファイルのサイズによって異なります。プロセスが失敗した場合は、ファイルが見つからなかったことを意味します。 例えば、使用した URL が正しくないか、FTP 情報が正しくないか、解析エラーが発生したとします。

## フィードのステータスとインジケーター {#concept_E475986720D1400999868B3DFD14A7A0}

フィードのステータスとそのインジケーターについて説明します。

### フィードステータス {#status}

次に、フィードのステータスを示します。

| ステータス | 説明 |
|--- |--- |
| [!UICONTROL Syncing] | フィード設定の詳細を [!DNL Target] に保存しています。 |
| [!UICONTROL Sync Failed] | フィード設定の詳細を [!DNL Target] に保存できませんでした。 再試行する。 |
| [!UICONTROL No Feed Run] | フィードを作成しましたが、スケジュールされていません（頻度が「なし」に設定されています）。 |
| *スケジュールされた日時* | フィードは実行されていませんが、特定の日時に実行するようスケジュールされています。 |
| [!UICONTROL Waiting for Download] | [!DNL Target] はフィード ファイルのダウンロードを準備しています。 |
| [!UICONTROL Downloading Feed File] | [!DNL Target] はフィード ファイルをダウンロードしています。 |
| [!UICONTROL Importing Items] | [!DNL Target] はフィード ファイルからアイテムをインポートしています。 |
| フィードを正常に読み込みました：*時間* | [!DNL Target] がフィードファイルをコンテンツ配信システムに読み込みました。 項目属性の変更はコンテンツ配信システムで既に行われており、間もなく配信されるレコメンデーションに反映されます。 期待された変更が表示されない場合は、もう一度試して、レコメンデーションを含むページを更新します。<br> 注：<ul><li>項目の属性を変更した結果、レコメンデーションから項目が除外された場合、その除外は直ちに反映されます。 項目を新しく追加した場合、または属性を変更した結果、項目がレコメンデーションから除外 *されなくなった* 場合は、24 時間以内に発生する次のアルゴリズムが更新されるまで反映されません。</li><li>このステータスが表示されると、更新がまだ [!UICONTROL Catalog Search] UI に反映されていない場合があります。 検索可能なカタログが最後に更新されたことを示す別のステータスが [!UICONTROL Catalog Search] に表示されます。</li></ul> |
| [!UICONTROL Failed to Index] | インデックス操作が失敗しました。再試行する。 |
| [!UICONTROL Server Not Found] | FTP または URL の場所が無効か、そうでなければ到達不能です。 |

フィードを更新するには（フィード設定やフィードファイルを変更する場合など）、フィードを開き、必要な変更を加えて「**[!UICONTROL Save]**」をクリックします。

>[!IMPORTANT]
>
>アップロードしたエンティティは 61 日後に有効期限切れになります。つまり、レコメンデーションのアクティビティの中断を防ぐために、フィードファイルは少なくとも 60 日ごとにアップロードする必要があります。アイテムがフィード ファイル（または他のエンティティの更新方法）に含まれていない場合は、少なくとも 60 日に 1 回、そのアイテムが関係 [!DNL Target] なくなると判断し、カタログから削除します。

### フィードステータスのインジケーター {#section_3C8A236C5CB84C769A9E9E36B8BFABA4}

次のフィードステータスインジケーターが「[!UICONTROL Status]」列に表示されます。

| ステータスのインジケーター | 説明 |
|--- |--- |
| 緑のステータスインジケーター | フィードのインデックス作成が正常に完了すると、緑の点でフィードが成功状態にあることを示します。 |
| 黄色のステータスインジケーター | フィードまたはフィードインデックスで、フィードの頻度の 25％の遅れが生じると、黄色い点のステータスインジケーターが表示されます。例えば、スケジュールされた時間から 6 時間後にインデックスが完了していない場合、フィードセットが毎日実行されるように黄色のドットが表示されます。 メモ：フィードステータスが「インデックスキューを待機中」になると、新しく更新された値を配信および条件の処理で使用できます。 |
| 白のステータスインジケーター | フィードのスケジュールが設定されていない場合は、白の点でフィードがまだ実行されていないことを示します。 |
| 赤のステータスインジケーター | フィードがサーバーへのデータのアップロードに失敗した場合は、赤いステータスインジケーターが表示されます。 |

次の例をご覧ください。

**例 1:**

* 1 日目：毎日午前 9:00 （PST）のフィードプロセス。
* 2 日目：:30 後 3 時で、フィードは昨日の午前 9:00 から実行されていません。

インデックスは約 6.5 時間前に実行されているはずだったので、ステータスは黄色になります。6.5 時間 +24 はフィード期間の 127％です。

**例 2:**

* 1 月 1 日：毎月のフィードプロセスは午前 9:00 （PST）。
* 2 月 3 日 :00 前 10 時で飼料が 1 か月、1 日、1 時間前まで出ない。

インデックスは約 1 日と 1 時間前に実行されているはずだったので、ステータスは黄色になります。これは、わずか（31+（1/25））/30 = 1.03％の頻度設定にもかかわらず、1 日の遅延の最大値を上回ります。

## トレーニングビデオ

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### Recommendations （3:01）のフィードについて ![ 概要バッジ ](/help/main/assets/overview.png)

このビデオには、次の情報が含まれています。

* フィードの目的の説明
* フィードの値の説明

>[!VIDEO](https://video.tv.adobe.com/v/27695)

### フィード（6:44）の作成 ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* フィードの設定
* 使用するフィードのタイプの説明

>[!VIDEO](https://video.tv.adobe.com/v/27696)
