---
description: Web ページで Target ライブラリ（at.js または mbox.js）を参照し、Target を実装します。
keywords: document.write;Target;実装;Target の実装;DTM;Dynamic Tag Management;at.js;mbox.js;target.js;mbox
seo-description: Web ページで Target ライブラリ（at.js または mbox.js）を参照し、Target を実装します。
seo-title: Target JavaScript ライブラリについて
title: Target JavaScript ライブラリについて
topic: 'Target '
uuid: c8a254c9-afc9-4a55-be01-788c11bef7cc
translation-type: tm+mt
source-git-commit: f99fbba17dc7e33454f162c823577db0ba78ac29

---


# [!DNL Target] JavaScript ライブラリ{#understand-the-target-javascript-libraries}について

Web ページで [!DNL Target] ライブラリ（at.js または mbox.js）を参照して [!DNL Target] を実装します。

>[!NOTE]
>
>mbox.js ライブラリの開発は終了しました。すべてのお客様が mbox.js から at.js に移行する必要があります。詳しくは、「[mbox.js から at.js への移行](../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)」を参照してください。

## 2 つのライブラリの違い {#section_40117C78C2F84FECAC4F1BA40CC4F171}

次の表は、この 2 つのライブラリの違いを説明しています。

| ライブラリリファレンス | 説明 |
|--- |--- |
| at.js | at.js は、mbox.js に替わる [!DNL Target] 実装ライブラリです。<br>多くのメリットがある中でも、at.js は、Web 実装のページ読み込み時間を改善し、セキュリティを強化して、Google Chrome での document.write 警告を回避し、シングルページアプリケーション向けのより優れた実装オプションを提供します。<br>詳しくは、「[at.js の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md)」を参照してください。 |
| mbox.js | [!DNL Target] 16.3.1（2016 年 3 月）以前は、[!DNL Target] がアクティビティの配信、クリックの追跡、および最も成功した指標の追跡を行うためには、[!DNL Target] が mbox.js を呼び出して必要なグローバル mbox を作成する必要がありました。mbox.js ファイルには、各アクティビティに必要なものがすべて格納されています。アクティビティごとに異なる mbox.js ファイルを管理する必要はありません。<br>古いスタイルの [!DNL Target] 実装から既にページに mbox のラッピングが含まれている場合、その mbox は、新しいインターフェイスでもそのまま使用できます。更新された mbox.js ファイルは引き続き必要になりますが、これらの mbox は、アクティビティ用に選択したり、Visual Experience Composer を使用して編集したりすることができます。<br>[!DNL Target] Standard および Premium では、target.js ファイルを参照することで mbox.js が更新および補完されます。target.js ファイルは、アドビがホストしています。target.js によって、事前定義された mbox がページに含まれていなくても、Visual Experience Composer を使用してどのページでもコンテンツの編集が可能になります。このファイルは、サイト上のすべてのページで参照する必要があります。<br>詳しくは、「[mbox.js の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)」を参照してください。<br>**重要**： mbox.js ライブラリは引き続きサポートされますが、機能はアップデートされません。すべてのお客様が at.js に移行する必要があります。詳しくは、「[mbox.js から at.js への移行](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)<br>」を参照してください。 |

## at.js と mbox.js がページ読み込み時間に与える影響 {#section_16630CD0FF0A498EB596A51381366A5A}

特に新しいユーザーとリピートユーザーのコンテキストにおいて [!DNL at.js] と [!DNL mbox.js] がページ読み込み時間に与える影響を知りたいと考えているお客様やコンサルタントは数多くいます。残念ながら、[!DNL at.js] または [!DNL mbox.js] が各ページの読み込み時間にどのように影響するかはお客様の実装に左右されるので、具体的な数値を測定して示すことは困難です。

ただし、訪問者 API がページに存在する場合は、[!DNL at.js] と [!DNL mbox.js] がページ読み込み時間にどのように影響するかを把握できます。

>[!NOTE]
>
>訪問者 API と [!DNL at.js] または [!DNL mbox.js] は、（本文を非表示にする技術により）グローバル mbox を使用している場合にのみ、ページ読み込み時間に影響を与えます。リージョナル mbox は訪問者 API 統合の影響を受けません。

以降のセクションでは、新しい訪問者と再訪問者の一連のアクションについて説明します。

### 新しい訪問者

1. 訪問者 API が読み込まれ、解析され、実行されます。
1. at.js または mbox.js が読み込まれ、解析され、実行されます。
1. グローバル mbox の自動作成が有効な場合、Target JavaScript ライブラリは次の操作を実行します。

   * Visitor オブジェクトをインスタンス化します。
   * Target ライブラリが、Experience Cloud 訪問者 ID データの取得を試みます。
   * この訪問者は新しい訪問者なので、訪問者 API によって demdex.net へのクロスドメインリクエストが発行されます。
   * Experience Cloud 訪問者 ID データが取得された後、Target に対するリクエストが発行されます。

### 再訪問者

1. 訪問者 API が読み込まれ、解析され、実行されます。
1. at.js または mbox.js が読み込まれ、解析され、実行されます。
1. グローバル mbox の自動作成が有効な場合、Target JavaScript ライブラリは次の操作を実行します。

   * Visitor オブジェクトをインスタンス化します。
   * Target ライブラリが、Experience Cloud 訪問者 ID データの取得を試みます。
   * 訪問者 API が、Cookie からデータを取得します。
   * Experience Cloud 訪問者 ID データが取得された後、Target に対するリクエストが発行されます。

>[!NOTE]
>
>新しい訪問者の場合、訪問者 API が存在すると、Target は、Target リクエストに Experience Cloud 訪問者 ID データが含まれていることを確認するために複数回やり取りをおこなう必要があります。再訪問者の場合、Target は、パーソナライズされたコンテンツを取得するためにのみ通信をおこないます。
