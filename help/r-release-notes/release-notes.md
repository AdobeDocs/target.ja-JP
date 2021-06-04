---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScriptライブラリなど、 [!DNL Adobe Target]の現在のリリースに含まれる新機能、機能強化、修正点について説明します。
title: 現在のリリースに含まれる新機能
feature: リリースノート
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: a63b123ed180a818de5338656781957931abd755
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 83%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、Target API、SDK、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。 

>[!IMPORTANT]
>
>**mbox.js のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しは失敗し、デフォルトのコンテンツを表示して [!DNL Target] アクティビティを実行しているページには影響があります。
>
>新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに移行して、サイトで発生する可能性のある問題を回避します。 詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

## ![Adobe Experience Platform Web SDKバッ](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] ジバージョン2.6.0（2021年6月2日）

このリリースの[!DNL Platform Web SDK]には、次のサポートが含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL Analytics for Target](A4T)によるリダイレクトのサポート | [A4T](/help/c-integrating-target-with-mac/a4t/a4t.md)を使用する場合、Platform Web SDKで[!DNL Target]リダイレクトがサポートされるようになりました。<br>詳しくは、実装のAnalyticsを参照 [して [!DNL Target] ください](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 |

## at.jsバージョン2.5.0（2021年5月14日）

at.js のこのリリースには、次の機能強化および変更が含まれています。

* at.js の[オンデバイス判定](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)のサポート。
* Automated Personalization アクティビティでの[プレビューリンク](/help/c-activities/c-activity-qa/activity-qa.md)のサポート

このリリースでは、Microsoft Internet Explorer 10、Internet Explorer 11、およびすべての古いバージョンのサポートも削除されます。 Microsoft Edgeは、at.js 2.5.0以降で引き続きサポートされます。

## Target Standard／Premium 21.4.1（2021 年 4 月 19 日（PT））

このリリースには、次の新機能および機能強化が含まれています。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

| 機能 | 詳細 |
| --- | --- |
| at.js のオンデバイス判定のサポート<br>（日付は後日発表） | オンデバイス判定機能を使用すると、マーケターと開発者は、ほぼゼロの待ち時間でユーザーのブラウザー上で実験とパーソナライズを行うことができます。<br>詳しくは、[at.js のオンデバイス判定](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)を参照してください。 |
| ![Premium](/help/assets/premium.png) エンティティフィルタリングルール用のリストベースの演算子 | [!DNL Target Recommendations] では、エンティティフィルタリングルールでリストベースの新しい演算子をサポートしています。 （TGT-39234）<br>新たに追加された演算子は次のとおりです。<br><ul><li>リストに含まれる</li><li>リストに含まれない</li><li>リストに項目が含まれる</li><li>リストに項目が含まれない</li><li>リストにすべての項目が含まれる</li><li>リストにすべての項目が含まれているわけではない</li></ul>詳しくは、[動的および静的包含ルールの使用](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators)の「使用可能な演算子」を参照してください。 |

このリリースには、次の修正が含まれています。

* オーディエンスを[!UICONTROL すべての訪問者]に変更した後でアクティビティを同期できない問題を修正しました。 （TGT-40259）
* 「[!UICONTROL 重複を許可しない]」オプションが有効になっている場合でも、[!UICONTROL Automated Personalization] アクティビティの異なる場所で使用するとオファーを複製できない問題を修正しました。 （TGT-39567）
* [!UICONTROL 管理]／[!UICONTROL Scene7 設定]ページが正しく読み込まれない問題を修正しました。 （TGT-39918）
* プロパティが誤ったワークスペースにマッピングされる問題を修正しました。 （TGT-39869）
* レコメンデーションの除外を作成中に環境を変更した後にリクエストが失敗した場合、無限の読み込みが発生する問題を修正しました。 （TGT-39948）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報を表示します。<br>詳しくは、「[ドキュメントの変更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](/help/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、[Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe 優先製品のアップデート | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
