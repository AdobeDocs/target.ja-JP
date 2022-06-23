---
keywords: 実装；javascript ライブラリ；js;atjs;on-device decisioning;on device decisioning；サポートされる機能
description: オンデバイス判定でサポートされる機能について説明します。
title: On-Device Decisioning でサポートされる機能
feature: at.js
role: Developer
exl-id: 3531ff55-c3db-44c1-8d0a-d7ec2ccb6505
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 13%

---

# オンデバイス判定でサポートされる機能

この [!DNL Adobe Target] JS SDK は、お客様がパフォーマンスと決定のためのデータの鮮度を柔軟に選択できるようにします。 つまり、機械学習を通じて最も関連性が高く、パーソナライズされたコンテンツを配信することが最も重要な場合は、ライブサーバー呼び出しをおこなう必要があります。 しかし、パフォーマンスがより重要な場合は、デバイス上およびメモリ内での判断が必要です。 オンデバイス判定が機能するようにするには、次の節で、サポートされる機能の一覧を参照してください。

## サポートされているアクティビティのタイプ

次の表に、どの [アクティビティタイプ](/help/main/c-activities/target-activities-guide.md) 作成者 [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) または [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) は、オンデバイス判定でサポートされているか、サポートされていません。

| アクティビティタイプ | 対応? |
| --- | --- |
| [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md) | ○ |
| [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | × |
| [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ![Premium](/help/main/assets/premium.png) | × |
| [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | × |
| [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md)（XT） | ○ |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) ![プレミアム](/help/main/assets/premium.png) | × |
| [レコメンデーション](/help/main/c-recommendations/recommendations.md) ![プレミアム](/help/main/assets/premium.png) | × |
| [Analytics for Target を使用するアクティビティ](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | ○ |

## オーディエンスのターゲティング

次の表は、オンデバイス判定でサポートされるオーディエンスルールとサポートされないオーディエンスルールを示しています。

| オーディエンスルール | 対応? |
| --- | --- |
| [地域](/help/main/c-target/c-audiences/c-target-rules/geo.md) | ○ |
| [ネットワーク](/help/main/c-target/c-audiences/c-target-rules/network.md) | × |
| [モバイル](/help/main/c-target/c-audiences/c-target-rules/mobile.md) | × |
| [カスタムパラメーター](/help/main/c-target/c-audiences/c-target-rules/custom-parameters.md) | ○ |
| [オペレーティングシステム](/help/main/c-target/c-audiences/c-target-rules/operating-system.md) | ○ |
| [サイトのページ](/help/main/c-target/c-audiences/c-target-rules/site-pages.md) | ○ |
| [ブラウザー](/help/main/c-target/c-audiences/c-target-rules/browser.md) | ○ |
| [訪問者プロファイル](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) | × |
| [トラフィックソース](/help/main/c-target/c-audiences/c-target-rules/traffic-sources.md) | × |
| [時間枠](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | ○ |
| Adobe Experience Cloud Audiences<br>( オーディエンス元： [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]、および [!DNL Adobe Experience Manager] | × |

### オンデバイス判定のジオターゲティング

地域ベースのオーディエンスを使用したオンデバイス判定アクティビティの待ち時間を最小限に抑えるために、Adobeでは、 [getOffers](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/). リクエストのコンテキストで地域オブジェクトを設定します。 つまり、ブラウザーを使用して、各訪問者の場所を特定する方法です。 例えば、設定したサービスを使用して、IP-to-Geo ルックアップを実行できます。 Google Cloud など、一部のホスティングプロバイダーは、各 `HttpServletRequest`.

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

ただし、サーバーで IP-to-Geo 検索を実行できず、でオンデバイス判定を実行したい場合は、 [getOffers](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/) 地域ベースのオーディエンスを含むリクエストもサポートされます。 このアプローチの欠点は、リモートの IP-to-Geo ルックアップを使用し、各 IP-to-Geo ルックアップに遅延が追加される点です `getOffers` 呼び出し。 この遅延は、 `getOffers` サーバーの近くにある CDN をヒットするので、サーバー側判定を使用してを呼び出します。 SDK が訪問者の IP アドレスの地域情報を取得するために、リクエストのコンテキストの地域オブジェクトに「ipAddress」フィールドのみを指定します。 「ipAddress」以外のフィールドを指定した場合、 [!DNL Target] SDK は解決のために位置情報メタデータを取得しません。

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

次の表は、オンデバイス判定でサポートされる割り当て方法とサポートされない割り当て方法を示しています。

| 配分方法 | 対応? |
| --- | --- |
| 手動 | ○ |
| [最良のエクスペリエンスに自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | × |
| [パーソナライズされたエクスペリエンスの自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | × |
