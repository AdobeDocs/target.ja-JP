---
keywords: targeting;cookie;first-party cookie;1st-party cookie
description: Adobe Target は、at.js または mbox.js JavaScript ライブラリによって Web ページと統合できます。
title: ターゲット設定の仕組み
uuid: 8b5a36c0-555d-42c5-8b24-c08d07440a53
translation-type: tm+mt
source-git-commit: ba4c776d93f911c122f36113a99ce4349b3c5524

---


# ターゲット設定の仕組み{#how-targeting-works}

Adobe Target は、at.js または mbox.js JavaScript ライブラリによって Web ページと統合できます。各ページで1つのJavaScriptライブラリを参照するだけで、最適化アクティビティを実行できます。

訪問者が Target が有効なページをリクエストするたびに、[!DNL Target] は次の処理によってオファーを表示します。

1. 訪問者が、サーバー上のページをリクエストしてブラウザーに表示します。
1. 一意な訪問者 ID を割り当てるため、ファーストパーティ Cookie が顧客のブラウザーに設定されます。

   マスターマーケティングプロファイルを使用している場合も、A [!DNL Experience Cloud visitor ID] が設定されます。

1. ページ上の [!DNL Target] ファイルまたは mbox 経由で [!DNL target.js] が呼び出されます。
1. [!DNL Target] は、訪問者と関連付けられたプロファイルを参照します。
1. [!DNL Target] は、プロファイルに関連付けられている任意のプロファイルスクリプトを実行します。
1. [!DNL Target] 応答を計算します。
1. アクティビティまたはキャンペーンのルールに基づいてコンテンツが表示されます。

基本的な A/B テストで表示されるオファーはランダムに選択されます。このランダムなトラフィック分割の結果、トラフィックの割合が均等化するまでの初期のトラフィック量が多くなる場合があります。例えば、2 つのエクスペリエンスを含むアクティビティがある場合、最初のエクスペリエンスはランダムに選択されます。トラフィック量がほとんどない場合は、訪問者の割合が一方のエクスペリエンスに偏っている可能性があります。トラフィックが増加するほど、その割合も均等化されていきます。
