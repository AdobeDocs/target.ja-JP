---
keywords: オーディエンス、オーディエンスルール、オーディエンスの作成、オーディエンスの作成、ターゲットオーディエンス、レポートオーディエンス、レポートオーディエンス、セグメント、カスタムプロファイルパラメーター、オーディエンス定義、オーディエンスリスト
description: オーディエンスの使用方法については、 [!DNL Adobe Target].
title: オーディエンスリストの使用方法
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1333'
ht-degree: 23%

---

# オーディエンスの作成

のオーディエンス [!DNL Adobe Target] ターゲットアクティビティでコンテンツとエクスペリエンスを表示する対象を決定します。

オーディエンスは、ターゲット設定を利用できるあらゆる場所で使用されます。アクティビティをターゲティングする場合、次のオプションがあります。

* 次の場所から再利用可能なオーディエンスを選択 [!UICONTROL オーディエンス] リスト
* [アクティビティ固有のオーディエンスの作成](/help/main/c-target/creating-activity-only-audience.md) そして、ターゲットにします。
* [複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) アドホックオーディエンスを作成するには

また、 [!DNL Adobe Analytics] でのリアルタイムのターゲティングとパーソナライゼーションのための [!DNL Target] その他 [!DNL Adobe Experience Cloud] アプリケーション。 詳しくは、 [Experience Cloudオーディエンス](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=ja) 内 *Experience Cloud中央インターフェイスコンポーネント* ガイド。

オーディエンスのタイプは次の 2 つです。 [!DNL Target]:

* **ターゲティングオーディエンス：** 異なるタイプの訪問者に異なるコンテンツを配信するために使用します。
* **レポート用オーディエンス：** 異なるタイプの訪問者が同じコンテンツにどのように反応するかを判断するために使用され、テスト結果を分析できます。

   [!DNL Target] では、レポートソースとして [!DNL Target] を使用する場合にのみ、レポート用オーディエンスを設定できます。レポートソースとして [ Adobe Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md)（A4T）を使用する場合は、[!DNL Analytics] 内でレポート用オーディエンスを設定する必要があります。

## 以下を使用： [!UICONTROL オーディエンス] リスト {#use-list}

[!UICONTROL オーディエンス]リストにアクセスするには、上部のメニューバーで「**[!UICONTROL オーディエンス]**」をクリックします。

![オーディエンスリスト](assets/audiences_list.png)

