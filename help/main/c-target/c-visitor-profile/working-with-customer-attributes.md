---
keywords: 顧客関係管理；顧客レコードサービス； crs; crm; mbox3rdpartyid；顧客属性；ターゲット設定； csv; crm; adobe experience cloud people
description: でのコンテンツターゲティングに、顧客関係管理 (CRM) データベースの企業顧客データを使用する方法を説明します。 [!DNL Adobe Target].
title: 顧客属性とは何ですか？それらの使用方法を教えてください。
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1575'
ht-degree: 34%

---

# 顧客属性

でのコンテンツターゲティングに、顧客関係管理 (CRM) データベースの企業顧客データを使用する方法に関する情報 [!DNL Adobe Target] 顧客属性を [!DNL Adobe Enterprise Cloud People] サービス。

複数のソースから収集され、CRM データベース内に保存された企業顧客データを [!DNL Target] を使用すれば、最も関連性の高いコンテンツを再訪問者に絞って戦略的に配信できます。 のオーディエンスと顧客属性 [!DNL People] サービス（以前の Profiles &amp; Audiences）では、データの収集や分析をテストや最適化と組み合わせ、アクションにつながるデータやインサイトを得ることができます。

## 顧客属性の概要 {#section_B4099971FA4B48598294C56EAE86B45A}

[顧客属性](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html) 内 [!DNL People] サービスは [!DNL Adobe Experience Cloud] お客様のデータを [!DNL Experience Cloud] プラットフォーム。

[!DNL Experience Cloud] に転送されたデータは、[!DNL Experience Cloud] のすべてのワークフローで利用できます。[!DNL Target] は、このデータを使用し、属性に基づいて再訪問者をターゲットに設定します。 [!DNL Adobe Analytics] では、これらの属性を分析やセグメント化に使用できます。

![crs の例](/help/main/c-target/c-visitor-profile/assets/crs.png)

顧客属性と [!DNL Target]:

