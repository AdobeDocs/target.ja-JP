---
keywords: 実装；実装；at.js;adobe experience platform web sdk;aep web sdk
description: Adobe [!DNL Target] for client-side web using the Adobe Experience Platform Web SDK  (AEP Web SDK) or the [!DNL Target] at.js JavaScriptライブラリの実装方法を説明します。
title: クライアント側Web用に [!DNL Target] を実装する方法
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 48%

---

# 概要：クライアント側Web用の[!DNL Target]の実装

クライアント側での [!DNL Adobe Target] の実装では、[!DNL Target] アクティビティに関連付けられたエクスペリエンスをクライアントブラウザーに直接配信します。ブラウザーは、表示するエクスペリエンスを決定して表示します。クライアント側の実装では、WYSIWYG エディタ、[Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）、または非視覚的インタフェースである[フォームベースの Experience Composer ](/help/c-experiences/form-experience-composer.md)を使用して、アクティビティとパーソナライズされたエクスペリエンスを作成できます。

[!DNL Adobe Target]クライアント側を実装するには、次のJavaScriptライブラリのいずれかを使用する必要があります。

* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Target at.js JavaScriptライブラリ](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**mbox.js のサポート**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しはエラーなく失敗し、デフォルトコンテンツを提供することで [!DNL Target] アクティビティを実行しているページに影響を与えます。Adobe では、サイトに発生する可能性のある問題を回避するため、すべてのお客様に、新しい[!DNL Adobe Experience Platform Web SDK]または at.js JavaScript ライブラリを最新バージョンに移行することをお勧めします。
>
>* **Adobe Experience Platform Web SDK**: [!UICONTROL Adobe Experience Platform Web ] SDKを使用すると、Adobe Experience Edgeネットワークを通じて内の様々な [!DNL Experience Cloud] サービス( [!DNL Target]を含む)を操作できます。[!DNL Adobe Experience Platform Web SDK]に移行する場合は、『*Web SDKガイド*』の「[Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)とは」を参照してください。
   >
   >
* **at.js**:at.js JavaScriptライブラリは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。at.jsに移行する場合は、 [At.jsの仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)および[Adobe Target Skill Builderを参照してください。開発者チャット、Adobe Targetを使用してmbox.jsをat.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)に移行します。


