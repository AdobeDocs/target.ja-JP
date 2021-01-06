---
keywords: implement;implementation;at.js;adobe experience platform web sdk;aep web sdk
description: クライアント側 Web 用の Adobe Target の実装に関する情報です。
title: クライアント側 Web 用の Adobe Target の実装
feature: client-side
translation-type: tm+mt
source-git-commit: 1b426e0b2004e729ba75d218a9b6ccd5195449cd
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 66%

---


# 概要：Target をクライアント側 Web に実装する

クライアント側での [!DNL Adobe Target] の実装では、[!DNL Target] アクティビティに関連付けられたエクスペリエンスをクライアントブラウザーに直接配信します。ブラウザーは、表示するエクスペリエンスを決定して表示します。クライアント側の実装では、WYSIWYG エディタ、[Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）、または非視覚的インタフェースである[フォームベースの Experience Composer ](/help/c-experiences/form-experience-composer.md)を使用して、アクティビティとパーソナライズされたエクスペリエンスを作成できます。

[!DNL Adobe Target]クライアント側を実装するには、[Adobe Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)、[at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)、またはmbox.jsライブラリを使用する必要があります。

>[!NOTE]
>
>mbox.js ライブラリの開発は終了しました。すべてのお客様が、[AEP Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)、[at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md)をデプロイするか、[mbox.jsからat.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)に移行する必要があります。
