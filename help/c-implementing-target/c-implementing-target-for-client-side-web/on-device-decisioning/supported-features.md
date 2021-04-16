---
keywords: 実装；javascriptライブラリ；js;atjs;on-device decisioning;on device decisioning；サポートされる機能
description: オンデバイスの判定でサポートされる機能について説明します。
title: On-Device Decisioningでサポートされる機能
feature: at.js
role: Developer
exl-id: 3531ff55-c3db-44c1-8d0a-d7ec2ccb6505
translation-type: tm+mt
source-git-commit: 62a3b387445977a1bdcd2cf45306c8ff032fca50
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 12%

---

# オンデバイスの判定でサポートされる機能

[!DNL Adobe Target] JS SDKを使用すると、お客様は柔軟にデータのパフォーマンスと鮮度を選択して判断できます。 つまり、機械学習を通じて最も関連性が高く魅力的なパーソナライズされたコンテンツを配信することが最も重要な場合は、ライブサーバーコールを行う必要があります。 ただし、パフォーマンスがより重要な場合は、デバイス上およびメモリ内の判断を行う必要があります。 オンデバイス判定が機能するようにするには、サポートされる機能のリストについて、以下の節を参照してください。

## サポートされるアクティビティタイプ

次の表に、[フォームベースのExperience Composer](/help/c-experiences/form-experience-composer.md)または[Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)(VEC)で作成された[アクティビティタイプ](/help/c-activities/target-activities-guide.md)が、オンデバイスの判定でサポートされているかどうかを示します。

| アクティビティタイプ | 対応? |
| --- | --- |
| [A/B テスト](/help/c-activities/t-test-ab/test-ab.md) | ○ |
| [自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | × |
| [自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md) ![Premium](/help/assets/premium.png) | × |
| [多変量分析テスト](/help/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | × |
| [エクスペリエンスのターゲット設定](/help/c-activities/t-experience-target/experience-target.md) (XT) | ○ |
| [自動](/help/c-activities/t-automated-personalization/automated-personalization.md) ![パーソナライゼーションPremium](/help/assets/premium.png) | × |
| [Recommendations](/help/c-recommendations/recommendations.md)  ![プレミアム](/help/assets/premium.png) | × |
| [ターゲットにAnalyticsを使用するアクティビティ](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | ○ |

## オーディエンスのターゲット設定

次の表に、オンデバイスの判定でサポートされているオーディエンスルールとサポートされていないデバイスルールを示します。

| オーディエンス規則 | 対応? |
| --- | --- |
| [地域](/help/c-target/c-audiences/c-target-rules/geo.md) | ○ |
| [ネットワーク](/help/c-target/c-audiences/c-target-rules/network.md) | × |
| [モバイル](/help/c-target/c-audiences/c-target-rules/mobile.md) | × |
| [カスタムパラメーター](/help/c-target/c-audiences/c-target-rules/custom-parameters.md) | ○ |
| [オペレーティングシステム](/help/c-target/c-audiences/c-target-rules/operating-system.md) | ○ |
| [サイトのページ](/help/c-target/c-audiences/c-target-rules/site-pages.md) | ○ |
| [ブラウザー](/help/c-target/c-audiences/c-target-rules/browser.md) | ○ |
| [訪問者プロファイル](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) | × |
| [トラフィックソース](/help/c-target/c-audiences/c-target-rules/traffic-sources.md) | × |
| [時間枠](/help/c-target/c-audiences/c-target-rules/time-frame.md) | ○ |
| Adobe Experience Cloudオーディエンス<br>([!DNL Adobe Analytics]、[!DNL Adobe Audience Manager]、[!DNL Adobe Experience Manager]のオーディエンス | × |

### オンデバイス判定の地域ターゲット設定

地域ベースのオーディエンスを使用するオンデバイス判定アクティビティの待ち時間を最小限に抑えるために、Adobeでは、[getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)への呼び出しで地域の値を自分で指定することをお勧めします。 リクエストのコンテキストで地域オブジェクトを設定します。 これは、ブラウザーから各訪問者の場所を判断する方法を意味します。 例えば、設定したサービスを使用して、IPから地域へのルックアップを実行できます。 一部のホスティングプロバイダー（Google Cloudなど）は、各`HttpServletRequest`のカスタムヘッダーを使用してこの機能を提供します。

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				city: "SAN FRANCISCO", 
				countryCode: "US", 
				stateCode: "CA", 
				latitude: 37.75, 
				longitude: -122.4 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

ただし、サーバー上でIPから地域への検索を実行できず、地域ベースのオーディエンスを含む[getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)の要求に対してオンデバイス判定を実行したい場合は、この方法もサポートされます。 このアプローチの欠点は、リモートのIPから地域への参照を使用し、`getOffers`の各呼び出しに遅延が追加される点です。 この待ち時間は、サーバーの近くにあるCDNをヒットするので、サーバー側判定での`getOffers`呼び出しよりも短くする必要があります。 SDKが訪問者のIPアドレスの地域を取得するようにリクエストした場合、コンテキスト内のGeoオブジェクトに「ipAddress」フィールドのみを指定します。 「ipAddress」以外のフィールドを指定した場合、[!DNL Target] SDKは解決のために地域位置メタデータを取得しません。

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				ipAddress: "127.0.0.1" 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

### 配分方法

次の表に、オンデバイスの判定でサポートされている割り当てメソッド、またはサポートされていない割り当てメソッドを示します。

| 配分方法 | 対応? |
| --- | --- |
| 手動 | ○ |
| [最高のエクスペリエンスへの自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | × |
| [パーソナライズされたエクスペリエンスの自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md) | × |
