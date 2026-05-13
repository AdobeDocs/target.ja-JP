---
keywords: コンテンツ;アセット;コンテンツの管理;オファー;アセットの管理;選択モードを入力;選択モード
description: '[!UICONTROL Offers] ライブラリを使用して、コードと画像オファーを効率的に管理する方法について説明します。'
title: コードと画像オファーを管理するにはどうすればよいですか？
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
TQID: https://experienceleague.adobe.com/A8ZLHW-FrWHGPJR7P-mhl2pO6SPoDc--LWpFEjtQzBY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 820
ht-degree: 7%

---

# オファー

[!DNL Adobe Target]の[!UICONTROL Offers] ライブラリを使用して、コードと画像オファーを効率的に管理する方法について説明します。

[!UICONTROL Offers] ライブラリを表示するには、[!DNL Target] UIの上部にある「**[!UICONTROL Offers]**」タブをクリックします。

![オファーページ](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

[!UICONTROL Offers] ライブラリには、[!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] （AEM）、[!DNL Adobe Mobile Services] （AMS）およびAPIを介して設定されたオファーが含まれています。 [!DNL Target Classic] またはその他のソリューションで作成されたオファーは [!DNL Target Standard/Premium] で編集可能です。

[!UICONTROL Offers] ライブラリには、すべてのコードと画像オファーの概要が表示され、様々なアクションを実行できます。

| 要素 | 説明 |
|--- |--- |
| 左側のナビゲーションパネル | [!UICONTROL Code Offers]と[!UICONTROL Image Offers]の表示を切り替えます。 |
| [!UICONTROL Show Folders] / [!UICONTROL Hide Folders]<P>![&#x200B; フィルターを表示/フィルターを非表示アイコン &#x200B;](/help/main/assets/icons/RailLeft.svg) | **[!UICONTROL Show Folders]**&#x200B;または&#x200B;**[!UICONTROL Hide Folders]** アイコンをクリックして、オファーフォルダー構造を表示するか、フォルダー構造を表示しないかを切り替えます。<P>詳しくは、[&#x200B; オファーフォルダーの作成](/help/main/c-experiences/c-manage-content/create-content-folder.md)を参照してください。 |
| [!UICONTROL Show filters] アイコン<P>![&#x200B; フィルターアイコンを表示](/help/main/assets/icons/Filter.svg) | **[!UICONTROL Show filters]** アイコンをクリックして、[!UICONTROL Type]、[!UICONTROL Source]、[!UICONTROL AEM Type]でオファーをフィルタリングします。<P>詳しくは、以下の「[&#x200B; オファーリストにフィルターを適用する](#filters)」を参照してください。 |
| フィールドを検索 | **[!UICONTROL Search in]** フィールドを使用して、オファーをすばやく検索したり、[!UICONTROL Offers] ライブラリに表示されるオファーの数を減らしたりします。 [!UICONTROL Offer Name]、[!UICONTROL AEM Paths]または[!UICONTROL AEM Tags]で検索できます。 検索オプションはセッション永続的です。 |
| [!UICONTROL Create Folder] | 「**[!UICONTROL Create Folder]**」をクリックして[!UICONTROL Offer] ライブラリにフォルダーを作成し、コード オファー、画像オファーおよびその他のフォルダーを保持して、サブフォルダー構造を作成します。<P>詳しくは、[&#x200B; オファーフォルダーの作成](/help/main/c-experiences/c-manage-content/create-content-folder.md)を参照してください。 |
| [!UICONTROL [!UICONTROL Create Offer]] | **[!UICONTROL Create Offer]**&#x200B;をクリックしてオファーを作成します。<P>様々なオファータイプの作成について詳しくは、次を参照してください。 <ul><li>HTML オファー</li><li>[JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[&#x200B; リダイレクトオファー](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[&#x200B; リモートオファー](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| 一括操作のチェックボックス<P>![一括操作アイコン &#x200B;](/help/main/assets/icons/Rectangle.svg) | 「[!UICONTROL Bulk Operations]」チェックボックスをクリックして、すべてのオファーまたは選択したオファーに対して一括操作を実行します。<P>使用可能なアクションのリスト（権限とオファーステータスに応じて）については、以下の「[&#x200B; クイックアクションを実行](#quick-actions)」を参照してください。 |
| [!UICONTROL Name] | 各オファーの名前。<P>各オファー名の横にある&#x200B;**[!UICONTROL Quick Info]** アイコン（![&#x200B; クイック情報アイコン &#x200B;](/help/main/assets/icons/InfoOutline.svg)）をクリックして、そのオファーに関する詳細情報（オファーID、種類、オファーの最終変更日、変更者など）をポップアップカードで表示します。<p>各オファー名の横にある&#x200B;**[!UICONTROL More Actions]** アイコン（![詳細アクションアイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックして、アクティビティに対してクイックアクションを実行できるメニューを開きます。 次のアクションを使用できます（権限とオファーステータスに応じて）: [!UICONTROL Edit]、[!UICONTROL Copy]、[!UICONTROL Delete]、および[!UICONTROL Move]。 各アクションについて詳しくは、以下の「[&#x200B; クイックアクションを実行する](#quick-actions)」を参照してください。<P>表ヘッダーをクリックして、リストをアルファベット順に昇順または降順で並べ替えます。 |
| [!UICONTROL Type] | オファータイプ：[!UICONTROL HTML Offers]、[[!UICONTROL Redirect Offers]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL Remote Offers]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)、[[!UICONTROL JSON Offers]](/help/main/c-experiences/c-manage-content/create-json-offer.md)。 |
| [!UICONTROL Source] | オファーが作成された場所を表示します：[!DNL Adobe Target]、[!DNL Adobe Target Classic]、[!DNL Adobe Experience Manager]。 |
| [!UICONTROL Last updated] | オファーが最後に変更された日時と変更者を表示します。<P>表ヘッダーをクリックして、リストを日付ごとに昇順または降順で並べ替えます。 |

## オファーライブラリへのフィルターの適用 {#filters}

**[!UICONTROL Show filters]** アイコン（![&#x200B; オファーページ &#x200B;](/help/main/assets/icons/Filter.svg)の「フィルターを表示」アイコン）をクリックして、[!UICONTROL Type]、[!UICONTROL Source]、および[!UICONTROL AEM Type]でオファーをフィルタリングします。

**[!UICONTROL Show filters]** アイコンを使用すると、次のカテゴリでオファーをフィルタリングできます。

* **[!UICONTROL Type]**: [!UICONTROL HTML Offer]、[[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)、[[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md)。

* **[!UICONTROL Source]**: [!DNL Adobe Target]、[!DNL Adobe Target Classic]、[!DNL Adobe Experience Manager]。

* **AEM Type**: [&#x200B; コンテンツフラグメント &#x200B;](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md)と[&#x200B; エクスペリエンスフラグメント &#x200B;](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md)。 様々なフラグメントタイプについて詳しくは、[AEM エクスペリエンスフラグメントとコンテンツフラグメントの概要](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)を参照してください。

フィルターはセッション永続的です。

## クイックアクションの実行 {#quick-actions}

適切なアイコンをクリックすると、次のクイックアクションを実行できます。

### クイック情報

各オファー名の横にある&#x200B;**[!UICONTROL Quick Info]** アイコン（![&#x200B; クイック情報アイコン &#x200B;](/help/main/assets/icons/InfoOutline.svg)）をクリックして、そのオファーに関する詳細情報（オファーID、種類、オファーの最終変更日、変更者など）をポップアップカードで表示します。 使用可能なオプションは、オファータイプ [!UICONTROL HTML Offer]、[[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md)、[[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)によって異なります。

### その他のアクション

[!UICONTROL Code Offers]と[!UICONTROL Image Offers]で使用できるアクションは、少し異なります。 詳しくは以下のセクションで説明されています。

#### [!UICONTROL Code Offer]個のオプション

各オファー名の横にある&#x200B;**[!UICONTROL More actions]** アイコン（![詳細アクションアイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックして、アクティビティに対してクイックアクションを実行できるメニューを開きます。

次のアクションを使用できます（権限とオファーステータスによって異なります）。

* [!UICONTROL Edit]
* [!UICONTROL Copy]
* [!UICONTROL Delete]
* [!UICONTROL Move] （例えば、1つ以上のアイテムをフォルダーに移動するには、目的のアイテムの横にある&#x200B;**[!UICONTROL Move]**&#x200B;をクリックし、目的のフォルダーをクリックしてから&#x200B;**[!UICONTROL Move]**&#x200B;をクリックします）。

権限によっては、すべてのオプションにアイコンが表示されない場合があります。 例えば、[!UICONTROL Observer]権限を持つユーザーには、[!UICONTROL Copy] オプションを使用する権限がありません。

オファーとフォルダーで実行できるタスクについて詳しくは、[&#x200B; アセットライブラリでのコンテンツの操作](/help/main/c-experiences/c-manage-content/assets-working.md)を参照してください。

#### [!UICONTROL Image Offer]個のオプション

[!UICONTROL Image Offers] タブの目的の画像オファーまたはフォルダーにカーソルを合わせ、目的のアイコンをクリックして、追加のタスクを実行します。

オプションは以下のとおりです。

* [!UICONTROL Select]
* [!UICONTROL Download]
* [!UICONTROL View Properties]
* [!UICONTROL More Actions]
* [!UICONTROL Edit]
* [!UICONTROL Annotate]
* [!UICONTROL Copy]

オファーとフォルダーで実行できるタスクについて詳しくは、[&#x200B; アセットライブラリでのコンテンツの操作](/help/main/c-experiences/c-manage-content/assets-working.md)を参照してください。

>[!NOTE]
>
>画像オファーは、[&#x200B; エンタープライズユーザー権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) モデルの一部ではありません。

## オファー定義の表示 {#section_6B059DD121434E6292CAB393507D010E}

オファーを開かずに[!UICONTROL Offers] ライブラリのポップアップカードでオファー定義の詳細を表示するには、（![&#x200B; クイック情報アイコン &#x200B;](/help/main/assets/icons/InfoOutline.svg)）をクリックします。

以下の情報が表示されます。

* [!UICONTROL Name]
* [!UICONTROL Offer ID]
* [!UICONTROL Type]
* [!UICONTROL Last Modified]

[!UICONTROL View Full Details] リンクをクリックして、各オファーの定義ポップアップカードでコードオファーを参照するオファーの属性とアクティビティを表示します。 この機能は画像オファーには適用されません。 これにより、オファーの編集中に他のアクティビティに影響が及ぶことを防止できます。 情報には、[!UICONTROL Live Activities]と[!UICONTROL Inactive Activities]の詳細が含まれます。
