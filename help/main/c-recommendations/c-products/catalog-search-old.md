---
keywords: カタログ検索；カタログ；検索；除外；コレクション；フィルター
description: Recommendations カタログ検索を使用して、商品やコンテンツの検索、コレクションや除外の作成、カタログからのアイテムの削除などを行う方法について説明します。
title: Recommendations カタログ検索の使用方法は？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 22%

---

# カタログ検索

[!DNL Adobe Recommendations] の [!UICONTROL Catalog Search] ページは、カタログ内の製品またはコンテンツを見つけるのに役立ちます。 このページで実行できる最も基本的なタスクは、項目を検索することです。 また、環境の変更、検索結果のコレクションまたは除外への保存、フィルターファセットの追加、テーブル内の列の変更、新しい検索ファセットの追加などを行うことができます。

カタログは、製品セット（エンティティ）全体を表します。カタログには多数のコレクションを含めることができるので、商品を論理的なグループにまとめて整理できます。

## カタログ検索へのアクセス

[!UICONTROL Catalog Search] ページにアクセスするには、**[!UICONTROL Recommendations]**/**[!UICONTROL Catalog Search]** をクリックします。

![ カタログ検索ページ ](/help/main/c-recommendations/c-products/assets/catalog-search.png)

## 項目を検索

簡易検索または詳細検索を使用して、カタログ内の項目を見つけることができます。

### 簡易検索の実行

1. 検索語句を「**[!UICONTROL Search Products]**」フィールドに入力します。

1. （オプション）検索フィールドの下向き矢印をクリックしたときに表示されるオプション メニューから検索オプションを選択して、検索を絞り込むことができます。

   ![searchproductsmenu 画像 ](assets/searchproductsmenu.png)

   次の検索オプションがあります。

   * ALL - OR ロジックを使用して、他のすべての検索条件を適用して検索します。
   * 名前
   * ブランド
   * カテゴリ
   * ID
   * メッセージ

1. 検索結果の項目をスクロールして、サムネールやその他の製品情報を表示できるようになりました。

   次の図は、「すべて」オプションを使用した「bike」の結果を示しています。

   ![ 自転車のカタログ検索 ](/help/main/c-recommendations/c-products/assets/bike-results.png)

   「製品」のとなりに表示されている数字は、指定された環境での有効数の中で検索語句に一致した製品の数です。

   検索のオートコンプリート機能を使用できることに注意してください。 次の図では、「bik」と入力すると、「bike」という単語を含むすべての製品が返されます。

   ![ オートコンプリートを検索 ](/help/main/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >数値を使用してカスタム属性に対してカタログ検索を実行すると、カスタム属性は数値ではなく文字列型とみなされます。
   >
   >現在、属性のタイプを変更できる機能はありません。 変更をおこなうには、[顧客のイシューを開く](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)、タイプを文字列から数値に変更する必要がある属性を参照します。

1. また、フィルターを使用して、目的の製品を見つけることもできます。 次の例では、[!UICONTROL Collections] ファセットを展開して「Bike Tools」を選択すると、カタログ内のすべての自転車ツールが表示されます。

   ![ 自転車用具 ](/help/main/c-recommendations/c-products/assets/bike-results-3.png)

1. 検索語（「chain」など）を入力すると、結果リストをさらに検索できます。

   ![ チェーンの検索 ](/help/main/c-recommendations/c-products/assets/bike-results-4.png)

### 詳細検索の実行 {#advanced-search}

[!UICONTROL Advanced Search] を使用して、検索結果をさらに絞り込んだり、検索結果を [ コレクション ](/help/main/c-recommendations/c-products/collections.md) または [ 除外 ](/help/main/c-recommendations/c-products/exclusions.md) として保存したりできます。

1. **[!UICONTROL Advanced Search]** リンクをクリックします。

   ![ 詳細検索ページ ](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. ドロップダウンリストを使用して、検索のパラメーター、演算子、値を指定します。

1. （任意）「**[!UICONTROL Add Rule]**」をクリックして、追加の検索ルールを追加します。

   追加された各検索ルールは、AND 演算子で結合されます。

1. **[!UICONTROL Search]** をクリックします。

1. （オプション）「**[!UICONTROL Save As]**」をクリックして、「**[!UICONTROL Collection]**」または「**[!UICONTROL Exclusion]**」をクリックします。

   ![ 別名で保存オプション ](/help/main/c-recommendations/c-products/assets/save-as.png)

   詳しくは、以下の [ 詳細検索に基づくコレクションまたは除外の作成 ](#save-as) を参照してください。

## 項目の詳細の表示

ID、名前、メッセージ、カテゴリなど、個々の項目の詳細を、その詳細を表示することで表示できます。

1. 詳細を表示するには、検索結果内の項目をクリックします。

   ![ 製品詳細 ](/help/main/c-recommendations/c-products/assets/bike-results-5.png)

## カタログからのアイテムの削除

1. 詳細を表示するには、検索結果内の項目をクリックします。

1. **[!UICONTROL Remove from Catalog]** をクリックします。

1. 項目の削除を確認します。

その項目に関するすべての情報がカタログ インデックスから削除されます。 項目は、データフィードで再度追加された場合にのみ、カタログに含まれます。 削除された項目は、フィードから個別に削除する必要があります。

## カタログを更新

カタログのインデックスは、最初のフィードをアップロードすると自動的に作成され、[ 指定されたスケジュール ](/help/main/c-recommendations/c-products/feeds.md#steps) に従って更新されます。

カタログは、フィードファイル、API または mbox の更新を介して更新を受け取ると、自動的に更新されます。更新は、通常、1 時間で完了します。更新が進行中の場合、最も新しく更新を開始した時間が表示されます。更新が進行中でない場合、最も新しく更新を開始および終了した時間が表示されます。

## 詳細検索に基づいたコレクションまたは除外の作成 {#save-as}

[!UICONTROL Catalog Search] ページ（[!UICONTROL Recommendations]/[!UICONTROL Catalog Search]/[!UICONTROL Advanced Search]）の [!UICONTROL Advanced Search] を使用して [ コレクション ](/help/main/c-recommendations/c-products/collections.md) または [ 除外 ](/help/main/c-recommendations/c-products/exclusions.md) を作成できます。

1. [ 詳細検索 ](#advanced-search) を実行します。

1. 「**[!UICONTROL Save As]**」をクリックし、「**[!UICONTROL Collection]**」または「**[!UICONTROL Exclusion]**」をクリックします。

   ![ 別名で保存オプション ](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >[!UICONTROL Advanced Search] の機能では、大文字と小文字が区別されません。ただし、配信時に返される製品は、大文字と小文字を区別した検索に基づいています。 この違いが混乱を招くこともあります。[!UICONTROL Advanced Search] 機能を使用して結果に基づいてコレクションや除外を作成する場合は、大文字と小文字を区別するようにしてください。 例えば、最初に「Holiday」と検索すると、「Holiday」または「holiday」を含む結果が返されます。その後、「holiday」を含む商品を返すことを目的としたカタログを作成すると、「holiday」を含む商品のみが返されます。「Holiday」を含む商品は返されません。除外も同様に処理されます。

## 環境の変更

[ 環境 ](/help/main/administrating-target/environments.md) を使用すると、サイトと実稼動前の環境を整理し、管理と環境別レポートを容易にできます。

1. 「環境」リンクをクリックします。

   ![ 環境リンク ](/help/main/c-recommendations/c-products/assets/environment.png)

1. 目的の環境を選択します。

## カタログ検索ページの変更（フィルターと列）

現在のセッションの [!UICONTROL Catalog Search] ページで使用可能なフィルターと列を一時的に変更できます。

### フィルターを変更

[!UICONTROL Catalog Search] ページにフィルターファセットを追加できます。

1. **[!UICONTROL Filters]** パネルで、「**[!UICONTROL Modify]**」をクリックします。

   ![ 「フィルターを変更」リンク ](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. 目的の検索ファセット（ID、名前、メッセージなど）を選択し、「**[!UICONTROL Save]**」をクリックします。

   ![ フィルターの追加 ](/help/main/c-recommendations/c-products/assets/add-filters.png)

追加のフィルターファセットは、現在のセッションでのみ使用できます。

### 列を変更

[!UICONTROL Catalog Search] ページ上のアクティブな列を一時的に変更できます。

1. **[!UICONTROL Columns]** リンクをクリックします。

   ![ 列オプション ](/help/main/c-recommendations/c-products/assets/columns.png)

1. （条件付き）アクティブな列の順序を並べ替えるには、**[!UICONTROL Active Columns]** セクションの列を目的の順序でドラッグ&amp;ドロップします。

1. （条件付き）必要に応じて、**[!UICONTROL Active Columns]** ージから **[!UICONTROL Inactive Columns]** ージに（およびその逆に）項目をドラッグ&amp;ドロップします。

   また、アクティブなセクションから非アクティブなセクションに移動する列の横にある削除アイコン（x）をクリックすることもできます。

加えた変更は、現在のセッションにのみ適用されることに注意してください。
