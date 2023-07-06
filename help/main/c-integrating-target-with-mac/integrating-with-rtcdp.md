---
keywords: Real-time Customer Data Platform;RTCDP;パーソナライズ機能;AEP オーディエンス;Adobe Experience Platform オーディエンス;プロファイル属性
description: ' [!DNL Target]/[!DNL Real-Time Customer Data Platform] （RTCDP）統合を使用して、より豊富な顧客データとよりインパクトのあるパーソナライゼーションを提供する方法を説明します。'
title: ' [!DNL Target] と [!DNL Real-Time Customer Data Platform] の統合方法'
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 210e9de954dba813972b0da9a7db5b9383d3e303
workflow-type: ht
source-wordcount: '1060'
ht-degree: 100%

---

# [!DNL Real-Time Customer Data Platform] との統合

[!DNL Real-Time Customer Data Platform]（RTCDP）は、[!DNL Adobe Experience Platform] にビルドされ、企業が複数のエンタープライズソースから既知の匿名データを統合するのに役立ちます。RTCDP では、すべてのチャネルとデバイスにわたって、リアルタイムでパーソナライズされた顧客体験を提供するために使用できる顧客プロファイルを作成できます。

RTCDP について詳しくは、[Real-time Customer Data Platform の概要](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=ja){target=_blank}を参照してください。

## 主な機能

主な機能は以下のとおりです。

* エッジにおける Real-Time CDP/[!DNL Adobe Experience Platform] と [!DNL Target] の直接統合（[!DNL Audience Core services] への依存を排除 - AAM）
* ガバナンスとポリシーが強化された [!UICONTROL Target エッジ宛先カード]
* Real-time CDP セグメントと共有プロファイル属性

## 実装シナリオ

以下の節では、様々な実装方法を使用する場合に使用可能なパーソナライズ機能のユースケースのタイプ（次のセッションまたは同じページ）を示します。

### at.js の実装

| 解決策 | 使用可能なユースケース |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager]（AAM）と [!DNL Target]</li><li>[!DNL RTCDP]（Premium または Ultimate）と [!DNL Target]</li><li>[!DNL RTCDP]（任意の SKU）、[!DNL AAM]、[!DNL Target]</li></ul> | 次のセッションのパーソナライズ機能 |

### [!DNL Adobe Experience Platform Web SDK] または [!DNL Experience Platform Server-Side API] の実装

| 解決策 | 使用可能なユースケース |
| --- | --- |
| <ul><li>[!DNL RTCDP]（任意の SKU）と [!DNL Target]</li></ul> | <ul><li>次のセッションのパーソナライズ機能</li><li>エッジを介した同じページのパーソナライズ機能</li><li>セグメントの共有時に適用されるガバナンス</li></ul> |
| <ul><li>[!DNL RTCDP]（任意の SKU）、[!DNL AAM]、[!DNL Target]</li></ul> | <ul><li>次のセッションのパーソナライズ機能</li><ul><li>[!DNL AAM] セグメント</li><li>[!DNL AAM] を介したサードパーティセグメント</li></ul><li>エッジを介した同じページのパーソナライズ機能</li><ul><li>[!DNL RTCDP] セグメント</li><li>セグメントの共有時に適用されるガバナンス</li></ul> |

### [!UICONTROL at.js] と [!DNL Platform Web SDK] 実装の組み合わせ

| 解決策 | 使用可能なユースケース |
| --- | --- |
| <ul><li>[!DNL RTCDP]（任意の SKU）と [!DNL Target]</li></ul> | <ul><li>次のセッションのパーソナライズ機能</li><ul><li>[!UICONTROL at.js] を使用するすべてのページの場合</li></ul><li>同じページのパーソナライズ機能</li><ul><li>[!DNL Platform Web SDK] を使用するすべてのページの場合</li></ul> |
| <ul><li>[!DNL RTCDP]（任意の SKU）、[!DNL AAM]、[!DNL Target]</li></ul> | <ul><li>次のセッションのパーソナライズ機能</li><ul><li>[!UICONTROL at.js] を使用するすべてのページ</li><li>[!DNL AAM] セグメント</li><li>[!DNL AAM] を介したサードパーティセグメント</li></ul> |

## セグメント評価時間

次の表は、様々な実装シナリオから発生するイベントのセグメント評価時間を示しています。

