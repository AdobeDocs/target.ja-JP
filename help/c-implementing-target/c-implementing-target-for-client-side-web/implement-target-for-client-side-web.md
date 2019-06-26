---
description: クライアント側 Web 用の Target の実装に関する情報です。
seo-description: クライアント側 Web 用の Adobe Target の実装に関する情報です。
seo-title: クライアント側 Web 用の Adobe Target の実装
solution: 'Target '
title: 概要 ― クライアント側 Web 用の Target の実装
topic: Standard
uuid: 8ed04881-3dd9-496f-9c9c-feb9c740ed80
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 概要：Target をクライアント側 Web に実装する

クライアント側での [!DNL Adobe Target] の実装では、[!DNL Target] アクティビティに関連付けられたエクスペリエンスをクライアントブラウザーに直接配信します。ブラウザーは、表示するエクスペリエンスを決定して表示します。クライアント側の実装では、WYSIWYG エディタ、[Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）、または非視覚的インタフェースである[フォームベースの Experience Composer ](/help/c-experiences/form-experience-composer.md)を使用して、アクティビティとパーソナライズされたエクスペリエンスを作成できます。

[!DNL Adobe Target] クライアント側を実装するには 、 [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) また は mbox. Js ライブラリを使用する必要があります。

>[!NOTE]
>
>mbox.js ライブラリの開発は終了しました。すべてのお客様は、 [at.js をデプロイ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md)するか 、[ mbox.js から at.js に移行する必要があります](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)。