この [!UICONTROL オーディエンス] リストには、アクティビティで使用できるオーディエンスが含まれます。 以下を使用： [!UICONTROL オーディエンス] リストを使用して、オーディエンスを作成、編集、複製、コピー、組み合わせることができます。 リストには、オーディエンスが作成されたソースも表示されます。

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

   >[!NOTE]
   >
   >この [!DNL Adobe Experience Platform] ソースは、すべての [!DNL Target] のお客様が [Adobe Experience Platform Web SDK](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md). 次の場所から利用可能なオーディエンス： [!DNL Adobe Experience Platform] そのまま、またはとして使用できます [既存のオーディエンスとの組み合わせ](/help/main/c-target/combining-multiple-audiences.md).
   >
   >ユーザーが [!UICONTROL 承認者] または [!DNL Target] 設定する [!DNL Target] [!UICONTROL 宛先] AEP/RTCDP のカード ([!DNL Real-time Customer Data Platform]) をクリックします。
   >
   >詳しくは、 [Adobe Experience Platformのオーディエンスを使用](#aep).

事前定義済みのオーディエンス (「[!UICONTROL 新規訪問者]&quot;および&quot;[!UICONTROL 再訪問者]、「」の名前は変更できません。

元々 [!DNL Experience Cloud] または [!DNL Adobe Experience Platform], [!DNL Target] でオーディエンスを参照する場合に警告を表示します。 [!DNL Target] 次の場所で後で削除されたアクティビティ： [!DNL Experience Cloud] または [!DNL Adobe Experience Platform].

* オーディエンスが [!DNL Experience Cloud] または [!DNL Adobe Experience Platform]( 両方の [!UICONTROL 対象ユーザ] リストとオーディエンスピッカーが表示されます。 ツールチップ [!DNL Target] また、UI は、オーディエンスが [!DNL Experience Cloud] または [!DNL Adobe Experience Platform].
* 複数のオーディエンスを削除済みのオーディエンスに結合しようとした場合、または削除済みのオーディエンスを参照しているアクティビティを保存しようとした場合、警告メッセージが表示されます。

カスタムプロファイルパラメーターおよび `user.` パラメーターをターゲット設定することもできます。オーディエンスを作成する際に、アクティビティのターゲット設定に使用する属性をオーディエンスビルダーウィンドウにドラッグします。 目的の属性が表示されない場合、その属性は mbox で実行されていません。 他のカスタム mbox パラメーターは、[!UICONTROL カスタムパラメーター]ドロップダウンリストに表示されます。

以下を使用： [!UICONTROL フィルター] ボタンを使用してフィルターを適用します。 [!UICONTROL オーディエンス] ソース別のリスト： [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud]、および [!DNL Adobe Experience Platform].

![「フィルター」オプション ( [!UICONTROL オーディエンス] リスト](assets/filters.png)

以下を使用： [!UICONTROL オーディエンスを検索] ボックスで [!UICONTROL オーディエンス] リスト。 オーディエンス名の一部で検索したり、特定の文字列を引用符で囲んだりすることも可能です。

[!UICONTROL オーディエンス]リストは、オーディエンス名または最終更新日付で並べ替えることができます。名前や日付で並べ替える場合は、列見出しをクリックし、昇順または降順でオーディエンスを表示するよう選択します。

## オーディエンス定義を表示 {#section_11B9C4A777E14D36BA1E925021945780}

オーディエンス定義の詳細は、 [!DNL Target] オーディエンスを開かない UI。 この機能は、 [!DNL Target Standard/Premium] およびからインポートされたオーディエンス [!DNL Target Classic] または API を使用して作成されたもの。

例えば、次のオーディエンス定義カードには、 [!UICONTROL 詳細を表示] 目的のオーディエンスのアイコン：

![アクティビティ／オーディエンス定義](assets/audience_definition_list.png)

次のオーディエンス定義カードは、 [!UICONTROL 詳細を表示] アクティビティのアイコン [!UICONTROL 概要] ページ：

![アクティビティ／オーディエンス定義](assets/view-details-activity-overview.png)

オーディエンス定義カードには、オーディエンスのタイプ、ソースおよび属性が表示されます。 クリック **[!UICONTROL 詳細を表示]** 該当する場合は、そのオーディエンスを参照する他のアクティビティを表示する。 アクティビティの [!UICONTROL 概要] ページ、クリック **[!UICONTROL オーディエンスの使用状況]**.

オーディエンスの使用状況情報は、オーディエンスの編集中に他のアクティビティに予期しない影響を与えるのを防ぐのに役立ちます。 次の情報が含まれます。 [!UICONTROL ライブアクティビティ], [!UICONTROL 非アクティブなアクティビティ], [!UICONTROL アーカイブ済みアクティビティ]、および [!UICONTROL アクティビティの同期]. この機能は、すべてのオーディエンス ( ライブラリオーディエンスおよび [アクティビティのみのオーディエンス](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)) をクリックします。

オーディエンスが [他のオーディエンスと組み合わされる](/help/main/c-target/combining-multiple-audiences.md) と結合オーディエンスは、アクティビティの作成に使用されます。両方のオーディエンスの使用情報には、新しく作成されたアクティビティが表示されます。

![](assets/audience_definition_list_usage.png)

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

## 次のオーディエンスを使用： [!DNL Adobe Experience Platform] {#aep}

[!DNL Adobe Experience Platform] で作成されたオーディエンスを使用すると、よりインパクトのあるパーソナライゼーションにつながる豊富な顧客データが提供されます。この [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=ja){target=_blank} (RTCDP)。 [!DNL Adobe Experience Platform]は、企業が複数のエンタープライズソースから既知の匿名データを統合するのに役立ちます。 このプロセスでは、すべてのチャネルとデバイスにわたって、リアルタイムでパーソナライズされた顧客体験を提供するために使用できる顧客プロファイルを作成できます。

接続により [!DNL Target] から [!DNL Real-time Customer Data Platform]では、以前にアクセスできなかった新しいセグメントをロック解除して、Web パーソナライゼーションを強化できます [!DNL Target] 顧客の web 訪問の最初のページでリアルタイムのミリ秒パーソナライゼーションを有効にする。 で作成されたオーディエンスの使用 [!DNL Adobe Experience Platform] を使用すると、利用可能なデータポイントを拡張して、より豊富なパーソナライゼーションを実現できます。

この統合により、RTCDP での主な使用例のロックが解除されます。

* 同じページ/次のヒットのパーソナライゼーション
* 初回/不明なユーザーのパーソナライゼーション

主な特長は次のとおりです。

* RTCDP/との直接 Target 統合[!DNL Adobe Experience Platform] Edge 上 ( [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge Destinations カード] ガバナンスの執行を受けて
* 統合プロファイルを使用したエッジセグメント化とエッジプロファイル

詳しくは、次のトピックを参照してください。

* [宛先のリリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} *Adobe Experience Platformリリースノート*
* [同じページと次のページのパーソナライゼーション用にパーソナライゼーションの宛先を設定](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} *宛先の概要* ガイド。
* [カスタムパーソナライゼーション接続](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} *宛先の概要* ガイド
* [Adobe Target接続](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} *宛先の概要* ガイド
* [同じページおよび次のページのパーソナライゼーションの使用例に対するパーソナライゼーションの宛先の設定](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} *宛先の概要* ガイド

### 追加情報

次のオーディエンスを使用する際は、次の情報を考慮してください。 [!DNL Adobe Experience Platform]:

#### パーソナライズ機能の使用例

次の表に、 [!DNL Adobe Experience Platform Web SDK] at.js の使用と比較して：

| 実装 | ソリューション/ユースケースが有効 |
| --- | --- |
| at.js | **ソリューション**:<ul><li>[!DNL Adobe Audience Manager] (AAM) および [!DNL Target]</li><li>[!DNL RTCDP] （Premium または Ultimate）および [!DNL Target]</li><li>[!DNL RTCDP] （任意の SKU）、 [!DNL AAM]、および [!DNL Target]</li></ul>**ユースケース**:<ul><li>次セッションのパーソナライゼーション</li></ul> |
| [!DNL Platform Web SDK] または [!DNL AEP Server-Side API] | **ソリューション**:<ul><li>[!DNL RTCDP] （任意の SKU）および [!DNL Target]</li></ul>**使用例**:<ul><li>次セッションのパーソナライゼーション</li><li>Edge を使用した同じページのパーソナライゼーション</li><li>セグメントの共有時に適用されるガバナンス</li></ul>**ソリューション**:<ul><li>[!DNL RTCDP] （任意の SKU）、 [!DNL AAM]、および [!DNL Target]</li></ul>**使用例**:<ul><li>次セッションのパーソナライゼーション</li><ul><li>[!DNL AAM] セグメント</li><li>を介したサードパーティセグメント [!DNL AAM]</li></ul><li>Edge を使用した同じページのパーソナライゼーション</li><ul><li>[!DNL RTCDP] セグメント</li><li>セグメントの共有時に適用されるガバナンス</li></ul> |
| 組み合わせ [!UICONTROL at.js] および [!DNL Platform Web SDK] | **ソリューション**:<ul><li>[!DNL RTCDP] （任意の SKU）および [!DNL Target]</li></ul>**使用例**:<ul><li>次セッションのパーソナライゼーション</li><ul><li>を含むすべてのページ [!UICONTROL at.js]</li></ul><li>同じページのパーソナライゼーション</li><ul><li>を含むすべてのページ [!DNL Platform Web SDK]</li></ul></ul>**ソリューション**:<ul><li>[!DNL RTCDP] （任意の SKU）、 [!DNL AAM]、および [!DNL Target]</li></ul>**使用例**:<ul><li>次セッションのパーソナライゼーション</li><ul><li>を含むすべてのページ [!UICONTROL at.js]</li><li>[!DNL AAM] セグメント</li><li>を介したサードパーティセグメント [!DNL AAM]</li></ul> |

#### セグメント評価時間

次の表に、様々な実装シナリオから発生するイベントのセグメント評価時間を示します。

| シナリオ | エッジセグメント（ミリ秒評価） | ストリーミングセグメント（分単位の評価） | バッチセグメント評価 |
| --- | --- | --- | --- |
| イベント/データの取得元 [!DNL Adobe Experience Platform] SDK | ○ | ○ | 該当なし |
| イベント元 [!UICONTROL at.js] | × | ○ | 該当なし |
| イベント元 [!DNL Target Mobile] SDK | × | ○ | 該当なし |
| バッチアップロードからのイベント | × | × | ○ |
| オフラインデータ（ストリーム）からのイベント | × | ○ | ○ |

### ビデオ：リアルタイム CDP と [!DNL Adobe Target]{#RTCDP}

を使用して次回のヒットでのパーソナライズ方法を説明します。 [!DNL Real-time Customer Data Platform] および [!DNL Adobe Target]. この [!DNL Adobe Target] の宛先 [!DNL Real-time CDP] を使用すると、 [!DNL Experience Platform] セグメント [!DNL Adobe Target] ガバナンスとプライバシーのサポートを含む、同じページと次のページのパーソナライゼーション。

詳しくは、 [リアルタイム CDP とAdobe Targetを使用した次回ヒットのパーソナライゼーション](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} *PlatformTutorials* ガイド。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Adobe Targetのブログとビデオ：

[[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] および [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

## トレーニングビデオ：オーディエンスの使用 ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスの使用に関する情報が説明されています。

* 用語「オーディエンス」の説明
* 最適化のためにオーディエンスを使用する 2 つの方法の説明
* オーディエンスリストでのオーディエンスの検索
* アクティビティのオーディエンスへのターゲット設定
* アクティビティの受動的なレポート用でのオーディエンスの使用

>[!VIDEO](https://video.tv.adobe.com/v/17398)
