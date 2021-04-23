---
keywords: 実装;mbox.js; DOM 操作ライブラリ;target.js;Visual Experience Composer;iframe;角度サイト;単一ページアプリケーション;単一ページアプリ;SPA
description: Adobe Targetのレガシーmbox.js実装について説明します。 Adobe Experience PlatformWeb SDK(AEP Web SDK)またはat.jsの最新バージョンに移行します。
title: ' [!DNL Target] mbox.jsライブラリの機能'
feature: at.js
role: Developer
exl-id: 62f0cbd2-17f0-43f4-98d3-ea39f314525e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 74%

---

# mbox.js の機能

技術担当者が、mbox.js の実装とユーザーのサイトに与える影響を理解するのに役立つ情報を紹介します。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリをサポートし [!DNL Adobe Target] なくなりました。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。
>
>サイトに発生する可能性のある問題を回避するため、すべてのお客様に、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに今日までに移行することをお勧めします。 詳しくは、[概要：クライアント側web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)のターゲットを実装します。

Target Standard では、[!DNL mbox.js] バージョン 58 以降が必要です。[!DNL mbox.js] のダウンロードおよび更新の手順については、「[mbox の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420)」を参照してください。

Target Standard では、[!DNL mbox.js] は別の JavaScript ファイル [!DNL target.js] を呼び出します。[!DNL Target.js] は Adobe がホストし、自動的に更新します。[!DNL target.js] を更新するための操作は不要で、クライアント固有のカスタマイズもありません。

[!DNL Target.js] により、`target-global-mbox` という mbox がページの `<head>` セクションに作成されます。

[!DNL Target.js] は、 [!UICONTROL Extra JavaScript] フィールドの [!DNL mbox.js] に追加された JavaScript コードの行によって [!DNL mbox.js] から呼び出されます。[!DNL target.js] を無効にするには、コードのこの行を含めないようにするしかなく、その場合 [!DNL Target] も無効になります。

[!DNL Target.js] の [!DNL Target] での機能は 2 つあります。

* DOM 操作
* [!UICONTROL Visual Experience Composer] のビジュアル要素の有効化

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

詳しくは、「[at.js の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17)」を参照してください。
