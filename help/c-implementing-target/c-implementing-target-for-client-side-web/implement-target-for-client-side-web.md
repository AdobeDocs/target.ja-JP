---
keywords: 実装；実装；at.js;adobe experience platform web sdk;aep web sdk
description: Adobe Experience PlatformWeb SDK(AEP Web SDK)またはat.js JavaScriptライブラリを使用して、クライアント側Web用のAdobe Targetを実装する方法を学びます。
title: クライアント側Web用のターゲットを実装する方法
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
translation-type: tm+mt
source-git-commit: 0a685427a047bfc0a2f5e81525b32df70af6d69f
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 18%

---

# 概要：Target をクライアント側 Web に実装する

クライアント側での [!DNL Adobe Target] の実装では、[!DNL Target] アクティビティに関連付けられたエクスペリエンスをクライアントブラウザーに直接配信します。ブラウザーは、表示するエクスペリエンスを決定して表示します。クライアント側の実装では、WYSIWYG エディタ、[Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）、または非視覚的インタフェースである[フォームベースの Experience Composer ](/help/c-experiences/form-experience-composer.md)を使用して、アクティビティとパーソナライズされたエクスペリエンスを作成できます。

[!DNL Adobe Target]クライアント側を実装するには、次のJavaScriptライブラリのいずれかを使用する必要があります。

* [Adobe Experience PlatformウェブSDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [at.js JavaScriptライブラリのターゲット](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリをサポートし [!DNL Adobe Target] なくなりました。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに今日までに移行することをお勧めします。
>
>* **Adobe Experience PlatformウェブSDK**: [!UICONTROL Adobe Experience PlatformWeb ] SDKを使用すると、Adobe Experience Edge Networkを介して、( [!DNL Experience Cloud] 含む [!DNL Target])様々なサービスをインタラクティブに操作できます。[!DNL Adobe Experience Platform Web SDK]に移行する場合は、『*Web SDKガイド*』の[Adobe Experience PlatformWeb SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)とは何ですかを参照してください。
   >
   >
* **at.js**:at.js JavaScriptライブラリは、mbox.jsよりも多くの利点を提供します。多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。 at.jsに移行する場合は、[At.jsの仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)と[Adobe Targetスキルビルダーを参照してください。開発者チャットで、Adobe Targetのmbox.jsをat.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)に移行します。
>
>
mbox.jsは現在サポートされていますが（2021年3月31日まで）、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 すべてのお客様を[!UICONTROL Adobe Experience PlatformWeb SDK]またはat.jsに移行することで、アドビのエンジニアとサポートスタッフは、Adobeから期待される新しい機能とオファーをお客様に提供できます。
