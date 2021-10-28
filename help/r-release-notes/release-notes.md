---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれる新機能
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 89b995f20491fe0a51c91f8a1fe7e6b1ccc7f974
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 38%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

>[!IMPORTANT]
>
>**mbox.js のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しは失敗し、デフォルトのコンテンツを表示して [!DNL Target] アクティビティを実行しているページには影響があります。
>
>サイトに起こりうる問題を回避するため、新しい [!DNL Adobe Experience Platform Web SDK] の最新バージョンまたは at.js JavaScript ライブラリの最新バージョンに移行してください。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

## at.js バージョン 2.7.0（2021 年 10 月 29 日）

このリリースで強化された機能は次のとおりです。

* のサポートを追加しました。 [Web コンポーネント](https://developer.mozilla.org/en-US/docs/Web/Web_Components). このバージョンの at.js は、カスタム要素およびカスタム要素内の要素に対して、パーソナライズされたエクスペリエンスおよびオファーを作成およびテストするために必要です。 この機能は、 [!DNL Target Standard/Premium] 21.10.5リリース。

## [!DNL Target Standard/Premium] 21.10.5（2021 年 10 月 29 日）

このメンテナンスリリースで強化された機能は次のとおりです。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL Visual Experience Composer]（VEC） | のサポートを追加しました。 [Web コンポーネント](https://developer.mozilla.org/en-US/docs/Web/Web_Components). パーソナライズされたエクスペリエンスとオファーを、カスタム要素およびカスタム要素内の要素で作成およびテストできます。<br>詳しくは、 [Visual Experience Composer のオプション](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#custom). |

## [!DNL Target Standard/Premium] 21.10.4（2021 年 10 月 22 日）

このメンテナンスリリースで強化された機能は次のとおりです。

| 機能 | 詳細 |
| --- | --- |
| 買い物かごベースのRecommendations | 訪問者の買い物かごの内容に基づいてレコメンデーションを配信するためのアルゴリズムの新しいファミリーが追加されました。<br>詳しくは、 [条件の作成](/help/c-recommendations/c-algorithms/create-new-algorithm.md) および「買い物かごへの追加/買い物かごの表示/チェックアウトページ」および「訪問者の買い物かごに既に存在する項目を除外」 [Recommendationsの計画と実装](/help/c-recommendations/plan-implement.md). |

## [!DNL Target Standard/Premium] 21.10.3（2021 年 10 月 20 日）

このメンテナンスリリースには、以下の機能強化、修正および変更が含まれています。

* お客様が [!UICONTROL A4T] パネル内 [!DNL Analysis Workspace] クリックして [!UICONTROL Analytics で表示] ボタンで [!DNL Target] アクティビティレポート。 （TGT-42099、TGT-42100）
* 次の問題を修正しました： [!UICONTROL デザインを編集] ボタンを編集中に表示しない [!UICONTROL A/B テスト] および [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ [!UICONTROL フォームベースの Experience Composer]. （TGT-41980）
* が [!UICONTROL 互換] 新しい作成時に条件選択で表示されないチェックボックス [!UICONTROL Recommendations] アクティビティ。 （TGT-42053）
* 選択できない場合に表示される誤ったエラーメッセージを修正しました。 [!DNL Analytics] がないため (A4T)、レポートソースとして [!DNL Analytics] 権限。 （TGT-41954）
* キーボード操作が [!DNL Target] UI

## [!DNL Target Standard/Premium] 21.10.2（2021 年 10 月 14 日）

を使用する際に、次の機能が追加されました。 [!DNL Target] [!UICONTROL オーディエンス] と [!DNL Adobe Experience Platform Web SDK]:

* の様々な場所に警告アイコン、ポップオーバーおよびメッセージが追加されました。 [!DNL Target] オーディエンスがソースで削除され、で使用できなくなったことを示す UI [!DNL Target] アクティビティ。

   次の図に、アイコン、ポップオーバー、メッセージが表示される場所の一部を示します。

   * [!UICONTROL アクティビティ] リストページ

      ![オーディエンスがアクティビティリストページのソースメッセージで削除されました](assets/deleted-at-source-audiences-list.png)

   * アクティビティ [!UICONTROL 概要] ページ：

      ![オーディエンスが概要ページのソースメッセージで削除されました](assets/deleted-at-source-overview.png)

   * [!UICONTROL エクスペリエンス] アクティビティ作成ワークフローのステップ：

      ![オーディエンスが次のソースメッセージで削除されました： [!UICONTROL エクスペリエンス] ページ](assets/deleted-at-source-experiences.png)

   * [!UICONTROL ターゲット設定] アクティビティ作成ワークフローのステップ：

      ![オーディエンスが次のソースメッセージで削除されました： [!UICONTROL ターゲット設定] ページ](assets/deleted-at-source-targeting.png)

   * [!UICONTROL 目標と設定] アクティビティ作成ワークフローのステップ：

      ![オーディエンスが [!UICONTROL 目標と設定] ページ](assets/deleted-at-source-goals-settings.png)

   * オーディエンスの絞り込み ([!UICONTROL オーディエンスを置換] の [!UICONTROL ターゲット設定] （アクティビティ作成ワークフローの手順）:

* オーディエンスを結合機能を使用しようとしたときに、いずれかのオーディエンスがソースから削除された場合、 [!UICONTROL 保存] は無効です。

## [!DNL Target Standard/Premium] 21.10.1（2021年10月6日（PT））

このリリースには、次の新機能が含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL オーディエンス UI の更新] | の一部として [!DNL Adobe Target] のユーザーエクスペリエンスを改善するためのチームの継続的な取り組み [!DNL Target] ユーザー、このリリースでは [!UICONTROL オーディエンス] および [!UICONTROL プロファイルスクリプト] ページ [!DNL Target] UI この更新により、以前は一貫性がなかったデザインパターンを統合および標準化し、次のような新しい機能強化を追加しました。<ul><li>複数のオーディエンスを同時に選択および削除する機能</li><li>更新済み [audience builder のデザイン](/help/c-target/c-audiences/create-audience.md)</li><li>での除外ルールのサポート [!UICONTROL 対象ユーザ] ライブラリルールビルダー</li><li>新しい「オーディエンスソース」フィルターにより、オーディエンスの検出を高速化</li><li>セッションの永続的な検索およびフィルターオプション</li></ul>詳しくは、[オーディエンス](/help/c-target/target.md)を参照してください。<br>**注意**:新しい [!UICONTROL オーディエンス] UI は一部のお客様のみご利用いただけます。 2022 年 1 月以降、すべてのお客様に対して段階的に更新が実施される予定です。 |
| [!UICONTROL プロファイルスクリプト] UI の更新 | この [!UICONTROL プロファイルスクリプト] ライブラリも更新され、更新されたインターフェイスといくつかの生産性の更新が含まれています。<ul><li>複数のプロファイルスクリプトを同時に選択および削除する機能</li><li>プロファイルスクリプト用の新しいコードエディター</li><li>コードエディター内での構文のハイライトとエラーチェック</li><li>キーボードショートカットを使用したトークン（mbox またはプロファイル）のオートコンプリートパラメーター</li></ul>詳しくは、 [訪問者プロファイル](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**注意**:新しい [!UICONTROL プロファイルスクリプト] UI は一部のお客様のみご利用いただけます。 2022 年 1 月以降、すべてのお客様に対して段階的に更新が実施される予定です。 |
| ![Premium バッジ](/help/assets/premium.png) Recommendations条件の作成と編集 | この [!UICONTROL Recommendations条件] 作成と編集ワークフローが合理化され、目標を達成するために適切なレコメンデーションアルゴリズムと設定を簡単に選択できるようになりました。<br>詳しくは、 [条件の作成](/help/c-recommendations/c-algorithms/create-new-algorithm.md). |
| ![Premium バッジ](/help/assets/premium.png) Recommendationsのルックバックウィンドウとアルゴリズムの更新率の改善 | 6 時間のルックバックウィンドウで「最も多く閲覧された」および「トップセラー」アルゴリズムを実行して、最近トレンドを示すコンテンツを取り込めるようになりました。 6 時間のルックバックウィンドウを選択すると、レコメンデーションの結果は 1 日を通して 3～6 時間ごとに更新されます。<br>詳しくは、 [データソース](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) in *条件の作成*. |

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
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
