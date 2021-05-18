---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースで追加される新機能
feature: リリースノート
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7eb44049a954f1f18c1e4a52d455d352d0fcfdf0
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 36%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021 年 5 月 18 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングに応じて、これらのページの情報は同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリをサポートし [!DNL Adobe Target] なくなりました。2021年3月31日以降、mbox.jsから行われたすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにデフォルトコンテンツが提供されるようになりました。
>
>サイトに発生する可能性のある問題を回避するには、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに移行します。 詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## at.jsバージョン2.5.0（2021年5月14日）

at.jsのこのリリースには、次の機能強化および変更が含まれています。

* [at.jsのオンデバイス](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) 判定のサポート。
* [](/help/c-activities/c-activity-qa/activity-qa.md) Automated Personalization  (AP)アクティビティのプレビューリンクのサポート

このリリースでは、Microsoft Internet Explorer 10、Internet Explorer 11、およびすべての古いバージョンのサポートも削除されます。 Microsoft Edgeは、at.js 2.5.0以降で引き続きサポートされます。 詳しくは、「[サポートされているブラウザー](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)」を参照してください。

## [!DNL Adobe Experience Platform Web SDK] バージョン2.5.0（2021年5月24日）

[!DNL Platform Web SDK]のこのリリースには、[!DNL Target]リダイレクトの[!UICONTROL ターゲット](A4T)の解析のサポートが含まれています。

## [!DNL Target Standard/Premium] 21.5.1（2021年5月25日）

リリース日が近づくと、コンテンツが追加されます。

## [!DNL Target Standard/Premium] 21.5.2 （決定日）

このリリースには、次の新機能および機能強化が含まれています。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

| 機能 | 詳細 |
| --- | --- |
| ![プレミアム](/help/assets/premium.png) [!DNL Recommendations] | [!DNL Recommendations]人気アルゴリズムに適用される改良点：<ul><li>行動データソースが[!DNL Target]の場合、すべての人気（最も多く閲覧された/トップセラー）アルゴリズムで、新しい6時間の「ルックバックウィンドウ」（データ範囲）オプションが利用できます。 （このルックバックウィンドウは、[!DNL Adobe Analytics]が行動データソースの場合は&#x200B;*利用できません*。）</li><li>選択した場合、以下のアルゴリズムは、12時間ごとではなく、約3時間ごとに実行されます。<ul><li>最も多く閲覧された</li><li>最も多く購入された</li><li>最も多く閲覧されたカテゴリ</li><li>最も多く購入されたカテゴリ</li><li>カスタム属性（groupBy機能を使用）によって最も多く閲覧された</li><li>カスタム属性で最も多く購入されたもの（groupBy機能を使用）</li></ul></ul>(TOP-1086) |

このリリースには、次の修正が含まれています。

* リリース日が近づくと、コンテンツが追加されます。

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
