---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースで追加される新機能
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8f5e2c5025dc4b9caf31f51c03fb073ddd9ba756
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 41%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021 年 10 月 7 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.js のサポート**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しはエラーなく失敗し、デフォルトコンテンツを提供することで [!DNL Target] アクティビティを実行しているページに影響を与えます。
>
>サイトで発生する可能性のある問題を回避するには、 [!DNL Adobe Experience Platform Web SDK] または at.js JavaScript ライブラリの最新バージョンに移行します。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## [!DNL Target Standard/Premium] 21.10.1（2021 年 10 月 7 日）

このリリースには、次の新機能が含まれています。

| 機能 | 詳細 |
| --- | --- |
|  AudiencesUI の更新 | [!DNL Adobe Target] チームが継続的に [!DNL Target] ユーザーのユーザーエクスペリエンスを向上させるための取り組みの一環として、このリリースでは、[!DNL Target] UI の [!UICONTROL Audiences] ページと [!UICONTROL  プロファイルスクリプト ] ページを更新します。 この更新により、以前は一貫性がなかったデザインパターンを統合および標準化し、次のような新しい機能強化を追加しました。<ul><li>複数のオーディエンスを同時に選択および削除する機能</li><li>更新された [audience builder デザイン ](/help/c-target/c-audiences/create-audience.md)</li><li>[!UICONTROL  オーディエンス ] ライブラリルールビルダーでの除外ルールのサポート</li><li>新しい「オーディエンスソース」フィルターにより、オーディエンスの検出を高速化</li><li>セッションの永続的な検索およびフィルターオプション</li></ul>詳しくは、[オーディエンス](/help/c-target/target.md)を参照してください。<br>**注意**:この UI の更新は、EMEA 地域のお客様にのみ影響します。北米を含む世界の他の地域のお客様は、来週更新された UI を参照します。 |
| [!UICONTROL プロファイル] スクリプト UI の更新 | [!UICONTROL  プロファイルスクリプト ] ライブラリも更新され、更新されたインターフェイスと複数の生産性の更新が含まれています。<ul><li>複数のプロファイルスクリプトを同時に選択および削除する機能</li><li>プロファイルスクリプト用の新しいコードエディター</li><li>コードエディター内での構文のハイライトとエラーチェック</li><li>キーボードショートカットを使用したオートコンプリートトークン（mbox またはプロファイル）パラメーター</li></ul>詳しくは、[ 訪問者プロファイル ](/help/c-target/c-visitor-profile/visitor-profile.md) を参照してください。<br>**注意**:この UI の更新は、EMEA 地域のお客様にのみ影響します。北米を含む世界の他の地域のお客様は、来週更新された UI を参照します。 |
| ![Premium バッ](/help/assets/premium.png) ジ Recommendations 条件の作成と編集 | [!UICONTROL Recommendations条件 ] の作成および編集ワークフローが簡素化され、目標を達成するために適切なレコメンデーションアルゴリズムと設定を簡単に選択できるようになりました。<br>詳しくは、条件の作成を参照 [してください](/help/c-recommendations/c-algorithms/create-new-algorithm.md)。 |
| ![Premium バッ](/help/assets/premium.png) ジ Recommendations のルックバックウィンドウとアルゴリズムの更新率の改善 | 「最も多く閲覧された」および「トップセラー」アルゴリズムを 6 時間のルックバックウィンドウで実行して、最近トレンドを示すコンテンツを取り込めるようになりました。 6 時間のルックバックウィンドウを選択すると、レコメンデーションの結果は 1 日を通じて 3 ～ 6 時間ごとに更新されます。<br>詳しくは、「条件の作成」の「デ [ータソ](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) ー *ス*」を参照してください。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
