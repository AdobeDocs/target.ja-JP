---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれる新機能
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 8fe168950effe60ead262c842fe9d89d1e376e57
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 96%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

>[!IMPORTANT]
>
>**mbox.js のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target] mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しは失敗し、デフォルトのコンテンツを表示して [!DNL Target] アクティビティを実行しているページには影響があります。
>
>サイトに起こりうる問題を回避するため、新しい [!DNL Adobe Experience Platform Web SDK] の最新バージョンまたは at.js JavaScript ライブラリの最新バージョンに移行してください。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

## at.js バージョン 2.8.0（2022 年 1 月 8 日）

この [!DNL Target] at.js JavaScript ライブラリが機能使用状況およびパフォーマンスのテレメトリデータを収集するようになりました。 個人データは収集されません。 この機能のオプトアウトは、次の設定で使用できます。 `telemetryEnabled` 偽りを言う `targetGlobalSettings`. 詳しくは、 [targetGlobalSettings で telemetryEnabled](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#telemetry).

## [!DNL Target Standard/Premium] 21.10.5（2021年10月28日（PT））

このメンテナンスリリースで強化された機能は次のとおりです。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL Visual Experience Composer]（VEC） | [Web コンポーネント](https://developer.mozilla.org/ja/docs/Web/Web_Components)のサポートを追加しました。パーソナライズされたエクスペリエンスとオファーを、カスタム要素およびカスタム要素内の要素に対して作成し、テストできます。<br>詳しくは、「[Visual Experience Composer オプション](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#custom)」を参照してください。 |

## [!DNL Target Standard/Premium] 21.10.4（2021年10月21日（PT））

このメンテナンスリリースで強化された機能は次のとおりです。

| 機能 | 詳細 |
| --- | --- |
| 買い物かごベースの推奨事項 | 訪問者の買い物かごの内容に基づいて推奨事項を提供する、新しいアルゴリズムファミリーが追加されました。<br>詳しくは、[条件の作成](/help/c-recommendations/c-algorithms/create-new-algorithm.md)の「買い物かごベース」、[計画とレコメンデーションの実装](/help/c-recommendations/plan-implement.md)の「買い物かごの追加／買い物かごの表示／チェックアウトページ」および「訪問者の買い物かごに既に存在する項目の除外」、[レコメンデーションキーに基づくレコメンデーションベース](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)の「買い物かごベース」を参照してください。 |

## [!DNL Target Standard/Premium] 21.10.3（2021年10月19日（PT））

このメンテナンスリリースには、以下の機能強化、修正および変更が含まれています。

* [!DNL Target] アクティビティレポートで「[!UICONTROL Analytics で表示]」ボタンをクリックしても [!DNL Analysis Workspace] の [!UICONTROL A4T] パネルが開かない問題を修正しました。（TGT-42099、TGT-42100）
* [!UICONTROL フォームベースのエクスペリエンスコンポーザー]を使用して「[!UICONTROL A/B テスト]」および「[!UICONTROL エクスペリエンスのターゲット設定]（XT）」アクティビティを編集しているときに「[!UICONTROL デザインを編集]」ボタンが表示されない問題を修正しました。（TGT-41980）
* 新しい [!UICONTROL Recommendations] アクティビティの作成時に「[!UICONTROL 互換性]」チェックボックスが条件の選択に表示されない問題を修正しました。（TGT-42053）
* [!DNL Analytics] の権限がないので [!DNL Analytics] をレポートソース（A4T）として選択できない場合に表示される誤ったエラーメッセージを修正しました。（TGT-41954）
* アクセシビリティに関する複数の修正を実装して、[!DNL Target] UI 全体のキーボードナビゲーションを改善しました。

## [!DNL Target Standard/Premium] 21.10.2（2021年10月13日（PT））

[!DNL Target] [!UICONTROL オーディエンス]を [!DNL Adobe Experience Platform Web SDK] で使用する場合の次の機能拡張が追加されました。

* オーディエンスがソースで削除され [!DNL Target] アクティビティで使用できなくなったことを示す警告アイコン、ポップオーバーおよびメッセージが、[!DNL Target] UI の様々な場所に追加されました。

   次の図は、アイコン、ポップオーバーおよびメッセージの表示場所をいくつか示しています。

   * [!UICONTROL アクティビティ]リストページ

      ![ソースメッセージで削除されたオーディエンスの使用に関する警告が表示されているアクティビティリストページ](assets/deleted-at-source-audiences-list.png)

   * アクティビティ[!UICONTROL 概要]ページ：

      ![ソースメッセージで削除されたオーディエンスの使用に関する警告が表示されている概要ページ](assets/deleted-at-source-overview.png)

   * アクティビティ作成ワークフローの[!UICONTROL エクスペリエンス]ステップ：

      ![ソースメッセージで削除されたオーディエンスに関する警告の表示（[!UICONTROL エクスペリエンス]ページ）](assets/deleted-at-source-experiences.png)

   * アクティビティ作成ワークフローの[!UICONTROL ターゲティング]ステップ：

      ![ソースメッセージで削除されたオーディエンスに関する警告の表示（[!UICONTROL ターゲティング]ページ）](assets/deleted-at-source-targeting.png)

   * アクティビティ作成ワークフローの[!UICONTROL 目標と設定]ステップ：

      ![ソースメッセージで削除されたオーディエンスに関する警告の表示（[!UICONTROL 目標と設定]ページ）](assets/deleted-at-source-goals-settings.png)

   * オーディエンスの絞り込み（アクティビティ作成ワークフローの[!UICONTROL ターゲティング]ステップの「[!UICONTROL オーディエンスを置換]」）：

* オーディエンスの結合機能を使用しようとしたときに、一方のオーディエンスがソースで削除されていた場合は、「[!UICONTROL 保存]」が無効になります。

## [!DNL Target Standard/Premium] 21.10.1（2021年10月6日（PT））

このリリースには、次の新機能が含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL オーディエンス] UI の更新 | [!DNL Target] ユーザーのユーザーエクスペリエンスを向上させるための [!DNL Adobe Target] チームの継続的な取り組みの一環として、このリリースでは [!DNL Target] UI の[!UICONTROL オーディエンス]ページと[!UICONTROL プロファイルスクリプト]ページが更新されました。この更新では、以前は一貫性がなかったデザインパターンが統合および標準化されたほか、次のような新しい機能強化が追加されています。<ul><li>複数のオーディエンスを同時に選択および削除する機能</li><li>[オーディエンスビルダーのデザイン](/help/c-target/c-audiences/create-audience.md)の更新</li><li>[!UICONTROL オーディエンス]ライブラリルールビルダーでの除外ルールのサポート</li><li>新しい「オーディエンスソース」フィルターによるオーディエンス検出の迅速化</li><li>セッションの永続的な検索とフィルターオプション</li></ul>詳しくは、[オーディエンス](/help/c-target/target.md)を参照してください。<br>**メモ**：新しい [!UICONTROL Audiences] UI は一部のお客様のみご利用いただけます。このアップデートは、2022年1月からすべてのお客様に段階的に公開されます。  |
| [!UICONTROL プロファイルスクリプト] UI の更新 | また、[!UICONTROL プロファイルスクリプト]ライブラリも更新され、更新されたインターフェイスのほか、生産性向上のための更新が含まれています。<ul><li>複数のプロファイルスクリプトを同時に選択および削除する機能</li><li>プロファイルスクリプトの新しいコードエディター</li><li>コードエディター内での構文のハイライト表示とエラーチェック</li><li>キーボードショートカットを使用したトークン（mbox またはプロファイル）パラメーターのオートコンプリート</li></ul>詳しくは、[訪問者プロファイル](/help/c-target/c-visitor-profile/visitor-profile.md)を参照してください。<br>**メモ**：新しい[!UICONTROL プロファイルスクリプト] UI は一部のお客様のみご利用いただけます。このアップデートは、2022年1月からすべてのお客様に段階的に公開されます。  |
| ![プレミアムバッジ](/help/assets/premium.png) Recommendations 条件の作成と編集 | [!UICONTROL Recommendations 条件]の作成と編集のワークフローが効率化され、目標を達成するための適切なレコメンデーションアルゴリズムと設定の選択が容易になりました。<br>詳しくは、[条件の作成](/help/c-recommendations/c-algorithms/create-new-algorithm.md)を参照してください。 |
| ![プレミアムバッジ](/help/assets/premium.png) Recommendations のルックバックウィンドウとアルゴリズム更新頻度の改善 | 6 時間のルックバックウィンドウで「最も多く閲覧」アルゴリズムや「トップセラー」アルゴリズムを実行することで、直近のトレンドとなっているコンテンツをキャプチャできるようになりました。6 時間のルックバックウィンドウを選択すると、レコメンデーション結果は 1 日で 3〜6 時間ごとに更新されます。<br>詳しくは、*条件の作成*&#x200B;の[データソース](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source)を参照してください。 |

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
| Adobe Priority Product Update | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
