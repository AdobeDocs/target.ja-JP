---
keywords: 実装；mbox;mbox.jsのダウンロード；apiのダウンロード；mbox.js api
description: Adobe Targetのレガシーmbox.js実装について説明します。 Adobe Experience Platform Web SDK(AEP Web SDK)または最新バージョンのat.jsに移行します。
title: mbox.jsを使用して [!DNL Target] を実装する方法を教えてください。
feature: at.js
role: Developer
exl-id: 105095d7-8e29-413b-a7f4-e46e2e30e91f
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 65%

---

# mbox.js の実装

[!DNL Adobe Target Standard]または[!DNL Target Premium]を使用するには、1行のコードを追加してmbox.jsを呼び出します。

次の2つのライブラリリファレンスのいずれかを使用できます。[!DNL Adobe Experience Platform Web SDK]または[!DNL at.js]。

>[!IMPORTANT]
>
>**mbox.js のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しは失敗し、デフォルトのコンテンツを表示して [!DNL Target] アクティビティを実行しているページには影響があります。
>
>サイトで発生する可能性のある問題を回避するため、すべてのお客様にこの日までに新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに移行することをお勧めします。 詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

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
