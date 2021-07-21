---
keywords: 顧客関係管理；顧客レコードサービス；crs;crm;mbox3rdpartyid；顧客属性；ターゲティング；csv;crm;adobe experience cloudの人
description: 顧客関係管理(CRM)データベースの企業顧客データを [!DNL Adobe Target]でのコンテンツターゲティングに使用する方法を説明します。
title: 顧客属性とは何ですか？顧客属性の使用方法を教えてください。
feature: オーディエンス
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: c19163020cdcb41a17ea6b65b5b500fadc9c7512
workflow-type: tm+mt
source-wordcount: '1496'
ht-degree: 36%

---

# 顧客属性

[!DNL Adobe Enterprise Cloud People]サービスの顧客属性を使用して、顧客関係管理(CRM)データベースの企業顧客データを[!DNL Adobe Target]でのコンテンツターゲティングに使用する方法について説明します。

複数のソースから収集し、CRMデータベースに格納された企業顧客データを[!DNL Target]で使用して、最も関連性の高いコンテンツを再訪問者に絞って戦略的に配信できます。 [!DNL People]サービス（旧称Profiles &amp; Audiences）のオーディエンスと顧客属性を使用すると、データの収集と分析をテストや最適化と組み合わせ、アクションにつながるデータやインサイトを得ることができます。

## 顧客属性の概要 {#section_B4099971FA4B48598294C56EAE86B45A}

[顧客属](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=ja) 性サービス [!DNL People] は、の一部で [!DNL Adobe Experience Cloud] あり、顧客データをプラットフォームにプッシュするツールを企業に提供 [!DNL Experience Cloud] します。

[!DNL Experience Cloud] に転送されたデータは、[!DNL Experience Cloud] のすべてのワークフローで利用できます。[!DNL Target] は、このデータを使用し、属性に基づいて再訪問者をターゲティングします。[!DNL Adobe Analytics] では、これらの属性を分析やセグメント化に使用できます。

![crsの例](/help/c-target/c-visitor-profile/assets/crs.png)

顧客属性と[!DNL Target]を使用する際は、次の情報を考慮してください。

* [!DNL People]サービスの[!UICONTROL 顧客属性]機能を使用する前に満たす必要がある前提条件がいくつかあります。 詳しくは、*Experience Cloudサービスおよび管理に関するドキュメント*&#x200B;の[顧客属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0)の「顧客属性をアップロードするための前提条件」を参照してください。

   >[!NOTE]
   >
   >[!DNL at.js] （任意のバージョン）または [!DNL mbox.js] バージョン58以降が必要です。

* [!DNL Adobe] は、CRMデータベースの顧客属性（訪問者プロファイル）データの100%がに転送されることを保証しませ [!DNL Experience Cloud] ん。したがって、でのターゲティングに使用でき [!DNL Target]ます。現在の設計では、データのごく一部（大規模な実稼動バッチの最大0.1%）がオンボーディングされない可能性があります。
* [!DNL Experience Cloud]から[!DNL Target]にインポートされた顧客属性データの有効期間は、訪問者プロファイルの有効期間（デフォルトでは14日）に依存します。 詳しくは、[訪問者プロファイルの有効期間](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)を参照してください。
* `vst.*`パラメーターのみが訪問者を識別するものである場合、`authState`がUNAUTHENTICATED (0)である限り、既存の「認証済み」プロファイルは取得されません。 `authState`がAUTHENTICATED (1)に変わった場合にのみ、プロファイルが動作します。

   例えば、`vst.myDataSource.id`パラメーターが訪問者の識別に使用され（`myDataSource`はデータソースエイリアス）、MCIDもサードパーティIDもない場合、パラメーター`vst.myDataSource.authState=0`を使用しても、顧客属性のインポートで作成されたプロファイルは取得されません。 認証済みプロファイルを取得する動作が必要な場合、`vst.myDataSource.authState`の値は1(AUTHENTICATED)にする必要があります。

* 送信する `mbox3rdPartyID` には、プラス記号（+）とスラッシュ（/）を含めることはできません。

## Peopleサービスでの顧客属性へのアクセス

