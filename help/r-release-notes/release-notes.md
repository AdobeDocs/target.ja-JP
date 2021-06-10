---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScriptライブラリなど、 [!DNL Adobe Target]の現在のリリースに含まれる新機能、機能強化、修正点について説明します。
title: 現在のリリースに含まれる新機能
feature: リリースノート
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 29b8bf64b0ce4e7e830d9fff5341849799072dfa
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 58%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、Target API、SDK、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。 

>[!IMPORTANT]
>
>**mbox.js のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しは失敗し、デフォルトのコンテンツを表示して [!DNL Target] アクティビティを実行しているページには影響があります。
>
>新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに移行して、サイトで発生する可能性のある問題を回避します。 詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

## Target Standard／Premium 21.5.1（2021 年 6 月 7 日（PT））

このリリースで強化された機能は次のとおりです。

| 機能 | 詳細 |
| --- | --- |
| ![Premium ](/help/assets/premium.png) [!DNL Recommendations] [!UICONTROL badgeCatalog ] SearchAPI | APIを使用して[!DNL Recommendations]製品およびコンテンツカタログをプログラムで検索し、検索条件に一致する項目を特定して、カタログの管理を簡略化します。<br>**制限事項と注意事項**:<ul><li>APIを使用したカタログ検索は、2,000,000個を超える項目を持つ環境ではサポートされていません。</li><li>APIを使用したカタログ検索結果は、[!DNL Target] UIを使用したカタログ検索結果よりも迅速に更新されます。 [!DNL Target] UIでのカタログ検索には、最新の結果を反映するのに、さらに時間がかかる場合があります。</li></ul>詳しくは、『 *[!DNL Adobe Target][!DNL Recommendations] API* 』ガイドの[エンティティ](http://developers.adobetarget.com/api/recommendations/#tag/Searching-Entities)の検索を参照してください。 |

このリリースのメンテナンスリリースには、次の修正が含まれています。

* [!UICONTROL オーディエンス]ページを更新すると、デフォルトのワークスペースが別のワークスペースに変更される問題を修正しました。 （TGT-38871）
* [!UICONTROL 管理] / [!UICONTROL 実装]で、「グローバルmboxが同期していない可能性があります。」というエラーメッセージが表示される問題を修正しました。 保存し直してください」

## ![Adobe Experience Platform Web SDKバッ](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] ジバージョン2.5.0（2021年6月2日）

このリリースの[!DNL Platform Web SDK]には、次のサポートが含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL Analytics for Target](A4T)によるリダイレクトのサポート | [A4T](/help/c-integrating-target-with-mac/a4t/a4t.md)を使用する場合、Platform Web SDKで[!DNL Target]リダイレクトがサポートされるようになりました。<br>詳しくは、実装のAnalyticsを参照 [して [!DNL Target] ください](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 |

## at.jsバージョン2.5.0（2021年5月14日）

at.js のこのリリースには、次の機能強化および変更が含まれています。

* at.js の[オンデバイス判定](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)のサポート。
* Automated Personalization アクティビティでの[プレビューリンク](/help/c-activities/c-activity-qa/activity-qa.md)のサポート

このリリースでは、Microsoft Internet Explorer 10、Internet Explorer 11、およびすべての古いバージョンのサポートも削除されます。 Microsoft Edgeは、at.js 2.5.0以降で引き続きサポートされます。

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
