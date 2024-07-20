---
keywords: コンテンツ;アセット;コンテンツの管理;オファー;アセットの管理;選択モードを入力;選択モード
description: オファーライブラリを使用して、コードおよび画像オファーを管理する方法を説明します。
title: コードと画像オファーの管理方法
feature: Experiences and Offers
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: 5d14dfd700cb1cec0fa62f66da1400bc8d7fd109
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 17%

---

# オファー

[!DNL Adobe Target] の [!UICONTROL Offers] ライブラリを使用して、コードと画像オファーのコンテンツを管理します。

>[!NOTE]
>
>この記事では、現在Beta プログラムの一部である [!DNL Target] ユーザーインターフェイスのアップデートについて説明します。 [!DNL Adobe Target] チームは、多くの場合、テストやフィードバックの目的で、一部のお客様に対して新機能を有効にします。 テスト期間が完了すると、これらの機能は今後の [!DNL Target Standard/Premium] リリースですべてのお客様に対して有効になり、リリースノートで発表されます。

[!DNL Target] UI の上部にある「**[!UICONTROL Offers]**」タブをクリックして、[!UICONTROL Offers] ライブラリを表示します。

![Adobe Targetのオファーライブラリ ](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

[!UICONTROL Offers] ライブラリには、[!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] （AEM）、[!DNL Adobe Mobile Services] （AMS）および API を使用して設定されたオファーが含まれています。 [!DNL Target Classic] またはその他のソリューションで作成されたオファーは [!DNL Target Standard/Premium] で編集可能です。

オファーライブラリを使用すると、すべてのコードおよび画像オファーの概要を把握し、様々なアクションを実行できます。

| 要素 | 説明 |
|--- |--- |
| 左側のナビゲーションパネル | リストの [!UICONTROL Code Offers] または [!UICONTROL Image Offers] を切り替えます。 |
| [!UICONTROL Show filters] アイコン<P>![ フィルターアイコンを表示 ](/help/main/c-activities/assets/show-filters-icon.png) | **[!UICONTROL Show filters]** アイコンをクリックして、[!UICONTROL Type]、[!UICONTROL Source]、[!UICONTROL AEM Type] でオファーをフィルタリングします<P>詳しくは、以下の [ オファーリストにフィルターを適用 ](#filters) を参照してください。 |
| 検索フィールド | **[!UICONTROL Search in]** のフィールドを使用すると、オファーをすばやく検索したり、[!UICONTROL Offers] ライブラリに表示されるオファーの数を減らしたりできます。 [!UICONTROL Offer Name]、[!UICONTROL AEM Paths] または [!UICONTROL AEM Tags] で検索できます。 |
| [!UICONTROL Create Folder] | 「フォルダーを作成」をクリックして、[!UICONTROL Offer] ライブラリ内にフォルダーを作成します。このフォルダーには、コードオファーや画像オファーだけでなく、サブフォルダー構造を作成するための他のフォルダーも含まれます。 詳しくは、[ オファーフォルダーの作成 ](/help/main/c-experiences/c-manage-content/create-content-folder.md) を参照してください。 |
| [!UICONTROL [!UICONTROL Create Offer]] | オファーを作成します。 様々なオファータイプの作成について詳しくは、以下を参照してください。 <ul><li>HTML オファー</li><li>[JSON オファー ](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[ リダイレクトオファー ](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[ リモートオファー ](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| 一括操作チェックボックス | すべてのアクティビティまたは選択したアクティビティで一括操作を実行します。<P>（権限とオファーのステータスに応じて）使用可能なアクションのリストについては、以下の [ クイックアクションの実行 ](#quick-actions) を参照してください。 |
| [!UICONTROL Name] | 各オファーの名前。<P>各オファー名の横にある「**[!UICONTROL Quick Info]**」アイコンをクリックすると、ポップアップカードにそのオファーに関する詳細情報（オファー ID、タイプ、オファーの最終変更日、変更者など）が表示されます。<p>各オファー名の横にある「**[!UICONTROL More actions]**」アイコン（水平省略記号）をクリックしてメニューを開くと、アクティビティに対してクイックアクションを実行できます。 （権限とオファーのステータスに応じて） [!UICONTROL Edit]、[!UICONTROL Copy]、[!UICONTROL Delete]、[!UICONTROL Move] のアクションを使用できます。 各アクションについて詳しくは、以下の [ クイックアクションの実行 ](#quick-actions) を参照してください。<P>テーブルのヘッダーをクリックすると、名前の昇順または降順でアルファベット順にリストを並べ替えることができます。 |
| [!UICONTROL Type] | オファータイプ：HTMLオファー、[ リダイレクトオファー ](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[ リモートオファー ](/help/main/c-experiences/c-manage-content/about-remote-offers.md)、[JSON オファー ](/help/main/c-experiences/c-manage-content/create-json-offer.md)。 |
| [!UICONTROL Source] | オファーが作成された場所（[!DNL Adobe Target]、[!DNL Adobe Target Classic]、[!DNL Adobe Experience Manager]）を表示します。 |

## オファーライブラリへのフィルターの適用 {#filters}

オファー **[!UICONTROL Show filters]** アイコン（![ オファーページにフィルターを表示アイコン ](/help/main/c-experiences/c-manage-content/assets/show-filters-icon.png)）をクリックして、オファーを [!UICONTROL Type]、[!UICONTROL Source]、[!UICONTROL AEM Type] でフィルタリングします。

![offers_filter 画像 ](assets/offers-filter-new.png)

**[!UICONTROL Show filters]** のアイコンを使用すると、次のカテゴリでオファーをフィルタリングできます。

* **タイプ**:HTMLオファー、[JSON オファー ](/help/main/c-experiences/c-manage-content/create-json-offer.md)、[ リダイレクトオファー ](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[ リモートオファー ](/help/main/c-experiences/c-manage-content/about-remote-offers.md)。

* **Source**: [!DNL Adobe Target]、[!DNL Adobe Target Classic]、および [!DNL Adobe Experience Manager]。

* **AEM タイプ**: [ コンテンツフラグメント ](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) および [ エクスペリエンスフラグメント ](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md)。 様々なフラグメントタイプについて詳しくは、[AEM エクスペリエンスフラグメントおよびコンテンツフラグメントの概要 ](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md) を参照してください。

## クイックアクションの実行 {#quick-actions}

該当するアイコンをクリックして、次のクイックアクションを実行できます。

### クイック情報

各オファー名の横にある「**[!UICONTROL Quick Info]**」アイコンをクリックすると、ポップアップカードにそのオファーに関する詳細情報（オファー ID、タイプ、オファーの最終変更日、変更者など）が表示されます。 使用できるオプションは、オファータイプ（HTMLオファー、[JSON オファー ](/help/main/c-experiences/c-manage-content/create-json-offer.md)、[ リダイレクトオファー ](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[ リモートオファー ](/help/main/c-experiences/c-manage-content/about-remote-offers.md) によって異なります。

![](/help/main/c-experiences/c-manage-content/assets/quick-actions.png)

### その他のアクション

コードオファーと画像オファーで使用できるアクションは、わずかに異なります。 詳しくは以下のセクションで説明されています。

#### [!UICONTROL Code Offer] オプション

各オファー名の横にある「**[!UICONTROL More actions]**」アイコン（水平省略記号）をクリックしてメニューを開くと、アクティビティに対してクイックアクションを実行できます。 （権限とオファーのステータスに応じて） [!UICONTROL Edit]、[!UICONTROL Copy]、[!UICONTROL Delete]、[!UICONTROL Move] のアクションを使用できます。

![Target オファーライブラリの「その他のアクション」オプション ](/help/main/c-experiences/c-manage-content/assets/more-actions.png)

* 編集
* コピー
* 削除
* 移動（例えば、1 つ以上の項目をフォルダーに移動するには、目的の項目の **[!UICONTROL Move]** のアイコンをクリックし、目的のフォルダーをクリックしてから「**[!UICONTROL Drop]**」をクリックします）。

権限によっては、一部のオプションのアイコンが表示されない場合があります。 例えば、[!UICONTROL Observer] の権限を持つユーザーは [!UICONTROL Copy] オプションを使用する権限を持っていません。

オファーおよびフォルダーに対して実行できるタスクについて詳しくは、「[ アセットライブラリのコンテンツの操作 ](/help/main/c-experiences/c-manage-content/assets-working.md)」を参照してください。

#### [!UICONTROL Image Offer] オプション

[!UICONTROL Image Offers] タブで目的の画像オファーまたはフォルダーにカーソルを合わせ、目的のアイコンをクリックして、追加のタスクを実行します。

![ 画像オファーオプション ](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

オプションは以下のとおりです。

* 選択
* ダウンロード
* プロパティを表示
* 編集
* 注釈
* コピー

オファーおよびフォルダーに対して実行できるタスクについて詳しくは、「[ アセットライブラリのコンテンツの操作 ](/help/main/c-experiences/c-manage-content/assets-working.md)」を参照してください。

>[!NOTE]
>
>画像オファーは、「[ エンタープライズユーザー権限 ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) モデルには含まれていません。

## オファー定義の表示 {#section_6B059DD121434E6292CAB393507D010E}

オファーを開かなくても、[!UICONTROL Offers] ライブラリのポップアップカードにオファー定義の詳細を表示できます。

例えば、HTMLオファーに対して次に示すオファー定義カードは、[!UICONTROL Content] ータリストのオファーにマウスポインターを置いてから情報アイコンをクリックしてアクセスします。

![offer-card-html 画像 ](assets/offer-card-html.png)

以下の情報が表示されます。

* 名前
* ソース
* タイプ
* オファー ID
* オファーパス
* 最終変更日

「[!UICONTROL Offer Usage]」タブをクリックして、各オファーの定義ポップアップカードでコードオファーを参照するアクティビティを表示します。 この機能は画像オファーには適用されません。これにより、オファーの編集中に他のアクティビティに影響が及ぶことを防止できます。情報には、[!UICONTROL Live Activities] と [!UICONTROL Inactive Activities] があります。

![ オファーカードの使用状況画像 ](assets/offer-card-usage.png)

以下に示すリダイレクトオファーのオファー定義カードの場合：

![ オファーカードのリダイレクト画像 ](assets/offer-card-redirect.png)

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

![offer-card-remote 画像 ](assets/offer-card-remote.png)

以下の情報が表示されます。

* 名前
* ソース
* タイプ
* オファー ID
* オファーパス
* 最終変更日
* リダイレクト URL のタイプ
* 絶対 URL または相対 URL

## トレーニングビデオ：コンテンツリポジトリ ![ 概要バッジ ](/help/main/assets/overview.png)

このビデオでは、オファーの管理について説明します。

* [Experience Cloud アセットライブラリ](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html)と Target コンテンツライブラリの間の接続
* カスタム HTML オファー
* Visual Experience Composer のカスタム HTML オファー

>[!VIDEO](https://video.tv.adobe.com/v/17387)
