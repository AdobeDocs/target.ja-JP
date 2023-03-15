---
keywords: レコメンデーションフィード；フィード；SAINT;ftp;csv；分類；analytics 分類
description: フィードがエンティティをAdobeにインポートする方法を説明します [!DNL Target] Recommendationsを CSV ファイル、Google製品検索フィード形式、Analytics 製品分類の 3 つを使用します。
title: でのフィードの使用方法 [!DNL Target] Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 7b336a9e-23f4-4b09-9c8f-b9cb68162b1b
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '2511'
ht-degree: 87%

---

# フィード

フィードを使用して [!DNL Adobe Target Recommendations] に読み込んだエンティティを取得できます。エンティティは、CSV ファイル、Google Product Search フィード形式および Adobe Analytics の製品分類を使用して送信できます。

## フィードの概要 {#concept_D1E9C7347C5D4583AA69B02E79607890}

フィードによって、[エンティティ](/help/main/c-recommendations/c-products/products.md)を渡したり、ページ上で使用できない、またはページから直接送信するのは安全でない情報（利益幅や売上原価など）を mbox データに追加したりできます。

フィードを使用すると、詳細な項目情報をに渡すことができます。 [!DNL Recommendations]製品 ID、カテゴリ、名前、メッセージ、その他の属性など。

[!DNL Target] の製品分類ファイル、または Google による製品検索のファイルのどの列を [!DNL Recommendations] サーバーに送信するかを選択できます。

各項目に関するこれらのデータは、次の目的で使用できます。

* デザインでの値の表示
* 条件インクルージョンルールの定義
* 項目を別のコレクションに並べ替える
* レコメンデーションへの除外の適用

項目の説明は、 [!DNL Target] フィードまたは mbox の使用 エンティティフィードと mbox の両方でデータが収集される場合、どちらか最新のほうが使用されます。通常、mbox のほうが頻繁に閲覧されるので、mbox のデータが最新になります。まれにエンティティフィードのデータと mbox のデータが同時に収集されたものである場合、mbox のデータが使用されます。

[!UICONTROL フィード]リスト（**[!UICONTROL レコメンデーション]**／**[!UICONTROL フィード]**）には、作成したフィードについての情報が表示されます。

![フィードページ](/help/main/c-recommendations/c-products/assets/feeds-page.png)

フィードページには、次の列が含まれています。

