---
keywords: 顧客関係管理;顧客レコードサービス;crs;crm;mbox3rdpartyid;顧客属性;ターゲット設定;csv;crm;adobe experience cloud people
description: ' [!DNL Adobe Target] でのコンテンツターゲティングに、顧客関係管理（CRM）データベースの企業顧客データを使用する方法を学びます。'
title: 顧客属性およびその使用方法とは
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 94%

---

# 顧客属性

[!DNL Adobe Enterprise Cloud People] サービスの顧客属性を使用して、顧客関係管理（CRM）データベースの企業顧客データを [!DNL Adobe Target] でのコンテンツターゲティングに活用する方法について説明します。

複数のソースから収集し、CRM データベースに保管されている企業顧客データを [!DNL Target] で使用することで、最も関連性の高いコンテンツを戦略的に配信でき、特に再訪問者に対して効果を発揮します。[!DNL People] サービスのオーディエンスおよび顧客属性（以前のプロファイルおよびオーディエンス）により、データの収集や分析をテストや最適化と組み合わせることで、アクションにつながるデータやインサイトを得ることができます。

## 顧客属性の概要 {#section_B4099971FA4B48598294C56EAE86B45A}

[!DNL People] サービスの[顧客属性](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=ja)は [!DNL Adobe Experience Cloud] の一部であり、 顧客データを [!DNL Experience Cloud] プラットフォームにプッシュするツールを企業に提供します。

[!DNL Experience Cloud] に転送されたデータは、[!DNL Experience Cloud] のすべてのワークフローで利用できます。[!DNL Target] では、このデータを利用し、属性に基づいて再訪問者をターゲティングします。[!DNL Adobe Analytics] では、これらの属性を分析やセグメント化に使用できます。

![CRS の例](/help/main/c-target/c-visitor-profile/assets/crs.png)

顧客属性と [!DNL Target] を使用する際は次の点に注意してください。

* [!UICONTROL Customer attributes] サービスの [!DNL People] 機能を使用するには、いくつかの前提条件を満たしておく必要があります。 詳しくは、*Experience Cloud サービスおよび管理ドキュメント*&#x200B;の[顧客属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=ja#section_BD38693AFBF34926BA28E964963B4EA0)の「顧客属性をアップロードするための前提条件」を参照してください。
* 「*Experience Cloud 中央インターフェイスコンポーネントガイド*」の「[顧客属性のデータファイルとデータソースについて](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=ja)」に記載されている通り、ファイルのアップロードに関する制限についてご注意ください。ベストプラクティスは次のとおりです。

   * 単一の大きなファイル（[指定された制限](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=ja)の範囲内）をアップロードします。複数の小さなファイルよりも、単一の大きなファイルの方が望ましいです。
   * アップロードを複数のファイルに分割する必要がある場合は、新しいファイルを送信する前に、今のファイルが完全に処理されていることを確認してください。バッチ内に次のファイルを送信する前に、バッチ内の各ファイルが完全に処理されていることを確認してください。

* CRM データベースの顧客属性（訪問者プロファイル）データがすべて [!DNL Experience Cloud] に転送され、[!DNL Target] でのターゲティングに利用できることを、[!DNL Adobe] は必ずしも保証するものではありません。現在の設計では、わずかな割合のデータ（大規模な生産バッチの 0.1％以下）はオンボードされない可能性があります。
* [!DNL Experience Cloud] から [!DNL Target] に読み込んだ顧客属性データの有効期間は、訪問者プロファイルの有効期間（デフォルトでは 14 日間）によって決まります。詳しくは、[訪問者プロファイルの有効期間](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)を参照してください。
* `vst.*` が訪問者を特定する唯一のパラメーターである場合は、`authState` が UNAUTHENTICATED (0) である限り、既存の「認証済み」プロファイルが取得されません。プロファイルは、`authState` が AUTHENTICATED (1) に変更された場合のみ利用されます。

  例えば、訪問者の特定に `vst.myDataSource.id` パラメーター（`myDataSource` はデータソースのエイリアス）を使用しており、MCID もサードパーティ ID も存在しない場合には、パラメーター `vst.myDataSource.authState=0` を使用しても、顧客属性インポートにより作成されるなどしたプロファイルが取得されることはありません。認証済みプロファイルを取得する動作が必要であれば、`vst.myDataSource.authState` の値が「1 (AUTHENTICATED)」になっている必要があります。

