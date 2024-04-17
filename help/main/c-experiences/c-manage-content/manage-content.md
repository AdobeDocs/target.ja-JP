---
keywords: コンテンツ;アセット;コンテンツの管理;オファー;アセットの管理;選択モードを入力;選択モード
description: Adobe Targetでオファーライブラリを使用して、コードおよび画像オファーを管理する方法を説明します。
title: コードと画像オファーの管理方法
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: f93e33e91fb7be9c0d1772a2014864b46c1dfe47
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 16%

---

# オファー

の使用 [!UICONTROL Offers] のライブラリ [!DNL Adobe Target] を使用して、コードオファーと画像オファーのコンテンツを管理します。

1. クリック **[!UICONTROL Offers]** をクリックしてライブラリを開きます。

   ライブラリには、[!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager]（AEM）、[!DNL Adobe Mobile Services]（AMS）および API で設定されたオファーが含まれています。[!DNL Target Classic] またはその他のソリューションで作成されたオファーは [!DNL Target Standard/Premium] で編集可能です。

   この [!UICONTROL Offers] ページの右側に 2 つのタブがあります。 [!UICONTROL Code Offers] および [!UICONTROL Image Offers] タイプ別にオファーを表示できます。

   ![「コードオファー」タブと「画像オファー」タブを表示するオファーページ](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. （任意） **[!UICONTROL Type]** タイプでオファーをフィルタリングするためのドロップダウンリスト（HTMLオファー、 [エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [リダイレクトオファー](/help/main/c-experiences/c-manage-content/offer-redirect.md), [リモートオファー](/help/main/c-experiences/c-manage-content/about-remote-offers.md), [JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md)、および [フォルダー](/help/main/c-experiences/c-manage-content/create-content-folder.md)）に設定します。

   ![offers_filter 画像](assets/offers_filter.png)

1. （任意） **[!UICONTROL Source]** ソース（Adobe Target、Adobe Target Classic、Adobe Experience Manager）別にオファーをフィルタリングするドロップダウンリスト。

1. （オプション）で目的のオファーまたはフォルダーにカーソルを合わせて、追加のタスクを実行します。 [!UICONTROL Code Offers] タブをクリックしてから、目的のアイコンをクリックします。

   ![コードオファーオプション](assets/offer-picker-large.png)

   オプションは以下のとおりです。

   * を表示します（詳しくは、 [オファー定義の表示](#section_6B059DD121434E6292CAB393507D010E) 下）
   * 編集
   * コピー
   * 移動（例えば、1 つ以上の項目を 1 つのフォルダーに移動するには、 **[!UICONTROL Move]** アイコンをクリックします。目的の項目を選択し、 **[!UICONTROL Drop]**.）
   * 削除

   権限によっては、一部のオプションのアイコンが表示されない場合があります。 例えば、次を含むユーザー [!UICONTROL Observer] 権限にはを使用する権限がありません [!UICONTROL Copy] オプション。

   オファーおよびフォルダーに対して実行できるタスクについて詳しくは、を参照してください。 [アセットライブラリ内のコンテンツの操作](/help/main/c-experiences/c-manage-content/assets-working.md).

1. （オプション）で目的の画像オファーまたはフォルダーにカーソルを合わせて、追加のタスクを実行します [!UICONTROL Image Offers] タブをクリックしてから、目的のアイコンをクリックします。

   ![画像オファーオプション](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   オプションは以下のとおりです。

   * 選択
   * ダウンロード
   * プロパティを表示
   * 編集
   * 注釈
   * コピー

   オファーおよびフォルダーに対して実行できるタスクについて詳しくは、を参照してください。 [アセットライブラリ内のコンテンツの操作](/help/main/c-experiences/c-manage-content/assets-working.md).

   >[!NOTE]
   >
   >画像オファーはの一部ではありません [Enterprise ユーザーの権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) モデル。


## オファー定義の表示 {#section_6B059DD121434E6292CAB393507D010E}

のポップアップカードにオファー定義の詳細を表示できます [!UICONTROL Offers] オファーを開かないライブラリ。

例えば、HTMLオファーに対して次に示すオファー定義カードは、情報アイコン

![offer-card-html 画像](assets/offer-card-html-new.png)

以下の情報が表示されます。

* 名前
* オファー ID
* タイプ
* 最終変更日

「」をクリックします [!UICONTROL View Full Details] オファーのコンテンツと、コードオファーを参照するアクティビティを表示するためのリンク。 これにより、オファーの編集中に他のアクティビティに影響が及ぶことを防止できます。次の情報が含まれます [!UICONTROL Live Activities] および [!UICONTROL Inactive Activities].

各HTMLに表示される情報は、オファータイプによって異なります。 [エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [リダイレクトオファー](/help/main/c-experiences/c-manage-content/offer-redirect.md), [リモートオファー](/help/main/c-experiences/c-manage-content/about-remote-offers.md)、または [JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md).

オファー詳細機能は、画像オファーには適用されません。

<!--

## Training video: The Content Repository ![Overview badge](/help/main/assets/overview.png)

This video includes information about managing offers.

* Connection between the [Experience Cloud Asset Library](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) and the Target Content Library 
* Custom HTML Offers 
* Custom HTML Offer in the [!UICONTROL Visual Experience Composer]

>[!VIDEO](https://video.tv.adobe.com/v/17387)

-->
