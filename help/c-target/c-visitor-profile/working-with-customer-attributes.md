---
description: アドビのプロファイルおよびオーディエンスコアサービスの顧客属性を使用して、顧客関係管理（CRM）データベースの企業顧客データを Adobe Target でのコンテンツターゲットに活用する方法について説明します。
keywords: 顧客レコードサービス;crs;crm;mbox3rdpartyid;顧客属性;ターゲット設定
seo-description: アドビのプロファイルおよびオーディエンスコアサービスの顧客属性を使用して、顧客関係管理（CRM）データベースの企業顧客データを Adobe Target でのコンテンツターゲットに活用する方法について説明します。
seo-title: 顧客属性（Adobe Target）
solution: 'Target '
subtopic: 導入
title: 顧客属性
topic: Standard
uuid: fc3c9a02-30d7-43df-838d-10ce1aa17f16
translation-type: tm+mt
source-git-commit: 8ec84183de4c5a7c2a7a1f30e0196cd021ce937f

---


# 顧客属性 {#customer-attributes}

Information about using enterprise customer data from a customer relationship management (CRM) databases for content targeting in [!DNL Adobe Target] by using customer attributes in the [!DNL Adobe Enterprise Cloud] core service.

複数のソースから収集し、CRM データベースに保管されている企業顧客データを [!DNL Target] で使用することで、最も関連性の高いコンテンツを再訪問者に絞って戦略的に配信できます。[!DNL Audiences] コアサービス（以前の Profiles &amp; Audiences）では、データの収集や分析をテストや最適化と組み合わせることで、アクションにつながるデータやインサイトを得ることができます。

## Customer attributes overview {#section_B4099971FA4B48598294C56EAE86B45A}

The Audiences core service is part of the [!DNL Adobe Experience Cloud] and provides enterprises a tool to push their customer data to the [!DNL Experience Cloud] platform. [!DNL Experience Cloud] に転送されたデータは、[!DNL Experience Cloud] のすべてのワークフローで利用できます。[!DNL Target] 属性に基づいて再訪顧客をターゲット設定する場合に、このデータを使用します。 [!DNL Adobe Analytics] では、これらの属性を分析やセグメント化に使用できます。

![](assets/crs.png)

Consider the following information as your work with customer attributes and [!DNL Target]:

* There are some prerequisite requirements that you must meet before you can use the [!UICONTROL Customer attributes] feature in the [!DNL Audiences] core service. For more information, see "Prerequisites for uploading Customer Attributes" in [Customer attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) in the *Experience Cloud Product documentation*.

   >[!NOTE]
   >
   >[!DNL at.js] （任意のバージョン）または [!DNL mbox.js] バージョン58以降が必要です。

* Adobe does not guarantee that 100% of customer attribute (visitor profile) data from CRM databases will be onboarded to the [!DNL Experience Cloud] and, thus, be available for use for targeting in [!DNL Target]. 現在の設計では、データのごく一部が転送されない可能性があります。
* The lifetime of customer attributes data imported from the [!DNL Experience Cloud] to [!DNL Target] depends on the lifetime of the visitor profile, which is 14 days by default. For more information, see Visitor Profile Lifetime.[](../../c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)
* If the `vst.*` parameters are the only thing identifying the visitor, the existing "authenticated" profile will not be fetched as long as `authState` is UNAUTHENTICATED (0). 認証済みプロファイルは、`authState` が UNAUTHENTICATED（1）に変わったときに取得されます。

   For example, if the `vst.myDataSource.id` parameter is used to identify the visitor (where `myDataSource` is the data source alias) and there is no MCID or third-party ID, using the parameter `vst.myDataSource.authState=0` won't fetch the profile that might have been created through a Customer Attributes import. 認証済みプロファイルを取得する動作が必要であれば、`vst.myDataSource.authState` の値が 1（AUTHENTICATED）になっている必要があります。

* 送信する `mbox3rdPartyID` には、プラス記号（+）とスラッシュ（/）を含めることはできません。

## Customer attribute workflow for Target {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

[!DNL Target] で CRM データを使用する手順は次の図のとおりです。

![](assets/crm_workflow.png)

Detailed instructions for completing each of the following tasks can be found in [Create a customer attribute source and upload the data file](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html) in the *Experience Cloud Product Documentation*.

1. データファイルを作成します。

   CRM の顧客データを CSV 形式にエクスポートして、.csv ファイルを作成します。アップロード用に zip ファイルまたは gzip ファイルを作成することもできます。Ensure that first row of the CSV file is the header and all rows (customer data) have the same number of entries.

   ![](assets/CRS_sample.png)

   ![](assets/CRS_CSV_sample.png)

