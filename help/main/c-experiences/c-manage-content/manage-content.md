---
keywords: コンテンツ;アセット;コンテンツの管理;オファー;アセットの管理;選択モードを入力;選択モード
description: '[!UICONTROL Offers] ライブラリを使用してコードおよび画像オファーを効率的に管理する方法を説明します。'
title: コードと画像オファーの管理方法
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: f3090ad7ab1c3d15de496039e76bb5ec0b02886f
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 7%

---

# オファー

[!DNL Adobe Target] の [!UICONTROL Offers] ライブラリを使用して、コードおよび画像オファーを効率的に管理する方法を説明します。

[!UICONTROL Offers] ライブラリを表示するには、[!DNL Target] UI の上部にある「**[!UICONTROL Offers]**」タブをクリックします。

![オファーページ](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

>[!NOTE]
>
>この記事では、2025 年 1 月 9 日（PT）にリリースされた更新された [!UICONTROL Offers] UI について説明します。 従来の [!UICONTROL Offers] UI を使用する場合は、オンの位置に切り替 [!UICONTROL Switch to the Old Experience] ます。

[!UICONTROL Offers] ライブラリには、[!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] （AEM）、[!DNL Adobe Mobile Services] （AMS）および API を使用して設定されたオファーが含まれています。 [!DNL Target Classic] またはその他のソリューションで作成されたオファーは [!DNL Target Standard/Premium] で編集可能です。

[!UICONTROL Offers] ライブラリは、すべてのコードおよび画像オファーの概要を提供し、様々なアクションを実行できます。

| 要素 | 説明 |
|--- |--- |
| 左側のナビゲーションパネル | [!UICONTROL Code Offers] または [!UICONTROL Image Offers] の表示を切り替えます。 |
| [!UICONTROL Show Folders] / [!UICONTROL Hide Folders]<P>![ フィルターを表示/フィルターアイコンを非表示 ](/help/main/assets/icons/RailLeft.svg) | **[!UICONTROL Show Folders]** アイコンまたは **[!UICONTROL Hide Folders]** アイコンをクリックして、オファーフォルダー構造を表示するか、フォルダー構造を表示しないかを切り替えます。<P>詳しくは、[ オファーフォルダーの作成 ](/help/main/c-experiences/c-manage-content/create-content-folder.md) を参照してください。 |
| [!UICONTROL Show filters] アイコン<P>![ フィルターアイコンを表示 ](/help/main/assets/icons/Filter.svg) | **[!UICONTROL Show filters]** アイコンをクリックして、[!UICONTROL Type]、[!UICONTROL Source]、[!UICONTROL AEM Type] でオファーをフィルタリングします。<P>詳しくは、以下の [ オファーリストにフィルターを適用 ](#filters) を参照してください。 |
| 検索フィールド | **[!UICONTROL Search in]** のフィールドを使用すると、オファーをすばやく検索したり、[!UICONTROL Offers] ライブラリに表示されるオファーの数を減らしたりできます。 [!UICONTROL Offer Name]、[!UICONTROL AEM Paths] または [!UICONTROL AEM Tags] で検索できます。 検索オプションは、セッションで固定されます。 |
| [!UICONTROL Create Folder] | 「**[!UICONTROL Create Folder]**」をクリックして、コードオファー、画像オファーおよびサブフォルダー構造を作成するその他のフォルダーを格納するフォルダーを [!UICONTROL Offer] ライブラリに作成します。<P>詳しくは、[ オファーフォルダーの作成 ](/help/main/c-experiences/c-manage-content/create-content-folder.md) を参照してください。 |
| [!UICONTROL [!UICONTROL Create Offer]] | 「**[!UICONTROL Create Offer]**」をクリックして、オファーを作成します。<P>様々なオファータイプの作成について詳しくは、以下を参照してください。 <ul><li>HTML オファー</li><li>[JSON オファー ](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[ リダイレクトオファー ](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[ リモートオファー ](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| 一括操作チェックボックス<P>![ 一括操作アイコン ](/help/main/assets/icons/Rectangle.svg) | [!UICONTROL Bulk Operations] のチェックボックスをクリックして、すべてのオファーまたは選択したオファーで一括操作を実行します。<P>（権限とオファーのステータスに応じて）使用可能なアクションのリストについては、以下の [ クイックアクションの実行 ](#quick-actions) を参照してください。 |
| [!UICONTROL Name] | 各オファーの名前。<P>各オファー名の横にある **[!UICONTROL Quick Info]** アイコン ![ クイック情報アイコン ](/help/main/assets/icons/InfoOutline.svg)）をクリックすると、ポップアップカードにそのオファーの詳細情報（オファー ID、タイプ、オファーの最終変更日、変更者など）が表示されます。<p>各オファー名の横にある **[!UICONTROL More Actions]** のアイコン ![ その他のアクションアイコン ](/help/main/assets/icons/MoreSmallList.svg)）をクリックしてメニューを開き、アクティビティに対してクイックアクションを実行できます。 （権限とオファーのステータスに応じて） [!UICONTROL Edit]、[!UICONTROL Copy]、[!UICONTROL Delete]、[!UICONTROL Move] のアクションを使用できます。 各アクションについて詳しくは、以下の [ クイックアクションの実行 ](#quick-actions) を参照してください。<P>テーブルのヘッダーをクリックすると、名前の昇順または降順でアルファベット順にリストを並べ替えることができます。 |
| [!UICONTROL Type] | オファータイプ：[!UICONTROL HTML Offers]、[[!UICONTROL Redirect Offers]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL Remote Offers]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)、[[!UICONTROL JSON Offers]](/help/main/c-experiences/c-manage-content/create-json-offer.md)。 |
| [!UICONTROL Source] | オファーが作成された場所（[!DNL Adobe Target]、[!DNL Adobe Target Classic]、[!DNL Adobe Experience Manager]）を表示します。 |
| [!UICONTROL Last updated] | オファーが最後に変更された日時とユーザーを表示します。<P>テーブルのヘッダーをクリックして、日付順で昇順または降順にリストを並べ替えます。 |

## オファーライブラリへのフィルターの適用 {#filters}

オファーのアイコン（![ オファーページのフィルターを表示 ](/help/main/assets/icons/Filter.svg)）をク **[!UICONTROL Show filters]** ックして、オファーを [!UICONTROL Type]、[!UICONTROL Source]、[!UICONTROL AEM Type] でフィルタリングします。

**[!UICONTROL Show filters]** のアイコンを使用すると、次のカテゴリでオファーをフィルタリングできます。

* **[!UICONTROL Type]**:[!UICONTROL HTML Offer]、[[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)、[[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md)。

* **[!UICONTROL Source]**:[!DNL Adobe Target]、[!DNL Adobe Target Classic]、[!DNL Adobe Experience Manager]。

* **AEM タイプ**: [ コンテンツフラグメント ](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) および [ エクスペリエンスフラグメント ](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md)。 様々なフラグメントタイプについて詳しくは、[AEM エクスペリエンスフラグメントおよびコンテンツフラグメントの概要 ](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md) を参照してください。

フィルターは、セッションで固定されます。

## クイックアクションの実行 {#quick-actions}

該当するアイコンをクリックして、次のクイックアクションを実行できます。

### クイック情報

各オファー名の横にある **[!UICONTROL Quick Info]** アイコン ![ クイック情報アイコン ](/help/main/assets/icons/InfoOutline.svg)）をクリックすると、ポップアップカードにそのオファーの詳細情報（オファー ID、タイプ、オファーの最終変更日、変更者など）が表示されます。 使用できるオプションは、オファータイプ（[!UICONTROL HTML Offer]、[[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md)、[[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)）によって異なります。

### その他のアクション

[!UICONTROL Code Offers] で使用できるアクションと [!UICONTROL Image Offers] で使用できるアクションは、多少異なります。 詳しくは以下のセクションで説明されています。

#### [!UICONTROL Code Offer] オプション

各オファー名の横にある **[!UICONTROL More actions]** のアイコン ![ その他のアクションアイコン ](/help/main/assets/icons/MoreSmallList.svg)）をクリックしてメニューを開き、アクティビティに対してクイックアクションを実行できます。

使用できるアクションは次のとおりです（権限とオファーのステータスによって異なります）。

* [!UICONTROL Edit]
* [!UICONTROL Copy]
* [!UICONTROL Delete]
* [!UICONTROL Move] （例えば、1 つ以上の項目をフォルダーに移動するには、目的の項目の横にある「**[!UICONTROL Move]**」をクリックし、目的のフォルダーをクリックして「**[!UICONTROL Move]**」をクリックします。）

権限によっては、一部のオプションのアイコンが表示されない場合があります。 例えば、[!UICONTROL Observer] の権限を持つユーザーは [!UICONTROL Copy] オプションを使用する権限を持っていません。

オファーおよびフォルダーに対して実行できるタスクについて詳しくは、「[ アセットライブラリのコンテンツの操作 ](/help/main/c-experiences/c-manage-content/assets-working.md)」を参照してください。

#### [!UICONTROL Image Offer] オプション

[!UICONTROL Image Offers] タブで目的の画像オファーまたはフォルダーにカーソルを合わせ、目的のアイコンをクリックして、追加のタスクを実行します。

オプションは以下のとおりです。

* [!UICONTROL Select]
* [!UICONTROL Download]
* [!UICONTROL View Properties]
* [!UICONTROL More Actions]
* [!UICONTROL Edit]
* [!UICONTROL Annotate]
* [!UICONTROL Copy]

オファーおよびフォルダーに対して実行できるタスクについて詳しくは、「[ アセットライブラリのコンテンツの操作 ](/help/main/c-experiences/c-manage-content/assets-working.md)」を参照してください。

>[!NOTE]
>
>画像オファーは、「[ エンタープライズユーザー権限 ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) モデルには含まれていません。

## オファー定義の表示 {#section_6B059DD121434E6292CAB393507D010E}

オファーを開かずに、[!UICONTROL Offers] ライブラリのポップアップカードにオファー定義の詳細を表示するには、（![ クイック情報アイコン ](/help/main/assets/icons/InfoOutline.svg)）をクリックします。

以下の情報が表示されます。

* [!UICONTROL Name]
* [!UICONTROL Offer ID]
* [!UICONTROL Type]
* [!UICONTROL Last Modified]

[!UICONTROL View Full Details] リンクをクリックして、各オファーの定義ポップアップカードでコードオファーを参照するオファーの属性とアクティビティを表示します。 この機能は画像オファーには適用されません。これにより、オファーの編集中に他のアクティビティに影響が及ぶことを防止できます。情報には、[!UICONTROL Live Activities] と [!UICONTROL Inactive Activities] の詳細が含まれます。
