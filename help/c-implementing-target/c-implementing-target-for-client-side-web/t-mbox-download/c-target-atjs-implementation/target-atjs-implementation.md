---
description: at.js ライブラリは、一般的な Web 実装とシングルページアプリケーションの両方のために設計された、Adobe Target の新しい実装ライブラリです。
keywords: Target Standard;at.js;実装
seo-description: at.js ライブラリは、一般的な Web 実装とシングルページアプリケーションの両方のために設計された、Adobe Target の新しい実装ライブラリです。
seo-title: mbox.js から at.js への移行
solution: 'Target '
title: mbox.js から at.js への移行
topic: Standard
uuid: 10da01d7-d308-44e3-9c6e-ff4f713bd312
translation-type: tm+mt
source-git-commit: ac86b0131b0c65f3367c47b3a1315c37d9b9aa93

---


# mbox.js から at.js への移行{#migrate-from-mbox-js-to-at-js}

at.js ライブラリは、一般的な Web 実装とシングルページアプリケーションの両方のために設計された、[!DNL Adobe Target] の新しい実装ライブラリです。

多くのメリットがある中でも、[!DNL at.js] は、Web 実装のページ読み込み時間を強化し、シングルページアプリケーション向けのより優れた実装オプションを提供します。

[!DNL at.js] は、[!DNL Target] 実装の [!DNL mbox.js] を置き換えます。また、[!DNL at.js] ライブラリは、[!DNL target.js] に含まれるコンポーネントを含んでいるので、[!DNL target.js] を呼び出す必要がありません。

>[!NOTE]
>
>（FP-11577 以降）が適用された Adobe Experience Manager（AEM）6.2 では、at.js 実装とその Adobe Target Cloud Services 統合がサポートされています。詳しくは、*Adobe Experience Manager 6.2 ドキュメント*の[機能パック](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html)および [Adobe Target との統合](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html)を参照してください。

## at. jsの利点 {#benefits}

次の表は、この 2 つのライブラリの違いを説明しています。

| ライブラリリファレンス | 説明 |
|--- |--- |
| at.js | at.js は、mbox.js に替わる [!DNL Target] 実装ライブラリです。<br>多くのメリットがある中でも、at.js は、Web 実装のページ読み込み時間を改善し、セキュリティを強化して、Google Chrome での document.write 警告を回避し、シングルページアプリケーション向けのより優れた実装オプションを提供します。<br>詳しくは、「[at.js の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md)」を参照してください。 |
| mbox.js | [!DNL Target] 16.3.1（2016 年 3 月）以前は、[!DNL Target] がアクティビティの配信、クリックの追跡、および最も成功した指標の追跡を行うためには、[!DNL Target] が mbox.js を呼び出して必要なグローバル mbox を作成する必要がありました。mbox.js ファイルには、各アクティビティに必要なものがすべて格納されています。アクティビティごとに異なる mbox.js ファイルを管理する必要はありません。<br>古いスタイルの [!DNL Target] 実装から既にページに mbox のラッピングが含まれている場合、その mbox は、新しいインターフェイスでもそのまま使用できます。更新された mbox.js ファイルは引き続き必要になりますが、これらの mbox は、アクティビティ用に選択したり、Visual Experience Composer を使用して編集したりすることができます。<br>[!DNL Target] Standard および Premium では、target.js ファイルを参照することで mbox.js が更新および補完されます。target.js ファイルは、アドビがホストしています。target.js によって、事前定義された mbox がページに含まれていなくても、Visual Experience Composer を使用してどのページでもコンテンツの編集が可能になります。このファイルは、サイト上のすべてのページで参照する必要があります。<br>詳しくは、「[mbox.js の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)」を参照してください。<br>**重要**： mbox.js ライブラリは引き続きサポートされますが、機能はアップデートされません。すべてのお客様が at.js に移行する必要があります。詳しくは、「[mbox.js から at.js への移行](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)<br>」を参照してください。 |

## at. jsの実装

[!DNL at.js] を使用するには、実装したいページの [!DNL mbox.js] 参照を置き換えます。[!DNL mbox.js] と [!DNL at.js] の両方をシングルページで使用できません。ただし、サイトのページごとにどちらかを使用できます。

[!DNL at.js] ライブラリは、`mboxCreate()`、`mboxDefine()`、および `mboxUpdate()` 関数を使用する既存の実装で機能し、シングルページアプリベースの実装に重点を置いた新機能をサポートします。

現在 [!DNL at.js] を使用している場所ならどこでも [!DNL mbox.js] を使用できます。

[!DNL at.js] ライブラリには、以下のように、[!DNL mbox.js] ライブラリに対していくつかの強化点があります。

* クロスドメイン AJAX を使用した完全非同期通信

   >[!IMPORTANT]
   >
   >[!DNL at.js] は、[!DNL Target] サーバーと非同期で通信しますが、[!DNL at.js] ファイル自体は、ページの `<head>` セクションで同期して読み込む必要があります。理想的には、最初に読み込まれるスクリプトの 1 つである必要があります。読み込まれると、[!DNL at.js] は、`XMLHttpRequest` を使用して mbox 呼び出しを非同期で実行し、ページレンダリングをブロックしません。

* これ以上呼び出しをブロックしない
* `document.write()` を使用しない
* [!DNL Target] 応答の JavaScript をすぐに実行しない
* より優れたタイムアウトとエラー処理

   * 呼び出しごとに[タイムアウト](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)をカスタマイズ可能
   * タイムアウト時にリロードしない

* シングルページアプリ／MVC フレームワーク用に特別に設計された関数

## トレーニングビデオ： at.js - メリットと実装に関するベストプラクティス

このビデオは、「[Office Hours](../../../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」（アドビカスタマーケアチーム主導による取り組みの 1 つ）の録画です。

* at.js ライブラリの仕組み
* mbox.js に勝る at.js のメリット
* at.js によるちらつきの制御方法
* at.js でのエラー処理
* デバッグ手法
* 既知の問題と今後のロードマップ

>[!VIDEO](https://video.tv.adobe.com/v/22223/)
