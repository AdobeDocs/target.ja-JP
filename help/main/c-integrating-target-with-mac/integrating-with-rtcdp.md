---
keywords: Real-time Customer Data Platform;rtcdp;パーソナライゼーション;aep オーディエンス;adobe experience platform オーディエンス
description: ' [!DNL Target]/[!DNL Real-time Customer Data Platform] （RTCDP）統合を使用して、より豊富な顧客データとよりインパクトのあるパーソナライゼーションを提供する方法を説明します。'
title: ' [!DNL Target] と [!DNL Real-time Customer Data Platform] の統合方法'
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 9581cfd1e5a2f0329ceed00fd370dbaabe9b92f9
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 20%

---

# Real-time Customer Data Platform との統合

[!DNL Adobe Experience Platform] 上に構築された [!DNL Real-time Customer Data Platform]（RTCDP）は、企業が顧客プロファイルを作成するために複数の企業ソースから既知および匿名のデータを収集するのに役立ちます。顧客プロファイルを使用すれば、パーソナライズされた顧客エクスペリエンスをすべてのチャネルおよびデバイスにわたってリアルタイムに提供できます。

RTCDP の詳細については、 [Real-time Customer Data Platformの概要](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=ja){target=_blank}.

## 次のオーディエンスを使用： [!DNL Adobe Experience Platform] {#aep}

[!DNL Adobe Experience Platform] で作成されたオーディエンスを使用すると、よりインパクトのあるパーソナライゼーションにつながる豊富な顧客データが提供されます。この [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=ja){target=_blank} (RTCDP): [!DNL Adobe Experience Platform]は、企業が複数のエンタープライズソースから既知の匿名データを統合するのに役立ちます。 このプロセスでは、すべてのチャネルとデバイスにわたって、リアルタイムでパーソナライズされた顧客体験を提供するために使用できる顧客プロファイルを作成できます。

[!DNL Target] と [!DNL Real-time Customer Data Platform] を接続することで、お客様は、以前は [!DNL Target] でアクセスできなかった可能性のある新しいセグメントを解放し、お客様の web 訪問の最初のページでミリ秒単位のリアルタイムのパーソナライゼーションを可能にすることで、web パーソナライゼーションを充実させることができます。で作成したオーディエンスとプロファイル属性の使用 [!DNL Adobe Experience Platform] を使用すると、利用可能なデータポイントを拡張して、より豊富なパーソナライゼーションを実現できます。

この統合により、リアルタイム CDP での主なユースケースのロックが解除されます。

* 同じページ/次のヒットのパーソナライゼーション
* 初回/不明なユーザーのパーソナライゼーション

主な特長は次のとおりです。

* 直接 [!DNL Target] リアルタイム CDP/との統合[!DNL Adobe Experience Platform] Edge 上 ( [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge Destinations カード] ガバナンスと政策の執行を伴う
* リアルタイム CDP セグメントと共有プロファイル属性

リアルタイム CDP プロファイル属性の機能の制限と考慮事項：

* 特定のオファー内の属性は、同じ AEP サンドボックスからのものである必要があります。 （つまり、1 つのオファーに異なる AEP サンドボックスの属性を含めることはできません）。
* 特定のオファー内の属性は、別のソースから取得される場合があります。つまり、Target プロファイルと AEP プロファイルです。（つまり、属性は、Target から取得したものか AEP プロファイルから取得したものかに関わらず、組み合わせることができます）。
* オファーを定義する際に、属性に明示的な値がない場合に備えて、リアルタイム CDP プロファイル属性にデフォルト値を割り当てることができます。 例えば、同意またはガバナンスポリシーがパーソナライゼーションサービスで使用される属性をブロックする場合は、代わりにデフォルト値を使用できます。
* 共有すると、リアルタイム CDP プロファイル属性が、自動ターゲットとAutomated Personalizationの人工知能/機械学習パーソナライゼーションモデルで使用されます。

>[!NOTE]
>
>リアルタイム CDP プロファイル属性機能は、現在、ベータ版では、HTMLオファーおよび [JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md).

詳しくは、次のトピックを参照してください。

* [宛先のリリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} 内 *Adobe Experience Platformリリースノート*
* [同じページと次のページのパーソナライゼーション用にパーソナライゼーションの宛先を設定](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} 内 *宛先の概要* ガイド。
* [カスタムパーソナライゼーション接続](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} 内 *宛先の概要* ガイド
* [Adobe Target接続](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} 内 *宛先の概要* ガイド
* [同じページおよび次のページのパーソナライゼーションの使用例に対するパーソナライゼーションの宛先の設定](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} 内 *宛先の概要* ガイド

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

詳しくは、 [リアルタイム CDP とAdobe Targetを使用した次回ヒットのパーソナライゼーション](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} 内 *PlatformTutorials* ガイド。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Adobe Targetのブログとビデオ：

[[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] および [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

## とのリアルタイム CDP プロファイル属性の共有 [!DNL Target] {#rtcdp-profile-attributes}

リアルタイム CDP プロファイル属性は、と共有できます。 [!DNL Target] HTMLオファーと JSON オファーで使用する （この機能は現在ベータ版であることに注意してください）。

詳しくは、 [とのリアルタイム CDP プロファイル属性の共有 [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes)

使用例：グレースは、オンラインマーケターとして、AEP/統合プロファイルに属性値を共有させたいと考えています。 [!DNL Target] リアルタイムパーソナライゼーションを提供するために。 リアルタイム CDP プロファイル属性を使用すると、猶予は、 [!DNL Target] トークン置換を使用したオファー 例えば、Sarah は、顧客が好む色に応じて、 `${aep.profile.favoriteColor}`、またはトークンを使用したロイヤリティ層とロイヤルティポイントの値 `${aep.loyalty.tier}` および `${aep.loyalty.points}`.

![offer-json-aep-shared-attribute image](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

デフォルト値の割り当てはオプションです。
