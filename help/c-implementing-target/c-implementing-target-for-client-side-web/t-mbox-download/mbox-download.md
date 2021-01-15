---
keywords: implementation;mbox;download mbox.js;download api;mbox.js api
description: Adobe Target標準またはターゲットプレミアムを使用するには、1行のコードを追加してmbox.jsを呼び出します。
title: mbox.js の実装
feature: null
translation-type: tm+mt
source-git-commit: bffda8c3461998767a002d66fd9340252237ae5d
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 32%

---


# mbox.js の実装

[!DNL Adobe Target Standard]または[!DNL Target Premium]を使用するには、1行のコードを追加してmbox.jsを呼び出します。

次の2つのライブラリ参照のいずれかを使用できます。[!DNL Adobe Experience Platform Web SDK]または[!DNL at.js]。 [at.jsのメリットは、mbox.jsとat.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) jsライブラリの違いを意味します。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリ [!DNL Adobe Target] はサポートされなくなります。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに今日までに移行することをお勧めします。
>
>* **Adobe Experience PlatformウェブSDK**: [!UICONTROL Adobe Experience PlatformWeb ] SDKを使用すると、Adobe Experience Edge Networkを介して、( [!DNL Experience Cloud] 含む [!DNL Target])様々なサービスをインタラクティブに操作できます。[!DNL Adobe Experience Platform Web SDK]に移行する場合は、『*Web SDKガイド*』の[Adobe Experience PlatformWeb SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)とは何ですかを参照してください。
   >
   >
* **at.js**:at.js JavaScriptライブラリは、mbox.jsよりも多くの利点を提供します。多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。 at.jsに移行する場合は、[At.jsの仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)と[Adobe Targetスキルビルダーを参照してください。開発者チャットで、Adobe Targetのmbox.jsをat.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)に移行します。
>
>
mbox.jsは現在サポートされていますが（2021年3月31日まで）、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 すべてのお客様を[!UICONTROL Adobe Experience PlatformWeb SDK]またはat.jsに移行することで、アドビのエンジニアとサポートスタッフは、Adobeから期待される新しい機能とオファーをお客様に提供できます。

各ページの [!DNL mbox.js] への単一の参照は、すべてのアクティビティに必要なライブラリを提供します。[!DNL mbox.js] は、[!DNL mbox.js] ファイルを参照するすべてのページから [!DNL Target] を呼び出します。これにより、[!DNL Target] で次の作業ができるようになります。

* Target アクティビティの配信
* クリックの追跡
* 最も成功した指標の追跡

>[!TIP]
>
>実装を簡略化するには、グローバルヘッダーで [!DNL mbox.js] を参照します。

アクティビティごとに異なる mbox.js ファイルを管理する必要はありません。

1. サイトの各ページの `<head>` セクションで [!DNL mbox.js] を参照します。

   `<script src="/ *`directory`*/ *`scripts`*/mbox.js"></script>`

   ここで、` *`directory`*/ *`scripts`*` は、ダウンロード後に [!DNL mbox.js] ファイルを保存したディレクトリです。
レガシー実装のページに既に mbox が含まれている場合、その mbox は新しいインターフェイスでもそのまま使用できます。更新された [!DNL mbox.js] ファイルは引き続き必要になりますが、これらの mbox は、アクティビティ用に選択したり、[!UICONTROL Visual Experience Composer] を使用して編集したりすることができます。