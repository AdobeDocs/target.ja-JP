---
keywords: ドキュメント.write;ターゲット；実装；ターゲットの実装；dtm;dynamic tag management;at.js;mbox.js;ターゲット.js;mbox;adobe experience platform web skd;aep web sdk;web sdk
description: WebページにAdobe [!DNL Target] by referencing the [!DNL Target] ライブラリ（at.jsまたはmbox.js）を実装します。
title: ' [!DNL Target]  JavaScript ライブラリについて '
feature: 実装
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 23%

---


# [!DNL Target] JavaScript ライブラリについて 

Webページ上の[!DNL Adobe Target]ライブラリ(Adobe Experience PlatformWeb SDKまたはat.js)を参照して、[!DNL Adobe Target]を実装します。

>[!NOTE]
>
>mbox.js ライブラリの開発は終了しました。すべてのお客様は、2021年3月31日までに、mbox.jsからat.jsまたは[!UICONTROL Adobe Experience PlatformWeb SDK]に移行する必要があります。 詳しくは、[mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)または[Adobe Experience PlatformWeb SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)からat.jsへの移行を参照してください。

## [!DNL Target] JavaScriptライブラリ{#section_40117C78C2F84FECAC4F1BA40CC4F171}の違い

次の表は、[!DNL Target] JavaScriptライブラリの違いを説明しています。

| ライブラリリファレンス | 説明 |
|--- |--- |
| Adobe Experience PlatformウェブSDK | [!UICONTROL Adobe Experience PlatformWeb SDK]を使用すると、Adobe Experience Edge Networkを介して[!DNL Experience Cloud]（[!DNL Target]を含む）の様々なサービスを操作できます。 [!DNL Adobe Experience Platform Web SDK]に移行する場合は、『*Web SDKガイド*』の[Adobe Experience PlatformWeb SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)とは何ですかを参照してください。 |
| at.js | at.jsは、[!DNL [!DNL Target]]実装のmbox.jsを置き換えます。<br>多くのメリットがある中でも、at.js は、Web 実装のページ読み込み時間を改善し、セキュリティを強化して、Google Chrome での document.write 警告を回避し、シングルページアプリケーション向けのより優れた実装オプションを提供します。<br>詳しくは、「[at.js の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md)」を参照してください。 |

## at.jsのページ読み込み時間に対する影響{#section_16630CD0FF0A498EB596A51381366A5A}

多くの顧客やコンサルタントは、特に新規ユーザーとリピーターのコンテキストにおいて、ページ読み込み時間に対する[!DNL at.js]の影響を知りたいと思っています。 残念ながら、[!DNL at.js]が各顧客の実装に伴うページ読み込み時間に与える影響について具体的な数値を測定し、示すのは難しいです。

ただし、訪問者APIがページに存在する場合、[!DNL Target]は[!DNL at.js]がページ読み込み時間に与える影響をより深く理解できます。

>[!NOTE]
>
>訪問者APIと[!DNL at.js]は、グローバルmboxを使用している場合のみ、ページ読み込み時間に影響します（本文の非表示の手法が原因です）。 リージョナル mbox は訪問者 API 統合の影響を受けません。

以降のセクションでは、新しい訪問者と再訪問者の一連のアクションについて説明します。

### 新しい訪問者

1. 訪問者 API が読み込まれ、解析され、実行されます。
1. at.jsが読み込まれ、解析され、実行されます。
1. グローバルmbox自動作成が有効な場合、[!DNL Target] JavaScriptライブラリ：

   * Visitor オブジェクトをインスタンス化します。
   * [!DNL Target]ライブラリは、[!UICONTROL Experience Cloud訪問者ID]データの取得を試みます。
   * 新しい訪問者の場合、訪問者APIは`demdex.net`に対してクロスドメインリクエストを実行します。
   * [!UICONTROL Experience Cloud訪問者ID]データが取得された後、ターゲットへの要求が発生します。

### 再訪問者

1. 訪問者 API が読み込まれ、解析され、実行されます。
1. at.jsが読み込まれ、解析され、実行されます。
1. グローバルmbox自動作成が有効な場合、[!DNL Target] JavaScriptライブラリ：

   * Visitor オブジェクトをインスタンス化します。
   * [!DNL Target]ライブラリは、[!UICONTROL Experience Cloud訪問者ID]データの取得を試みます。
   * 訪問者 API が、Cookie からデータを取得します。
   * [!UICONTROL Experience Cloud訪問者ID]データが取得された後、[!DNL Target]に対する要求が発生します。

>[!NOTE]
>
>新しい訪問者では、訪問者APIが存在する場合、[!DNL Target]は、[!DNL Target]リクエストに[!UICONTROL Experience Cloud訪問者ID]データが含まれていることを確認するために何度も回線を調べます。 再訪問者の場合、[!DNL Target]は[!DNL Target]にのみ回線を渡し、パーソナライズされたコンテンツを取得します。
