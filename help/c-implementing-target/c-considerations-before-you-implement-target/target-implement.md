---
keywords: document.write;target；実装；targetの実装；at.js;mbox.js;target.js;mbox;adobe experience platform web skd;aep web sdk;web sdk
description: WebページにAdobe [!DNL Target] by referencing the [!DNL Target] ライブラリ（at.jsまたはmbox.js）を実装します。
title: ' [!DNL Target]  JavaScript ライブラリについて '
feature: 実装
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 24%

---


# [!DNL Target] JavaScript ライブラリについて 

Webページで[!DNL Adobe Target]ライブラリ(Adobe Experience Platform Web SDKまたはat.js)を参照して[!DNL Adobe Target]を実装します。

>[!NOTE]
>
>mbox.js ライブラリの開発は終了しました。2021年3月31日より前に、すべてのお客様がmbox.jsからat.jsまたは[!UICONTROL Adobe Experience Platform Web SDK]に移行する必要があります。

## [!DNL Target] JavaScriptライブラリの違い {#section_40117C78C2F84FECAC4F1BA40CC4F171}

次の表に、[!DNL Target] JavaScriptライブラリの違いを示します。

| ライブラリリファレンス | 説明 |
|--- |--- |
| Adobe Experience Platform Web SDK | [!UICONTROL Adobe Experience Platform Web SDK]を使用すると、Adobe Experience Edgeネットワークを介して[!DNL Experience Cloud]の様々なサービス（[!DNL Target]を含む）を操作できます。 [!DNL Adobe Experience Platform Web SDK]に移行する場合は、『*Web SDKガイド*』の「[Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)とは」を参照してください。 |
| at.js | at.jsは、mbox.jsに代わる[!DNL [!DNL Target]]実装です。<br>多くのメリットがある中でも、at.js は、Web 実装のページ読み込み時間を改善し、セキュリティを強化して、Google Chrome での document.write 警告を回避し、シングルページアプリケーション向けのより優れた実装オプションを提供します。 |

## at.jsがページ読み込み時間に与える影響 {#section_16630CD0FF0A498EB596A51381366A5A}

特に新しいユーザーと再訪問者のコンテキストにおいて[!DNL at.js]がページ読み込み時間に与える影響を知りたいと考えているお客様やコンサルタントは多くいます。 残念ながら、[!DNL at.js]が各顧客の実装によってページ読み込み時間に与える影響に関して具体的な数値を測定して示すのは困難です。

ただし、訪問者APIがページに存在する場合は、[!DNL Target]がページ読み込み時間に[!DNL at.js]がどのように影響するかをより深く理解できます。

>[!NOTE]
>
>訪問者APIと[!DNL at.js]は、（本文を非表示にする技術により）グローバルmboxを使用している場合にのみ、ページ読み込み時間に影響します。 リージョナル mbox は訪問者 API 統合の影響を受けません。

以降のセクションでは、新しい訪問者と再訪問者の一連のアクションについて説明します。

### 新しい訪問者

1. 訪問者 API が読み込まれ、解析され、実行されます。
1. at.jsが読み込まれ、解析され、実行されます。
1. グローバルmbox自動作成が有効な場合、[!DNL Target] JavaScriptライブラリは次のようになります。

   * Visitor オブジェクトをインスタンス化します。
   * [!DNL Target]ライブラリは、[!UICONTROL Experience Cloud訪問者ID]データの取得を試みます。
   * 新しい訪問者の場合、訪問者APIは`demdex.net`に対してクロスドメインリクエストを実行します。
   * [!UICONTROL Experience Cloud訪問者ID]データが取得された後、Targetへのリクエストが実行されます。

### 再訪問者

1. 訪問者 API が読み込まれ、解析され、実行されます。
1. at.jsが読み込まれ、解析され、実行されます。
1. グローバルmbox自動作成が有効な場合、[!DNL Target] JavaScriptライブラリは次のようになります。

   * Visitor オブジェクトをインスタンス化します。
   * [!DNL Target]ライブラリは、[!UICONTROL Experience Cloud訪問者ID]データの取得を試みます。
   * 訪問者 API が、Cookie からデータを取得します。
   * [!UICONTROL Experience Cloud訪問者ID]データが取得された後、[!DNL Target]に対するリクエストが実行されます。

>[!NOTE]
>
>新規訪問者の場合、訪問者APIが存在すると、[!DNL Target]は[!DNL Target]リクエストに[!UICONTROL Experience Cloud訪問者ID]データが含まれていることを確認するために複数回やり取りします。 再訪問者の場合、[!DNL Target]は、パーソナライズされたコンテンツを取得するために[!DNL Target]にのみ通信をおこないます。
