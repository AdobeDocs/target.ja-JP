---
keywords: カタログ検索；カタログ；検索；除外；コレクション；フィルター；recommendations
description: ' [!DNL Recommendations] [!UICONTROL Catalog Search] を使用して、製品やコンテンツを検索したり、カタログから項目を削除したりする方法を説明します。'
title: ' [!DNL Recommendations] [!UICONTROL Catalog Search] の使い方'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 24%

---

# [!UICONTROL Catalog Search]

[!DNL Adobe Recommendations] の [!UICONTROL Catalog Search] ページは、カタログ内の製品またはコンテンツを見つけるのに役立ちます。 このページで実行できる最も基本的なタスクは、項目を検索することです。 さらに、環境の変更、ファセットのフィルタリング、テーブル内の列の変更、新しい検索ファセットの追加などを行うことができます。

カタログは、製品セット（エンティティ）全体を表します。カタログには多数のコレクションを含めることができるので、商品を論理的なグループにまとめて整理できます。

## アクセス [!UICONTROL Catalog Search]

1. [!UICONTROL Catalog Search] ページにアクセスするには、**[!UICONTROL Recommendations]**/**[!UICONTROL Catalog Search]** をクリックします。

1. （任意）検索にフィルターを適用するには、「**[!UICONTROL Show Filters]**」アイコン（![ 「フィルターを表示」アイコン ](/help/main/assets/icons/Filter.svg)）をクリックします。 [!UICONTROL Environment]、[!UICONTROL Collections]、[!UICONTROL Category]、[!UICONTROL Brand]、[!UICONTROL Inventory] および [!UICONTROL Value] でフィルタリングできます。

## 簡易検索の実行

1. 検索語句を「**[!UICONTROL Search In]**」フィールドに入力します。

1. （オプション）検索フィールドの下向き矢印をクリックしたときに表示されるオプション メニューから検索オプションを選択して、検索を絞り込むことがで [!UICONTROL Search In] ます。

   次の検索オプションがあります。

   * ID
   * 名前
   * メッセージ

1. 検索結果の項目をスクロールして、サムネールやその他の製品情報を表示します。

   >[!NOTE]
   >
   > 数値を使用してカスタム属性に対してカタログ検索を実行すると、カスタム属性は数値ではなく文字列型とみなされます。
   >
   >現在、属性のタイプを変更できる機能はありません。 変更をおこなうには、[顧客のイシューを開く](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)、タイプを文字列から数値に変更する必要がある属性を参照します。

<!-- ### Perform an advanced search {#advanced-search}

You can use [!UICONTROL Advanced Search] to further refine your search results or to save your search results as a [collection](/help/main/c-recommendations/c-products/collections.md) or [exclusion](/help/main/c-recommendations/c-products/exclusions.md).

1. Click the **[!UICONTROL Advanced Search]** link.

   ![Advanced Search page](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Use the drop-down lists to specify the parameter, operator, and values for your search.

1. (Optional) Click **[!UICONTROL Add Rule]** to add an additional search rule.

   Each additional search rule is joined with the AND operator.

1. Click **[!UICONTROL Search]**.

1. (Optional) Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   For more information, see [Create a collection or exclusion based on Advanced Search](#save-as) below.-->

## 項目の詳細の表示

ID、名前、メッセージ、カテゴリなど、個々の項目の詳細を、その詳細を表示することで表示できます。

1. 詳細を表示するには、検索結果内の項目をクリックします。

## カタログからのアイテムの削除

1. 詳細を表示するには、検索結果内の項目をクリックします。

1. **[!UICONTROL Remove from Catalog]** をクリックします。

1. 項目の削除を確認します。

その項目に関するすべての情報がカタログ インデックスから削除されます。 項目は、データフィードで再度追加された場合にのみ、カタログに含まれます。 削除された項目は、フィードから個別に削除する必要があります。

## カタログを更新

カタログのインデックスは、最初のフィードをアップロードすると自動的に作成され、[ 指定されたスケジュール ](/help/main/c-recommendations/c-products/feeds.md#steps) に従って更新されます。

カタログは、フィードファイル、API または mbox の更新を介して更新を受け取ると、自動的に更新されます。更新は通常、1 時間以内に完了します。 更新が進行中の場合、最も新しく更新を開始した時間が表示されます。更新が進行中でない場合、最も新しく更新を開始および終了した時間が表示されます。

<!-- ## Create a collection or exclusion based on Advanced Search {#save-as}

You can create [collections](/help/main/c-recommendations/c-products/collections.md) or [exclusions](/help/main/c-recommendations/c-products/exclusions.md) using [!UICONTROL Advanced Search] on the [!UICONTROL Catalog Search] page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Perform an [advanced search](#advanced-search).

1. Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections or exclusions based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. Exclusions are handled in a similar fashion.-->

## 環境の変更

[ 環境 ](/help/main/administrating-target/environments.md) を使用すると、サイトと実稼動前の環境を整理し、管理と環境別レポートを容易にできます。

1. 「フィルターを表示」アイコン（![ フィルターを表示アイコン ](/help/main/assets/icons/Filter.svg)）をクリックします。

1. **[!UICONTROL Environment]** ドロップダウンリストから目的の環境を選択します。

<!-- ## Modify the Catalog Search page (filters and columns)

You can temporarily modify the available filters and columns on the [!UICONTROL Catalog Search] page for the current session.

### Modify filters

You can add additional filter facets to the [!UICONTROL Catalog Search] page.

1. In the **[!UICONTROL Filters]** panel, click **[!UICONTROL Modify]**.

   ![Modify filters link](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Select the desired search facets (ID, name, message, etc.), then click **[!UICONTROL Save]**.

   ![Add filters](/help/main/c-recommendations/c-products/assets/add-filters.png)

Keep in mind that the additional filter facets are available in the current session only.-->

## 列を変更

[!UICONTROL Catalog Search] ページのアクティブな列を変更できます。

1. **[!UICONTROL Customize Table]** アイコン（![ テーブルアイコンをカスタマイズ ](/help/main/assets/icons/ColumnSetting.svg)）をクリックします。

1. 表示または非表示にする列を選択または選択解除します。

加えた変更は、セッションをまたいで永続的に適用されます。