1. 属性ソースを作成し、データファイルをアップロードします。

   データソースの名前と説明、エイリアス ID を指定します。The alias Id is a unique ID to be used in your Customer Attribute code in `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >データソース名と属性名にピリオドを含めることはできません。

   HTTP メソッドを使用して最大 100 MB のデータファイルをアップロードできます。100 MBを超えるファイル（最大4 GB）は、FTPを使用してアップロードできます。

   * **** HTTPS:.csvデータファイルをドラッグ&amp;ドロップするか、「参照」をクリックして **[!UICONTROL ファイル]** ・システムからアップロードできます。
   * **** FTP:FTPリンクをクリックして、FTP [経由でファイルをアップロードします](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-upload-attributes-ftp.html)。 まず、アドビが指定した FTP サーバーのパスワードを入力します。Specify the password, then click **[!UICONTROL Done]**.

      CSV、ZIP または GZIP ファイルを FTP サーバーに転送します。このファイル転送が正常に完了したら、同じ名前と拡張子.finを持つ新しいファイルを作成します。 この空のファイルをサーバーに転送します。This indicates a End Of Transfer and the [!DNL Experience Cloud] starts to process the data file.

1. スキーマを検証します。

   検証プロセスでは、アップロードした属性（文字列、整数、数値など）に表示名と説明を設定できます。各属性を適切なデータタイプ、表示名、説明に対応付けます。

   Click **[!UICONTROL Save]** after the schema validation is complete. ファイルのアップロード時間はサイズによって異なります。

   ![](assets/SchemaValidate.png)

   ![](assets/upload1.png)

1. 購読を設定し、属性ソースを有効にします。

   「**[!UICONTROL 購読を追加]**」をクリックして、これらの属性を登録するソリューションを選択します。[Configure subscriptions](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html) sets up the data flow between the [!DNL Experience Cloud] and solutions. 属性ソースを有効化すると、購読しているソリューションでデータが利用できるようになります。アップロードした顧客レコードは、Web サイトまたはアプリケーションから入ってくる ID 信号と照合されます。

   ![](assets/solution.png)

   ![](assets/activate.PNG)

   この手順を実行する際は、次の制限事項に注意してください。

   * HTTP を使用する場合、一度にアップロードできる最大ファイルサイズは 100 MB です。
   * FTP を使用する場合、一度にアップロードできる最大ファイルサイズは 4 GB です。
   * 購読できる属性の数は、[!DNL Target Standard] の場合は 5 個、[!DNL Target Premium] の場合は 200 個です。

##  Target での顧客属性の使用{#section_107E3A0F0EC7478E82E6DBD17B30B756}

[!DNL Target] で顧客属性を使用する方法は次のとおりです。

### ターゲットオーディエンスを作成する

[!DNL Target] では、オーディエンスの作成時に「訪問者プロファイル」セクションから顧客属性を選択できます。リスト内の顧客属性はすべて先頭に &lt; data_source_name &gt; が付きます。これらの属性を、必要に応じて他のデータ属性と組み合わせることで、オーディエンスを構築します。

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

* [顧客属性ソースを作成し、](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html)*Experience cloud製品ドキュメントにデータファイルをアップロードします。*
* *Digital Marketing ブログ*&#x200B;の[顧客属性：情報が増えるほどつながりが強くなる](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/)

## Issues frequently encountered by customers {#section_BE0F70E563F64294B17087DE2BC1E74C}

顧客属性と [!DNL Target] を使用する際に次の問題が発生することがあります。

| 問題 | 詳細 |
|--- |--- |
| プロファイルが大きすぎることが原因で顧客属性が削除される | ユーザープロファイルの 1 つのフィールドごとに文字数制限はありません。ただし、プロファイルが 64,000 文字を超えると、64,000 文字を下回るまで最も古い属性から順に削除されて切り詰められます。 |
| 数日間経っても [!DNL Target] のオーディエンスライブラリに属性が表示されない | その場合は、パイプラインの接続に問題が生じているケースがほとんどです。顧客属性チームにフィードの再発行を依頼してください。 |
| 属性に基づく配信が適切に機能しない | プロファイルがまだエッジで更新されていません。顧客属性チームにフィードの再発行を依頼してください。 |
| 実装に関する問題 | 注意を要する実装に関する問題は次のとおりです。<ul><li>訪問者 ID が適切に渡されなかった。The ID was passed in `mboxMCGVID` instead of `setCustomerId`.</li><li>訪問者 ID は適切に渡されたが、認証状態が認証済みに設定されなかった。</li><li>`mbox3rdPartyId` が適切に渡されなかった。</li> |
| `mboxUpdate` が適切に実行されない | `mboxUpdate` が `mbox3rdPartyId` で適切に実行されませんでした。 |
| 顧客属性がTargetにインポートされない | If you cannot find Customer Attributes data in Target, ensure that the import occurred within the last *x* days where *x* is the Target [Visitor Profile Lifetime](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) value (14 days by default). |

この領域の問題の約 60％は、上記の 1 行目と 2 行目が原因です。問題の約 30％は 3 行目が原因、約 5％は 4 行目が原因です。残りの 5％はその他の原因です。

## トレーニングビデオ：顧客属性を使用したオフラインデータのアップロード {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

このビデオでは、CRM、ヘルプデスク、POS などのオフラインのマーケティングデータを Experience Cloud の People サービスにインポートし、既知の ID を使用して訪問者に関連付ける方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/?captions=jpn)
