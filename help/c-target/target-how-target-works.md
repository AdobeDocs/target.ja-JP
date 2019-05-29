---
description: Adobe Target は、at.js または mbox.js JavaScript ライブラリによって Web ページと統合できます。
keywords: ターゲット設定、cookie、ファーストパーティcookie、ファーストパーティCookie
seo-description: Adobe Target は、at.js または mbox.js JavaScript ライブラリによって Web ページと統合できます。
seo-title: ターゲット設定の仕組み
solution: 'Target '
title: ターゲット設定の仕組み
uuid: 8b5a36c0-555d-42c5-8b24-c08d07440a53
translation-type: tm+mt
source-git-commit: ac86b0131b0c65f3367c47b3a1315c37d9b9aa93

---


# ターゲット設定の仕組み{#how-targeting-works}

Adobe Target は、at.js または mbox.js JavaScript ライブラリによって Web ページと統合できます。

[!DNL Target Classic] では、ターゲットコンテンツや収集データを表示するページの各領域で mbox を使用しています。これらのmboxは、で [!DNL Target Standard] は必要ありません。代わりに、各ページで参照する JavaScriptライブラリ は、最適化アクティビティを実行する必要があります。

訪問者が が有効なページをリクエストするたびに、[!DNL Target]Target は次の処理によってオファーを表示します。

1. 訪問者が、サーバー上のページをリクエストしてブラウザーに表示します。
1. 一意な訪問者 ID を割り当てるため、ファーストパーティ Cookie が顧客のブラウザーに設定されます。

   マスターマーケティングプロファイルを使用している場合も、A [!DNL Experience Cloud visitor ID] が設定されます。

1. ページ上の [!DNL Target] ファイルまたは mbox 経由で [!DNL target.js] が呼び出されます。
1. [!DNL Target] は、訪問者と関連付けられたプロファイルを参照します。
1. [!DNL Target] は、プロファイルに関連付けられている任意のプロファイルスクリプトを実行します。
1. [!DNL Target] 応答を計算します。
1. アクティビティまたはキャンペーンのルールに基づいてコンテンツが表示されます。

基本的な A/B テストで表示されるオファーはランダムに選択されます。このランダムなトラフィック分割の結果、トラフィックの割合が均等化するまでの初期のトラフィック量が多くなる場合があります。例えば、2 つのエクスペリエンスを含むアクティビティがある場合、最初のエクスペリエンスはランダムに選択されます。トラフィック量がほとんどない場合は、訪問者の割合が一方のエクスペリエンスに偏っている可能性があります。トラフィックが増加するほど、その割合も均等化されていきます。
