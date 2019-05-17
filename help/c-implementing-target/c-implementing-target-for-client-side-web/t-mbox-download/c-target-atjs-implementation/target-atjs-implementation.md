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
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# mbox.js から at.js への移行{#migrate-from-mbox-js-to-at-js}

at.js ライブラリは、一般的な Web 実装とシングルページアプリケーションの両方のために設計された、[!DNL Adobe Target] の新しい実装ライブラリです。

多くのメリットがある中でも、[!DNL at.js] は、Web 実装のページ読み込み時間を強化し、シングルページアプリケーション向けのより優れた実装オプションを提供します。

[!DNL at.js] は、[!DNL Target] 実装の [!DNL mbox.js] を置き換えます。また、[!DNL at.js] ライブラリは、[!DNL target.js] に含まれるコンポーネントを含んでいるので、[!DNL target.js] を呼び出す必要がありません。

>[!NOTE]
>
>（FP-11577 以降）が適用された Adobe Experience Manager（AEM）6.2 では、at.js 実装とその Adobe Target Cloud Services 統合がサポートされています。詳しくは、*Adobe Experience Manager 6.2 ドキュメント*の[機能パック](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html)および [Adobe Target との統合](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html)を参照してください。

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
