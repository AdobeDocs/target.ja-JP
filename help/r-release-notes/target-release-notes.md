---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースで追加される新機能
feature: リリースノート
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 3be6ad187b99472ccd3019e6998eba4953e2f5b5
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 33%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021 年 5 月 24 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングに応じて、これらのページの情報は同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日現在、 [!DNL Adobe Target] はmbox.jsライブラリをサポートしていません。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、デフォルトコンテンツを提供することで実行中の[!DNL Target]アクティビティを持つページに影響が及びます。
>
>サイトで発生する可能性のある問題を回避するには、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに移行します。 詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## ![Adobe Experience Platform Web SDKバッ](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] ジバージョン2.5.0（2021年6月2日）

このリリースの[!DNL Platform Web SDK]には、次のサポートが含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL Analytics for Target](A4T)によるリダイレクトのサポート | A4Tを使用する際に、Platform Web SDKで[!DNL Target]リダイレクトがサポートされるようになりました。 [!DNL Adobe Target]のリダイレクトオファーは、ブラウザーが新しいページにリダイレクトされる原因となります。 |
| レスポンストークン | Platform Web SDKで[!DNL Target]レスポンストークンがサポートされるようになりました。 レスポンストークンを使用すると、[!DNL Adobe Target]に固有の情報をブランドのWebページに自動的に出力できます。 この情報には、アクティビティ、オファー、エクスペリエンス、ユーザープロファイル、地域情報などの詳細が含まれます。 これらの詳細は、内部またはサードパーティのシステムと共有したり、デバッグに使用したりするための追加の応答データを提供します。 |

## [!DNL Target Standard/Premium] 21.5.1（2021年6月9日）

リリース日が近づくと、内容が追加されます。

## [!DNL Target Standard/Premium] 21.5.2（決定日）

このリリースには、次の新機能および機能強化が含まれています。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

| 機能 | 詳細 |
| --- | --- |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | [!DNL Recommendations]人気度アルゴリズムに次の機能強化が適用されます。<ul><li>[!DNL Target]が行動データソースの場合、すべての人気（最も多く閲覧された/トップセラー）アルゴリズムに対して、6時間の新しい「ルックバックウィンドウ」（データ範囲）オプションが利用できます。 （このルックバックウィンドウは、[!DNL Adobe Analytics]が行動データソースの場合は&#x200B;*使用できません*。）</li><li>選択した場合、次のアルゴリズムは、（12時間ごとではなく）約3時間ごとに実行されます。<ul><li>最も多く閲覧された</li><li>最も多く購入された</li><li>カテゴリ別最も多く閲覧された</li><li>カテゴリ別で最も多く購入</li><li>カスタム属性で最も多く閲覧された（groupBy機能を使用）</li><li>カスタム属性で最も多く購入されたもの（groupBy機能を使用）</li></ul></ul>（1086年上位） |

このリリースには、次の修正が含まれています。

* リリース日が近づくと、内容が追加されます。

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
