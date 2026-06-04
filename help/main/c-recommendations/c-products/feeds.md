---
keywords: レコメンデーションフィード；SAINT;ftp;csv；分類；analytics分類
description: フィードがCSV ファイル、 [!DNL Google Product Search]  フィード形式、 [!DNL Analytics] 製品分類を使用して [!DNL Adobe Target] [!DNL Recommendations]にエンティティを読み込む方法について説明します。
title: ' [!DNL Target Recommendations]で[!UICONTROL  フィード ]を使用するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 7b336a9e-23f4-4b09-9c8f-b9cb68162b1b
TQID: https://experienceleague.adobe.com/lXXX8XEXGtt1DDMI63Ck4AbCGDjzkxs60oW2nEnc0Go
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2725
ht-degree: 36%

---

# フィード

フィードを使用して、[!DNL Adobe Target] [!DNL Recommendations]に読み込まれたエンティティを取得します。 エンティティは、CSV ファイル、[!DNL Google Product Search] フィード形式、[!DNL Adobe Analytics]製品の分類を使用して送信できます。

## フィードの概要 {#concept_D1E9C7347C5D4583AA69B02E79607890}

フィードを使用すると、[ エンティティ ](/help/main/c-recommendations/c-products/products.md)を渡したり、ページ上で利用できない情報や、ページから直接送信できない情報でmbox データを拡張したりできます。 たとえば、マージン、売上原価（COGS）などがあります。

フィードでは、製品ID、カテゴリ、名前、メッセージ、その他の属性など、詳細な項目情報を[!DNL Recommendations]に渡すこともできます。

[!DNL Target]製品分類ファイルまたは[!DNL Google Product Search] ファイルから、[!DNL Recommendations] サーバーに送信する列を選択できます。

各項目に関するこれらのデータは、次のことに使用できます。

* デザインの値の表示
* 基準の包含ルールの定義
* アイテムを異なるコレクションに並べ替える
* レコメンデーションへの除外の適用

アイテムの説明は、フィードまたはmboxを使用して[!DNL Target]に渡すことができます。 [!DNL Target]がエンティティフィードとmboxの両方を使用してデータを収集すると、最新のデータが優先されます。 通常、mbox のほうが頻繁に閲覧されるので、mbox のデータが最新になります。 まれにエンティティフィードのデータと mbox のデータが同時に収集されたものである場合、mbox のデータが使用されます。

[!UICONTROL  フィード ] リスト （**[!UICONTROL Recommendations]** > **[!UICONTROL フィード]**）には、作成したフィードに関する情報が表示されます。

[!UICONTROL  フィード ] ページには、次の列が含まれています。