| シナリオ | エッジセグメント（ミリ秒評価） | ストリーミングセグメント（分単位の評価） | バッチセグメント評価 |
| --- | --- | --- | --- |
| [!DNL Adobe Experience Platform] SDK からのイベント／データ | ○ | ○ | 該当なし |
| [!UICONTROL at.js] からのイベント | × | ○ | 該当なし |
| [!DNL Target Mobile] SDK からのイベント | × | ○ | 該当なし |
| バッチアップロードからのイベント | × | × | ○ |
| オフラインデータ（ストリーム）からのイベント | × | ○ | ○ |

## [!DNL Adobe Experience Platform] のオーディエンスの使用 {#aep}

[!DNL Adobe Experience Platform] で作成された[オーディエンス](/help/main/c-target/c-audiences/audiences.md)を使用すると、よりインパクトのあるパーソナライゼーションにつながる豊富な顧客データがを取得できます。[Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=ja){target=_blank}（RTCDP）は、[!DNL Adobe Experience Platform] にビルドされ、企業が複数のエンタープライズソースから既知の匿名データを統合するのに役立ちます。このプロセスでは、すべてのチャネルとデバイスにわたって、リアルタイムでパーソナライズされた顧客体験を提供するために使用できる顧客プロファイルを作成できます。

[!DNL Target] を [!DNL Real-Time Customer Data Platform] に接続することで、顧客は web パーソナライゼーションを強化できます。この統合により、以前は [!DNL Target] にアクセスできなかった可能性のある新しいセグメントのロックを解除して、顧客の web 訪問の最初のページでミリ秒単位のリアルタイムのパーソナライゼーションが可能になります。[!DNL Adobe Experience Platform] で作成されたオーディエンスとプロファイル属性を使用すると、利用可能なデータポイントを拡張して、パーソナライゼーションを強化できます。

この統合により、Real-Time CDP での主なユースケースのロックが解除されます。

* 同じページ／次のヒットのパーソナライズ化
* 初回／不明なユーザーのパーソナライズ化

## Real-Time CDP プロファイル属性の [!DNL Target] との共有 {#rtcdp-profile-attributes}

Real-Time CDP プロファイル属性は、HTML オファーおよび [JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md)で使用するために [!DNL Target] と共有できます。

### Real-Time CDP プロファイル属性機能の制限と考慮事項

次の点に留意してください。

* 特定のオファー内の属性は、同じ [!UICONTROL Experience Platform] サンドボックスからの属性である必要があります。（つまり、オファーには異なる [!UICONTROL Experience Platform] サンドボックスからの属性を含めることはできません）。
* 特定のオファー内の属性は、様々なソース（[!DNL Target] プロファイルと [!UICONTROL Experience Platform] プロファイル）から取得できます。（つまり、属性が [!DNL Target] または [!UICONTROL Experience Platform] プロファイルのいずれかから取得されたかに関係なく、属性を結合できます）。
* オファーを定義する際、属性に明示的な値がない場合に備えて、[!UICONTROL Real-Time CDP プロファイル属性]にデフォルト値を割り当てることができます。例えば、パーソナライゼーションサービスで使用されている属性が同意ポリシーやガバナンスポリシーによってブロックされている場合は、代わりにデフォルト値を使用できます。

### JSON サンプルのユースケース

オンラインマーケターは、AEP／統合プロファイルで属性値を [!DNL Target] と共有して、リアルタイムのパーソナライゼーションを実現したいと考えています。[!UICONTROL Real-Time CDP プロファイル属性]を使用すると、トークンの置換を使用して、[!DNL Target] オファーに [!UICONTROL Experience Platform] 属性の値を表示できます。例えば、`${aep.profile.favoriteColor}` を使用して顧客のお気に入りのカラーに応じてパーソナライズしたり、トークン `${aep.loyalty.tier}` と `${aep.loyalty.points}` を使用して顧客のロイヤルティ層とロイヤルティポイント値に従ってパーソナライズしたりできます。

AEP／統合プロファイル属性を [!DNL Target] と共有するための JSON オファーを作成するには：

