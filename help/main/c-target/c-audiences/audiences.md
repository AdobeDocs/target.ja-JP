---
keywords: オーディエンス、オーディエンスルール、オーディエンスの作成、オーディエンスの作成、ターゲットオーディエンス、レポートオーディエンス、レポートオーディエンス、セグメント、カスタムプロファイルパラメーター、オーディエンス定義、オーディエンスリスト
description: ' [!DNL Adobe Target] でオーディエンスを使用する方法を説明します。'
title: オーディエンスリストの使用方法
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 22%

---

# オーディエンスの作成

[!DNL Adobe Target] のオーディエンスは、ターゲットアクティビティで、コンテンツとエクスペリエンスをどのユーザーに表示するかを決定します。

オーディエンスは、ターゲット設定を利用できるあらゆる場所で使用されます。アクティビティをターゲット設定する場合、次のオプションがあります。

* オーディエンスリストから再利用可能なオーディ [!UICONTROL Audiences] ンスを選択
* [ アクティビティ固有のオーディエンスを作成し ](/help/main/c-target/creating-activity-only-audience.md) ターゲット設定します
* [ 複数のオーディエンスの結合 ](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) によるアドホックオーディエンスの作成

また、[!DNL Adobe Analytics] で収集したオーディエンスデータを使用して、[!DNL Target] やその他の [!DNL Adobe Experience Cloud] アプリケーションでリアルタイムのターゲティングやパーソナライゼーションを行うこともできます。 *Experience Cloudの中央インターフェイスコンポーネント [&#128279;](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=ja) ガイドの Experience Cloudオーディエンス* を参照してください。

オーディエンスには次の 2 種類があり [!DNL Target] す。

* **オーディエンスのターゲティング：** 様々なコンテンツを様々なタイプの訪問者に配信するために使用します。
* **レポートオーディエンス：** 様々なタイプの訪問者が同じコンテンツにどのように応答するかを決定し、テスト結果を分析できるようにします。

  [!DNL Target] では、レポートソースとして [!DNL Target] を使用する場合にのみ、レポート用オーディエンスを設定できます。[Adobe Analyticsをレポートソースとして使用する場合 ](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）、[!DNL Analytics] 内でレポートオーディエンスを設定する必要があります。

## [!UICONTROL Audiences] リストの使用 {#use-list}

[!UICONTROL Audiences] リストにアクセスするには、上部のメニューバーで「**[!UICONTROL Audiences]**」をクリックします。

リ ![[!UICONTROL Audiences] ト ](assets/audiences_list.png)

[!UICONTROL Audiences] リストには、アクティビティで使用できるオーディエンスが表示されます。 [!UICONTROL Audiences] リストを使用して、オーディエンスを作成、編集、複製、コピーまたは組み合わせます。 このリストには、オーディエンスが作成されたソースも表示されます。

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

  >[!NOTE]
  >
  >[!DNL Adobe Experience Platform] ソースは、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} を使用するすべての [!DNL Target] ユーザーが利用できます。 [!DNL Adobe Experience Platform] から使用可能なオーディエンスは、そのまま使用することも、[ 既存のオーディエンスと組み合わせて ](/help/main/c-target/combining-multiple-audiences.md) 使用することもできます。
  >
  >AEP/RTCDP （[!DNL Real-time Customer Data Platform]）で [!DNL Target] [!UICONTROL Destinations] カードを設定 [!DNL Target] るには、ユーザーのステータスが [!UICONTROL Approver] 以上である必要があります。
  >
  >詳しくは、[Adobe Experience Platformのオーディエンスの使用 ](#aep) を参照してください。

定義済みオーディエンス（「[!UICONTROL New Visitors]」や「[!UICONTROL Returning Visitors]」など）の名前は変更できません。

最初に [!DNL Experience Cloud] または [!DNL Adobe Experience Platform] で作成されたオーディエンスを使用する場合、後で [!DNL Experience Cloud] または [!DNL Adobe Experience Platform] で削除された [!DNL Target] アクティビティのオーディエンスを参照すると、[!DNL Target] でアラートが表示されます。

* [!DNL Experience Cloud] または [!DNL Adobe Experience Platform] でオーディエンスが削除された場合、[!UICONTROL Audience] リストとオーディエンスピッカーの両方に警告アイコンが表示されます。 [!DNL Target] UI のツールヒントにも、オーディエンスが [!DNL Experience Cloud] または [!DNL Adobe Experience Platform] で削除されたことが示されます。
* 複数のオーディエンスを削除済みのオーディエンスに結合しようとした場合、または削除済みのオーディエンスを参照しているアクティビティを保存しようとした場合、警告メッセージが表示されます。

カスタムプロファイルパラメーターおよび `user.` パラメーターをターゲット設定することもできます。オーディエンスを作成する際に、アクティビティのターゲット設定に使用する属性をオーディエンスビルダーウィンドウにドラッグします。 目的の属性が表示されない場合、その属性は mbox によって呼び出されていません。 その他のカスタム mbox パラメーターは、[!UICONTROL Custom Parameters] ドロップダウンリストで選択できます。

「[!UICONTROL Filters]」ボタンを使用して、ソース（[!DNL Adobe Target]、[!DNL Adobe Target Classic]、[!DNL Experience Cloud] および [!DNL Adobe Experience Platform]）で [!UICONTROL Audiences] リストをフィルタリングします。

![[!UICONTROL Audiences] リストの「フィルター」オプション ](assets/filters.png)

[!UICONTROL Search audiences] のボックスを使用して、[!UICONTROL Audiences] リストを検索します。 オーディエンス名の一部で検索したり、特定の文字列を引用符で囲んだりすることも可能です。

オーディエンス名または最終変更日で [!UICONTROL Audiences] リストを並べ替えることができます。 名前や日付で並べ替える場合は、列見出しをクリックし、昇順または降順でオーディエンスを表示するよう選択します。

## オーディエンス定義の表示 {#section_11B9C4A777E14D36BA1E925021945780}

オーディエンスを開かなくても、[!DNL Target] UI の様々な場所で、ポップアップカードのオーディエンス定義の詳細を表示できます。 この機能は、[!DNL Target Standard/Premium] で作成されたオーディエンス、[!DNL Target Classic] からインポートされたオーディエンス、または API を使用して作成されたオーディエンスに適用されます。

例えば、次のオーディエンス定義カードは、目的のオーディエンスの [!UICONTROL View Details] のアイコンをクリックしてアクセスします。

![アクティビティ／オーディエンス定義](assets/audience_definition_list.png)

次のオーディエンス定義カードにアクセスするには、アクティビティの [!UICONTROL Overview] ページで「[!UICONTROL View Details]」アイコンをクリックします。

![アクティビティ／オーディエンス定義](assets/view-details-activity-overview.png)

オーディエンス定義カードに、オーディエンスのタイプ、ソースおよび属性が表示されます。 該当する場合は、「**[!UICONTROL View full details]**」をクリックして、そのオーディエンスを参照する他のアクティビティを表示します。 アクティビティの [!UICONTROL Overview] ページでオーディエンス定義カードを表示している場合は、「**[!UICONTROL Audience Usage]**」をクリックします。

オーディエンスの使用状況情報は、オーディエンスの編集中に他のアクティビティに誤って影響を与えることを回避するのに役立ちます。 情報には、[!UICONTROL Live Activities]、[!UICONTROL Inactive Activities]、[!UICONTROL Archived Activities]、[!UICONTROL Syncing Activities] などがあります。 この機能は、すべてのオーディエンス（ライブラリオーディエンスと [ アクティビティのみのオーディエンス） ](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) 使用できます。

オーディエンスが [ 別のオーディエンスと結合 ](/help/main/c-target/combining-multiple-audiences.md) され、結合されたオーディエンスを使用してアクティビティが作成されている場合、両方のオーディエンスの使用状況情報には、新しく作成されたアクティビティがリストされます。

![audience_definition_list_usage 画像 ](assets/audience_definition_list_usage.png)

<!--The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM).

![Usage tab on Audience Definition card](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

| Audience Type | Details |
|--- |--- |
|Mobile audience|Marketing Name, Vendor, and Model.<br>The `matches | does not match` operator displays instead of `equals | does not equal`<br>![Imported Mobile Audience](/help/main/c-target/c-audiences/assets/imported_mobile_audience.png).|
|Visitor-behavior audience|**user.categoryAffinity:** `categoryAffinity` with `FAVORITE` parameter.<br>![Imported Category Affinity](/help/main/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoring:** Monitoring service equals true.<br>**No Monitoring Service:** Monitoring service equals false.<br>![Imported Monitoring](/help/main/c-target/c-audiences/assets/imported_monitoring.png)|
|Audiences using the NOT operator|**Single Rule:** Target displays the audience in the format `[All Visitor AND [NOT [rule]`. Single NOT rule displays with AND with `AllVisitor` audience.<br>![Imported Not Audience](/help/main/c-target/c-audiences/assets/imported_not_audience.png)|

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium. 
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.-->

## [!DNL Adobe Experience Platform] のオーディエンスの使用 {#aep}

[!DNL Adobe Experience Platform] で作成されたオーディエンスを使用すると、よりインパクトのあるパーソナライゼーションにつながる豊富な顧客データが提供されます。

詳しくは、[ のオーディエンスの使用  [!DNL Adobe Experience Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#aep) を参照してください。

## トレーニングビデオ：オーディエンスの使用 ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスの使用に関する情報が説明されています。

* 用語「オーディエンス」の説明
* 最適化のためにオーディエンスを使用する 2 つの方法の説明
* オーディエンスリストでのオーディエンスの検索
* アクティビティのオーディエンスへのターゲット設定
* アクティビティの受動的なレポート用でのオーディエンスの使用

>[!VIDEO](https://video.tv.adobe.com/v/29956?captions=jpn)
