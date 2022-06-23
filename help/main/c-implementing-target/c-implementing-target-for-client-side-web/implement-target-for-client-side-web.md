---
keywords: 実装；実装；at.js;adobe experience platform web sdk;aep web sdk
description: Adobe [!DNL Target] Adobe Experience Platform Web SDK(AEP Web SDK) または [!DNL Target] at.js JavaScript ライブラリ。
title: 実装方法 [!DNL Target] （クライアント側 Web 用）
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 27%

---

# 概要：実装する [!DNL Target] クライアント側 Web の場合

クライアント側での [!DNL Adobe Target] の実装では、[!DNL Target] アクティビティに関連付けられたエクスペリエンスをクライアントブラウザーに直接配信します。ブラウザーは、表示するエクスペリエンスを決定して表示します。クライアント側の実装では、WYSIWYG エディタ、[Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）、または非視覚的インタフェースである[フォームベースの Experience Composer ](/help/main/c-experiences/form-experience-composer.md)を使用して、アクティビティとパーソナライズされたエクスペリエンスを作成できます。

実装するには [!DNL Adobe Target] クライアント側では、次の JavaScript ライブラリのいずれかを使用する必要があります。

* [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/)

   この [!UICONTROL Adobe Experience Platform Web SDK] を使用すると、 [!DNL Experience Cloud] ( [!DNL Target]) を Adobe Experience Edge ネットワーク経由でアップロードする必要があります。 を [!DNL Adobe Experience Platform Web SDK]を参照してください。 [Adobe Experience Platform Web SDK とは](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/) 内 *Web SDK ガイド*.

* [Target at.js JavaScript ライブラリ](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/)

   at.js JavaScript ライブラリは、Web 実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。 at.js に移行する場合は、 [At.js の仕組み](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/) および [Adobe Target Skill Builder:開発者チャット， Adobe Targetを使用して mbox.js を at.js に移行](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).



