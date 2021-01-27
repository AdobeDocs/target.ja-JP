---
keywords: content;assets;manage content;offers;manage assets;enter selection mode;selection mode
description: コードと画像のオファーを管理する方法を教えてください。
title: オファー
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 70547a05155aa2909b0e66a1f26b0fd2cc730dd9
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 40%

---


# オファー

[!DNL Adobe Target]の[!UICONTROL オファー]ライブラリを使用して、コードオファーと画像オファーのコンテンツを管理します。

1. **[!UICONTROL オファー]**&#x200B;をクリックして、ライブラリを開きます。

   ライブラリには、[!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager]（AEM）、[!DNL Adobe Mobile Services]（AMS）および API で設定されたオファーが含まれています。[!DNL Target Classic] またはその他のソリューションで作成されたオファーは [!DNL Target Standard/Premium] で編集可能です。

   [!UICONTROL オファー]ページの右側に2つのタブがあります。[!UICONTROL コードオファー]と[!UICONTROL 画像オファー]。オファーをタイプ別に表示できます。

   ![「コードオファー」タブと「画像オファー」タブを表示するオファーページ](/help/c-experiences/c-manage-content/assets/offers-page.png)

1. （オプション）「**[!UICONTROL タイプ]**」ドロップダウンリストをクリックして、オファーをタイプ(HTMLオファー、[エクスペリエンスフラグメント](/help/c-experiences/c-manage-content/aem-experience-fragments.md)、[リダイレクトオファー](/help/c-experiences/c-manage-content/offer-redirect.md)、[リモートオファー](/help/c-experiences/c-manage-content/about-remote-offers.md)、[JSONオファー](/help/c-experiences/c-manage-content/create-json-offer.md)、a10/>フォルダー](/help/c-experiences/c-manage-content/create-content-folder.md))。[

   ![](assets/offers_filter.png)

1. （オプション）「**[!UICONTROL ソース]**」ドロップダウンリストをクリックして、オファーをソース(Adobe Target、Adobe Targetクラシック、Adobe Experience Manager)でフィルターします。

1. （オプション）「[!UICONTROL コードオファー]」タブで目的のオファーーまたはフォルダーの上にカーソルを置き、目的のタスクをクリックして、追加のアイコンを実行します。

   ![コードオファーオプション](assets/offer-picker-large.png)

   オプションは以下のとおりです。

   * 表示(詳しくは、下の[オファー定義の表示](#section_6B059DD121434E6292CAB393507D010E)を参照してください)。
   * 編集
   * コピー
   * 移動（例えば、1つ以上の項目を1つのフォルダーに移動するには、目的の項目の&#x200B;**[!UICONTROL 移動]**&#x200B;アイコンをクリックし、目的のフォルダーをクリックしてから、**[!UICONTROL ドロップ]**&#x200B;をクリックします）。
   * 削除

   権限によっては、すべてのオプションのアイコンが表示されない場合があります。 例えば、[!UICONTROL オブザーバー]権限を持つユーザーには、[!UICONTROL コピー]オプションを使用する権限がありません。

1. （オプション）「[!UICONTROL 画像オファーー]」タブで目的の画像オファーーまたはタスクーの上にカーソルを置き、目的のアイコンをクリックして、追加のフォルダーを実行します。

   ![画像オファーオプション](/help/c-experiences/c-manage-content/assets/image-offers-icons.png)

   オプションは以下のとおりです。

   * Select
   * ダウンロード
   * プロパティを表示
   * 編集
   * 注釈
   * コピー

## オファー定義の表示{#section_6B059DD121434E6292CAB393507D010E}

オファーを開かずに、[!UICONTROL オファー]ライブラリのポップアップカードにオファー定義の詳細を表示できます。

例えば、HTMLオファー用の次のオファー定義カードにアクセスするには、[!UICONTROL コンテンツ]リストー上のオファーーの上にカーソルを置き、情報アイコンをクリックします。

![](assets/offer-card-html.png)

以下の情報が表示されます。

* 名前
* ソース
* タイプ
* オファー ID
* オファーパス
* 最終変更日

「[!UICONTROL オファーの使用状況]」タブをクリックし、各オファー定義のポップアップカードのコードオファーを参照しているアクティビティを表示します。この機能は画像オファーには適用されません。これにより、オファーの編集中に他のアクティビティに影響が及ぶことを防止できます。[!UICONTROL ライブアクティビティ]と[!UICONTROL 非アクティブアクティビティ]が含まれます。

![](assets/offer-card-usage.png)

以下に示すリダイレクトオファーのオファー定義カードの場合：

![](assets/offer-card-redirect.png)

以下の情報が表示されます。

* 名前
* ソース
* タイプ
* オファー ID
* オファーパス
* 最終変更日
* リダイレクト URL
* すべてのURLパラメーターを含める（オンまたはオフ）
* mboxセッションIDを渡す（オンまたはオフ）

以下に示すリモートオファーのオファー定義カードの場合：

![](assets/offer-card-remote.png)

以下の情報が表示されます。

* 名前
* ソース
* タイプ
* オファー ID
* オファーパス
* 最終変更日
* リダイレクト URL のタイプ
* 絶対 URL または相対 URL

## トレーニングビデオ：コンテンツリポジトリ  ![概要バッジ](/help/assets/overview.png)

このビデオでは、オファーの管理について説明します。

* [Experience Cloud アセットライブラリ](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html)と Target コンテンツライブラリの間の接続
* カスタム HTML オファー
* Visual Experience Composer のカスタム HTML オファー

>[!VIDEO](https://video.tv.adobe.com/v/17387)