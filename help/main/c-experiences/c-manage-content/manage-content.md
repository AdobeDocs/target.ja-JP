---
keywords: コンテンツ;アセット;コンテンツの管理;オファー;アセットの管理;選択モードを入力;選択モード
description: '[!UICONTROL Offers] ライブラリを使用して、コードと画像オファーを効率的に管理する方法について説明します。'
title: コードと画像オファーを管理するにはどうすればよいですか？
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
TQID: https://experienceleague.adobe.com/A8ZLHW-FrWHGPJR7P-mhl2pO6SPoDc--LWpFEjtQzBY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 958
ht-degree: 8%

---

# オファー

[!DNL Adobe Target]の[!UICONTROL Offers] ライブラリを使用して、コードと画像オファーを効率的に管理する方法について説明します。

[!UICONTROL Offers] ライブラリを表示するには、[!DNL Target] UIの上部にある「**[!UICONTROL Offers]**」タブをクリックします。

![オファーページ](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

[!UICONTROL Offers] ライブラリには、[!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] （AEM）、[!DNL Adobe Mobile Services] （AMS）、およびAPIを介して設定されたオファーが含まれています。 [!DNL Target Classic] またはその他のソリューションで作成されたオファーは [!DNL Target Standard/Premium] で編集可能です。

[!UICONTROL Offers] ライブラリでは、すべてのコードと画像オファーの概要を提供し、様々なアクションを実行できます。

| 要素 | 説明 |
|--- |--- |
| 左側のナビゲーションパネル | [!UICONTROL  コードオファー]または[!UICONTROL 画像オファー]の表示を切り替えます。 |
| [!UICONTROL  フォルダーを表示] / [!UICONTROL  フォルダーを非表示]<P>![ フィルターを表示/フィルターを非表示アイコン ](/help/main/assets/icons/RailLeft.svg) | 「**[!UICONTROL フォルダーを表示]**」または「**[!UICONTROL フォルダーを非表示]**」アイコンをクリックして、オファーフォルダー構造を表示するか、フォルダー構造を表示しないかを切り替えます。<P>詳しくは、[ オファーフォルダーの作成](/help/main/c-experiences/c-manage-content/create-content-folder.md)を参照してください。 |
| [!UICONTROL  フィルターを表示] アイコン<P>![ フィルターアイコンを表示](/help/main/assets/icons/Filter.svg) | **[!UICONTROL フィルターを表示]** アイコンをクリックして、[!UICONTROL Type]、[!UICONTROL Source]、[!UICONTROL AEM Type]でオファーをフィルタリングします。<P>詳しくは、以下の「[ オファーリストにフィルターを適用する](#filters)」を参照してください。 |
| フィールドを検索 | **[!UICONTROL 検索]** フィールドを使用して、オファーをすばやく検索したり、[!UICONTROL  オファー] ライブラリに表示されるオファーの数を減らしたりします。 [!UICONTROL  オファー名]、[!UICONTROL AEM パス ]、または[!UICONTROL AEM タグ ]で検索できます。 検索オプションはセッション永続的です。 |
| [!UICONTROL  フォルダーを作成] | 「**[!UICONTROL フォルダーを作成]**」をクリックして、[!UICONTROL  オファー] ライブラリにフォルダーを作成し、コードオファー、画像オファー、その他のフォルダーを保持してサブフォルダー構造を作成します。<P>詳しくは、[ オファーフォルダーの作成](/help/main/c-experiences/c-manage-content/create-content-folder.md)を参照してください。 |
| [!UICONTROL [!UICONTROL オファーの作成]] | 「**[!UICONTROL オファーを作成]**」をクリックして、オファーを作成します。<P>様々なオファータイプの作成について詳しくは、次を参照してください。 <ul><li>HTML オファー</li><li>[JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[ リダイレクトオファー](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[ リモートオファー](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| 一括操作のチェックボックス<P>![一括操作アイコン ](/help/main/assets/icons/Rectangle.svg) | 「[!UICONTROL 一括操作]」チェックボックスをクリックして、すべてのオファーまたは選択したオファーに対して一括操作を実行します。<P>使用可能なアクションのリスト（権限とオファーステータスに応じて）については、以下の「[ クイックアクションを実行](#quick-actions)」を参照してください。 |
| [!UICONTROL Name] | 各オファーの名前。<P>各オファー名の横にある&#x200B;**[!UICONTROL クイック情報]** アイコン（![ クイック情報アイコン ](/help/main/assets/icons/InfoOutline.svg)）をクリックして、そのオファーに関する詳細情報をポップアップカードで表示します。これには、オファーID、タイプ、オファーの最終変更日、およびオファーの変更日時などが含まれます。<p>各オファー名の横にある&#x200B;**[!UICONTROL その他のアクション]** アイコン （![その他のアクション アイコン ](/help/main/assets/icons/MoreSmallList.svg)）をクリックして、アクティビティに対してクイックアクションを実行できるメニューを開きます。 次のアクションを使用できます（権限とオファーステータスに応じて）。[!UICONTROL 編集]、[!UICONTROL  コピー]、[!UICONTROL 削除]、および[!UICONTROL 移動]。 各アクションについて詳しくは、以下の「[ クイックアクションを実行する](#quick-actions)」を参照してください。<P>表ヘッダーをクリックして、リストをアルファベット順に昇順または降順で並べ替えます。 |
| [!UICONTROL タイプ] | オファータイプ：[!UICONTROL HTML オファー]、[[!UICONTROL  リダイレクトオファー]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL  リモートオファー]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)、および[[!UICONTROL JSON オファー]](/help/main/c-experiences/c-manage-content/create-json-offer.md)。 |
| [!UICONTROL ソース] | オファーが作成された場所を表示します：[!DNL Adobe Target]、[!DNL Adobe Target Classic]、[!DNL Adobe Experience Manager]。 |
| [!UICONTROL 最終更新日] | オファーが最後に変更された日時と変更者を表示します。<P>表ヘッダーをクリックして、リストを日付ごとに昇順または降順で並べ替えます。 |

## オファーライブラリへのフィルターの適用 {#filters}

**[!UICONTROL フィルターを表示]** アイコン（![ オファーページ ](/help/main/assets/icons/Filter.svg)）をクリックして、[!UICONTROL Type]、[!UICONTROL Source]、[!UICONTROL AEM Type]でオファーをフィルタリングします。

**[!UICONTROL フィルターを表示]** アイコンを使用すると、次のカテゴリでオファーをフィルタリングできます。

* **[!UICONTROL 種類]**: [!UICONTROL HTML オファー]、[[!UICONTROL  リダイレクト オファー]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL  リモートオファー]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)、および[[!UICONTROL JSON オファー]](/help/main/c-experiences/c-manage-content/create-json-offer.md)。

* **[!UICONTROL Source]**: [!DNL Adobe Target]、[!DNL Adobe Target Classic]、[!DNL Adobe Experience Manager]。

* **AEM Type**: [ コンテンツフラグメント ](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md)と[ エクスペリエンスフラグメント ](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md)。 様々なフラグメントタイプについて詳しくは、[AEM エクスペリエンスフラグメントとコンテンツフラグメントの概要](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)を参照してください。

フィルターはセッション永続的です。

## クイックアクションの実行 {#quick-actions}

適切なアイコンをクリックすると、次のクイックアクションを実行できます。

### クイック情報

各オファー名の横にある&#x200B;**[!UICONTROL クイック情報]** アイコン（![ クイック情報アイコン ](/help/main/assets/icons/InfoOutline.svg)）をクリックして、そのオファーに関する詳細情報をポップアップカードで表示します。これには、オファーID、タイプ、オファーの最終変更日、およびオファーの変更日時などが含まれます。 使用可能なオプションは、オファータイプによって異なります：[!UICONTROL HTML Offer]、[[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md)、[[!UICONTROL  リダイレクトオファー]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL  リモートオファー]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)。

### その他のアクション

[!UICONTROL  コードオファー]と[!UICONTROL 画像オファー]で使用できるアクションは、わずかに異なります。 詳しくは以下のセクションで説明されています。

#### [!UICONTROL  コードオファー] オプション

各オファー名の横にある&#x200B;**[!UICONTROL その他のアクション]** アイコン（![その他のアクション アイコン ](/help/main/assets/icons/MoreSmallList.svg)）をクリックして、アクティビティに対してクイックアクションを実行できるメニューを開きます。

次のアクションを使用できます（権限とオファーステータスによって異なります）。

* [!UICONTROL Edit]
* [!UICONTROL コピー]
* [!UICONTROL Delete]
* [!UICONTROL 移動] （例えば、1つ以上のアイテムをフォルダーに移動するには、目的のアイテムの横にある&#x200B;**[!UICONTROL 移動]**&#x200B;をクリックし、目的のフォルダーをクリックしてから&#x200B;**[!UICONTROL 移動]**&#x200B;をクリックします）。

権限によっては、すべてのオプションにアイコンが表示されない場合があります。 例えば、[!UICONTROL Observer]権限を持つユーザーには、[!UICONTROL Copy] オプションを使用する権限がありません。

オファーとフォルダーで実行できるタスクについて詳しくは、[ アセットライブラリでのコンテンツの操作](/help/main/c-experiences/c-manage-content/assets-working.md)を参照してください。

#### [!UICONTROL 画像オファー] オプション

[!UICONTROL 画像オファー] タブで目的の画像オファーまたはフォルダーにカーソルを合わせ、目的のアイコンをクリックして、追加のタスクを実行します。

オプションは以下のとおりです。

* [!UICONTROL Select]
* [!UICONTROL ダウンロード]
* [!UICONTROL  プロパティを表示]
* [!UICONTROL その他のアクション ]
* [!UICONTROL Edit]
* [!UICONTROL 注釈]
* [!UICONTROL コピー]

オファーとフォルダーで実行できるタスクについて詳しくは、[ アセットライブラリでのコンテンツの操作](/help/main/c-experiences/c-manage-content/assets-working.md)を参照してください。

>[!NOTE]
>
>画像オファーは、[ エンタープライズユーザー権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) モデルの一部ではありません。

## オファー定義の表示 {#section_6B059DD121434E6292CAB393507D010E}

オファーを開かずに[!UICONTROL Offers] ライブラリのポップアップカードでオファー定義の詳細を表示するには、（![ クイック情報アイコン ](/help/main/assets/icons/InfoOutline.svg)）をクリックします。

以下の情報が表示されます。

* [!UICONTROL Name]
* [!UICONTROL  オファーID]
* [!UICONTROL タイプ]
* [!UICONTROL 最終変更日]

「[!UICONTROL 詳細を表示]」リンクをクリックして、各オファーの定義ポップアップカードでコードオファーを参照するオファーの属性とアクティビティを表示します。 この機能は画像オファーには適用されません。 これにより、オファーの編集中に他のアクティビティに影響が及ぶことを防止できます。 情報には、[!UICONTROL  ライブアクティビティ ]および[!UICONTROL 非アクティブアクティビティ ]の詳細が含まれます。
