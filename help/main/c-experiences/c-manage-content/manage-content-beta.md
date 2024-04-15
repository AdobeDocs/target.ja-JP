---
keywords: コンテンツ;アセット;コンテンツの管理;オファー;アセットの管理;選択モードを入力;選択モード
description: オファーライブラリを使用して、コードおよび画像オファーを管理する方法を説明します。
title: コードと画像オファーの管理方法
feature: Experiences and Offers
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: ebce41ea70be81ea0d27abee4b760117cc6ee10c
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 17%

---

# オファー

の使用 [!UICONTROL Offers] のライブラリ [!DNL Adobe Target] を使用してコードと画像オファーのコンテンツを管理します。

>[!NOTE]
>
>この記事には、の更新に関する情報が含まれています [!DNL Target] 現在ベータ版プログラムに含まれているユーザーインターフェイス。 この [!DNL Adobe Target] チームは、多くの場合、一部のお客様に対して、テストやフィードバックの目的で新機能を有効にします。 テスト期間が完了すると、今後、これらの機能はすべての顧客に対して有効になります [!DNL Target Standard/Premium] のリリースとリリースは、リリースノートで発表されました。

「」をクリックします **[!UICONTROL Offers]** 上部のタブ [!DNL Target] を表示する UI [!UICONTROL Offers] ライブラリ。

