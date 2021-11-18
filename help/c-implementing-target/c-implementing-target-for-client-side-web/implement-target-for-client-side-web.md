---
keywords: 実装；実装；at.js;adobe experience platform web sdk;aep web sdk
description: Adobe [!DNL Target] for client-side web using the Adobe Experience Platform Web SDK  (AEP Web SDK) or the [!DNL Target] at.js JavaScript ライブラリ。
title: 実装方法 [!DNL Target] （クライアント側 Web 用）
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
source-git-commit: bef2b493e8964f468d4f766c932a96d32e994a03
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 47%

---

# 概要：実装する [!DNL Target] クライアント側 Web の場合

クライアント側での [!DNL Adobe Target] の実装では、[!DNL Target] アクティビティに関連付けられたエクスペリエンスをクライアントブラウザーに直接配信します。ブラウザーは、表示するエクスペリエンスを決定して表示します。クライアント側の実装では、WYSIWYG エディタ、[Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）、または非視覚的インタフェースである[フォームベースの Experience Composer ](/help/c-experiences/form-experience-composer.md)を使用して、アクティビティとパーソナライズされたエクスペリエンスを作成できます。

実装するには [!DNL Adobe Target] クライアント側では、次の JavaScript ライブラリのいずれかを使用する必要があります。

* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Target at.js JavaScript ライブラリ](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target] mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しはエラーなく失敗し、デフォルトコンテンツを提供することで [!DNL Target] アクティビティを実行しているページに影響を与えます。Adobe では、サイトに発生する可能性のある問題を回避するため、すべてのお客様に、新しい[!DNL Adobe Experience Platform Web SDK]または at.js JavaScript ライブラリを最新バージョンに移行することをお勧めします。
>
>* **Adobe Experience Platform Web SDK**:この [!UICONTROL Adobe Experience Platform Web SDK] を使用すると、 [!DNL Experience Cloud] ( [!DNL Target]) を Adobe Experience Edge ネットワーク経由でアップロードする必要があります。 を [!DNL Adobe Experience Platform Web SDK]を参照してください。 [Adobe Experience Platform Web SDK とは](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) 内 *Web SDK ガイド*.
>
>* **at.js**:at.js JavaScript ライブラリは、Web 実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。 at.js に移行する場合は、 [At.js の仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) および [Adobe Target Skill Builder:開発者チャット， Adobe Targetを使用して mbox.js を at.js に移行](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).