* **名前**：作成中に指定されたフィードの名前。フィードの名前を編集するには、フィード自体を編集する必要があります。新しい名前で保存すると、フィードは更新されます。
* **タイプ**：タイプには、[CSV](/help/main/c-recommendations/c-products/feeds.md#section_65CC1148C7DD448FB213FDF499D35FCA)、[Google 製品フィード](/help/main/c-recommendations/c-products/feeds.md#section_8EFA98B5BC064140B3F74534AA93AFFF)および [Analytics 分類](/help/main/c-recommendations/c-products/feeds.md#section_79E430D2C75443BEBC9AA0916A337E0A)が含まれます。
* **ステータス**：フィードの現在の[ステータス](/help/main/c-recommendations/c-products/feeds.md#concept_E475986720D1400999868B3DFD14A7A0)。
* **スケジュール**：フィード更新スケジュールを表示します（毎日、毎週、2 週間ごと、なし）。
* **項目**：フィード内の項目数を表示します。
* **最終更新日**：フィードが最後に更新された日時とフィードを更新した人物の名前を表示します。[!UICONTROL 最終更新日]フィードが「未定義」である場合、そのフィードは [!DNL Recommendations Classic] フィードです。[!DNL Target Premium Recommendations] 内では変更できません。

>[!IMPORTANT]
>
>アップロードしたエンティティとエンティティの属性は、61 日後に有効期限が切れます。 つまり、以下のとおりです。
>
>* カタログのコンテンツが期限切れにならないように、フィードは少なくとも毎月実行する必要があります。
>* フィードファイルから項目を削除しても、カタログからはその項目は削除されません。 カタログから項目を削除するには、Target UI または API を使用して手動で項目を削除します。 または、品目の属性（在庫など）を変更して、品目が考慮から除外されるようにします。


## ソースタイプ

エンティティは、CSV ファイル、Google Product Search フィード形式および Adobe Analytics の製品分類を使用して送信できます。

### CSV {#section_65CC1148C7DD448FB213FDF499D35FCA}

アドビ独自の CSV アップロード形式を使用して、.csv ファイルを作成できます。このファイルには、製品の予約済み属性とカスタム属性に関する表示情報が含まれています。個々の環境に合った属性をアップロードするためには、ヘッダー行の `CustomN` を、使用する属性名に変更します。以下の例では、`entity.Custom1` が `entity.availability` に変更されています。このファイルを [!DNL Recommendations] サーバーに一括アップロードできます。

.csv 形式は、Google フィード形式よりも次の点で優れています。

* フィールドのマッピングが不要です。
* 複数値の属性をサポートしています（以下の例を参照）。
* 最大 100 個のカスタム属性をサポートします。必要なカスタム属性が 100 個を超える場合は、2 つ目のフィードファイルを作成し、カスタム属性の別のセットを指定できます。

ページに mbox がない場合は一括アップロードメソッドを使用して表示情報を送信することができ、また、サイトに用意されていない品目で表示情報を補うことも可能です。例えば、サイトに公開されていない可能性のある在庫情報の送信などができます。

.csv ファイル、Google 製品フィードまたは Analytics の製品分類フィードを利用してアップロードされたデータは、データベース内の既存のエンティティ属性値を上書きします。Mbox リクエストで価格情報を送信し、ファイルで異なる価格値を送信した場合、mbox リクエストで送信された値は、ファイル内の値で上書きされます。この例外は、`categoryId` エンティティの属性で、この場合、カテゴリの値は上書きされる代わりに 250 文字制限まで追加されます。

>[!IMPORTANT]
>
>意図的でない限り、.csv ファイルで値を二重引用符（&quot;）で囲まないでください。値を二重引用符で囲む場合、別の二重引用符のセットで囲んでエスケープする必要があります。エスケープしていない二重引用符は、レコメンデーションフィードの適切な読み込みを妨げます。

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
>既存の値を空白の値で上書きできません。上書きするには、別の値をその場所に渡す必要があります。 販売価格の場合、一般的なソリューションは、実際の「NULL」か別のメッセージを渡すことです。次に、テンプレートルールを記述して、その値の品目を除外します。

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

フィードのタイプが Google による製品検索の場合は、Google の形式が使用されます。これは、Adobe 固有の csv アップロード形式とは異なります。

Google 製品フィードを利用している場合は、それをインポートファイルとして使用できます。

>[!NOTE]
>
>Google データを使用する必要はありません。単に、[!DNL Recommendations] が Google と同じ形式を使用するだけです。この方法を使用して、あらゆるデータをアップロードしたり、スケジューリング機能を使用したりできます。ただし、ファイルをセットアップする際に、Google によってあらかじめ定義された属性名を保持する必要があります。

多くの小売業者が商品を Google にアップロードしているので、訪問者が Google による製品検索を使用すると、商品が表示されます。[!DNL Recommendations] では、Google の仕様に厳密に従ったエンティティフィードを使用します。エンティティフィードは .xml、.txt、.tsv のいずれかの形式で [!DNL Recommendations] に送信でき、また [Google により定義された属性](https://support.google.com/merchants/answer/188494?hl=en&amp;topic=2473824&amp;ctx=topic#US)を使用できます。結果は [Google のショッピングページ](https://www.google.com/prdhp)で検索できます。

>[!NOTE]
>
>Google フィードコンテンツをホストするサーバーで POST メソッドを有効にする必要があります。

[!DNL Recommendations] の使用時に、URL または FTP 経由で Google に送信する .xml フィードまたは .txt フィードを既に設定しているので、エンティティフィードはこの商品データを受け取り、このデータを使用して recommendations カタログを作成します。フィードの場所を指定すると、recommendations サーバーでデータが取得されます。

エンティティフィードのアップロードに Google による製品検索を使用する場合で、そこにレコメンデーションを表示したい場合や表示数に基づいたアルゴリズム配信のために製品表示数を追跡したい場合は、製品ページ mbox がページ上にある必要があります。

Google フィードは、カスタム属性での複数の値には対応していません。

フィードは、保存およびアクティブ化する際に実行します。フィードを保存する際に実行し、その後、毎日 1 時間後に実行します。

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

### Analytics の製品分類 {#section_79E430D2C75443BEBC9AA0916A337E0A}

Analytics の製品分類は、レコメンデーションで使用できる唯一の分類です。この分類ファイルについて詳しくは、 [分類について](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html) 内 *Analytics コンポーネント* ガイド。 レコメンデーションに必要なすべての情報が、現在の実装で使用できるとは限りません。したがって、ご使用の分類ファイルを追加する場合は、このユーザーガイドを参照してください。

>[!IMPORTANT]
>
>エンティティデータをにインポートする前に [!DNL Recommendations] Analytics の製品分類を使用する場合は、この方法はお勧めしません。
>
> その際は次の点にご注意ください。
>
>* エンティティ属性を更新すると、最大で 24 時間の遅延が生じます。
>* [!DNL Target] は、製品分類のみをサポートしています。 Analytics の製品 SKU は、 の [!DNL Recommendations]`entity.id` と同じレベルにマッピングする必要があります。アドビのコンサルティングサービスを使用して、Analytics のカスタム分類を作成できます。疑問点については、アカウントマネージャーまでお問い合わせください。


## フィードの作成 {#steps}

フィードを作成して、製品やサービスについての情報を [!DNL Recommendations] に挿入します。

1. Target インターフェイスから、**[!UICONTROL レコメンデーション]**／**[!UICONTROL フィード]**／**[!UICONTROL フィードを作成]**&#x200B;をクリックします。

   ![フィードを作成ダイアログボックス](assets/CreateFeed.png)

1. フィードにわかりやすい名前を指定します。
1. 「**[!UICONTROL ソースタイプ]**」を選択します。

   * CSV
   * Google 製品フィード
   * Analytics 分類

   CSV および Google 製品フィードフィードタイプについて詳しくは、[フィードの概要](/help/main/c-recommendations/c-products/feeds.md#concept_D1E9C7347C5D4583AA69B02E79607890)を参照してください。また、 [モデル CSV ガイドのダウンロード](/help/main/c-recommendations/c-products/assets/EntityFileUploadTemplate.csv) を使用して、フィードを正しく書式設定できます。

1. （条件付き）**[!UICONTROL CSV]** または **[!UICONTROL Google 製品フィード]**&#x200B;を選択した場合、フィードがアクセスできる場所を指定します。

   * **FTP**：FTP を選択した場合は、FTP サーバー情報、ログイン資格情報、ファイル名、FTP ディレクトリを指定します。より安全なアップロードのために、SSL を使用した FTP（FTPS）を使用することもできます。

      サポートされる FTP サーバー設定：

      * FTP および FTPS は、パッシブ FTP を使用するように設定する必要があります。
      * FTPS の場合、明示的な FTPS 接続を受け入れるようにサーバーを設定します。
      * SFTP はサポートされていません。
      * 接続を開始するポートを手動で指定できます（例：`ftp://ftp.yoursite.com:2121`）。ポートを指定しない場合、デフォルト FTP または FTPS ポートが使用されます。
   * **URL**：URL を選択した場合は、URL を指定します。


1. （条件付き）**[!UICONTROL Analytics 分類]**&#x200B;を選択した場合、ドロップダウンリストからレポートスイートを選択します。

1. 「**[!UICONTROL 次へ]**」矢印をクリックして、「[!UICONTROL スケジュール]」オプションを表示します。

   ![ステップの結果](assets/CreateFeedSchedule.png)

1. 更新オプションを選択します。

   * 毎日
   * 毎週
   * 2 週間ごと
   * なし：更新のスケジュールは設定しません。このフィードを実行したくない場合に、これを選択します。

1. フィードを実行する時間を指定します。

   このオプションは、ブラウザーで使用されるタイムゾーンに基づいています。別のタイムゾーンの時間を使用したい場合、タイムゾーンに応じて時間を計算する必要があります。

1. 「**[!UICONTROL 次へ]**」矢印をクリックして「[!UICONTROL マッピング]」オプションを表示してから、データを [!DNL Target] 定義にマッピングする方法を指定します。

   ![ステップの結果](assets/CreatFeedMapping.png)

1. （オプション）フィードを環境（ホストグループ）に所属させたい場合、ホストグループを選択します。

   デフォルトでは、フィードはすべてのホストグループに所属しています。これで、このフィードの品目はどの環境でも利用できるようになります。詳しくは、[ホスト](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)を参照してください。

1. 「**[!UICONTROL 保存]**」をクリックします。

フィードを作成または編集したら、フィードは即座に実行され、設定したパラメーターに応じて更新されます。すべての情報が利用できるようになるまで、しばらく時間がかかります。まず、フィードの同期が実行され、処理をおこなってインデックスが構築された上で、発行されて使用可能になります。現在のステータスは、フィードリストの[フィードステータス](/help/main/c-recommendations/c-products/feeds.md#status)に表示されます。処理が終了する前に [!DNL Target] を閉じても構いません。処理は継続されます。

インデックス構築中は、個々の値のインデックスが作成されるまでは、製品とフィードのヘッダーが表示されます。そのため、インデックスの構築が完了する前でも製品の検索や参照ができ、コレクション、除外、デザイン、アクティビティの作成が可能です。

「ステータス」に表示される「成功」は、ファイルが見つかり、正しく解析されたことを示します。ファイルのインデックスが作成されるまで、[!DNL Recommendations] 内で情報は使用できません。インデックスの作成には時間がかかります。かかる時間はファイルのサイズによって異なります。処理が失敗した場合、ファイルが見つからなかった（例えば、誤った URL が使用された場合や、FTP 情報が誤っていた場合）、または解析エラーが発生したことを示します。

## フィードのステータスとインジケーター {#concept_E475986720D1400999868B3DFD14A7A0}

フィードのステータスとそのインジケーターについて説明します。

### フィードステータス {#status}

次に、フィードのステータスを示します。

| ステータス | 説明 |
|--- |--- |
| 同期中 | フィードの設定の詳細を Target に保存中です。 |
| 同期に失敗しました | フィード設定の詳細を、Target に保存できませんでした。再試行してください。 |
| フィードが実行されていません | フィードを作成しましたが、スケジュールされていません（頻度がなしに設定されている）。 |
| *スケジュールされた日時* | フィードは実行されていませんが、特定の日時に実行するようスケジュールされています。 |
| ダウンロードを待機中 | Target はフィードファイルをダウンロードする準備中です。 |
| フィードファイルのダウンロード | Target はフィードファイルをダウンロード中です。 |
| 項目の読み込み | Target は、フィードファイルから項目を読み込んでいます。 |
| フィードを正常に読み込みました：*時間* | Target は、フィードファイルをそのコンテンツ配信システムに読み込みました。コンテンツ配信システムで項目属性に対する変更がおこなわれ、配信されたレコメンデーションがすぐに反映されます。期待された変更が表示されない場合、すぐに再試行して、レコメンデーションを含むページを更新します。<br>メモ:<ul><li>項目の属性に対する変更によって項目がレコメンデーションから除外されると、除外が直ちに反映されます。 項目が新しく追加された、または属性に対する変更によって項目がレコメンデーションから除外されなくなった場合&#x200B;**、次のアルゴリズム更新（24 時間以内におこなわれる）まで反映されません。</li><li>このステータスが表示される場合、カタログ検索ユーザーインターフェイスで更新がまだ反映されていない可能性があります。 前回検索可能なカタログが更新されたことを示す別のステータスがカタログ検索にリストされます。</li></ul> |
| インデックスに失敗しました | インデックス操作が失敗しました。再試行してください。 |
| サーバーが見つかりません | FTP または URL の場所が無効か、そうでなければ到達不能です。 |

フィードを更新するには（例えば、フィード構成やフィードファイルを変更する場合など）、フィードを開き、必要な変更をおこなってから、「**[!UICONTROL 保存]**」をクリックします。

>[!IMPORTANT]
>
>アップロードしたエンティティは 61 日後に有効期限切れになります。つまり、おすすめアクティビティの中断を防ぐために、フィードファイルは少なくとも 60 日ごとにアップロードする必要があります。項目が少なくとも 60 日に 1 回、フィードファイル（またはその他のエンティティ更新方法）に含まれていない場合、 [!DNL Adobe Target] は、項目が関連しなくなり、カタログから削除します。

### フィードステータスのインジケーター {#section_3C8A236C5CB84C769A9E9E36B8BFABA4}

次のフィードステータスのインジケーターは、[!UICONTROL ステータス]列に表示されます。

| ステータスのインジケーター | 説明 |
|--- |--- |
| 緑のステータスインジケーター | フィードのインデックス作成が正常に完了すると、緑の点でフィードが成功状態にあることを示します。 |
| 黄色のステータスインジケーター | フィードまたはフィードインデックスで、フィードの頻度の 25％の遅れが生じると、黄色い点のステータスインジケーターが表示されます。例えば、1 日 1 回実行されるフィードのセットで、予定されている時間を 6 時間過ぎてもインデックスが完了していない場合は、黄色い点が表示されます。注意：フィードのステータスが「インデックスキューを待機中」になると、新たに更新された値を配信と条件の処理で利用できるようになります。 |
| 白のステータスインジケーター | フィードのスケジュールが設定されていない場合は、白の点でフィードがまだ実行されていないことを示します。 |
| 赤のステータスインジケーター | フィードによってデータをサーバーにアップロードできなかった場合は、赤いステータスインジケーターが表示されます。 |

次の例をご覧ください。

**例 1:**

* 1 日目：毎日のフィードが午前 9:00 PST に処理されます。
* 2 日目：午後 3:30 時点で、昨日の午前 9:00 以降、フィードが実行されていません。

インデックスは約 6.5 時間前に実行されているはずだったので、ステータスは黄色になります。6.5 時間 +24 はフィード期間の 127％です。

**例 2:**

* 1 月 1 日：毎月のフィードが午前 9:00 PST に処理されます。
* 2 月 3 日：午前 10:00 時点で、1 ヶ月と 1 日 1 時間前からフィードが実行されていません。

インデックスは約 1 日と 1 時間前に実行されているはずだったので、ステータスは黄色になります。これは、わずか（31+（1/25））/30 = 1.03％の頻度設定にもかかわらず、1 日の遅延の最大値を上回ります。

## トレーニングビデオ

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### Recommendations のフィードの説明（3:01）![概要バッジ](/help/main/assets/overview.png)

このビデオには、次の情報が含まれています。

* フィードの目的の説明
* フィードの値の説明

>[!VIDEO](https://video.tv.adobe.com/v/27695)

### フィードの作成（6:44）![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* フィードの設定
* 使用するフィードのタイプの説明

>[!VIDEO](https://video.tv.adobe.com/v/27696)
