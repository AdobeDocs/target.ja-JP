---
keywords: catalog;search
description: Adobe Target でカタログ検索を使用すると、カタログ内の製品やコンテンツを探すことができます。
title: Adobe Target のカタログ検索
feature: catalog
uuid: e0876963-5905-4850-a615-953e435f26e9
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 96%

---


# ![PREMIUM](/help/assets/premium.png) カタログ検索 {#catalog-search}

カタログ検索を使用すると、カタログ内の製品やコンテンツを探すことができます。

To access catalog search, click **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**.

検索フィールドで下矢印をクリックすると表示されるオプションメニューから検索オプションを選択することで、検索を絞り込むことができます。

![](assets/searchproductsmenu.png)

次の検索オプションがあります。

* すべて
* 名前
* ブランド
* カテゴリ
* ID
* メッセージ

「**[!UICONTROL すべて]**」は、すべての他の検索条件の OR 論理を使用して検索します。

検索結果で「**[!UICONTROL 環境]**」フィルターをクリックし、カタログを表示している実稼動[ホストグループ環境](/help/administrating-target/hosts.md)を指定します。検索結果で品目をスクロールして、サムネールなどの製品情報を表示することもできます。

「製品」のとなりに表示されている数字は、指定された環境での有効数の中で検索語句に一致した製品の数です。

カタログは、フィードファイル、API または mbox の更新を介して更新を受け取ると、自動的に更新されます。更新は、通常、1 時間で完了します。更新が進行中の場合、最も新しく更新を開始した時間が表示されます。更新が進行中でない場合、最も新しく更新を開始および終了した時間が表示されます。

## 詳細検索に基づいたコレクションまたは除外の作成

カタログ検索ページ（[!UICONTROL レコメンデーション]／[!UICONTROL カタログ検索]／[!UICONTROL 詳細検索]）の詳細検索を使用して、[コレクション](/help/c-recommendations/c-products/collections.md)または[除外](/help/c-recommendations/c-products/exclusions.md)を作成できます。

![名前を付けて保存ダイアログ](/help/c-recommendations/c-products/assets/save-as-dialog.png)

「ID／次を含む」などを使用した検索を作成したら、[!UICONTROL 名前を付けて保存]／[!UICONTROL コレクションまたは除外]をクリックします。

>[!IMPORTANT]
>
>詳細検索機能では大文字と小文字は区別されません。ただし、配信時に返される商品は、大文字と小文字が区別される検索に基づきます。この違いが混乱を招くこともあります。詳細検索機能による結果を基にしてコレクションまたは除外を作成する際は、大文字と小文字の区別を考慮してください。例えば、最初に「Holiday」と検索すると、「Holiday」または「holiday」を含む結果が返されます。その後、「holiday」を含む商品を返すことを目的としたカタログを作成すると、「holiday」を含む商品のみが返されます。「Holiday」を含む商品は返されません。除外も同様に処理されます。
