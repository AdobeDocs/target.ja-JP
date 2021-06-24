---
keywords: 実装;mbox.js; DOM 操作ライブラリ;target.js;Visual Experience Composer;iframe;角度サイト;単一ページアプリケーション;単一ページアプリ;SPA
description: Adobe Targetのレガシーmbox.js実装について説明します。 Adobe Experience Platform Web SDK(AEP Web SDK)または最新バージョンのat.jsに移行します。
title: ' [!DNL Target] mbox.jsライブラリの機能'
feature: at.js
role: Developer
exl-id: 62f0cbd2-17f0-43f4-98d3-ea39f314525e
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 78%

---

# mbox.js の機能

技術担当者が、mbox.js の実装とユーザーのサイトに与える影響を理解するのに役立つ情報を紹介します。

>[!IMPORTANT]
>
>**mbox.js のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しは失敗し、デフォルトのコンテンツを表示して [!DNL Target] アクティビティを実行しているページには影響があります。
>
>サイトで発生する可能性のある問題を回避するため、すべてのお客様にこの日までに新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに移行することをお勧めします。 詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## DOM 操作 {#section_169F8D4C077948DCB4F891ABBB03FF63}

[!DNL Target.js] は、Standard で使用される DOM 操作ライブラリを制御します。Web サイトのコンテンツを表示するために、[!DNL target.js] は [!DNL sizzle.js]（バージョン 1.10.8-pre）を参照します。[!DNL Sizzle.js] は、HTML 要素セレクターを有効にします。[!DNL sizzle.js] 以外は、ネイティブの JavaScript のみが使用されます。jquery は不要です。

さらに、DOM をポーリングするために次のスニペットが使用されます。




`https://github.com/dperini/ContentLoaded`

## Target.js と Visual Experience Composer {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

[!UICONTROL Visual Experience Composer] を使用アクティビティのエクスペリエンスを設定する場合、Web ページは iFrame で開きます。iFrame がロードされると、Standard は HTML5 `postMessage` API 呼び出しを送信します。[!DNL Target.js] は `postMessage` 呼び出しを検出して次の JavaScript ライブラリを Web サイトに含めます。

* サムネールの生成用： [!DNL https://html2canvas.hertzen.com/]
* クロスドメインクエリ用： [!DNL Admin.js]、[!DNL CDQ.base.js]、[!DNL CDQ.host.js]、[!DNL admin.css]（iFrames 間でメッセージを送信するために使用）。これらのスクリプトにより、Adobe はページ間でデータを送信できます。

## 角度サイトとシングルページアプリケーションの考慮事項 {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

Target を角度サイトまたはシングルページアプリケーション（SPA）で実装する場合、mbox.js ではなく at.js ライブラリを使用する必要があります。
