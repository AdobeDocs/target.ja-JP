---
keywords: カタログ検索；カタログ；検索；除外；コレクション；フィルタ
description: Recommendationsカタログ検索を使用して、商品やコンテンツの検索、コレクションや除外の作成、カタログからの項目の削除などを行う方法について説明します。
title: Recommendationsカタログ検索の使用方法
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 17%

---


# ![PREMIUMCatalog](/help/assets/premium.png) 検索

[!DNL Adobe Recommendations]の[!UICONTROL カタログ検索]ページを使用すると、カタログ内の商品やコンテンツを探すことができます。 このページで実行できる最も基本的なタスクは、アイテムを検索することです。 また、環境の変更、検索結果のコレクションまたは除外への保存、フィルターファセットの追加、テーブル内の列の変更、新しい検索ファセットの追加などを行うことができます。

カタログは、製品セット（エンティティ）全体を参照します。 カタログには多数のコレクションを含めることができ、商品を論理的なグループにまとめて整理できます。

## カタログ検索へのアクセス

[!UICONTROL カタログ検索]ページにアクセスするには、**[!UICONTROL Recommendations]**/**[!UICONTROL カタログ検索]**&#x200B;をクリックします。

![カタログ検索ページ](/help/c-recommendations/c-products/assets/catalog-search.png)

## 項目の検索

単純検索またはアドバンス検索を使用して、カタログ内の項目を検索できます。

### 単純検索の実行

1. [**[!UICONTROL 製品の検索]**]フィールドに検索語句を入力します。

1. （オプション）検索フィールドの下向き矢印をクリックすると表示されるオプションメニューから検索オプションを選択して、検索を絞り込むことができます。

   ![](assets/searchproductsmenu.png)

   次の検索オプションがあります。

   * すべて - OR論理を使用して、他のすべての検索条件を対象に検索します。
   * 名前
   * ブランド
   * カテゴリ
   * ID
   * メッセージ

1. 検索結果内の項目をスクロールして、表示のサムネールやその他の製品情報を表示できるようになりました。

   次の図に、「すべて」オプションを使用した「bike」の結果を示します。

   ![自転車のカタログ検索](/help/c-recommendations/c-products/assets/bike-results.png)

   「製品」のとなりに表示されている数字は、指定された環境での有効数の中で検索語句に一致した製品の数です。

   検索のオートコンプリート機能を使用できます。 次の図では、「bik」と入力すると、「bike」という語を含むすべての製品が返されます。

   ![オートコンプリートの検索](/help/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >数値を持つカスタム属性に対してカタログ検索を実行すると、結果では、カスタム属性が数値ではなく文字列タイプとして処理されます。
   >
   >現在、属性のタイプを変更できる機能はありません。 変更を行うには、[顧客の問題](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)を開き、型を文字列から数値に変更する必要がある属性を参照します。

1. フィルターを使用して目的の商品を探すこともできます。 次の例では、[!UICONTROL コレクション]ファセットを展開し、「Bike Tools」を選択すると、カタログ内のすべてのbikeツールが表示されます。

   ![バイク用ツール](/help/c-recommendations/c-products/assets/bike-results-3.png)

1. 検索語句（「chain」など）を入力して、結果リストをさらに検索できます。

   ![チェーンの検索](/help/c-recommendations/c-products/assets/bike-results-4.png)

### アドバンス検索{#advanced-search}の実行

「[!UICONTROL アドバンス検索]」を使用すると、検索結果を絞り込んだり、検索結果を[コレクション](/help/c-recommendations/c-products/collections.md)または[除外](/help/c-recommendations/c-products/exclusions.md)として保存したりできます。

1. 「**[!UICONTROL アドバンス検索]**」リンクをクリックします。

   ![[アドバンス検索]ページ](/help/c-recommendations/c-products/assets/advances-search.png)

1. ドロップダウンリストを使用して、検索のパラメータ、演算子、値を指定します。

1. （オプション）「**[!UICONTROL ルール]**」をクリックして、追加検索ルールを追加します。

   追加の検索ルールは、それぞれAND演算子で結合されます。

1. 「**[!UICONTROL 検索]**」をクリックします。

1. （オプション）「**[!UICONTROL 名前を付けて保存]**」をクリックし、「**[!UICONTROL コレクション]**」または「**[!UICONTROL 除外]**」をクリックします。

   ![「名前を付けて保存」オプション](/help/c-recommendations/c-products/assets/save-as.png)

   詳しくは、下の[アドバンス検索に基づいてコレクションまたは除外を作成する](#save-as)を参照してください。

## 品目の詳細の表示

ID、名前、メッセージ、カテゴリなど、個々のアイテムの詳細を表示するには、詳細を表示します。

1. 検索結果内の項目をクリックして、詳細を表示します。

   ![製品の詳細](/help/c-recommendations/c-products/assets/bike-results-5.png)

## カタログからの品目の削除

1. 検索結果内の項目をクリックして、詳細を表示します。

1. 「**[!UICONTROL カタログから削除]**」をクリックします。

1. 項目を削除することを確認します。

その項目に関するすべての情報がカタログインデックスから削除されます。 項目がデータフィードに再度追加された場合にのみ、その項目がカタログに含まれます。 削除した項目は、フィードから個別に削除する必要があります。

## カタログの更新

最初のフィードをアップロードするとカタログのインデックスが自動的に作成され、[指定されたスケジュール](/help/c-recommendations/c-products/feeds.md#steps)に従って更新されます。

カタログは、フィードファイル、API または mbox の更新を介して更新を受け取ると、自動的に更新されます。更新は、通常、1 時間で完了します。更新が進行中の場合、最も新しく更新を開始した時間が表示されます。更新が進行中でない場合、最も新しく更新を開始および終了した時間が表示されます。

## 詳細検索に基づいたコレクションまたは除外の作成 {#save-as}

カタログ検索ページ（[](/help/c-recommendations/c-products/collections.md)[](/help/c-recommendations/c-products/exclusions.md)レコメンデーション[!UICONTROL ／]カタログ検索[!UICONTROL ／]詳細検索[!UICONTROL ）の詳細検索を使用して、]コレクション[!UICONTROL または]除外を作成できます。

1. [アドバンス検索](#advanced-search)を実行します。

1. 「**[!UICONTROL 名前を付けて保存]**」をクリックし、「**[!UICONTROL コレクション]**」または「**[!UICONTROL 除外]**」をクリックします。

   ![「名前を付けて保存」オプション](/help/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >[!UICONTROL アドバンス検索]機能では大文字と小文字が区別されません。ただし、配信時に返される商品は、大文字と小文字が区別される検索に基づいています。 この違いが混乱を招くこともあります。[!UICONTROL アドバンス検索]機能を使用して結果に基づいてコレクションや除外を作成する場合は、大文字と小文字の区別を必ず考慮してください。 例えば、最初に「Holiday」と検索すると、「Holiday」または「holiday」を含む結果が返されます。その後、「holiday」を含む商品を返すことを目的としたカタログを作成すると、「holiday」を含む商品のみが返されます。「Holiday」を含む商品は返されません。除外も同様に処理されます。

## 環境の変更

[](/help/administrating-target/environments.md) 環境では、サイトと実稼働前の環境を整理し、管理やレポートを容易に分けることができます。

1. 環境リンクをクリックします。

   ![環境リンク](/help/c-recommendations/c-products/assets/environment.png)

1. 目的の環境を選択します。

## カタログ検索ページの変更(フィルターと列)

現在のセッションの[!UICONTROL カタログ検索]ページで、使用可能なフィルターと列を一時的に変更できます。

### フィルターの変更

[!UICONTROL カタログ検索]ページに、追加のフィルターファセットを追加できます。

1. **[!UICONTROL フィルター]**&#x200B;パネルで、**[!UICONTROL 修正]**&#x200B;をクリックします。

   ![フィルターの変更リンク](/help/c-recommendations/c-products/assets/modify-filters.png)

1. 目的の検索ファセット（ID、名前、メッセージなど）を選択し、「**[!UICONTROL 保存]**」をクリックします。

   ![フィルターを追加](/help/c-recommendations/c-products/assets/add-filters.png)

追加のフィルターファセットは、現在のセッションでのみ使用できます。

### 列の変更

[!UICONTROL カタログ検索]ページのアクティブな列を一時的に変更できます。

1. 「**[!UICONTROL 列]**」リンクをクリックします。

   ![列オプション](/help/c-recommendations/c-products/assets/columns.png)

1. （条件付き）アクティブな列の順序を変更するには、**[!UICONTROL 「アクティブな列」]**&#x200B;セクションの列を目的の順序でドラッグ&amp;ドロップします。

1. （条件付き）必要に応じて、「**[!UICONTROL アクティブな列]**」から「**[!UICONTROL 非アクティブな列]**」に項目をドラッグ&amp;ドロップします。また、その逆も同じです。

   アクティブなセクションから非アクティブなセクションに移動する列の横にある削除アイコン( x )をクリックすることもできます。

変更は現在のセッションにのみ適用されることに注意してください。

