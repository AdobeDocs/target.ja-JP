---
keywords: カタログ検索；カタログ；検索；除外；コレクション；フィルター；推奨事項
description: ' [!DNL Recommendations] [!UICONTROL Catalog Search]を使用して商品やコンテンツを検索する方法、カタログからアイテムを削除する方法などについて説明します。'
title: ' [!DNL Recommendations] [!UICONTROL Catalog Search]の使用方法を教えてください。'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
TQID: https://experienceleague.adobe.com/en3hkFsDjEE86Tc-3vPSiZFy0K47SftZMN6RW0INNic
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 519
ht-degree: 25%

---

# [!UICONTROL Catalog Search]

[!DNL Adobe Recommendations]の[!UICONTROL Catalog Search] ページは、カタログ内の商品またはコンテンツを検索するのに役立ちます。 このページで実行できる最も基本的なタスクは、項目を検索することです。 さらに、環境の変更、ファセットのフィルタリング、テーブルの列の変更、新しい検索ファセットの追加などを行うことができます。

カタログは、製品セット（エンティティ）全体を表します。 カタログには多数のコレクションを含めることができるため、商品を論理バケットで整理できます。

## [!UICONTROL Catalog Search]へのアクセス

1. [!UICONTROL Catalog Search] ページにアクセスするには、**[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**&#x200B;をクリックします。

1. （オプション）検索にフィルターを適用するには、**[!UICONTROL Show Filters]** アイコン （![ フィルターを表示アイコン ](/help/main/assets/icons/Filter.svg)）をクリックします。 [!UICONTROL Environment]、[!UICONTROL Collections]、[!UICONTROL Category]、[!UICONTROL Brand]、[!UICONTROL Inventory]および[!UICONTROL Value]でフィルタリングできます。

## シンプルな検索の実行

1. **[!UICONTROL Search In]** フィールドに検索語句を入力します。

1. （オプション） [!UICONTROL Search In] フィールドの下向き矢印をクリックすると表示されるオプションメニューから検索オプションを選択して、検索を絞り込むことができます。

   次の検索オプションがあります。

   * ID
   * 名前
   * メッセージ

1. 検索結果の項目をスクロールして、サムネールやその他の商品情報を表示します。

   >[!NOTE]
   >
   > 数値を使用してカスタム属性に対してカタログ検索を実行すると、カスタム属性は数値ではなく文字列型とみなされます。
   >
   >現在、属性のタイプを変更できる機能はありません。 変更をおこなうには、[顧客のイシューを開く](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)、タイプを文字列から数値に変更する必要がある属性を参照します。

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

## 項目の詳細を表示する

ID、名前、メッセージ、カテゴリなどの個々の項目の詳細を表示できます。

1. 検索結果の項目をクリックすると、その詳細が表示されます。

## カタログから項目を削除する

1. 検索結果の項目をクリックすると、その詳細が表示されます。

1. **[!UICONTROL Remove from Catalog]** をクリックします。

1. 項目を削除することを確認します。

そのアイテムに関するすべての情報は、カタログのインデックスから削除されます。 アイテムがカタログに含まれるのは、データフィードでアイテムが再度追加された場合のみです。 削除された項目は、フィードから個別に削除する必要があります。

## カタログを更新する

カタログのインデックスは、最初のフィードをアップロードしたときに自動的に作成され、[指定されたスケジュール ](/help/main/c-recommendations/c-products/feeds.md#steps)に従って更新されます。

カタログは、フィードファイル、API または mbox の更新を介して更新を受け取ると、自動的に更新されます。 通常、1時間以内に更新が完了します。 更新が進行中の場合、最も新しく更新を開始した時間が表示されます。 更新が進行中でない場合、最も新しく更新を開始および終了した時間が表示されます。

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

## 環境の変更

[環境](/help/main/administrating-target/environments.md)を使用すると、サイトとプリプロダクション環境を整理して、管理を容易にし、レポートを分離できます。

1. フィルターを表示アイコン（![ フィルターを表示アイコン ](/help/main/assets/icons/Filter.svg)）をクリックします。

1. **[!UICONTROL Environment]** ドロップダウンリストから目的の環境を選択します。

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

## 列を変更

[!UICONTROL Catalog Search] ページのアクティブな列を変更できます。

1. **[!UICONTROL Customize Table]** アイコン（![ テーブルをカスタマイズ アイコン ](/help/main/assets/icons/ColumnSetting.svg)）をクリックします。

1. 表示または非表示にする目的の列を選択または選択解除します。

加えた変更は、セッション間で永続的に保持されます。