![Adobe Targetのオファーライブラリ](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

この [!UICONTROL Offers] ライブラリには、を介して設定されたオファーが含まれています [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] （AEM）、 [!DNL Adobe Mobile Services] （AMS）と API のペアです。 [!DNL Target Classic] またはその他のソリューションで作成されたオファーは [!DNL Target Standard/Premium] で編集可能です。

オファーライブラリを使用すると、すべてのコードおよび画像オファーの概要を把握し、様々なアクションを実行できます。

| 要素 | 説明 |
|--- |--- |
| 左側のナビゲーションパネル | リストを切り替え [!UICONTROL Code Offers] または [!UICONTROL Image Offers]. |
| [!UICONTROL Show filters] アイコン<P>![フィルターアイコンを表示](/help/main/c-activities/assets/show-filters-icon.png) | 「」をクリックします **[!UICONTROL Show filters]** オファーをフィルタリングするアイコン [!UICONTROL Type], [!UICONTROL Source]、および [!UICONTROL AEM Type]<P>詳しくは、を参照してください [オファーリストへのフィルターの適用](#filters) 下。 |
| 検索フィールド | の使用 **[!UICONTROL Search in]** オファーをすばやく検索したり、 [!UICONTROL Offers] ライブラリ。 次から検索できます [!UICONTROL Offer Name], [!UICONTROL AEM Paths]、または [!UICONTROL AEM Tags]. |
| [!UICONTROL Create Folder] | 「フォルダーを作成」をクリックして、以下にフォルダーを作成します [!UICONTROL Offer] コードオファー、画像オファーおよびサブフォルダー構造を作成するその他のフォルダーを格納するライブラリ。 詳しくは、を参照してください [オファーフォルダーの作成](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Create Offer]] | オファーを作成します。 様々なオファータイプの作成について詳しくは、以下を参照してください。 <ul><li>HTML オファー</li><li>[JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[リダイレクトオファー](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[リモートオファー](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| 一括操作チェックボックス | すべてのアクティビティまたは選択したアクティビティで一括操作を実行します。<P>使用可能なアクションのリストについては（権限とオファーのステータスに応じて）を参照してください。 [クイックアクションの実行](#quick-actions) 下。 |
| [!UICONTROL Name] | 各オファーの名前。<P>「」をクリックします **[!UICONTROL Quick Info]** 各オファー名の横にあるアイコンをクリックすると、ポップアップカードにそのオファーに関する詳細情報（オファー ID、タイプ、オファーの最終変更日、変更者など）が表示されます。<p>「」をクリックします **[!UICONTROL More actions]** 各オファー名の横にあるアイコン（水平省略記号）をクリックすると、アクティビティに対してクイックアクションを実行できるメニューが開きます。 使用できるアクションは次のとおりです（権限とオファーのステータスによって異なります）。 [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete]、および [!UICONTROL Move]. 各アクションの詳細については、を参照してください [クイックアクションの実行](#quick-actions) 下。<P>テーブルのヘッダーをクリックすると、名前の昇順または降順でアルファベット順にリストを並べ替えることができます。 |
| [!UICONTROL Type] | オファータイプ：HTMLオファー、 [リダイレクトオファー](/help/main/c-experiences/c-manage-content/offer-redirect.md), [リモートオファー](/help/main/c-experiences/c-manage-content/about-remote-offers.md)、および [JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
| [!UICONTROL Source] | オファーが作成された場所を表示します。 [!DNL Adobe Target], [!DNL Adobe Target Classic]、および [!DNL Adobe Experience Manager]. |

## オファーライブラリへのフィルターの適用 {#filters}

「」をクリックします **[!UICONTROL Show filters]** アイコン （ ![オファーページにフィルターアイコンを表示](/help/main/c-experiences/c-manage-content/assets/show-filters-icon.png) ）を使用してオファーをフィルタリングします [!UICONTROL Type], [!UICONTROL Source]、および [!UICONTROL AEM Type].

![offers_filter 画像](assets/offers-filter-new.png)

この **[!UICONTROL Show filters]** アイコンを使用すると、次のカテゴリでオファーをフィルタリングできます。

* **タイプ**:HTMLオファー [JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md), [リダイレクトオファー](/help/main/c-experiences/c-manage-content/offer-redirect.md), [リモートオファー](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

* **ソース**: [!DNL Adobe Target], [!DNL Adobe Target Classic]、および [!DNL Adobe Experience Manager].

* **AEM タイプ**: [コンテンツフラグメント](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) および [エクスペリエンスフラグメント](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). 様々なフラグメントタイプについて詳しくは、 [AEM エクスペリエンスフラグメントおよびコンテンツフラグメントの概要](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## クイックアクションの実行 {#quick-actions}

該当するアイコンをクリックして、次のクイックアクションを実行できます。

### クイック情報

「」をクリックします **[!UICONTROL Quick Info]** 各オファー名の横にあるアイコンをクリックすると、ポップアップカードにそのオファーに関する詳細情報（オファー ID、タイプ、オファーの最終変更日、変更者など）が表示されます。

![](/help/main/c-experiences/c-manage-content/assets/quick-actions.png)

### その他のアクション

「」をクリックします **[!UICONTROL More actions]** 各オファー名の横にあるアイコン（水平省略記号）をクリックすると、アクティビティに対してクイックアクションを実行できるメニューが開きます。 使用できるアクションは次のとおりです（権限とオファーのステータスによって異なります）。 [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete]、および [!UICONTROL Move].

![Target オファーライブラリのその他のアクション オプション](/help/main/c-experiences/c-manage-content/assets/more-actions.png)

* 編集
* コピー
* 削除
* 移動（例えば、1 つ以上の項目を 1 つのフォルダーに移動するには、 **[!UICONTROL Move]** アイコンをクリックします。目的の項目を選択し、 **[!UICONTROL Drop]**.）

権限によっては、一部のオプションのアイコンが表示されない場合があります。 例えば、次を含むユーザー [!UICONTROL Observer] 権限にはを使用する権限がありません [!UICONTROL Copy] オプション。

オファーおよびフォルダーに対して実行できるタスクについて詳しくは、を参照してください。 [アセットライブラリ内のコンテンツの操作](/help/main/c-experiences/c-manage-content/assets-working.md).

の目的の画像オファーまたはフォルダーにカーソルを合わせて、追加のタスクを実行します。 [!UICONTROL Image Offers] タブをクリックしてから、目的のアイコンをクリックします。

![画像オファーオプション](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

オプションは以下のとおりです。

* 選択
* ダウンロード
* プロパティを表示
* 編集
* 注釈
* コピー

オファーおよびフォルダーに対して実行できるタスクについて詳しくは、を参照してください。 [アセットライブラリ内のコンテンツの操作](/help/main/c-experiences/c-manage-content/assets-working.md).

>[!NOTE]
>
>画像オファーはの一部ではありません [Enterprise ユーザーの権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) モデル。

## オファー定義の表示 {#section_6B059DD121434E6292CAB393507D010E}

のポップアップカードにオファー定義の詳細を表示できます [!UICONTROL Offers] オファーを開かないライブラリ。

例えば、HTMLオファーに対して次に示すオファー定義カードには、 [!UICONTROL Content] リストに追加したら、情報アイコンをクリックします。

![offer-card-html 画像](assets/offer-card-html.png)

以下の情報が表示されます。

* 名前
* ソース
* タイプ
* オファー ID
* オファーパス
* 最終変更日

「」をクリックします [!UICONTROL Offer Usage] タブをクリックして、各オファーの定義ポップアップカードでコードオファーを参照するアクティビティを表示します。 この機能は画像オファーには適用されません。これにより、オファーの編集中に他のアクティビティに影響が及ぶことを防止できます。次の情報が含まれます [!UICONTROL Live Activities] および [!UICONTROL Inactive Activities].

![オファーカードの使用状況画像](assets/offer-card-usage.png)

以下に示すリダイレクトオファーのオファー定義カードの場合：

![オファーカードのリダイレクト画像](assets/offer-card-redirect.png)

以下の情報が表示されます。

* 名前
* ソース
* タイプ
* オファー ID
* オファーパス
* 最終変更日
* リダイレクト URL
* すべての URL パラメーターを含める（オンまたはオフ）
* mbox セッション ID を渡す（オンまたはオフ）

以下に示すリモートオファーのオファー定義カードの場合：

![offer-card-remote 画像](assets/offer-card-remote.png)

以下の情報が表示されます。

* 名前
* ソース
* タイプ
* オファー ID
* オファーパス
* 最終変更日
* リダイレクト URL のタイプ
* 絶対 URL または相対 URL

## トレーニングビデオ：コンテンツリポジトリ ![概要バッジ](/help/main/assets/overview.png)

このビデオでは、オファーの管理について説明します。

* [Experience Cloud アセットライブラリ](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html)と Target コンテンツライブラリの間の接続
* カスタム HTML オファー
* Visual Experience Composer のカスタム HTML オファー

>[!VIDEO](https://video.tv.adobe.com/v/17387)
