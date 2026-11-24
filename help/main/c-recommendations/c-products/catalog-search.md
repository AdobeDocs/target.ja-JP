---
keywords: カタログ検索；カタログ；検索；除外；コレクション；フィルター；推奨事項
description: '[!DNL Recommendations] [!UICONTROL &#x200B; カタログ検索]を使用して、商品またはコンテンツを検索する方法、カタログからアイテムを削除する方法などについて説明します。'
title: '[!DNL Recommendations] [!UICONTROL &#x200B; カタログ検索]を使用するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
TQID: 'https://experienceleague.adobe.com/en3hkFsDjEE86Tc-3vPSiZFy0K47SftZMN6RW0INNic'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 3883dc9752db0a2427f70cb3036fe060c440361a
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 10%
---
# [!UICONTROL カタログ検索] {#catalog-search}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、[!DNL Adobe Recommendations]のカタログを検索して商品またはコンテンツを見つける方法と、アイテムをフィルタリング、表示、削除する方法について説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Recommendations]の&#x200B;**[!UICONTROL カタログ検索]** ページは、カタログ内の製品またはコンテンツの検索に使用されます。 このページの最も基本的なタスクは、項目を検索することです。 このページでは、環境の変更、ファセットのフィルタリング、テーブルの列の変更なども可能です。

カタログは、商品セット（エンティティ）全体です。 商品を論理グループで整理する多数のコレクションを含めることができます。

カタログのインデックスは、最初のフィードがアップロードされたときに自動的に作成され、[指定されたスケジュール &#x200B;](/help/main/c-recommendations/c-products/feeds.md#steps)に従って更新されます。

カタログは、フィード ファイル、API、またはmboxの更新を通じて更新を受信すると、自動的に更新されます。 通常、1時間以内に更新が完了します。 更新が進行中の場合、最も新しく更新を開始した時間が表示されます。 更新が進行中でない場合、最も新しく更新を開始および終了した時間が表示されます。

## カタログを検索

検索結果を使用してカタログ内のアイテムを確認し、必要に応じてカタログからアイテムを削除します。

1. **[!UICONTROL Recommendations]** > **[!UICONTROL カタログ検索]**&#x200B;をクリックします。

1. （オプション）結果をフィルタリングするには、「**[!UICONTROL フィルターを表示]**」アイコン（![&#x200B; フィルターを表示アイコン &#x200B;](/help/main/assets/icons/Filter.svg)）をクリックし、適用するフィルターを選択します。 使用可能なフィルターは、**[!UICONTROL 環境]**、**[!UICONTROL コレクション]**、**[!UICONTROL カテゴリー]**、**[!UICONTROL ブランド]**、**[!UICONTROL 在庫]**&#x200B;および&#x200B;**[!UICONTROL 値]**&#x200B;です。

   [環境](/help/main/administrating-target/environments.md)は、管理と分離されたレポート用にサイトと実稼動前の環境を整理します。 環境を変更するには、**[!UICONTROL 環境]** ドロップダウンリストから目的の環境を選択します。

   フィルターパネルが強調表示された![&#x200B; カタログ検索ページ：コレクション、カテゴリ、ブランド、在庫、値、および高度な検索](../assets/catalog_search.png)

1. 「**[!UICONTROL 検索先]**」フィールドに検索語を入力します。

1. （オプション）オプションメニューから検索オプションを選択して、検索を絞り込みます。このオプションは、**[!UICONTROL 検索先]** フィールドの下向き矢印から開きます。

   次の検索オプションがあります。

   * ID
   * 名前
   * メッセージ

1. **[!UICONTROL テーブルをカスタマイズ]** アイコン （![&#x200B; テーブルをカスタマイズ アイコン &#x200B;](/help/main/assets/icons/ColumnSetting.svg)）をクリックして、**[!UICONTROL カタログ検索]** ページのアクティブな列を変更します。

   ![&#x200B; テーブルをカスタマイズ アイコンがハイライト表示されたカタログ検索ページ &#x200B;](../assets/catalog_search_4.png)

1. 検索結果の項目をスクロールして、サムネールやその他の商品情報を表示します。

   >[!NOTE]
   >
   >数値を持つカスタム属性のカタログ検索では、結果はカスタム属性を数値ではなく文字列型として扱います。
   >
   >属性のタイプは現在変更できません。 変更を要求するには、[&#x200B; タイプが文字列から数値に変更する必要がある属性を参照して、顧客イシュー](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)を開きます。

1. 検索結果内の項目をクリックして、ID、名前、メッセージ、カテゴリなどの詳細を表示します。

   ![ID、カテゴリ、余白、その他の属性を示すカタログ項目の詳細](../assets/catalog_search_2.png)

1. カタログからアイテムを削除するには、**[!UICONTROL カタログから削除]**&#x200B;をクリックします。

   その後、その項目に関するすべての情報がカタログインデックスから削除されます。 アイテムがカタログに再度含まれるのは、データフィードでアイテムが再度追加された場合のみです。 削除されたアイテムは、フィードとは別に削除する必要があります。

   ![&#x200B; カタログから削除ボタンがハイライト表示されたカタログ項目の詳細](../assets/catalog_search_3.png)

<!--
### Perform an advanced search {#advanced-search}

You can use [!UICONTROL Advanced Search] to further refine your search results or to save your search results as a [collection](/help/main/c-recommendations/c-products/collections.md) or [exclusion](/help/main/c-recommendations/c-products/exclusions.md).

1. Click the **[!UICONTROL Advanced Search]** link.

   ![Advanced Search page](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Use the drop-down lists to specify the parameter, operator, and values for your search.

1. (Optional) Click **[!UICONTROL Add Rule]** to add an additional search rule.

   Each additional search rule is joined with the AND operator.

1. Click **[!UICONTROL Search]**.

1. (Optional) Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   For more information, see [Create a collection or exclusion based on Advanced Search](#save-as) below.
-->

<!--
## Modify the Catalog Search page (filters and columns)

You can temporarily modify the available filters and columns on the [!UICONTROL Catalog Search] page for the current session.

### Modify filters

You can add additional filter facets to the [!UICONTROL Catalog Search] page.

1. In the **[!UICONTROL Filters]** panel, click **[!UICONTROL Modify]**.

   ![Modify filters link](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Select the desired search facets (ID, name, message, etc.), then click **[!UICONTROL Save]**.

   ![Add filters](/help/main/c-recommendations/c-products/assets/add-filters.png)

Keep in mind that the additional filter facets are available in the current session only.
-->



<!--
## Create a collection or exclusion based on Advanced Search {#save-as}

You can create [collections](/help/main/c-recommendations/c-products/collections.md) or [exclusions](/help/main/c-recommendations/c-products/exclusions.md) using [!UICONTROL Advanced Search] on the [!UICONTROL Catalog Search] page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Perform an [advanced search](#advanced-search).

1. Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections or exclusions based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. Exclusions are handled in a similar fashion.
-->
