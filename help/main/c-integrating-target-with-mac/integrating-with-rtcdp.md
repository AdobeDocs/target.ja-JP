---
keywords: Real-time Customer Data Platform;rtcdp；パーソナライゼーション；aep オーディエンス；adobe experience platform オーディエンス；プロファイル属性
description: ' [!DNL Target]/[!DNL Real-Time Customer Data Platform] （RTCDP）統合を使用して、より豊富な顧客データとよりインパクトのあるパーソナライゼーションを提供する方法を説明します。'
title: ' [!DNL Target] と [!DNL Real-Time Customer Data Platform] の統合方法'
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 9db63ccce0d4f62f968cc99250f3ed3dec03a977
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 8%

---

# 統合対象 [!DNL Real-Time Customer Data Platform]

ビルド元 [!DNL Adobe Experience Platform], [!DNL Real-Time Customer Data Platform] (RTCDP) は、企業が既知のデータと匿名データを複数のエンタープライズソースから統合する際に役立ちます。 RTCDP を使用すると、すべてのチャネルとデバイスにわたって、リアルタイムでパーソナライズされたカスタマーエクスペリエンスを提供するために使用できる顧客プロファイルを作成できます。

RTCDP の詳細については、 [Real-time Customer Data Platformの概要](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=ja){target=_blank}.

## 次のオーディエンスを使用： [!DNL Adobe Experience Platform] {#aep}

使用 [audiences](/help/main/c-target/c-audiences/audiences.md) 次で作成： [!DNL Adobe Experience Platform] より効果的なパーソナライゼーションにつながる、より豊富な顧客データを提供します。 この [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=ja){target=_blank} (RTCDP): [!DNL Adobe Experience Platform]は、企業が複数のエンタープライズソースから既知の匿名データを統合するのに役立ちます。 このプロセスでは、すべてのチャネルとデバイスにわたって、リアルタイムでパーソナライズされた顧客体験を提供するために使用できる顧客プロファイルを作成できます。

接続により [!DNL Target] から [!DNL Real-Time Customer Data Platform]を使用すると、web パーソナライゼーションを強化できます。 この統合により、以前はアクセスできなかった可能性のある新しいセグメントのロックを解除できます [!DNL Target] 顧客の web 訪問の最初のページでリアルタイムのミリ秒パーソナライゼーションを有効にする。 で作成したオーディエンスとプロファイル属性の使用 [!DNL Adobe Experience Platform] を使用すると、利用可能なデータポイントを拡張して、より豊富なパーソナライゼーションを実現できます。

この統合により、Real-Time CDPの主なユースケースのロックが解除されます。

* 同じページ/次のヒットのパーソナライゼーション
* 初回/不明なユーザーのパーソナライゼーション

### 主な機能

主な特長は次のとおりです。

* 直接 [!DNL Target] Real-Time CDP/との統合[!DNL Adobe Experience Platform] Edge 上 ( [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge Destinations カード] ガバナンスと政策の執行を伴う
* リアルタイム CDP セグメントと共有プロファイル属性

### パーソナライズ機能の使用例

以下の節では、異なる実装方法を使用する場合に使用できるパーソナライゼーションの使用例のタイプ（次のセッションまたは同じページ）を示します。

#### at.js の実装

| 解決策 | 使用例が有効 |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM) および [!DNL Target]</li><li>[!DNL RTCDP] （Premium または Ultimate）および [!DNL Target]</li><li>[!DNL RTCDP] （任意の SKU）、 [!DNL AAM]、および [!DNL Target]</li></ul> | 次セッションのパーソナライゼーション |

#### [!DNL Adobe Experience Platform Web SDK] または [!DNL Experience Platform Server-Side API] 実装

| 解決策 | 使用例が有効 |
| --- | --- |
| <ul><li>[!DNL RTCDP] （任意の SKU）および [!DNL Target]</li></ul> | <ul><li>次セッションのパーソナライゼーション</li><li>Edge を使用した同じページのパーソナライゼーション</li><li>セグメントの共有時に適用されるガバナンス</li></ul> |
| <ul><li>[!DNL RTCDP] （任意の SKU）、 [!DNL AAM]、および [!DNL Target]</li></ul> | <ul><li>次セッションのパーソナライゼーション</li><ul><li>[!DNL AAM] セグメント</li><li>を介したサードパーティセグメント [!DNL AAM]</li></ul><li>Edge を使用した同じページのパーソナライゼーション</li><ul><li>[!DNL RTCDP] セグメント</li><li>セグメントの共有時に適用されるガバナンス</li></ul> |

#### 組み合わせ [!UICONTROL at.js] および [!DNL Platform Web SDK] 実装

| 解決策 | 使用例が有効 |
| --- | --- |
| <ul><li>[!DNL RTCDP] （任意の SKU）および [!DNL Target]</li></ul> | <ul><li>次セッションのパーソナライゼーション</li><ul><li>を含むすべてのページ [!UICONTROL at.js]</li></ul><li>同じページのパーソナライゼーション</li><ul><li>を含むすべてのページ [!DNL Platform Web SDK]</li></ul> |
| <ul><li>[!DNL RTCDP] （任意の SKU）、 [!DNL AAM]、および [!DNL Target]</li></ul> | <ul><li>次セッションのパーソナライゼーション</li><ul><li>を含むすべてのページ [!UICONTROL at.js]</li><li>[!DNL AAM] セグメント</li><li>を介したサードパーティセグメント [!DNL AAM]</li></ul> |

