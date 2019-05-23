---
description: at.js と mbox.js にはいくつかの違いがあります。このセクションでは、at.js で成功するために役立つ、いくつかの違いと制限を取り上げます。
keywords: visual experience composer の制限;ブラウザーサポート;統合;プラグイン;非同期の考慮事項
seo-description: at.js と mbox.js にはいくつかの違いがあります。このセクションでは、at.js で成功するために役立つ、いくつかの違いと制限を取り上げます。
seo-title: at.js の制限
solution: 'Target '
title: at.js の制限
topic: Premium
uuid: 6c2dfd85-4c4d-4204-a9e9-e358f0b70ded
translation-type: tm+mt
source-git-commit: e776db611baf2a844de1045a9e3268c28dd9b522

---


# at.js の制限{#at-js-limitations}

at.js と mbox.js にはいくつかの違いがあります。このセクションでは、at.js で成功するために役立つ、いくつかの違いと制限を取り上げます。

## Visual Experience Composer の既知の制限 {#section_4B63C97169DE4C93B22944E880FD3DF1}

* Visual Experience Composer の「要素を挿入」および「整列」オプションは、シングルページアプリでは避ける必要があります。

   従来の Web サイトで使用するように、シングルページアプリのページ読み込みイベント時に DOM がクリアされないので、「要素を挿入」および「整列」操作は、訪問者が SPA をナビゲートする方法によって複数回にわたって再適用される可能性があります。

## 統合とプラグイン {#section_D92E31170176406AAC7B5005F03D3425}

[!DNL mbox.js] 内の一部の関数は、[!DNL at.js] では利用できません。内部 [mbox.js オブジェクトおよびメソッド](../../../../c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537)（`mbox`、`mboxCurrent`、`mboxFactoryDefault`、`mboxFactories` など）は、[!DNL at.js] ではサポートされません（例： `mboxFactoryDefault`）。これは設計によるもので、長期的に見ると実装を機能しなくさせ、アップグレードできなくさせる可能性のある、サポートされていない機能を開発するために [!DNL at.js] を「ハッキング」するのを阻止することを目的としています。公開されたメソッドのみ、このドキュメントの API ページで説明しています。理由は以下のとおりです。

* 従来のアドビソリューションとのページベース [の統合](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39) は動作しない可能性があり、より新しいサーバー側統合にアップグレードする必要があります。
* [mbox.js 用に開発されたカスタムプラグイン](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF)は、[!DNL at.js] 用に更新しない限り、動作しない可能性がある。

   すべての[プラグイン](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF)をテストの一部として含めるようにします。

## 非同期の考慮事項 {#section_B586360A3DD34E2995AE25A18E3FB953}

現在すべての mbox は非同期なので、ページレンダリングをブロックせず、実行された順番で返されます。

* [フォームベースの Experience Composer](../../../../c-experiences/experiences.md#section_3643394BD424463C8768F2907DEBCC22) でグローバル mbox を使用している場合、HTML オファーには`<script>`、`<style>`、および `<link>` タグのみ含まれるようにしてください。

   配信中、[!DNL at.js] はグローバル mbox オファーを適用する際に他のすべての HTML タグを除外します。グローバル mbox オファーは HTML HEAD に適用されます。このタグでは、DIV、SPAN などは使用できません。例えば、`<div>test</div>` タグは HTML BODY 内でのみ使用できるので、`<div>` を適用できません。

* 従来のページベースの [!DNL Target] と [!DNL Analytics] の統合は動作しません。

   この統合は、[!DNL Target] 呼び出しの前に [!DNL Analytics] 呼び出しが実行される必要があります。

* オファーとページの間の JavaScript の依存関係に気をつけてください。

   オファーの JavaScript が mbox の下のハードコードされた JavaScript の前に実行されると想定すべきではありません。

* ページの複数のオファー間での JavaScript の依存関係に気をつけてください。

   最初の mbox によって配信されたオファーが 2 番目の mbox によって配信されたオファーの前に実行されると想定することはできません。

* DOM 操作およびリダイレクトオファーは、[!DNL at.js] で自動作成されたグローバル mbox を使用して配信されるか、`<head>` 内で配信される必要があります。

   `<body>` の最上部にある `mboxCreate()` 関数は、デフォルトコンテンツのちらつきを引き起こす可能性があります。

