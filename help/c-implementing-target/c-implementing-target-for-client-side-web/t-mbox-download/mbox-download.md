---
description: Target Standard または Target Premium を使用するには、コードを 1 行追加して mbox.js を呼び出します。
keywords: 実装;Mbox; mbox.js のダウンロード;api のダウンロード;mbox.js api
seo-description: Target Standard または Target Premium を使用するには、コードを 1 行追加して mbox.js を呼び出します。
seo-title: mbox.js の実装
solution: 'Target '
subtopic: 導入
title: mbox.js の実装
topic: Standard
uuid: aa53dfd4-db42-4a33-b561-7e84ca7e4497
translation-type: tm+mt
source-git-commit: ac86b0131b0c65f3367c47b3a1315c37d9b9aa93

---


# mbox.js の実装{#mbox-js-implementation}

Target Standard または Target Premium を使用するには、コードを 1 行追加して mbox.js を呼び出します。

[!DNL mbox.js] または [!DNL at.js] の 2 つのライブラリリファレンスのいずれかを使用できます。[at. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) の利点により、2つのライブラリの違いがわかります。

>[!NOTE]
>
>mbox.js ライブラリは引き続きサポートされますが、機能のアップデートはおこなわれません。すべてのお客様が at.js に移行する必要があります。詳細については、「[mbox.js から at.js に移行する方法](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)」を参照してください。

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