1. [JSON オファーの作成](/help/main/c-experiences/c-manage-content/create-json-offer.md)中に、**[!UICONTROL ソースを選択]**&#x200B;リストから **[!UICONTROL Adobe Experience Platform]** を選択します。
1. **[!UICONTROL プロファイルサンドボックス名を選択]**&#x200B;リストから、目的のサンドボックスを選択します。
1. **[!UICONTROL プロファイル属性を選択]**&#x200B;リストから、目的の属性を選択します。
1. （オプション）**[!UICONTROL デフォルト値を挿入]**&#x200B;リストから、目的の値を選択します。
1. 「**[!UICONTROL 追加]**」をクリックします。

次の図に、2 つのプロファイル属性、`loyalty.tier` と `loyalty.points` が JSON オファーに追加されたことを示します。

![offer-json-aep-shared-attribute の画像](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## 詳細情報へのリンク

詳しくは、次のトピックを参照してください。

* *Adobe Experience Platform リリースノート*&#x200B;の[宛先リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja#destinations){target=_blank}
* *宛先の概要*&#x200B;ガイドの[同じページと次のページのパーソナライゼーションに対するパーソナライゼーションの宛先の設定](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja){target=_blank}。
* *宛先の概要*&#x200B;ガイドの[Adobe Target 接続](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html?lang=ja){target=_blank}
* *宛先の概要*&#x200B;ガイドの[属性のマッピング。](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=ja#map-attributes){target=_blank}
* *宛先の概要*&#x200B;ガイドの[エッジパーソナライゼーションの宛先に対するオーディエンスのアクティブ化](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-edge-personalization-destinations.html?lang=ja){target=_blank}。
* *宛先の概要*&#x200B;ガイドの「よくある質問」の [ [!DNL Adobe Target]  およびカスタムパーソナライゼーションの宛先を使用した、同じページおよび次のページのパーソナライゼーション](https://experienceleague.adobe.com/docs/experience-platform/destinations/destinations-faq.html?lang=ja#same-next-page-personalization){target=_blank}。

## ビデオおよびブログ投稿 {#videos-blogs}

次のビデオとブログ投稿では、Target と RTCDP を使用した高度なパーソナライゼーションについて詳しく説明しています。

### ビデオ：Real-Time CDP と [!DNL Adobe Target] による次のヒットのパーソナライゼーション{#RTCDP}

[!DNL Real-Time Customer Data Platform] と [!DNL Adobe Target] を使用して、次のヒットでパーソナライズする方法を説明します。[!DNL Real-Time CDP] の [!DNL Adobe Target] 宛先では、[!DNL Adobe Target] の [!DNL Experience Platform] セグメントを使用して、ガバナンスとプライバシーをサポートする同じページのパーソナライゼーションと次のページのパーソナライゼーションを行うことができます。

詳しくは、*Platform チュートリアル*&#x200B;ガイドの[Real-Time CDP と Adobe Target による次のヒットのパーソナライゼーション](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html?lang=ja){target=_blank}を参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### ビデオ：[!DNL Real-Time Customer Data Platform] での [!DNL Adobe Target] の宛先の設定

[!DNL Real-Time Customer Data Platform] での [!DNL Adobe Target] の宛先を設定して、[!DNL Real-Time CDP] から [!DNL Target] へのセグメントとプロファイル属性の送信を開始する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3418799/?learn=on)

### ビデオ：セグメントとプロファイル属性のアクティブ化

[!DNL Adobe Real-Time Customer Data Platform] から [!DNL Adobe Target] までのセグメントとプロファイル属性をアクティブ化して、web サイト、モバイルアプリ、その他のデジタルプロパティにリアルタイムのパーソナライズされたコンテンツを表示する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3419036/?learn=on)

### ビデオ：[!DNL Target] での [!DNL Real-Time CDP] セグメントの使用

[!DNL Adobe Target] での [!DNL Real-Time Customer Data Platform] セグメントを使用して、web サイトやモバイルアプリでパーソナライズされたエクスペリエンスを提供する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3419149/?learn=on)

### ビデオ：[!DNL Adobe Target] での [!DNL Real-Time CDP] プロファイル属性の使用

[!DNL Adobe Target] での [!DNL Adobe Real-Time Customer Data Platform] プロファイル属性を使用して、web サイトやモバイルアプリでパーソナライズされたエクスペリエンスを提供する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3419318/?learn=on)

### [!DNL Adobe Target] のブログとビデオ：同じページの強化されたパーソナライゼーション

[[!DNL Adobe] announces Same-Page Enhanced Personalization with [!DNL Adobe Target] および [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}
