---
description: クライアント側Web用のTargetの実装に関する情報です。
seo-description: クライアント側Web用のAdobe Targetの実装に関する情報です。
seo-title: クライアント側Web用のAdobe Targetの実装
solution: 'Target '
title: 概要-クライアント側Web用のTargetの実装
topic: Standard
uuid: 8ed04881-3dd9-496f-9c9c-feb9c740ed80
translation-type: tm+mt
source-git-commit: 0d5aa4d1f46bc64b0c88ee1ca0298cb09238f7e1

---


# 概要:Targetをクライアント側Webに実装する

クライアント側の実装では、 [!DNL Adobe Target]アクティビティに関連付けられたエクスペリエンスを直接クライアントブラウザーに [!DNL Target] 配信します。ブラウザーは、表示するエクスペリエンスを決定して表示します。クライアント側の実装では、WYSIWYGエディター、 [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）、またはフォームベースのExperience Composer（ [フォームベースのExperience Composer](/help/c-experiences/form-experience-composer.md)）を使用して、アクティビティとパーソナライゼーションエクスペリエンスを作成できます。

クライアント側を実装 [!DNL Adobe Target] するには [、at. jsまた](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) はmbox. jsライブラリを使用する必要があります。

>[!NOTE]
>
>mbox.js ライブラリの開発は終了しました。すべてのお客様は、at. js [をデプロイ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) するか [、mbox. jsからat. jsに移行する必要](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)があります。
