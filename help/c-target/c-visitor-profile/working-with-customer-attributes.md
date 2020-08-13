---
keywords: customer relationship management;customer record service;crs;crm;mbox3rdpartyid;customer attributes;targeting;csv;crm;adobe experience cloud people
description: Adobe Experience Cloud の People コアサービスの顧客属性を使用して、顧客関係管理（CRM）データベースの企業顧客データを Adobe Target でのコンテンツターゲットに活用する方法について説明します。
title: Adobe Targetの顧客属性
feature: visitor profiles
subtopic: Getting Started
topic: Standard
uuid: fc3c9a02-30d7-43df-838d-10ce1aa17f16
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '1508'
ht-degree: 39%

---


# 顧客属性 {#customer-attributes}

Information about using enterprise customer data from Customer Relationship Management (CRM) databases for content targeting in [!DNL Adobe Target] by using customer attributes in the [!DNL Adobe Enterprise Cloud People] core service.

Enterprise customer data collected through multiple sources and stored inside CRM databases can be used in [!DNL Target] to strategically deliver the most relevant content to customers, specifically focusing on returning customers. Audiences and customer attributes in the [!DNL People] core service (formerly Profiles and Audiences) brings together data collection and analysis with testing and optimization, making data and insights actionable.

## Customer attributes overview {#section_B4099971FA4B48598294C56EAE86B45A}

[コアサービスの顧客属性](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) (Customer Attributes [!DNL People] in the [!DNL Adobe Experience Cloud] Core Service)は、の一部で [!DNL Experience Cloud] あり、企業は顧客データをプラットフォームにプッシュするためのツールを提供します。

[!DNL Experience Cloud] に転送されたデータは、[!DNL Experience Cloud] のすべてのワークフローで利用できます。[!DNL Target] このデータは、属性に基づいて再顧客をターゲティングするために使用されます。 [!DNL Adobe Analytics] では、これらの属性を分析やセグメント化に使用できます。

![crsの例](/help/c-target/c-visitor-profile/assets/crs.png)

Consider the following information as your work with customer attributes and [!DNL Target]:

* There are some prerequisite requirements that you must meet before you can use the [!UICONTROL Customer attributes] feature in the [!DNL People] core service. For more information, see &quot;Prerequisites for uploading Customer Attributes&quot; in [Customer attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) in the *Experience Cloud and Core Services Product documentation*.

   >[!NOTE]
   >
   >[!DNL at.js] （任意のバージョン）または [!DNL mbox.js] バージョン58以降が必要です。

* [!DNL Adobe] は、CRMデータベースの顧客属性(訪問者プロファイル)データの100%がに接続され、でのターゲティングに使用でき [!DNL Experience Cloud] ることを保証しません [!DNL Target]。 現在の設計では、小さな割合のデータ（大規模な生産バッチの0.1 %まで）はオンボードされない可能性があります。
* The lifetime of customer attributes data imported from the [!DNL Experience Cloud] to [!DNL Target] depends on the lifetime of the visitor profile, which is 14 days by default. 詳しくは、「 [訪問者プロファイルの有効期間](../../c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)」を参照してください。
* If the `vst.*` parameters are the only thing identifying the visitor, the existing &quot;authenticated&quot; profile will not be fetched as long as `authState` is UNAUTHENTICATED (0). The profile will come into play only if `authState` is changed to AUTHENTICATED (1).

   For example, if the `vst.myDataSource.id` parameter is used to identify the visitor (where `myDataSource` is the data source alias) and there is no MCID or third-party ID, using the parameter `vst.myDataSource.authState=0` won&#39;t fetch the profile that might have been created through a Customer Attributes import. If the desired behavior is to fetch the authenticated profile, the `vst.myDataSource.authState` must have the value of 1 (AUTHENTICATED).

* 送信する `mbox3rdPartyID` には、プラス記号（+）とスラッシュ（/）を含めることはできません。

## Peopleコアサービスでの顧客属性へのアクセス

