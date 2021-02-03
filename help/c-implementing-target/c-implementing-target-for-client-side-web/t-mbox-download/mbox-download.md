---
keywords: 実装；mbox;mbox.jsのダウンロード；ダウンロードapi;mbox.js api
description: Adobe Target標準またはターゲットプレミアムを使用するには、1行のコードを追加してmbox.jsを呼び出します。
title: mbox.js の実装
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 50%

---


# mbox.js の実装

[!DNL Adobe Target Standard]または[!DNL Target Premium]を使用するには、1行のコードを追加してmbox.jsを呼び出します。

次の2つのライブラリ参照のいずれかを使用できます。[!DNL Adobe Experience Platform Web SDK]または[!DNL at.js]。 [at.jsのメリットは、mbox.jsとat.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) jsライブラリの違いを意味します。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリ [!DNL Adobe Target] はサポートされなくなります。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。
>
>サイトに発生する可能性のある問題を回避するため、すべてのお客様に、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに今日までに移行することをお勧めします。 詳しくは、[概要：クライアント側web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)のターゲットを実装します。

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