* **名前**：作成中に指定されたフィードの名前。 フィードの名前を編集するには、フィード自体を編集する必要があります。 新しい名前でフィードを保存すると、フィードが更新されます。
* **ステータス**：フィードの現在の[ステータス](/help/main/c-recommendations/c-products/feeds.md#concept_E475986720D1400999868B3DFD14A7A0)。
* **タイプ**: タイプには、[CSV](/help/main/c-recommendations/c-products/feeds.md#section_65CC1148C7DD448FB213FDF499D35FCA)、[[!DNL Google Product Feed]](/help/main/c-recommendations/c-products/feeds.md#section_8EFA98B5BC064140B3F74534AA93AFFF)および[Analytics分類](/help/main/c-recommendations/c-products/feeds.md#section_79E430D2C75443BEBC9AA0916A337E0A)が含まれます。
* **項目**：フィード内の項目数を表示します。
* **スケジュール**: フィードの更新スケジュールを表示します：[!UICONTROL 毎日]、[!UICONTROL 毎週]、[!DNL Every 2 Weeks]、または[!UICONTROL なし]。
* **最終更新日**：フィードが最後に更新された日時とフィードを更新した人物の名前を表示します。

[!UICONTROL 表をカスタマイズ ] アイコン （![表をカスタマイズ アイコン ](/help/main/assets/icons/ColumnSetting.svg)）をクリックして、表示する列を選択または選択解除します。

[!UICONTROL 情報] アイコン （![情報アイコン ](/help/main/assets/icons/InfoOutline.svg)）をクリックすると、最後のアップロード日とフィードのURLを表示するカードが表示されます。

[!UICONTROL 詳細アクション ] アイコン （![詳細アクション アイコン ](/help/main/assets/icons/MoreSmallList.svg)）をクリックして、次のアクションにアクセスします。[!UICONTROL 無効化]、[!DNL Edit]、[!UICONTROL  コピー]、[!UICONTROL 削除]。

>[!IMPORTANT]
>
>アップロードされたエンティティとエンティティ属性は、61日後に有効期限が切れます。 つまり、以下のとおりです。
>
>* カタログの内容が期限切れにならないように、フィードは少なくとも毎月実行する必要があります。
>* フィードファイルから項目を削除しても、その項目はカタログから削除されません。 カタログからアイテムを削除するには、[!DNL Target] UIまたはAPIを使用して、手動でアイテムを削除します。 または、アイテム属性（在庫など）を変更して、そのアイテムが検討から除外されるようにします。

## Source タイプ

エンティティは、CSV ファイル、[!DNL Google Product Search] フィード形式、[!DNL Adobe Analytics]製品の分類を使用して送信できます。

### CSV {#section_65CC1148C7DD448FB213FDF499D35FCA}

[!DNL Adobe]独自のCSV アップロード形式を使用して.csv ファイルを作成できます。 このファイルには、製品の予約済み属性とカスタム属性に関する表示情報が含まれています。 個々の環境に合った属性をアップロードするためには、ヘッダー行の `CustomN` を、使用する属性名に変更します。 以下の例では、`entity.Custom1` が `entity.availability` に変更されています。 このファイルを [!DNL Recommendations] サーバーに一括アップロードできます。

.csv形式を使用すると、[!DNL Google] フィード形式よりも次の利点があります。

* .csv形式では、フィールドマッピングは必要ありません。
* .csv形式は、複数の値の属性をサポートします（以下の例を参照）。
* .csv形式では、最大100個のカスタム属性をサポートします。 必要なカスタム属性が 100 個を超える場合は、2 つ目のフィードファイルを作成し、カスタム属性の別のセットを指定できます。

ページにmboxがない場合や、サイトで使用できない項目で表示情報を補足する場合は、一括アップロード方法を使用して表示情報を送信します。 例えば、サイトに公開されていない可能性のある在庫情報の送信などができます。

.csv ファイル、Google Product Feed、または[!DNL Analytics]製品分類フィードを使用してアップロードされたデータは、データベース内の既存のエンティティ属性値を上書きします。 Mbox リクエストで価格情報を送信し、ファイルで異なる価格値を送信した場合、mbox リクエストで送信された値は、ファイル内の値で上書きされます。 この例外は、`categoryId` エンティティの属性で、この場合、カテゴリの値は上書きされる代わりに 250 文字制限まで追加されます。

>[!IMPORTANT]
>
>意図的でない限り、.csv ファイルで値を二重引用符（&quot;）で囲まないでください。 値を二重引用符で囲む場合は、値を別の二重引用符で囲んでエスケープする必要があります。 エスケープしていない二重引用符は、レコメンデーションフィードの適切な読み込みを妨げます。

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
>既存の値を空白の値で上書きできません。 別の値を渡して、既存の値を上書きします。 販売価格の場合、一般的な解決策は、実際の「NULL」または他のメッセージを渡すことです。 次に、テンプレートルールを記述して、その値の品目を除外します。

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

### [!DNL Google] {#section_8EFA98B5BC064140B3F74534AA93AFFF}

[!DNL Google Product Search] フィードの種類は[!DNL Google]形式を使用しています。 これは、[!DNL Adobe]独自のCSV アップロード形式とは異なります。

既存の[!DNL Google Product Feed]がある場合は、それを読み込みファイルとして使用できます。

>[!NOTE]
>
>[!DNL Google] データを使用する必要はありません。 [!DNL Recommendations]は[!DNL Google]と同じ形式を使用します。 この方法を使用して、あらゆるデータをアップロードしたり、スケジューリング機能を使用したりできます。 ただし、ファイルを設定する際は、[!DNL Google]個の定義済み属性名を保持する必要があります。

ほとんどの小売業者は商品を[!DNL Google]にアップロードするので、訪問者が[!DNL Google]商品検索を使用すると、商品が表示されます。 [!DNL Recommendations]は、エンティティフィードの[!DNL Google]仕様に従っています。 エンティティフィードは、.xml、.txt、または.tsvを介して[!DNL Recommendations]に送信でき、Google](https://support.google.com/merchants/answer/188494?hl=en&topic=2473824&ctx=topic#US)によって定義された[属性を使用できます。 検索結果は、[[!DNL Google]  ショッピング ページ ](https://www.google.com/prdhp)で検索できます。

>[!NOTE]
>
>POST メソッドは、[!DNL Google] フィード コンテンツをホストしているサーバーで許可されている必要があります。

[!DNL Recommendations]人のユーザーは既に.xmlまたは.txt フィードを設定してURLまたはFTPを介して[!DNL Google]に送信しているため、エンティティ フィードはその製品データを受け入れ、それを使用してレコメンデーションカタログを構築します。 フィードの場所を指定すると、recommendations サーバーでデータが取得されます。

エンティティ フィードのアップロードに[!DNL Google Product Search]を使用する場合でも、レコメンデーションをそこに表示したり、ビューに基づいてアルゴリズム配信の製品ビューを追跡したりするには、ページに製品ページ mboxが必要です。

[!DNL Google] フィードでは、カスタム属性の複数の値をサポートしていません。

フィードは、保存してアクティブ化した時点で実行されます。 フィードを保存した時点で実行され、1時間後に毎日。

[!DNL Google Product Search] フィード .xml ファイルのサンプルコードを次に示します。

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

[!DNL Google Product Search] フィード .tsv ファイルのサンプルコードを次に示します。

```
id    title    description    link    price    condition    availability    image_link    tax    shipping_weight    shipping    google_product_category    product_type    item_group_id    color    size    gender    age_group    pattern    brand    gtin    mpn 
na3454    RipCurl Watch with Titanium Dial    Cutting edge titanium with round case    https://example.com/shop/en-us/na3454_RipCurl    425    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075380 01050 5    DZ1437 
na3455    RipCurl Watch with Black Dial    Cutting edge matte black with round case    https://example.com/shop/en-us/na3455_RipCurl    275    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075340 01060 7    DZ1446
```

### [!DNL Analytics]製品の分類 {#section_79E430D2C75443BEBC9AA0916A337E0A}

[!DNL Adobe Analytics]製品分類は、推奨事項に使用できる唯一の分類です。 この分類ファイルについて詳しくは、*分析コンポーネント* ガイドの[分類について](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html)を参照してください。 レコメンデーションに必要なすべての情報が現在の実装で使用できるわけではないので、分類ファイルに追加する場合は、このユーザーガイドに従ってください。

>[!IMPORTANT]
>
>[!DNL Analytics]製品分類を使用してエンティティ データを[!DNL Recommendations]に読み込む前に、これが推奨される方法ではないことに注意してください。
>
> その際は次の点にご注意ください。
>
>* エンティティ属性を更新すると、最大で 24 時間の遅延が生じます。
>* [!DNL Target]は[!UICONTROL 製品分類]のみをサポートしています。 [!DNL Analytics]製品SKUは、[!DNL Recommendations] `entity.id`と同じレベルにマッピングする必要があります。 カスタム [!DNL Analytics]分類は、[!UICONTROL Adobe Consulting サービス ]を使用して設計できます。 ご質問がある場合は、アカウントマネージャーにお問い合わせください。

## フィードの作成 {#steps}

フィードを作成して、製品やサービスについての情報を [!DNL Recommendations] に挿入します。

1. [!DNL Target] インターフェイス内から、**[!UICONTROL Recommendations]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]**&#x200B;をクリックします。

1. フィードにわかりやすい名前を指定します。
1. **[!UICONTROL Sourceの種類]**&#x200B;を選択します。

   * [!UICONTROL CSV]
   * [!UICONTROL Google製品フィード ]
   * [!UICONTROL Analytics分類]

   [!UICONTROL CSV]および[!UICONTROL Google Product Feed] フィードの種類について詳しくは、[ フィードの概要](/help/main/c-recommendations/c-products/feeds.md#concept_D1E9C7347C5D4583AA69B02E79607890)を参照してください。 また、[ モデル CSV ガイドをダウンロード ](/help/main/c-recommendations/c-products/assets/EntityFileUploadTemplate.csv)して、フィードを正しくフォーマットできます。

1. （条件付き） **[!UICONTROL CSV]**&#x200B;または&#x200B;**[!UICONTROL Google Product Feed]**&#x200B;を選択した場合は、フィードにアクセスできる場所を指定します。

   * **FTP**：FTP を選択した場合は、FTP サーバー情報、ログイン資格情報、ファイル名、FTP ディレクトリを指定します。 より安全なアップロードのために、FTPとSSL （FTPS）を使用できます。

     サポートされる FTP サーバー設定：

      * FTP および FTPS は、パッシブ FTP を使用するように設定する必要があります。
      * FTPSの場合は、明示的なFTPS接続を受け入れるようにサーバーを設定します。
      * SFTP はサポートされていません。
      * 接続を開始するポートを手動で指定できます（例：`ftp://ftp.yoursite.com:2121`）。 ポートを指定しない場合、デフォルト FTP または FTPS ポートが使用されます。

   * **URL**: [!UICONTROL URL]を選択した場合は、URLを指定します。

1. （条件付き） **[!UICONTROL Analytics Classifications]**&#x200B;を選択した場合は、ドロップダウンリストからレポートスイートを選択します。

1. **[!UICONTROL 次へ]**&#x200B;矢印をクリックして、[!UICONTROL  スケジュール ] オプションを表示します。

1. 更新オプションを選択します。

   * [!UICONTROL 日別]
   * [!UICONTROL 週単位]
   * [!UICONTROL 2週間ごとに]
   * [!UICONTROL なし]：更新をスケジュールしません。 このフィードを実行したくない場合に、これを選択します。

1. フィードを実行する時間を指定します。

   このオプションは、ブラウザーで使用されるタイムゾーンに基づいています。 別のタイムゾーンの時間を使用したい場合、タイムゾーンに応じて時間を計算する必要があります。

1. **[!UICONTROL 次]**&#x200B;矢印をクリックして[!UICONTROL  マッピング ] オプションを表示し、データを[!DNL Target]定義にマッピングする方法を指定します。

1. （オプション）フィードを環境（ホストグループ）に所属させたい場合、ホストグループを選択します。

   デフォルトでは、フィードはすべてのホストグループに所属しています。 これで、このフィードの品目はどの環境でも利用できるようになります。 詳しくは、[ホスト](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)を参照してください。

1. 「**[!UICONTROL 保存]**」をクリックします。

フィードを作成または編集すると、フィードはすぐに実行されます。 フィードは、設定したパラメーターに従って更新されます。 情報が公開されるまでに時間がかかります。 まず、フィードの同期が実行され、処理をおこなってインデックスが構築された上で、発行されて使用可能になります。 現在のステータスは、[!UICONTROL  フィード ] リストの[ フィード ステータス ](/help/main/c-recommendations/c-products/feeds.md#status)に表示されます。 処理が終了する前に [!DNL Target] を閉じても構いません。処理は継続されます。

インデックス構築中は、個々の値のインデックスが作成されるまでは、製品とフィードのヘッダーが表示されます。 これにより、商品を検索して表示できるので、インデックス作成が完了する前にコレクション、除外、デザイン、アクティビティを作成できます。

「ステータス」に表示される「成功」は、ファイルが見つかり、正しく解析されたことを示します。 ファイルのインデックスが作成されるまで、[!DNL Recommendations] 内で情報は使用できません。インデックスの作成には時間がかかります。かかる時間はファイルのサイズによって異なります。 プロセスが失敗した場合は、ファイルが見つからなかったことを意味します。 例えば、誤ったURLを使用したり、FTP情報が正しくなかったり、解析エラーが発生したりしました。

## フィードのステータスとインジケーター {#concept_E475986720D1400999868B3DFD14A7A0}

フィードのステータスとそのインジケーターについて説明します。

### フィードステータス {#status}

次に、フィードのステータスを示します。

| ステータス | 説明 |
|--- |--- |
| [!UICONTROL 同期中] | フィード設定の詳細は[!DNL Target]に保存されています。 |
| [!UICONTROL 同期失敗] | フィード設定の詳細を[!DNL Target]に保存できませんでした。 再試行する。 |
| [!UICONTROL  フィード実行なし] | フィードを作成しましたが、スケジュールされていません（頻度は「なし」に設定されています）。 |
| *スケジュールされた日時* | フィードは実行されていませんが、特定の日時に実行するようスケジュールされています。 |
| [!UICONTROL  ダウンロード待ち] | [!DNL Target]はフィード ファイルのダウンロードを準備しています。 |
| [!UICONTROL  フィードファイルのダウンロード ] | [!DNL Target]がフィード ファイルをダウンロードしています。 |
| [!UICONTROL 項目の読み込み] | [!DNL Target]はフィード ファイルから項目を読み込んでいます。 |
| フィードを正常に読み込みました：*時間* | [!DNL Target]は、フィード ファイルをコンテンツ配信システムに読み込みました。 コンテンツ配信システムでアイテム属性が変更され、近日中に配信レコメンデーションに反映される予定です。 予想される変更が表示されない場合は、もう一度試して、推奨事項を含むページを更新します。<br> メモ：<ul><li>アイテムの属性に対する変更により、アイテムがレコメンデーションから除外された場合、除外はすぐに反映されます。 アイテムが新しく追加された場合、または属性に変更を加えた結果、アイテムが&#x200B;*もはや* レコメンデーションから除外されなくなった場合、次のアルゴリズムの更新（24時間以内に発生）まで反映されません。</li><li>このステータスが表示されている場合、更新が[!UICONTROL  カタログ検索] UIにまだ反映されていない可能性があります。 [!UICONTROL  カタログ検索]には、検索可能なカタログが最後に更新された日時を示す別のステータスが一覧表示されます。</li></ul> |
| 部分的な読み込みに失敗しました | 以前は、すべての行がアップロードされなかったときでも、フィードは成功としてマークされていました。 したがって、フィードが正常に表示されたときに、すべての行がアップロードされたという誤った印象を与えます。<P>ここでは、フィードの部分的なインポートが発生する可能性がある理由を示します。<ul><li>実稼動環境用のフィードファイル（100行など）をアップロードしました。</li><li>フィードは、それらの行のうち80行を実行してアップロードし、誤った書式設定、フィールドが文字を超えているなどの理由で20行をドロップしました。</li><li>フィードはUIで成功とマークされ、100行がすべてアップロードされたという印象を与えます。</li><li>これらの20の製品のいくつかをアクティビティの配信に期待していますが、実行されていません。</li><li> 該当する製品の製品詳細を含むフィードをアップロードしたので、この時点で戸惑います。 Entity APIを介してクエリを実行すると、バックエンドに表示されません。これは、バックエンドにないことを示します。</li></ul>この混乱を取り除くために、メッセージはフィードで何が起こったのかを正確に伝えるために改善されます。 成功としてマークするのではなく、部分的な読み込みに失敗としてマークされるようになりました。 |
| [!UICONTROL  インデックスを作成できませんでした] | インデックス操作が失敗しました。 再試行する。 |
| [!UICONTROL  サーバーが見つかりません] | FTP または URL の場所が無効か、そうでなければ到達不能です。 |

フィードを更新するには（例えば、フィード構成やフィードファイルを変更する場合など）、フィードを開き、必要な変更をおこなってから、「**[!UICONTROL 保存]**」をクリックします。

>[!IMPORTANT]
>
>アップロードしたエンティティは 61 日後に有効期限切れになります。 つまり、レコメンデーションのアクティビティの中断を防ぐために、フィードファイルは少なくとも 60 日ごとにアップロードする必要があります。 フィード ファイル （またはその他のエンティティ更新方法）にアイテムが少なくとも60日ごとに1回含まれていない場合、[!DNL Target]は、アイテムが関連性がなくなったと推測し、カタログから削除します。

### フィードステータスのインジケーター {#section_3C8A236C5CB84C769A9E9E36B8BFABA4}

次のフィードステータスのインジケーターは、[!UICONTROL ステータス]列に表示されます。

| ステータスのインジケーター | 説明 |
|--- |--- |
| 緑のステータスインジケーター | フィードのインデックス作成が正常に完了すると、緑の点でフィードが成功状態にあることを示します。 |
| 黄色のステータスインジケーター | フィードまたはフィードインデックスで、フィードの頻度の 25％の遅れが生じると、黄色い点のステータスインジケーターが表示されます。 例えば、1 日 1 回実行されるフィードのセットで、予定されている時間を 6 時間過ぎてもインデックスが完了していない場合は、黄色い点が表示されます。 注意：フィードのステータスが「索引キュー待ち」になると、新しく更新された値が配信および条件処理で使用できるようになります。 |
| 白のステータスインジケーター | フィードのスケジュールが設定されていない場合は、白の点でフィードがまだ実行されていないことを示します。 |
| 赤のステータスインジケーター | フィードでデータをサーバーにアップロードできない場合は、赤いステータスインジケーターが表示されます。 |

次の例をご覧ください。

**例 1:**

* 初日：午前9:00 （太平洋標準時）の毎日のフィード処理。
* 2日目：午後3時で、フィードは昨日の午前9時から実行されていません。:30:00

インデックスは約 6.5 時間前に実行されているはずだったので、ステータスは黄色になります。 6.5 時間 +24 はフィード期間の 127％です。

**例 2:**

* 1月1日：PSTの午前9:00時に月次フィード処理を行います。
* 2月3日：午前10時:00で、フィードが1か月、1日、1時間前に実行されていません。

インデックスは約 1 日と 1 時間前に実行されているはずだったので、ステータスは黄色になります。 これは、わずか（31+（1/25））/30 = 1.03％の頻度設定にもかかわらず、1 日の遅延の最大値を上回ります。

## トレーニングビデオ

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### Recommendations （3:01）のフィードについて![概要バッジ ](/help/main/assets/overview.png)

このビデオには、次の情報が含まれています。

* フィードの目的の説明
* フィードの値の説明

>[!VIDEO](https://video.tv.adobe.com/v/27695)

### フィードの作成（6:44） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* フィードの設定
* 使用するフィードのタイプの説明

>[!VIDEO](https://video.tv.adobe.com/v/27696)
