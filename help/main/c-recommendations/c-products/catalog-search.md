---
keywords: カタログ検索；カタログ；検索；除外；コレクション；フィルター
description: Recommendationsカタログ検索を使用して、製品やコンテンツを検索したり、コレクションや除外を作成したり、カタログから項目を削除したりする方法を説明します。
title: Recommendations Catalog 検索の使用方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 23%

---

# カタログ検索

この [!UICONTROL カタログ検索] ページ内 [!DNL Adobe Recommendations] は、カタログ内の製品やコンテンツを見つけるのに役立ちます。 このページで実行できる最も基本的な作業は、項目を検索することです。 また、環境の変更、検索結果のコレクションまたは除外への保存、フィルターファセットの追加、テーブル内の列の変更、新しい検索ファセットの追加などをおこなうことができます。

カタログは、製品セット（エンティティ）全体を表します。カタログには、多数のコレクションを含めることができます。これは、製品を論理的なグループに整理する方法です。

## カタログ検索にアクセス

次の手順で [!UICONTROL カタログ検索] ページ、クリック **[!UICONTROL Recommendations]** > **[!UICONTROL カタログ検索]**.

![カタログ検索ページ](/help/main/c-recommendations/c-products/assets/catalog-search.png)

## 項目の検索

簡易検索または詳細検索を使用して、カタログ内の項目を検索できます。

### 簡易検索の実行

1. 検索語を **[!UICONTROL 製品を検索]** フィールドに入力します。

1. （オプション）検索フィールドで下向き矢印をクリックしたときに表示されるオプションメニューから検索オプションを選択して、検索を絞り込むことができます。

   ![searchproductsmenu 画像](assets/searchproductsmenu.png)

   次の検索オプションがあります。

   * すべて - OR 論理を使用して、他のすべての検索条件を検索します。
   * 名前
   * ブランド
   * カテゴリ
   * ID
   * メッセージ