1. で、メニューアイコン( [!DNL Adobe Experience Cloud]メニューアイコン ![)をクリックし、「](/help/c-target/c-visitor-profile/assets/menu-icon.png) 人 ****」をクリックします。

   ![People](/help/c-target/c-visitor-profile/assets/people.png)

1. 「 **[!UICONTROL 顧客属性]** 」タブをクリックします。

   ![「Customer Attributes」タブ](/help/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Customer attribute workflow for Target {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

[!DNL Target] で CRM データを使用する手順は次の図のとおりです。

![crmワークフロー](/help/c-target/c-visitor-profile/assets/crm_workflow.png)

Detailed instructions for completing each of the following tasks can be found in [Create a customer attribute source and upload the data file](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html) in the *Experience Cloud and Core Services Product Documentation*.

1. データファイルを作成します。

   CRM の顧客データを CSV 形式にエクスポートして、.csv ファイルを作成します。アップロード用に zip ファイルまたは gzip ファイルを作成することもできます。CSVファイルの最初の行をヘッダーにし、すべての行（顧客データ）のエントリ数が同じであることを確認します。

   次の図に、企業顧客データファイルの例を示します。

   ![crsサンプル](/help/c-target/c-visitor-profile/assets/CRS_sample.png)

   次の図に、企業顧客の.csvファイルの例を示します。

   ![csvサンプル](/help/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 属性ソースを作成し、データファイルをアップロードします。

   データソースの名前と説明、エイリアス ID を指定します。The alias Id is a unique ID to be used in your Customer Attribute code in `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >データソース名と属性名にピリオドを含めることはできません。

   使用するデータファイルは、ファイルのアップロード要件に準拠し、100 MBを超えないようにする必要があります。 ファイルが大きすぎる場合や、定期的にアップロードする必要のあるデータがある場合は、FTP経由でファイルをアップロードできます。

   * **HTTPS:** .csvデータファイルをドラッグ&amp;ドロップするか、「 **[!UICONTROL 参照]** 」をクリックしてファイルシステムからアップロードできます。
   * **FTP:** 「FTP」リンクをクリックして、FTP経由でファイルを [アップロードします](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-upload-attributes-ftp.html)。 まず、アドビが指定した FTP サーバーのパスワードを入力します。Specify the password, then click **[!UICONTROL Done]**.

   CSV、ZIP または GZIP ファイルを FTP サーバーに転送します。このファイル転送が正常に完了したら、同じ名前と拡張子.finを持つ新しいファイルを作成します。 この空のファイルをサーバーに転送します。This indicates a End Of Transfer and the [!DNL Experience Cloud] starts to process the data file.

1. スキーマを検証します。

   検証プロセスでは、アップロードした属性（文字列、整数、数値など）に表示名と説明を設定できます。各属性を適切なデータタイプ、表示名、説明に対応付けます。

   Click **[!UICONTROL Save]** after the schema validation is complete. ファイルのアップロード時間はサイズによって異なります。

   ![スキーマの検証](/help/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![アップロードスキーマ](/help/c-target/c-visitor-profile/assets/upload1.png)

1. 購読を設定し、属性ソースを有効にします。

   「**[!UICONTROL 購読を追加]**」をクリックして、これらの属性を登録するソリューションを選択します。[「購読の設定](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html) 」では、とソリューション間のデータフロー [!DNL Experience Cloud] を設定します。 属性ソースを有効化すると、購読しているソリューションでデータが利用できるようになります。アップロードした顧客レコードは、Web サイトまたはアプリケーションから入ってくる ID 信号と照合されます。

   ![ソリューションの設定](/help/c-target/c-visitor-profile/assets/solution.png)

   ![アクティブ化](/help/c-target/c-visitor-profile/assets/activate.png)

   この手順を実行する際は、次の制限事項に注意してください。

   * HTTP を使用する場合、一度にアップロードできる最大ファイルサイズは 100 MB です。
   * FTP を使用する場合、一度にアップロードできる最大ファイルサイズは 4 GB です。
   * 購読できる属性の数は、[!DNL Target Standard] の場合は 5 個、[!DNL Target Premium] の場合は 200 個です。

##  Target での顧客属性の使用{#section_107E3A0F0EC7478E82E6DBD17B30B756}

[!DNL Target] で顧客属性を使用する方法は次のとおりです。

### ターゲットオーディエンスを作成する

[!DNL Target] では、オーディエンスの作成時に「訪問者プロファイル」セクションから顧客属性を選択できます。リスト内の顧客属性はすべて先頭に &lt; data_source_name > が付きます。これらの属性を、必要に応じて他のデータ属性と組み合わせることで、オーディエンスを構築します。

![Target オーディエンス](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### トークンを使用してプロファイルスクリプトを作成する

顧客属性をプロファイルスクリプトで参照するときは、`crs.get('<Datasource Name>.<Attribute name>')` 形式を使用できます。

このプロファイルスクリプトはオファーで直接使用し、現在の訪問者に属する属性を配信できます。

### 適切な実装して使用するために Web サイトで mbox3rdPartyID を使用する

Pass `mbox3rdPartyId` as a parameter to the global mbox inside the `targetPageParams()` method. The value of `mbox3rdPartyId` should be set to the customer ID that was present in the CSV data file.

```
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Experience Cloud ID サービスの使用

Experience Cloud ID サービスを使用する場合は、ターゲット設定で顧客属性を使用するために、顧客 ID と認証状態を設定する必要があります。For more information, see [Customer IDs and Authentication State](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html) in the *Experience Cloud Identity Service Help*.

[!DNL Target] で顧客属性を使用する方法について詳しくは、次のリソースを参照してください。

* [顧客属性ソースの作成と、](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html)*Experience Cloud製品ドキュメントでのデータファイルのアップロード*
* *Digital Marketing ブログ*&#x200B;の[顧客属性：情報が増えるほどつながりが強くなる](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/)

## Issues frequently encountered by customers {#section_BE0F70E563F64294B17087DE2BC1E74C}

You might encounter the following issues when working with customer attributes and [!DNL Target].

>[!NOTE]
>
>問題1と問題2は、この領域で約60%の問題を引き起こします。 問題3は、約30%の問題を引き起こします。 問題4は、問題の約5 %を引き起こします。 残りの 5％はその他の原因です。

### 問題1:プロファイルが大きすぎるため、顧客属性が削除されます。

ユーザープロファイルの 1 つのフィールドごとに文字数制限はありません。ただし、プロファイルが 64,000 文字を超えると、64,000 文字を下回るまで最も古い属性から順に削除されて切り詰められます。

### Issue 2: Attributes not listing in the Audience Library in [!DNL Target], even after several days

その場合は、パイプラインの接続に問題が生じているケースがほとんどです。顧客属性チームにフィードの再発行を依頼してください。

### 問題3:属性に基づいて配信が機能しない

プロファイルがまだエッジで更新されていません。顧客属性チームにフィードの再発行を依頼してください。

### 問題4:導入に関する問題

注意を要する実装に関する問題は次のとおりです。

* 訪問者 ID が適切に渡されなかった。The ID was passed in `mboxMCGVID` instead of `setCustomerId`.
* 訪問者 ID は適切に渡されたが、認証状態が認証済みに設定されなかった。
* `mbox3rdPartyId` が適切に渡されなかった。

### 問題5: `mboxUpdate` 適切に行われない

`mboxUpdate` が `mbox3rdPartyId` で適切に実行されませんでした。

### Issue 6: Customer attributes are not being imported into [!DNL Target]

If you cannot find Customer Attributes data in Target, ensure that the import occurred within the last *x* days where *x* is the Target [Visitor Profile Lifetime](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) value (14 days by default).

## Training video: Upload Offline Data using Customer Attributes {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8} ![Tutorial badge](/help/assets/tutorial.png)

This video shows you how to import offline CRM, help desk, point-of-sale, and other marketing data into the [!DNL Experience Cloud People] service and associate it with visitors using their known IDs.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