* を使用する前に満たす必要がある前提条件がいくつかあります。 [!UICONTROL 顧客属性] の機能 [!DNL People] サービス。 詳しくは、「顧客属性をアップロードするための前提条件」( [顧客属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) 内 *Experience Cloudサービスと管理に関するドキュメント*.
* ファイルのアップロードに関する制限に注意してください。詳しくは、 [顧客属性のデータファイルおよびデータソースについて](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=ja) 内 *Experience Cloud中央インターフェイスコンポーネントガイド*. ベストプラクティスは次のとおりです。

   * 1 つの大きなファイル ( [指定した制限](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=en)) をクリックします。 複数の小さいファイルよりも、1 つの大きいファイルの方が望ましいです。
   * アップロードを複数のファイルに分割する必要がある場合は、新しいファイルを送信する前に、ファイルが完全に処理されていることを確認してください。 バッチ内の次のファイルを送信する前に、バッチ内の各ファイルが完全に処理されていることを確認します。

* [!DNL Adobe] では、CRM データベースの顧客属性（訪問者プロファイル）データの 100%が [!DNL Experience Cloud] したがって、 [!DNL Target]. 現在の設計では、データのごく一部（大規模な実稼動バッチの 0.1%まで）がオンボーディングされない可能性があります。
* から読み込まれた顧客属性データの有効期間 [!DNL Experience Cloud] から [!DNL Target] 訪問者プロファイルの有効期間に依存します（デフォルトでは 14 日）。 詳しくは、 [訪問者プロファイルの有効期間](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* この `vst.*` 訪問者を識別するのはパラメーターのみで、既存の「認証済み」プロファイルは、 `authState` は未認証 (0) です。 プロファイルは、 `authState` が AUTHENTICATED (1) に変更されます。

   例えば、 `vst.myDataSource.id` パラメーターを使用して訪問者を識別します ( `myDataSource` はデータソースのエイリアスです ) で、パラメーターを使用して MCID またはサードパーティ ID が存在しません `vst.myDataSource.authState=0` は、顧客属性のインポートによって作成された可能性のあるプロファイルを取得しません。 認証済みプロファイルを取得する動作が必要な場合、 `vst.myDataSource.authState` は、値が 1(AUTHENTICATED) である必要があります。

* 送信する `mbox3rdPartyID` には、プラス記号（+）とスラッシュ（/）を含めることはできません。

## People サービスでの顧客属性へのアクセス

1. 内 [!DNL Adobe Experience Cloud]、メニューアイコン ( ![メニューアイコン](/help/main/c-target/c-visitor-profile/assets/menu-icon.png) ) をクリックし、 **[!UICONTROL 人]**.

   ![People](/help/main/c-target/c-visitor-profile/assets/people.png)

1. 次をクリック： **[!UICONTROL 顧客属性]** タブをクリックします。

   ![「顧客属性」タブ](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## の顧客属性のワークフロー [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

[!DNL Target] で CRM データを使用する手順は次の図のとおりです。

![crm ワークフロー](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

次の各タスクを実行する手順について詳しくは、 [顧客属性ソースの作成とデータファイルのアップロード](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html) 内 *Experience Cloudサービスと管理に関するドキュメント*.

1. データファイルを作成します。

   CRM の顧客データを CSV 形式にエクスポートして、.csv ファイルを作成します。アップロード用に zip ファイルまたは gzip ファイルを作成することもできます。CSV ファイルの最初の行がヘッダーであり、すべての行（顧客データ）のエントリ数が同じであることを確認します。

   次の図に、企業顧客データファイルの例を示します。

   ![crs サンプル](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   次の図に、企業顧客の.csv ファイルの例を示します。

   ![csv サンプル](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 属性ソースを作成し、データファイルをアップロードします。

   データソースの名前と説明、エイリアス ID を指定します。エイリアス ID は、 `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >データソース名と属性名にピリオドを含めることはできません。

   使用するデータファイルは、アップロード要件ファイルに準拠し、100 MB を超えないようにする必要があります。 ファイルが大きすぎる場合、または定期的にアップロードする必要があるデータがある場合は、代わりに FTP でファイルを FTP で送信できます。

   * **HTTPS:** .csv データファイルをドラッグ&amp;ドロップするか、 **[!UICONTROL 参照]** をクリックして、ファイルシステムからアップロードします。
   * **FTP:** FTP リンクをクリックして、 [FTP 経由でファイルをアップロード](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). まず、アドビが指定した FTP サーバーのパスワードを入力します。パスワードを指定し、「 **[!UICONTROL 完了]**.

   CSV、ZIP または GZIP ファイルを FTP サーバーに転送します。このファイル転送が正常に完了したら、同じ名前で `.fin` 拡張子。 この空のファイルをサーバーに転送します。これは、転送が終了したことを示し、 [!DNL Experience Cloud] データファイルの処理を開始します。

1. スキーマを検証します。

   検証プロセスでは、アップロードした属性（文字列、整数、数値など）に表示名と説明を設定できます。各属性を適切なデータタイプ、表示名、説明に対応付けます。

   クリック **[!UICONTROL 保存]** スキーマの検証が完了した後。 ファイルのアップロード時間はサイズによって異なります。

   ![スキーマを検証](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![スキーマをアップロード](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. 購読を設定し、属性ソースを有効にします。

   「**[!UICONTROL 購読を追加]**」をクリックして、これらの属性を登録するソリューションを選択します。[購読の設定](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) データフローを [!DNL Experience Cloud] とソリューション 属性ソースを有効化すると、購読しているソリューションでデータが利用できるようになります。アップロードした顧客レコードは、Web サイトまたはアプリケーションから入ってくる ID 信号と照合されます。

   ![ソリューションの設定](/help/main/c-target/c-visitor-profile/assets/solution.png)

   ![アクティブ化](/help/main/c-target/c-visitor-profile/assets/activate.png)

   この手順を実行する際は、次の制限事項に注意してください。

   * HTTP を使用する場合、一度にアップロードできる最大ファイルサイズは 100 MB です。
   * FTP を使用する場合、一度にアップロードできる最大ファイルサイズは 4 GB です。
   * 購読できる属性の数は、[!DNL Target Standard] の場合は 5 個、[!DNL Target Premium] の場合は 200 個です。

## での顧客属性の使用 [!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}

[!DNL Target] で顧客属性を使用する方法は次のとおりです。

### ターゲットオーディエンスを作成する

[!DNL Target] では、オーディエンスの作成時に「訪問者プロファイル」セクションから顧客属性を選択できます。リスト内の顧客属性はすべて先頭に &lt; data_source_name > が付きます。これらの属性を、必要に応じて他のデータ属性と組み合わせることで、オーディエンスを構築します。

![Target オーディエンス](/help/main/c-target/c-visitor-profile/assets/TargetAudience.png)

### トークンを使用してプロファイルスクリプトを作成する

顧客属性をプロファイルスクリプトで参照するときは、`crs.get('<Datasource Name>.<Attribute name>')` 形式を使用できます。

このプロファイルスクリプトはオファーで直接使用し、現在の訪問者に属する属性を配信できます。

### 適切な実装して使用するために Web サイトで mbox3rdPartyID を使用する

パス `mbox3rdPartyId` を、 `targetPageParams()` メソッド。 の値 `mbox3rdPartyId` を CSV データファイルに存在する顧客 ID に設定する必要があります。

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Experience Cloud ID サービスの使用

Experience CloudID サービスを使用している場合、ターゲティングで顧客属性を使用するには、顧客 ID と認証状態を設定する必要があります。 詳しくは、 [顧客 ID と認証状態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) 内 *Experience CloudID サービスヘルプ*.

[!DNL Target] で顧客属性を使用する方法について詳しくは、次のリソースを参照してください。

* [顧客属性ソースの作成とデータファイルのアップロード](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) 内 *Experience Cloudサービスと管理に関するドキュメント*

## よくある問題 {#section_BE0F70E563F64294B17087DE2BC1E74C}

顧客属性と [!DNL Target].

>[!NOTE]
>
>問題 1 と問題 2 は、この領域で約 60%の問題を引き起こします。 問題 3 は、問題の約 30%を引き起こします。 問題 4 は、問題の約 5%を引き起こします。 残りの 5％はその他の原因です。

### 問題 1:プロファイルが大きすぎるので、顧客属性が削除されます

ユーザープロファイルの 1 つのフィールドごとに文字数制限はありません。ただし、プロファイルが 64,000 文字を超えると、64,000 文字を下回るまで最も古い属性から順に削除されて切り詰められます。

### 問題 2:のオーディエンスライブラリに属性が表示されない [!DNL Target]数日後も

その場合は、パイプラインの接続に問題が生じているケースがほとんどです。顧客属性チームにフィードの再発行を依頼してください。

### 問題 3:配信が属性に基づいて動作していません

プロファイルがまだエッジで更新されていません。顧客属性チームにフィードの再発行を依頼してください。

### 問題 4:実装に関する問題

注意を要する実装に関する問題は次のとおりです。

* 訪問者 ID が適切に渡されなかった。ID が渡されました `mboxMCGVID` の代わりに `setCustomerId`.
* 訪問者 ID は適切に渡されたが、認証状態が認証済みに設定されなかった。
* `mbox3rdPartyId` が適切に渡されなかった。

### 問題 5: `mboxUpdate` 適切に実行されない

`mboxUpdate` が `mbox3rdPartyId` で適切に実行されませんでした。

### 問題 6:顧客属性が [!DNL Target]

顧客属性データが Target で見つからない場合は、インポートが *x* 日 *x* は Target です。 [訪問者プロファイルの有効期間](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) の値（デフォルトでは 14 日）。

## トレーニングビデオ：顧客属性を使用したオフラインデータのアップロード ![チュートリアルバッジ](/help/main/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

このビデオでは、CRM、ヘルプデスク、POS（販売時点管理）などのオフラインのマーケティングデータを [!DNL Experience Cloud People] サービスを使用し、既知の ID を使用して訪問者に関連付けます。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
