---
keywords: コンテンツ;アセット;コンテンツの管理;オファー;アセットの管理;選択モードを入力;選択モード
description: Adobe Targetでオファーライブラリを使用して、コードおよび画像オファーを管理する方法を説明します。
title: コードと画像オファーの管理方法
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 16%

---

# オファー

[!UICONTROL Offers] の [!DNL Adobe Target] ライブラリを使用して、コードオファーと画像オファーのコンテンツを管理します。

1. 「**[!UICONTROL Offers]**」をクリックしてライブラリを開きます。

   ライブラリには、[!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager]（AEM）、[!DNL Adobe Mobile Services]（AMS）および API で設定されたオファーが含まれています。[!DNL Target Classic] またはその他のソリューションで作成されたオファーは [!DNL Target Standard/Premium] で編集可能です。

   [!UICONTROL Offers] ページには、右側に 2 つのタブ（タイプ別にオファーを表示できる [!UICONTROL Code Offers] と [!UICONTROL Image Offers]）があります。

   ![&#x200B; 「コードオファー」タブと「画像オファー」タブを表示するオファーページ &#x200B;](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. （任意）「**[!UICONTROL Type]**」ドロップダウンリストをクリックして、タイプ（HTML オファー、[&#x200B; エクスペリエンスフラグメント &#x200B;](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)、[&#x200B; リダイレクトオファー &#x200B;](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[&#x200B; リモートオファー &#x200B;](/help/main/c-experiences/c-manage-content/about-remote-offers.md)、[JSON オファー &#x200B;](/help/main/c-experiences/c-manage-content/create-json-offer.md)、および [&#x200B; フォルダー &#x200B;](/help/main/c-experiences/c-manage-content/create-content-folder.md)）でオファーをフィルタリングします。

   ![offers_filter 画像 &#x200B;](assets/offers_filter.png)

1. （任意）「**[!UICONTROL Source]**」ドロップダウンリストをクリックして、ソース（Adobe Target、Adobe Target Classic、Adobe Experience Manager）別にオファーをフィルタリングします。

1. （オプション）「[!UICONTROL Code Offers]」タブで目的のオファーまたはフォルダーにマウスポインターを置いてから目的のアイコンをクリックして、追加のタスクを実行します。

   ![&#x200B; コードオファーオプション &#x200B;](assets/offer-picker-large.png)

   オプションは以下のとおりです。

   * 表示（詳しくは、以下の [&#x200B; オファー定義の表示 &#x200B;](#section_6B059DD121434E6292CAB393507D010E) を参照してください）。
   * 編集
   * コピー
   * 移動（例えば、1 つ以上の項目をフォルダーに移動するには、目的の項目の **[!UICONTROL Move]** のアイコンをクリックし、目的のフォルダーをクリックしてから「**[!UICONTROL Drop]**」をクリックします）。
   * 削除

   権限によっては、一部のオプションのアイコンが表示されない場合があります。 例えば、[!UICONTROL Observer] の権限を持つユーザーは [!UICONTROL Copy] オプションを使用する権限を持っていません。

   オファーおよびフォルダーに対して実行できるタスクについて詳しくは、「[&#x200B; アセットライブラリのコンテンツの操作 &#x200B;](/help/main/c-experiences/c-manage-content/assets-working.md)」を参照してください。

1. （オプション） [!UICONTROL Image Offers] ールタブで目的の画像オファーまたはフォルダーにマウスポインターを置き、目的のアイコンをクリックして、追加のタスクを実行します。

   ![&#x200B; 画像オファーオプション &#x200B;](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   オプションは以下のとおりです。

   * 選択
   * ダウンロード
   * プロパティを表示
   * 編集
   * 注釈
   * コピー

   オファーおよびフォルダーに対して実行できるタスクについて詳しくは、「[&#x200B; アセットライブラリのコンテンツの操作 &#x200B;](/help/main/c-experiences/c-manage-content/assets-working.md)」を参照してください。

   >[!NOTE]
   >
   >画像オファーは、「[&#x200B; エンタープライズユーザー権限 &#x200B;](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) モデルには含まれていません。


## オファー定義の表示 {#section_6B059DD121434E6292CAB393507D010E}

オファーを開かなくても、[!UICONTROL Offers] ライブラリのポップアップカードにオファー定義の詳細を表示できます。

例えば、HTMLオファーの次のオファー定義カードは、情報アイコンをクリックしてアクセスします。

![offer-card-html 画像 &#x200B;](assets/offer-card-html-new.png)

以下の情報が表示されます。

* 名前
* オファー ID
* タイプ
* 最終変更日

[!UICONTROL View Full Details] リンクをクリックして、オファーのコンテンツと、コードオファーを参照するアクティビティを表示します。 これにより、オファーの編集中に他のアクティビティに影響が及ぶことを防止できます。情報には、[!UICONTROL Live Activities] と [!UICONTROL Inactive Activities] があります。

各カードで使用できる情報は、オファータイプ（HTML オファー、[&#x200B; エクスペリエンスフラグメント &#x200B;](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)、[&#x200B; リダイレクトオファー &#x200B;](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[&#x200B; リモートオファー &#x200B;](/help/main/c-experiences/c-manage-content/about-remote-offers.md)、[JSON オファー &#x200B;](/help/main/c-experiences/c-manage-content/create-json-offer.md) によって異なります。

オファー詳細機能は、画像オファーには適用されません。

<!--

## Training video: The Content Repository ![Overview badge](/help/main/assets/overview.png)

This video includes information about managing offers.

* Connection between the [Experience Cloud Asset Library](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html?lang=ja) and the Target Content Library 
* Custom HTML Offers 
* Custom HTML Offer in the [!UICONTROL Visual Experience Composer]

>[!VIDEO](https://video.tv.adobe.com/v/17387)

-->