* 送信する `mbox3rdPartyID` には、プラス記号（+）とスラッシュ（/）を含めることはできません。

## 人物サービスでの顧客属性へのアクセス

1. [!DNL Adobe Experience Cloud] で、メニューアイコン（![&#x200B; メニューアイコン &#x200B;](/help/main/c-target/c-visitor-profile/assets/menu-icon.png)）をクリックしてから **[!UICONTROL People]** をクリックします。

   ![人物](/help/main/c-target/c-visitor-profile/assets/people.png)

1. 「**[!UICONTROL Customer Attributes]**」タブをクリックします。

   ![「顧客属性」タブ](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## [!DNL Target] での顧客属性のワークフロー {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

[!DNL Target] で CRM データを使用する手順は次の図のとおりです。

![CRM ワークフロー](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

次の各タスクを実行する方法について詳しくは、*Experience Cloud サービスおよび管理ドキュメント*&#x200B;の[顧客属性ソースの作成とデータファイルのアップロード](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=ja)を参照してください。

1. データファイルを作成します。

   CRM の顧客データを CSV 形式に書き出して、.csv ファイルを作成します。アップロード用に zip ファイルまたは gzip ファイルを作成することもできます。CSV ファイルの最初の行がヘッダーであり、すべての行（顧客データ）に同じ数のエントリが含まれていることを確認してください。

   次の図に、エンタープライズ顧客データファイルの例を示します。

   ![CRS サンプル](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   次の図に、エンタープライズ顧客の .csv ファイルの例を示します。

   ![CSV サンプル](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 属性ソースを作成し、データファイルをアップロードします。

   データソースの名前と説明、エイリアス ID を指定します。エイリアス ID は、`VisitorAPI.js` の顧客属性コードで使用する一意の ID です。

   >[!IMPORTANT]
   >
   >データソース名と属性名にピリオドを含めることはできません。

   使用するデータファイルは、ファイルのアップロード要件に準拠し、100 MB を超えないようにする必要があります。 ファイルが大きすぎる場合、または定期的にアップロードする必要があるデータがある場合は、代わりに FTP でファイルをアップロードすることができます。

   * **HTTPS:** .csv データファイルをドラッグ&amp;ドロップするか、「**[!UICONTROL Browse]**」をクリックしてファイルシステムからアップロードしてください。
   * **FTP：** FTP リンクをクリックして [FTP 経由でファイルをアップロード](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html?lang=ja)します。まず、アドビが指定した FTP サーバーのパスワードを入力します。パスワードを指定し、「**[!UICONTROL Done]**」をクリックします。

   CSV、ZIP または GZIP ファイルを FTP サーバーに転送します。このファイル転送が正常に完了したら、同じ名前と `.fin` 拡張子の新しいファイルを作成します。この空のファイルをサーバーに転送します。これにより転送が完了したことを示し、[!DNL Experience Cloud] がデータファイルの処理を開始します。

1. スキーマを検証します。

   検証プロセスでは、アップロードした属性（文字列、整数、数値など）に表示名と説明を設定できます。各属性を適切なデータタイプ、表示名、説明に対応付けます。

   スキーマの検証が完了したら、「**[!UICONTROL Save]**」をクリックします。 ファイルのアップロード時間はサイズによって異なります。

   ![スキーマの検証](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![スキーマのアップロード](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. 購読を設定し、属性ソースを有効にします。

   「**[!UICONTROL Add Subscription]**」をクリックして、これらの属性を登録するソリューションを選択します。 [購読の構成](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html?lang=ja)は、[!DNL Experience Cloud] とソリューションの間のデータフローを設定します。属性ソースを有効化すると、購読しているソリューションでデータが利用できるようになります。アップロードした顧客レコードは、Web サイトまたはアプリケーションから入ってくる ID 信号と照合されます。

   ![ソリューションの設定](/help/main/c-target/c-visitor-profile/assets/solution.png)

   ![アクティブ化](/help/main/c-target/c-visitor-profile/assets/activate.png)

   この手順を実行する際は、次の制限事項に注意してください。

   * HTTP を使用する場合、一度にアップロードできる最大ファイルサイズは 100 MB です。
   * FTP を使用する場合、一度にアップロードできる最大ファイルサイズは 4 GB です。
   * 購読できる属性の数は、[!DNL Target Standard] の場合は 5 個、[!DNL Target Premium] の場合は 200 個です。

## [!DNL Target] での顧客属性の使用 {#section_107E3A0F0EC7478E82E6DBD17B30B756}

[!DNL Target] で顧客属性を使用する方法は次のとおりです。

### ターゲットオーディエンスを作成する

[!DNL Target] では、オーディエンスの作成時に「[!UICONTROL Visitor Profile]」セクションから顧客属性を選択できます。 リスト内の顧客属性はすべて接頭辞 &lt; data_source_name > が付きます。これらの属性を、必要に応じて他のデータ属性と組み合わせることで、オーディエンスを構築します。

![Target オーディエンス](/help/main/c-target/c-visitor-profile/assets/TargetAudience.png)

### トークンを使用してプロファイルスクリプトを作成する

顧客属性をプロファイルスクリプトで参照するときは、`crs.get('<Datasource Name>.<Attribute name>')` 形式を使用できます。

このプロファイルスクリプトはオファーで直接使用し、現在の訪問者に属する属性を配信できます。

### 適切な実装して使用するために Web サイトで mbox3rdPartyID を使用する

`mbox3rdPartyId` をパラメーターとして、`targetPageParams()` メソッド内のグローバル mbox に渡します。`mbox3rdPartyId` の値は、CSV データファイルの顧客 ID に設定する必要があります。

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Experience Cloud ID サービスの使用

Experience Cloud ID サービスを使用する場合は、ターゲット設定で顧客属性を使用するために、顧客 ID と認証状態を設定する必要があります。詳しくは、*Experience Cloud ID サービスのヘルプ*&#x200B;で、[顧客 ID と認証状態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=ja)を参照してください。

[!DNL Target] で顧客属性を使用する方法について詳しくは、次のリソースを参照してください。

* *Experience Cloud サービスおよび管理ドキュメント*&#x200B;の[顧客属性ソースの作成とデータファイルのアップロード](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html?lang=ja)

## よくある問題 {#section_BE0F70E563F64294B17087DE2BC1E74C}

顧客属性と [!DNL Target] を使用する際に次の問題が発生することがあります。

>[!NOTE]
>
>この領域の問題の約 60％は、問題 1 と問題 2 が原因です。問題の約 30％は、問題 3 が原因です。問題の約 5％は、問題 4 が原因です。残りの 5％の原因はそれ以外です。

### 問題 1：プロファイルが大きすぎることが原因で顧客属性が削除される

ユーザープロファイルの 1 つのフィールドごとに文字数制限はありません。ただし、プロファイルが 64,000 文字を超えると、64,000 文字を下回るまで最も古い属性から順に削除されて切り詰められます。

### 問題 2：数日間経っても [!DNL Target] のオーディエンスライブラリに属性が表示されない

その場合は、パイプラインの接続に問題が生じているケースがほとんどです。顧客属性チームにフィードの再発行を依頼してください。

### 問題 3：属性に基づく配信が適切に機能しない

プロファイルがまだエッジで更新されていません。顧客属性チームにフィードの再発行を依頼してください。

### 問題 4：実装に関する問題

注意を要する実装に関する問題は次のとおりです。

* 訪問者 ID が適切に渡されなかった。ID が `setCustomerId` ではなく、`mboxMCGVID` で渡された。
* 訪問者 ID は適切に渡されたが、認証状態が認証済みに設定されなかった。
* `mbox3rdPartyId` が適切に渡されなかった。

### 問題 5：`mboxUpdate` が適切に実行されない

`mboxUpdate` が `mbox3rdPartyId` で適切に実行されませんでした。

### 問題 6：顧客属性が [!DNL Target] に読み込まれない

顧客属性データが Target に見つからない場合は、過去 *x* 日以内に読み込みを行ったかどうかを確認してください。ここで *x* は Target の[訪問者プロファイルのライフタイム](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md)値です（デフォルトでは 14 日）。

## トレーニングビデオ：顧客属性![チュートリアルバッジ](/help/main/assets/tutorial.png)を使用してオフラインデータをアップロード {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

このビデオでは、CRM、ヘルプデスク、販売時点（POS）などのオフラインのマーケティングデータを [!DNL Experience Cloud People] サービスにインポートし、訪問者の既知の ID を使用して訪問者に関連付ける方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
