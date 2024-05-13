---
keywords: コンテンツライブラリ;アセット;注釈;コピー;アセットの削除;アセットのダウンロード;コンテンツの編集;カードの共有;コンテンツプロパティの表示
description: でコードと画像オファーを管理する方法を説明します [!DNL Target] [!UICONTROL Offers] ライブラリ。
title: でのコンテンツの操作方法 [!UICONTROL Offers] 図書館？
feature: Experiences and Offers
hide: true
hidefromtoc: true
source-git-commit: 5931aef4a16e6e9777112fdda4b3277f8e6f7386
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 33%

---

# アセットライブラリ内のコンテンツの操作

のコンテンツ ライブラリ内のアセットに対して実行できるタスクについての情報 [!DNL Adobe Target] プロパティへの注釈、コピー、削除、ダウンロード、編集、共有、表示を含みます。

1. クリック **[!UICONTROL Offers]** > **[!UICONTROL Code Offers]** または **[!UICONTROL Image Offers]**.

   ![「オファーのコード」タブと「画像オファー」タブ](/help/main/c-experiences/c-manage-content/assets/offers-both.png)

   オファーライブラリの検索とスマートコレクションの作成について詳しくは、[コンテンツのフィルターと検索](/help/main/c-experiences/c-manage-content/filter-and-search-content.md#concept_3B59B8F025BF4CEA82ECC5199D365276)を参照してください。

1. （オプション）を切り替えます [!UICONTROL Card View] および [!UICONTROL List View]を選択し、 [!UICONTROL Card View] アイコンまたは [!UICONTROL List View] アイコン （コンテンツライブラリの右上隅）。 を使用することもできます。 [!UICONTROL View Settings] を表示する際に列をさらに設定するには [!UICONTROL List View].

   次の図は、 [!UICONTROL List View]:

   ![リスト表示オプション](/help/main/c-experiences/c-manage-content/assets/view-settings-options.png)

1. 次の節で説明するように、目的のアクションを実行します。

## コードオファーオプション

を表示する場合 [!UICONTROL Code Offers] ページで項目に対して次のアクションを実行するには、オファーまたはフォルダーにカーソルを合わせて、適切なアイコンを選択します。

![「コードオファー」タブにポインタを合わせる](/help/main/c-experiences/c-manage-content/assets/code-offers-hover-icons.png)

* **情報**：オファーの情報を表示します。
* **編集**：フォルダーまたはオファーを編集します。
* **コピー**：オファーをコピーします。 オファーをコピーして編集すると、類似した新しいオファーを簡単に作成できます。
* **移動**：移動アイコンをクリックし、オファーまたはフォルダーを移動する場所に移動して、 **[!UICONTROL Drop]** アイコン。 例えば、1 つ以上のフォルダーを別のフォルダーに移動して、サブフォルダーを作成できます。 クリック [!UICONTROL Clear Selection] をクリックして、選択したオファーまたはフォルダーの選択を解除します。
* **削除**：オファーまたはフォルダーを削除します。 参照： [項目を削除する際の考慮事項](#delete).

## 画像オファーオプション

を表示する場合 [!UICONTROL Image Offers] ページで項目に対して次のアクションを実行するには、オファーまたはフォルダーにカーソルを合わせて、適切なアイコンを選択します。

次の図は、 [!UICONTROL Card View].

![カード表示の場合は、画像オファータブにポインタを合わせます](/help/main/c-experiences/c-manage-content/assets/image-offers-hover-icons.png)

次の図は、 [!UICONTROL List View]. アイコンを表示するには、リストの項目をクリックします。

![リスト表示の場合は「画像オファー」タブにポインタを合わせる](/help/main/c-experiences/c-manage-content/assets/list-view-hover.png)

* **を選択**：次のアクションを実行する 1 つ以上のフォルダーを選択します。

   * ダウンロード
   * コピー
   * 移動
   * 削除（を参照） [項目を削除する際の考慮事項](#delete).）

  次のアクションを実行する画像オファーを 1 つ以上選択します。

   * 共有
   * ダウンロード
   * プロパティを表示
   * 編集
   * 注釈
   * 移動

* **Download**：画像オファーまたはフォルダーとそのコンテンツをダウンロードします。
* **プロパティを表示**：項目のプロパティを表示します。 必ずをクリックしてください。 [!UICONTROL Basic] tab キーと [!UICONTROL Advanced] tab キーを押すと、使用可能なすべての情報が表示されます。 プロパティページの鉛筆アイコンをクリックして、プロパティを編集し、情報を追加します。メタデータ情報、投稿状況およびライセンスデータを追加することができます。
* **その他のアクション**：での場合に追加オプションを表示します [!UICONTROL Card View].
* **編集**：フォルダーまたはオファーを編集します。
* **注釈**：アセットへのメモの追加。 アセットをクリックして、注釈を付ける領域を選択し、注釈を入力します。
* **コピー**：オファーをコピーします。 オファーをコピーして編集すると、類似した新しいオファーを簡単に作成できます。

## 項目を削除する際の考慮事項 {#delete}

* フォルダー内の任意の数のアセットとサブフォルダーを含んだフォルダー全体を削除できます。 この機能は、Adobe Experience Cloud Assets UI でも Target UI で使用できます。
* 多数の画像を含むフォルダーを削除する場合、UI が更新されて最終状態が表示されるまで、バックグラウンドで実行されるプロセスに時間がかかる場合があります（数分）。 必要な時間は、画像サイズではなく、画像数の関数です。適切な推定値は、2,000 画像に対し 10 分です。その他の作業を続行し、数分後に最終状態をチェックして削除を確認することができます。
* 画像オファーライブラリ内の空ではないフォルダを削除できます。フォルダー内のすべての画像がどのアクティビティでも参照されていない場合、フォルダー全体とそのコンテンツが削除されます。フォルダー内の一部の画像が何らかのアクティビティで参照されている場合、参照されていないすべての画像は削除されますが、参照画像とそれらの画像を含むフォルダは保持されます。

## トレーニングビデオ：コンテンツリポジトリ ![概要バッジ](/help/main/assets/overview.png)

このビデオでは、コンテンツの管理について説明します。(4:56)

* [Experience Cloud アセットライブラリ](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html)と Target コンテンツライブラリの間の接続
* カスタム HTML オファー
* Visual Experience Composer のカスタム HTML オファー

>[!VIDEO](https://video.tv.adobe.com/v/17387)