1. [!DNL Adobe Experience Cloud]で、メニューアイコン（ ![メニューアイコン](/help/c-target/c-visitor-profile/assets/menu-icon.png) ）をクリックし、「**[!UICONTROL ユーザー]**」をクリックします。

   ![People](/help/c-target/c-visitor-profile/assets/people.png)

1. 「**[!UICONTROL 顧客属性]**」タブをクリックします。

   ![「顧客属性」タブ](/help/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## [!DNL Target]の顧客属性のワークフロー {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

[!DNL Target] で CRM データを使用する手順は次の図のとおりです。

![crmワークフロー](/help/c-target/c-visitor-profile/assets/crm_workflow.png)

次の各タスクを実行する詳細な手順については、[Experience Cloud属性ソースの作成と&#x200B;*顧客サービスおよび管理に関するドキュメント*&#x200B;のデータファイル](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html)のアップロードを参照してください。

1. データファイルを作成します。

   CRM の顧客データを CSV 形式にエクスポートして、.csv ファイルを作成します。アップロード用に zip ファイルまたは gzip ファイルを作成することもできます。CSVファイルの最初の行がヘッダーであり、すべての行（顧客データ）のエントリ数が同じであることを確認します。

   次の図に、企業顧客データファイルの例を示します。

   ![crsサンプル](/help/c-target/c-visitor-profile/assets/CRS_sample.png)

   次の図に、企業顧客の.csvファイルの例を示します。

   ![csvサンプル](/help/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 属性ソースを作成し、データファイルをアップロードします。

   データソースの名前と説明、エイリアス ID を指定します。エイリアスIDは、`VisitorAPI.js`の顧客属性コードで使用される一意のIDです。

   >[!IMPORTANT]
   >
   >データソース名と属性名にピリオドを含めることはできません。

   データファイルは、アップロード要件ファイルに準拠し、100 MBを超えないようにする必要があります。 ファイルが大きすぎる場合、または定期的にアップロードする必要があるデータがある場合は、代わりにFTPでファイルをアップロードできます。

   * **HTTPS:** .csvデータファイルをドラッグ&amp;ドロップするか、「参照」をクリックして、ファ **** イルシステムからアップロードします。
   * **FTP:** 「FTP」リンクをクリックして、FTP [経由でファイルをアップロードします](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html)。まず、アドビが指定した FTP サーバーのパスワードを入力します。パスワードを指定し、「**[!UICONTROL 完了]**」をクリックします。

   CSV、ZIP または GZIP ファイルを FTP サーバーに転送します。このファイル転送が正常に完了したら、同じ名前で拡張子`.fin`を持つファイルを作成します。 この空のファイルをサーバーに転送します。これは転送が終了したことを示し、 [!DNL Experience Cloud]はデータファイルの処理を開始します。

1. スキーマを検証します。

   検証プロセスでは、アップロードした属性（文字列、整数、数値など）に表示名と説明を設定できます。各属性を適切なデータタイプ、表示名、説明に対応付けます。

   スキーマの検証が完了したら、「**[!UICONTROL 保存]**」をクリックします。 ファイルのアップロード時間はサイズによって異なります。

   ![スキーマの検証](/help/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![スキーマのアップロード](/help/c-target/c-visitor-profile/assets/upload1.png)

1. 購読を設定し、属性ソースを有効にします。

   「**[!UICONTROL 購読を追加]**」をクリックして、これらの属性を登録するソリューションを選択します。[購読を](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) 設定すると、とソリューション間のデータフロー [!DNL Experience Cloud] が設定されます。属性ソースを有効化すると、購読しているソリューションでデータが利用できるようになります。アップロードした顧客レコードは、Web サイトまたはアプリケーションから入ってくる ID 信号と照合されます。

   ![ソリューションの設定](/help/c-target/c-visitor-profile/assets/solution.png)

   ![アクティブ化](/help/c-target/c-visitor-profile/assets/activate.png)

   この手順を実行する際は、次の制限事項に注意してください。

   * HTTP を使用する場合、一度にアップロードできる最大ファイルサイズは 100 MB です。
   * FTP を使用する場合、一度にアップロードできる最大ファイルサイズは 4 GB です。
   * 購読できる属性の数は、[!DNL Target Standard] の場合は 5 個、[!DNL Target Premium] の場合は 200 個です。

## [!DNL Target]での顧客属性の使用 {#section_107E3A0F0EC7478E82E6DBD17B30B756}

[!DNL Target] で顧客属性を使用する方法は次のとおりです。

### ターゲットオーディエンスを作成する

[!DNL Target] では、オーディエンスの作成時に「訪問者プロファイル」セクションから顧客属性を選択できます。リスト内の顧客属性はすべて先頭に &lt; data_source_name > が付きます。これらの属性を、必要に応じて他のデータ属性と組み合わせることで、オーディエンスを構築します。

![Target オーディエンス](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### トークンを使用してプロファイルスクリプトを作成する

顧客属性をプロファイルスクリプトで参照するときは、`crs.get('<Datasource Name>.<Attribute name>')` 形式を使用できます。

このプロファイルスクリプトはオファーで直接使用し、現在の訪問者に属する属性を配信できます。

### 適切な実装して使用するために Web サイトで mbox3rdPartyID を使用する

`mbox3rdPartyId`を`targetPageParams()`メソッド内のグローバルmboxにパラメーターとして渡します。 `mbox3rdPartyId`の値は、CSVデータファイルに存在する顧客IDに設定する必要があります。

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Experience Cloud ID サービスの使用

Experience CloudIDサービスを使用している場合、ターゲティングで顧客属性を使用するには、顧客IDと認証状態を設定する必要があります。 詳しくは、*Experience CloudIDサービスのヘルプ*&#x200B;の[顧客IDと認証状態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)を参照してください。

[!DNL Target] で顧客属性を使用する方法について詳しくは、次のリソースを参照してください。

* [顧客属性ソースの作成とデータファイルのアップロ](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) ード( *Experience Cloudサービスと管理に関するドキュメント)*
* *Digital Marketing ブログ*&#x200B;の[顧客属性：情報が増えるほどつながりが強くなる](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/)

## よくある問題 {#section_BE0F70E563F64294B17087DE2BC1E74C}

顧客属性と[!DNL Target]を使用する際に、次の問題が発生する可能性があります。

>[!NOTE]
>
>問題1と問題2は、この領域で約60%の問題を引き起こします。 問題3は、問題の約30%を引き起こします。 問題4は、問題の約5%を引き起こします。 残りの 5％はその他の原因です。

### 問題1:プロファイルが大きすぎるので、顧客属性が削除されます

ユーザープロファイルの 1 つのフィールドごとに文字数制限はありません。ただし、プロファイルが 64,000 文字を超えると、64,000 文字を下回るまで最も古い属性から順に削除されて切り詰められます。

### 問題2:数日後でも[!DNL Target]のオーディエンスライブラリに属性が表示されない

その場合は、パイプラインの接続に問題が生じているケースがほとんどです。顧客属性チームにフィードの再発行を依頼してください。

### 問題3:配信が属性に基づいて機能しない

プロファイルがまだエッジで更新されていません。顧客属性チームにフィードの再発行を依頼してください。

### 問題4:実装に関する問題

注意を要する実装に関する問題は次のとおりです。

* 訪問者 ID が適切に渡されなかった。IDが`setCustomerId`ではなく`mboxMCGVID`で渡されました。
* 訪問者 ID は適切に渡されたが、認証状態が認証済みに設定されなかった。
* `mbox3rdPartyId` が適切に渡されなかった。

### 問題5:`mboxUpdate`が正しく実行されていません

`mboxUpdate` が `mbox3rdPartyId` で適切に実行されませんでした。

### 問題6:顧客属性が[!DNL Target]に読み込まれません

顧客属性データがTargetに見つからない場合は、インポートを過去&#x200B;*x*&#x200B;日以内におこなったことを確認してください。*x*&#x200B;はTarget [訪問者プロファイルの有効期間](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md)値です（デフォルトで14日）。

## トレーニングビデオ：顧客属性![チュートリアルバッジ](/help/assets/tutorial.png)を使用したオフラインデータのアップロード {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

このビデオでは、オフラインのCRM、ヘルプデスク、POSなどのマーケティングデータを[!DNL Experience Cloud People]サービスにインポートし、既知のIDを使用して訪問者に関連付ける方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