### セグメント評価時間

次の表に、様々な実装シナリオから発生するイベントのセグメント評価時間を示します。

| シナリオ | エッジセグメント（ミリ秒評価） | ストリーミングセグメント（分単位の評価） | バッチセグメント評価 |
| --- | --- | --- | --- |
| イベント/データの取得元 [!DNL Adobe Experience Platform] SDK | ○ | ○ | 該当なし |
| イベント元 [!UICONTROL at.js] | × | ○ | 該当なし |
| イベント元 [!DNL Target Mobile] SDK | × | ○ | 該当なし |
| バッチアップロードからのイベント | × | × | ○ |
| オフラインデータ（ストリーム）からのイベント | × | ○ | ○ |

### 詳細情報へのリンク

詳しくは、次のトピックを参照してください。

* [宛先のリリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} 内 *Adobe Experience Platformリリースノート*
* [同じページと次のページのパーソナライゼーション用にパーソナライゼーションの宛先を設定](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} 内 *宛先の概要* ガイド。
* [カスタムパーソナライゼーション接続](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} 内 *宛先の概要* ガイド
* [Adobe Target接続](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} 内 *宛先の概要* ガイド
* [同じページおよび次のページのパーソナライゼーションの使用例に対するパーソナライゼーションの宛先の設定](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} 内 *宛先の概要* ガイド

## Real-Time CDPプロファイル属性の共有先 [!DNL Target] {#rtcdp-profile-attributes}

Real-Time CDPプロファイル属性はと共有できます [!DNL Target] (HTMLオファーで使用 ) [JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Real-Time CDPプロファイル属性機能の制限と考慮事項

>[!NOTE]
>
>Real-Time CDPのプロファイル属性機能は、ベータ版ではHTMLオファーおよび [JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md).

次の点に留意してください。

* 特定のオファー内の属性は、同じオファーの属性である必要があります [!UICONTROL Experience Platform] サンドボックス。 ( つまり、1 つのオファーに異なる [!UICONTROL Experience Platform] サンドボックス )
* 特定のオファー内の属性は、別のソースから取得できます。すなわち、 [!DNL Target] プロファイルと [!UICONTROL Experience Platform] プロファイル。 ( つまり、属性を [!DNL Target] または [!UICONTROL Experience Platform] profile.)
* オファーを定義する際に、 [!UICONTROL Real-Time CDP Profile Attributes]を指定します。 例えば、同意またはガバナンスポリシーがパーソナライゼーションサービスで使用される属性をブロックする場合は、代わりにデフォルト値を使用できます。
* 共有時、 [!UICONTROL Real-Time CDP Profile Attributes] は、 [!UICONTROL 自動ターゲット] および [!UICONTROL Automated Personalization] アクティビティ。

### JSON のサンプルの使用例

オンラインマーケターは、AEP/統合プロファイルで属性値を共有したい [!DNL Target] リアルタイムパーソナライゼーションを提供する。 次を使用： [!UICONTROL Real-Time CDP Profile Attributes]に値を指定しない場合、 [!UICONTROL Experience Platform] 属性 [!DNL Target] トークン置換を使用したオファー 例えば、顧客が好む色に応じて、 `${aep.profile.favoriteColor}`、またはトークンを使用したロイヤリティ層とロイヤルティポイントの値 `${aep.loyalty.tier}` および `${aep.loyalty.points}`.

AEP/統合プロファイル属性を共有する JSON オファーを作成するには、以下を実行します。 [!DNL Target]:

1. While [JSON オファーの作成](/help/main/c-experiences/c-manage-content/create-json-offer.md)、 **[!UICONTROL ソースを選択]** リスト、選択 **[!UICONTROL Adobe Experience Platform]**.
1. 次の **[!UICONTROL プロファイルサンドボックス名を選択]** リストで、目的のサンドボックスを選択します。
1. 次の **[!UICONTROL プロファイル属性を選択]** リストで、目的の属性を選択します。
1. （オプション） **[!UICONTROL デフォルト値を挿入]** リストで、目的の値を選択します。
1. 「**[!UICONTROL 追加]**」をクリックします。

   次の図に、2 つのプロファイル属性を示します。 `loyalty.tier` および `loyalty.points` が JSON オファーに追加されました。

   ![offer-json-aep-shared-attribute image](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## ビデオおよびブログ投稿

次のビデオおよびブログ投稿では、Target と RTCDP を使用した拡張パーソナライゼーションの詳細を説明しています。

### ビデオ：Real-Time CDPとを使用した次回ヒットのパーソナライゼーション [!DNL Adobe Target]{#RTCDP}

を使用して次回のヒットでのパーソナライズ方法を説明します。 [!DNL Real-Time Customer Data Platform] および [!DNL Adobe Target]. この [!DNL Adobe Target] の宛先 [!DNL Real-Time CDP] を使用すると、 [!DNL Experience Platform] セグメント [!DNL Adobe Target] ガバナンスとプライバシーをサポートする、同じページのパーソナライゼーションと次のページのパーソナライゼーション。

詳しくは、 [Real-Time CDPとAdobe Targetを使用した次のヒットのパーソナライゼーション](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} 内 *PlatformTutorials* ガイド。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### [!DNL Adobe Target] ブログとビデオ：同じページで拡張されたパーソナライゼーション

[[!DNL Adobe] announces Same-Page Enhanced Personalization with [!DNL Adobe Target] および [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}