1. 検索結果内の項目間をスクロールして、サムネールやその他の製品情報を表示できるようになりました。

   次の図は、「すべて」オプションを使用した「bike」の結果を示しています。

   ![自転車のカタログ検索](/help/main/c-recommendations/c-products/assets/bike-results.png)

   「製品」のとなりに表示されている数字は、指定された環境での有効数の中で検索語句に一致した製品の数です。

   検索オートコンプリート機能を使用できます。 次の図では、「bik」と入力すると、「bike」という単語を含むすべての製品が返されます。

   ![オートコンプリートを検索](/help/main/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >数値を使用してカスタム属性に対してカタログ検索を実行すると、カスタム属性は数値ではなく文字列型とみなされます。
   >
   >現在、属性のタイプを変更できる機能はありません。 変更をおこなうには、[顧客のイシューを開く](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)、タイプを文字列から数値に変更する必要がある属性を参照します。

1. また、フィルターを使用して、目的の製品を検索することもできます。 次の例では、 [!UICONTROL コレクション] ファセットを選択し、「Bike Tools」を選択すると、カタログ内のすべての bike ツールが表示されます。

   ![バイクツール](/help/main/c-recommendations/c-products/assets/bike-results-3.png)

1. 検索語句（例：「チェーン」）を入力すると、結果リスト内でさらに検索できます。

   ![チェーンを検索](/help/main/c-recommendations/c-products/assets/bike-results-4.png)

### 詳細検索の実行 {#advanced-search}

以下を使用できます。 [!UICONTROL 詳細検索] 検索結果をさらに絞り込むため、または検索結果を [コレクション](/help/main/c-recommendations/c-products/collections.md) または [除外](/help/main/c-recommendations/c-products/exclusions.md).

1. 次をクリック： **[!UICONTROL 詳細検索]** リンク。

   ![詳細検索ページ](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. ドロップダウンリストを使用して、検索のパラメータ、演算子、値を指定します。

1. （オプション）「 **[!UICONTROL ルールを追加]** をクリックして、検索ルールを追加します。

   追加の各検索ルールは、AND 演算子で結合されます。

1. 「**[!UICONTROL 検索]**」をクリックします。

1. （オプション）「 **[!UICONTROL 名前を付けて保存]**&#x200B;を選択し、「 **[!UICONTROL コレクション]** または **[!UICONTROL 除外]**.

   ![「名前を付けて保存」オプション](/help/main/c-recommendations/c-products/assets/save-as.png)

   詳しくは、 [詳細検索に基づくコレクションまたは除外の作成](#save-as) 下

## 項目の詳細の表示

ID、名前、メッセージ、カテゴリなど、個々の項目の詳細を表示するには、その詳細を表示します。

1. 検索結果の項目をクリックすると、詳細が表示されます。

   ![製品の詳細](/help/main/c-recommendations/c-products/assets/bike-results-5.png)

## カタログから項目を削除

1. 検索結果の項目をクリックすると、詳細が表示されます。

1. クリック **[!UICONTROL カタログから削除]**.

1. 項目を削除することを確認します。

その項目に関するすべての情報がカタログインデックスから削除されます。 項目がデータフィードに再度追加された場合にのみ、その項目がカタログに含まれます。 削除した項目は、フィードから別に削除する必要があります。

## カタログを更新

最初のフィードをアップロードすると、カタログのインデックスが自動的に作成され、 [指定スケジュール](/help/main/c-recommendations/c-products/feeds.md#steps).

カタログは、フィードファイル、API または mbox の更新を介して更新を受け取ると、自動的に更新されます。更新は、通常、1 時間で完了します。更新が進行中の場合、最も新しく更新を開始した時間が表示されます。更新が進行中でない場合、最も新しく更新を開始および終了した時間が表示されます。

## 詳細検索に基づいたコレクションまたは除外の作成 {#save-as}

カタログ検索ページ（[](/help/main/c-recommendations/c-products/collections.md)[](/help/main/c-recommendations/c-products/exclusions.md)レコメンデーション[!UICONTROL ／]カタログ検索[!UICONTROL ／]詳細検索[!UICONTROL ）の詳細検索を使用して、]コレクション[!UICONTROL または]除外を作成できます。

1. の実行 [詳細検索](#advanced-search).

1. クリック **[!UICONTROL 名前を付けて保存]**&#x200B;を選択し、「 **[!UICONTROL コレクション]** または **[!UICONTROL 除外]**.

   ![「名前を付けて保存」オプション](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >この [!UICONTROL 詳細検索] 機能では大文字と小文字が区別されません。ただし、配信時に返される製品は、大文字と小文字を区別した検索に基づいています。 この違いが混乱を招くこともあります。コレクションや除外を作成する際は、 [!UICONTROL 詳細検索] 機能。 例えば、最初に「Holiday」と検索すると、「Holiday」または「holiday」を含む結果が返されます。その後、「holiday」を含む商品を返すことを目的としたカタログを作成すると、「holiday」を含む商品のみが返されます。「Holiday」を含む商品は返されません。除外も同様に処理されます。

## 環境の変更

[環境](/help/main/administrating-target/environments.md) を使用すると、サイトと実稼動前の環境を整理して、管理と個別のレポートを容易におこなえます。

1. 「環境」リンクをクリックします。

   ![環境リンク](/help/main/c-recommendations/c-products/assets/environment.png)

1. 目的の環境を選択します。

## カタログ検索ページ（フィルターと列）を変更する

次の項目で使用可能なフィルタと列を一時的に変更できます： [!UICONTROL カタログ検索] 現在のセッションのページ。

### フィルターを変更

フィルターファセットを [!UICONTROL カタログ検索] ページ。

1. 内 **[!UICONTROL フィルター]** パネル、クリック **[!UICONTROL 変更]**.

   ![フィルターを変更リンク](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. 目的の検索ファセット（ID、名前、メッセージなど）を選択し、 **[!UICONTROL 保存]**.

   ![フィルターを追加](/help/main/c-recommendations/c-products/assets/add-filters.png)

追加のフィルターファセットは、現在のセッションでのみ使用できることに注意してください。

### 列を変更

アクティブな列は、 [!UICONTROL カタログ検索] ページ。

1. 次をクリック： **[!UICONTROL 列]** リンク。

   ![列のオプション](/help/main/c-recommendations/c-products/assets/columns.png)

1. （条件付き）アクティブな列の順序を変更するには、列を **[!UICONTROL アクティブな列]** 」セクションを選択します。

1. （条件付き）項目を **[!UICONTROL アクティブな列]** から **[!UICONTROL 非アクティブな列]** （その逆も）必要に応じて。

   また、アクティブなセクションから非アクティブなセクションに移動する列の横にある削除アイコン ( x ) をクリックすることもできます。

変更は、現在のセッションにのみ適用されることに注意してください。
