---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースで追加される新機能
feature: リリースノート
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b897829595ef1cdda28a995481fa1d2d5d1616f4
workflow-type: ht
source-wordcount: '349'
ht-degree: 100%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021 年 6 月 24 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.js のサポート**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しはエラーなく失敗し、デフォルトコンテンツを提供することで [!DNL Target] アクティビティを実行しているページに影響を与えます。
>
>サイトで発生する可能性のある問題を回避するには、 [!DNL Adobe Experience Platform Web SDK] または at.js JavaScript ライブラリの最新バージョンに移行します。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## [!DNL Target Standard/Premium] 21.6.1（2021 年 6 月 30 日）

このリリースには、次の新機能および機能強化が含まれています。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL Analytics for Target]（A4T） | [!DNL Analytics] をレポートソースとして使用するアクティビティ（A4T）から、[!UICONTROL レポート]ページの「[!UICONTROL Analytics で表示]」リンクをクリックすると、[!DNL Analysis Workspace] が開くようになりました。以前は、このリンクをクリックすると、[!DNL Analytics] レポートが開きました。 （TGT-36959） |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | [!DNL Recommendations] 人気度アルゴリズムに次の機能強化が適用されます。<ul><li>[!DNL Target] が行動データソースの場合、すべての人気度（最も頻繁に閲覧された／トップセラー）アルゴリズムに対して、6 時間の新しい「ルックバックウィンドウ」（データ範囲）オプションが利用できます。 （このルックバックウィンドウは、[!DNL Adobe Analytics] が行動データソースの場合は&#x200B;*使用できません*。）</li><li>選択した場合、次のアルゴリズムは、（12 時間ごとではなく）約 3 時間ごとに実行されます。<ul><li>最も頻繁に閲覧された</li><li>最も多く購入された</li><li>カテゴリ別で最も多く閲覧された</li><li>カテゴリ別で最も多く購入された</li><li>カスタム属性別で最も多く閲覧された（groupBy 機能を使用）</li><li>カスタム属性別で最も多く購入された（groupBy 機能を使用）</li></ul></ul>リリース日は後日発表。（上位 1086 項目） |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
