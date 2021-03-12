---
keywords: ターゲットドキュメントの変更ログ；ドキュメントの更新；新しいトピック；編集；更新；更新
description: Adobe Target製品ドキュメントへの重要な追加と変更により、最新の情報を入手できます。
title: ターゲットに関する表示ドキュメントの更新はどこで行えますか？
feature: リリースノート
translation-type: tm+mt
source-git-commit: 6a1f51cba34038abc3c73fa5cf88bfab183dfb28
workflow-type: tm+mt
source-wordcount: '3767'
ht-degree: 28%

---


# ドキュメントの変更点

このページでは、[!DNL Adobe Target]製品ドキュメントに対して行われた重要な変更をリストしています。

## Adobe Target標準/プレミアム21.2.1（2021年3月9日）

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 2021 年 3 月 13 日 | [自動配分と自動ターゲットアクティビティのA4Tのサポート](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md#tutorial) | 次の新しいチュートリアルを追加しました。<ul><li>自動ターゲットアクティビティ用にAnalysis WorkspaceでA4Tレポートを設定する方法</li></ul> |
| 3月9日 | [制限](/help/r-troubleshooting-target/target-limits.md#offer-size) | <ul><li>オファーの許容サイズ制限を更新しました。</li><li>categoryIdパラメーターの文字制限を修正しました。</li></ul> |
|  | [許可リストターゲットエッジノード](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | [!DNL Target]エッジIPアドレスを更新しました。 |
|  | [エンティティの属性](/help/c-recommendations/c-products/entity-attributes.md) | entity.valueが10進数形式である必要があることを示すテキストを追加しました（例：15,99ではなく15.99）。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：21.2.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target Standard/Premium 21.1.1（2021 年 1 月 19 日） 

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 2月22日 | [レポートの表示 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | 次のFAQを更新しました。<ul><li>Analysis Workspaceでセグメントを適用できる場所</li></ul> |
| 2月16日 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | プレリリースノートのオファー制限サイズのテキストを更新しました。 |
| 2月11日 | [Target の仕組み](/help/c-intro/how-target-works.md) | 「ボット」節を更新しました。 |
| 2月10日 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 2021年2月24日水曜日のAdobe TargetコミュニティQ&amp;Aコーヒーブレークに関する情報を追加しました。 |
| 2月8日 | [Target モバイルのプレビュー](/help/c-target-mobile-app/target-mobile-preview.md) | AdobeモバイルSDKのバージョン4のAndroidManifest.xmlファイルに追加する必要があるコードスニペットを追加しました。 |
|  | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | 次の既知の問題について明確にしました。<ul><li>APIを使用して作成されたコレクション、除外、条件、デザインは、ターゲットのユーザーインターフェイスに表示されず、APIを介してのみ編集できます。 同様に、ターゲットUIでこれらの項目のいずれかを作成し、後でAPIを使用して編集した場合、その変更はターゲットUIに反映されません。 APIを使用して編集した項目は、変更の損失を防ぐため、引き続きAPIを使用して編集する必要があります。</li></ul> |
| 2月1日 | [自動パーソナライゼーション概要レポート](/help/c-reports/reports-ap.md) | 次の節を追加しました。「よくある質問(FAQ)」 |
| 27 年 1 月 | [リダイレクトオファーの作成](/help/c-experiences/c-manage-content/offer-redirect.md) | トピックを更新しました。 |
|  | [リモートオファーを作成](/help/c-experiences/c-manage-content/about-remote-offers.md) | トピックを更新しました。 |
| 26 年 1 月 | [コンバージョン率](/help/c-reports/conversion-rate.md) | ターゲットがスチューデントのt検定で「平方和」を使用する方法を明確にしました。 |
| 22 年 1 月 | [コンバージョン率](/help/c-reports/conversion-rate.md#t-test) | 次の節を追加しました。「ターゲットがスチューデントのtテストを使うことを推奨する理由は何ですか？」 |
| 21 年 1 月 | [Analytics と Target の統合（A4T）のトラブルシューティング](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md) | 次の節を追加しました。&quot;A4Tアクティビティレポートに、多数の&quot;未指定&quot;イベントを含む行が含まれます。&quot; |
|  | [レポートの表示 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | 次の節を更新しました。「Analyticsレポートに「未指定」と表示されるのはなぜですか？ どういう意味だ？」 |
| 20 年 1 月 | [Adobe Experience PlatformウェブSDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) | 新規トピックです。 |
| 19 年 1 月 | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | ターゲット21.1.1リリース（2021年1月19日）に関する情報を追加しました。 |
|  | [制限](/help/r-troubleshooting-target/target-limits.md) | `productPurchasedID`パラメーターのテキストを更新しました。 |
|  | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | [!UICONTROL Recommendation]アクティビティをアクティブなプロモーションでコピーする際の既知の問題を追加しました。 重複アクティビティを変更すると元のアクティビティにも影響し、逆も同様です。 一時的な回避策が含まれます。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：21.1.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target Standard/Premium 20.10.1（2020 年 10 月 28 日） 

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 14 年 1 月 | [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.js バージョン 2.4.0 に関する情報を追加しました。 |
| 12 年 1 月 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | Target Standard/Premium 21.1.1リリース（2021年1月20日）に関するプレリリース情報を追加しました。 |
| 11 年 1 月 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 1月13日のAdobe TargetコミュニティQ&amp;Aコーヒーブレークに関する情報と登録情報を追加しました。 |
| 6 年 1 月 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 次のライブウェビナーの情報と登録情報を追加しました。<ul><li>大規模なパーソナライゼーションの成功：Forrester Wave、エクスペリエンス最適化プラットフォームの主な結果です。</li></ul> |
| 1 月 4 日 | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | ターゲットがmbox.jsをサポートしなくなる日付を2021年1月18日から2021年3月31日に変更しました。 |
| 18 年 12 月 | [A/Aテスト](/help/c-activities/t-test-ab/aa-testing.md) | 新規トピックです。 |
| 17 年 12 月 | [Adobe Target のレポートソースとしての Adobe Analytics（A4T）](/help/c-integrating-target-with-mac/a4t/a4t.md) | Java SDKがA4Tをサポートしていることを示す表を更新しました。 |
| 16 年 12 月 | [自動ターゲットのトラブルシューティングとFAQ](/help/c-activities/auto-target/auto-target-troubleshooting-faqs.md) | 次のFAQを追加しました。「自動ターゲットアクティビティから1つのエクスペリエンスを削除するとどうなりますか？」 |
| 9 年 12 月 | [オンデバイス判定](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md) | 新規トピックです。 |
|  | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | 次の問題を「既知の問題」セクションから「解決された問題」セクションに移動しました。&quot;画像オファーに&quot;処理中&quot;のラベルが表示されています。&quot; |
| 1 年 12 月 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | ウェビナーの録画を埋め込み、「遅延なしでパーソナライズおよびテストを行い、Adobe Targetのデバイス上での意思決定を行う」を行いました。 |
| 24 年 11 月 | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | 次の既知の問題を追加しました。<ul><li>[レポート — ダウンロード可能な.csvレポートのデータとターゲットUIに表示されるレポートのデータが一致しない。](/help/r-release-notes/known-issues-resolved-issues.md#csv)</li></ul>次の解決された問題を追加しました。<ul><li>[Analytics for Target（A4T）レポート](/help/r-release-notes/known-issues-resolved-issues.md#section_FD2FC86E7C734D60B1EDC9DEF60E1014)</li></ul> |
|  | [指標の定義 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md) | 次のFAQを追加しました。「目標指標を設定する際に、詳細設定オプションにアクセスできないのはなぜですか？」 |
|  | [成功指標](/help/c-activities/r-success-metrics/success-metrics.md) | A4Tを使用するアクティビティに関する注意のテキストを調整しました。 |
| 17 年 11 月 | [アクティビティの設定 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md) | 次のFAQを追加しました。「訪問者は、A4Tを使用する自動ターゲットアクティビティで、様々な訪問でターゲット設定されたエクスペリエンスと制御されたエクスペリエンスを切り替えることができますか？」 |
|  | [自動ターゲットのトラブルシューティングとFAQ](/help/c-activities/auto-target/auto-target-troubleshooting-faqs.md) | 次のFAQを追加しました。「モデルが構築されるまで、90(Control)/10(Targeted)の分割で自動ターゲットを使用することをお勧めしますか？」 |
|  | [レポートの表示 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | 次のFAQを追加しました。&quot;Analyticsでは訪問はどのようにカウントされ、A4Tを使用する自動ターゲットアクティビティではコンバージョンクレジットが割り当てられますか？&quot; |
| 13 年 11 月 | [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.js 2.3.3 に関する情報を追加しました。 |
| 10 年 11 月 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 11月11日に予定されているAdobe TargetコミュニティQ&amp;Aコーヒーブレークに関する情報を追加しました。 |
| 3 年 11 月 | [Analytics と Target の統合（A4T）のトラブルシューティング](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md) | 次のトラブルシューティングトピックを更新しました。「必要なレポートスイートが表示されません。」 |
| 10月28日 | [サーバー側：Target の実装](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) | 初回訪問者は、クライアント側でのみ初期化でき、サーバー側では初期化できないことに注意を追加しました。 |
| 10月27日 | [サーバー側：Target の実装](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) | 新しい&#x200B;*[Adobe TargetSDK](https://adobetarget-sdks.gitbook.io/docs/)*&#x200B;ポータルへのリンクを追加しました。 |
|  | [Analyticsをレポートソースとして使用するアクティビティの作成](/help/c-integrating-target-with-mac/a4t/campaign-creation.md) | `analyticsLogging = client_side`を使用する場合、Analyticsを自動ターゲットアクティビティでレポートソース(A4T)として使用する場合は、`sessionId`値を[!DNL Analytics]に渡す必要があるという情報を追加しました。 |
|  | [Analytics for Target の実装](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) | `analyticsLogging = client_side`を使用して[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット]のアクティビティに対してもsessionIdを転送する必要があるという情報を追加しました。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：20.10.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target Standard／Premium 20.9.1（2020 年 10 月 1 日）

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 10月26日 | [Target のセキュリティの概要](/help/c-implementing-target/c-considerations-before-you-implement-target/target-security-overview.md) | *Adobe Targetセキュリティの概要*&#x200B;ホワイトペーパーを更新しました。 |
| 10月22日 | [CNAME と Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | at.jsバージョン1.8.2および2.3.1でのCNAMEサポートの修正に関する情報を追加しました。 |
|  | [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | at.jsバージョン1.8.2および2.3.1でのCNAMEサポートの修正に関する情報を追加しました。 |
| 10月15日 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | Target Standard/Premium 20.10.1リリース（2020年10月27日）のプレリリースノートを更新しました。 |
| 10月14日 | [自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 2つのエクスペリエンスのみを持つ自動配分アクティビティのトラフィック配分に関するメモを追加しました。 |
| 10月13日 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 2020年11月10日に予定されている次のライブウェビナーに関する情報を追加しました。<ul><li>Adobe Targetのデバイス上での意思決定により、遅延が発生しないパーソナライズとテストを実現</li></ul> |
|  | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | 2020年11月10日に予定されている次のライブウェビナーに関する情報を追加しました。<ul><li>Adobe Targetのデバイス上での意思決定により、遅延が発生しないパーソナライズとテストを実現</li></ul> |
| 10月12日 | [コンテンツ配信のトラブルシューティング](/help/c-activities/c-troubleshooting-activities/content-trouble.md) | [デバッグツール](/help/c-activities/c-troubleshooting-activities/content-trouble.md#section_BED130298E794D1FA229DB7C3358BA54)で使用する認証トークンを取得して、認証トークンを生成するために必要な権限レベルを示すように更新しました。 |
|  | [プロファイル API 設定](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/profile-api-settings.md) | 認証トークンを生成する必要がある権限レベルを示すトピックを更新しました。 |
|  | [自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md) | 自動ターゲットを使用した実際の成功事例を追加しました。 |
|  | [類似のページに同じエクスペリエンスを組み込む](/help/c-experiences/c-visual-experience-composer/temtest.md) | ドメイン全体で同じアクティビティをレンダリングする方法を説明する節を追加しました。 |
|  | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | 次の既知の問題を追加しました。<ul><li>自動配分と自動ターゲットアクティビティ用のターゲット用のAnalytics(A4T)指標</li></ul> |
| 10月8日 | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) | 次の解決された問題を追加しました。<ul><li>[自動ターゲットレポート](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics)</li></ul>次の問題を「既知の問題」セクションから「解決された問題」セクションに移動しました。<ul><li>[レポート](/help/r-release-notes/known-issues-resolved-issues.md#conversions-audiences)</li></ul> |
|  | [ハイブリッド実装](/help/c-implementing-target/hybrid-implementation.md) | 新規トピックです。 |
| 10月7日 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | Target Standard/Premium 20.10.1リリースに関する情報を追加しました。 |
| 10月1日 | [成功のために必要なトラフィックの見積もり](/help/c-activities/t-automated-personalization/ap-traffic-estimator.md) | FAQ節を追加しました。 |
| 9月30日 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 以下のライブウェビナーに関する情報を追加しました。<ul><li>Adobe Targetと分析により、パーソナライゼーションを微調整</li></ul> |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：20.9.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target標準/プレミアム20.8.1（2020年9月2日）

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 9月29日 | [Analytics と Target の統合（A4T）のトラブルシューティング](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md#section_75002584FA63456D8D9086172925DD8D) | at.js 1.xおよびat.js 2.xで追加のIDを検査する方法に関する情報を追加しました。 |
| 9月24日 | [アクティビティ QA ブックマークレット](/help/c-activities/c-activity-qa/activity-qa-bookmark.md) | at.js 2のアクティビティQAブックマークレットのコードを更新しました。*x*. |
|  | [カタログ検索](/help/c-recommendations/c-products/catalog-search.md#faq) | 数値を持つカスタム属性の検索に関する注意を追加しました。 |
|  | [Recommendations FAQ](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | 次のFAQを追加しました。&quot;数値を持つカスタム属性で検索すると、カタログ検索で正しい結果が表示されないのはなぜですか？&quot; |
|  | [Target の仕組み](/help/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934) | 「エッジネットワーク」に表示されているターゲットクラスタとターゲット中央クラスタの場所を更新しました。 |
| 9月23日 | [Analytics トラッキングサーバーの使用](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md) | [!DNL Adobe Experience Platform Debugger]とブラウザーのデベロッパーツールの情報でトピック全体が更新されました。 |
|  | [プロファイルと変数の用語集](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | 「user.header(&#39;x-forwarded-for&#39;)」行が更新され、「user.header(&#39;x-cluster-client-ip&#39;)」が廃止されたことが示されました。 |
|  | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | Target Standard/Premium 20.9.1（2020年9月31日）リリースに関する情報を追加しました。 |
| 9月15日 | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | Target Standard/Premium 20.8.3リリースに関する情報が追加されました。このリリースには、Analytics for Target(A4T)での自動ターゲットアクティビティのサポートが含まれます。 以前のリリースでは、自動割り当てアクティビティのサポートが追加されました。 |
|  | [A4Tでの自動割り当ておよび自動ターゲットアクティビティのサポート](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md) | 自動ターゲットアクティビティでのA4Tのサポートに関する情報を追加しました。 |
|  | [アクティビティ QA ブックマークレット](/help/c-activities/c-activity-qa/activity-qa-bookmark.md) | 空の値を持つ`at_preview_token`パラメーターを使用してサイトにページを読み込むことで、手動でQAモードを強制終了する方法がat.js 1に適用されることを示すテキストが更新されました。*x* のみで使用できます。 |
|  | [カタログ検索](/help/c-recommendations/c-products/catalog-search.md) | トピック全体を更新しました。 |
| 9月10日 | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | 次の新機能を含む、Target Standard/Premium 20.9.2リリースに関する情報を追加しました。条件シーケンス内の推奨スロットを制御します。 |
|  | [条件のシーケンスの作成](/help/c-recommendations/c-algorithms/create-criteria-sequence.md) | 「返されるアイテムの数を制限する」機能に関する情報を追加しました。 |
| 9月9日 | [アクティビティ QA ブックマークレット](/help/c-activities/c-activity-qa/activity-qa-bookmark.md) | at.js 2で使用するJavaScriptコードが追加されました。*x*. |
| 9月3日 | [Visual Experience Composer ヘルパー拡張機能](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) | Cookieの名前とドメインに関する情報を含む、「VEC Helperブラウザー拡張機能の取得とインストール」セクションを更新しました。 |
|  | [Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md) | 「最近発表されたGoogle Chrome SameSite Cookieの実施ポリシーがVECおよびEECに与える影響について教えてください」 を参照してください。 |
| 9月2日 | [リリースノート](/help/r-release-notes/release-notes.md)：20.8.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target Standard/Premium 20.7.1（2020 年 7 月 27 日） 

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 8月31日 | [RecommendationsでAdobe Analyticsを使用](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md) | FAQセクションを追加 |
| 8月28日 | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | 次の内容を更新しました。<ul><li>「既知の問題」セクションに追加されました。「レポート作成 — 現在、変換は、使用する対象ユーザーに応じて異なる増分で行われます。」</li><li>「解決された問題」セクションに追加：&quot;Google Chromeバージョン80以降を使用している場合、Visual Experience Composer(VEC)またはEnhanced Experience Composer(EEC)でページが読み込まれない。&quot;</li></ul> |
|  | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | mbox.jsの廃止日は、2020年8月30日から2021年1月18日に変更されました。 現在は2020年3月31日に変更されています。 |
| 8月26日 | [ターゲットRecommendationsでAdobe Analyticsを使用](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md) | 新規トピックです。 |
| 8月24日 | [成功指標](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) | 「詳細設定」セクションを更新 |
| 8月21日 | [Adobe Targetウェルカムキットの概要](/help/c-intro/target-welcome-kit.md) | 新しい記事とサブトピックです。 |
| 8月20日 | [Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md) | 次の節を追加しました。「最近発表されたGoogle Chrome SameSite Cookieの適用ポリシーは、VECとEECにどのように影響しますか？」 |
|  | [クリックの追跡](/help/c-activities/r-success-metrics/click-tracking.md) | 次のテキストを更新しました。「複数のエレメントを選択した場合、参加者が選択したエレメントの1つをクリックすると、クリックがカウントされます。 各項目を個別にカウントする場合、要素ごとに個別の成功指標を設定します。1つのページ上の複数のエレメントをクリックして1つのアイテムをカウントするには、複数のエレメントに一致するようにCSSエレメントセレクターを編集します。」 |
|  | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | Target Standard/Premium 20.9.1（2020年9月2日）リリースに関する情報を追加しました。 |
| 8月14日 | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | RecommendationsでのQAに関する既知の問題を追加。 |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | `serverState`を使用し、返されるコンテンツで`<script>`タグを使用する場合、HTMLコンテンツで`</script>`ではなく`<\/script>`を使用することを示すテキストを追加しました。 |
| 8月12日 | [ターゲットUIの理解](/help/c-intro/understand-the-target-ui.md) | 新規トピックです。 |
|  | [Adobe TargetAPIの概要](/help/api/api-overview.md) | 新規トピックです。 |
| 8月10日 | [CNAME と Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | CNAMEを使用するとCookieヘッダーのサイズが大きくなることを示すテキストが追加されました。 |
|  | [ターゲットとAdobe Audience Managerの統合](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) | 新規トピックです。 |
|  | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 次のアーカイブされたウェビナーを表示するリンクを追加しました。「HSBCは、Adobe TargetとAIを活用して、パーソナライズを迅速に最適化し、スケールで提供する方法」 |
| 8月6日 | [自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md#how-long) | 次のFAQの更新されたテキスト：「モデルが作られるのをどれくらい待てばいい？」 |
|  | [分類 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-classifications.md) | ターゲットタイプのテキストを更新しました。 |
| 8月5日 | [Target の Cookie の削除](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cookie-deleting.md) | トピック全体を更新しました。 |
| 8月4日 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 8月13日に予定されている「人工知能とAdobe Targetを使用したパーソナライゼーション戦略」ウェビナーに関する登録情報を追加しました。 |
|  | [ブラウザーで混合コンテンツを有効にする](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/mixed-content.md) | トピックを更新しました。 |
| 8月3日 | [成功指標](/help/c-activities/r-success-metrics/success-metrics.md) | 訪問者と訪問者に関して、「[!UICONTROL カウントを増やす]」オプションが意味することに関する注意を追加しました。 |
| 31 年 7 月 | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | 新しい既知の問題を追加しました。&quot;Image Offers showing &quot;Processing&quot; label.&quot; |
|  | [adobe.target.getOffers(options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | `getoffers()`を使用してpageLoadを実行するコードサンプルを追加しました。 |
|  | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 8月5日のAdobe Targetコミュニティコーヒーブレークに関する登録情報を追加。 |
| 28 年 7 月 | [Personalization Insightsレポート](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md),<br>[](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)Automated Segmentsレポート<br>, [および重要属性レポート](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) | トピックの上部にあるノートのテキストを更新しました。 |
|  | [自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 次の FAQ を追加しました。<ul><li>自動割り当てアクティビティの実行中に「レポート・データのリセット」オプションを使用できますか。</li><li>環境に関して、構築モデルの自動割り当てはどのように行われますか。</li></ul> |
|  | [自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md) | 以下の FAQ を追加しました。<ul><li>自動ターゲット・アクティビティの実行中に「レポート・データのリセット」オプションを使用できますか。</li></ul>「考慮事項」セクションのテキストを更新しました。 |
|  | [Automated Personalizationに関するFAQ](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | 次の FAQ を追加しました。<ul><li>Automated Personalizationアクティビティの実行中に「レポートデータをリセット」オプションを使用できますか？</li><li>Automated Personalizationは環境に関するモデルをどのように構築しているのか。</li></ul> |
|  | [サポートされているブラウザー](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md) | Internet Explorerと不明な要素に関する情報を追加しました。 |
|  | [顧客属性](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | 次の段落を更新しました。<br>[!DNL Adobe]は、CRMデータベースの顧客属性(訪問者プロファイル)データの100%が[!DNL Experience Cloud]にオンボードされ、[!DNL Target]でのターゲット設定に使用できるとは保証しません。 現在の設計では、少量のデータ（大量の生産バッチの0.1%まで）が重複しない可能性があります。 |
| 27 年 7 月 | [Target の管理](/help/administrating-target/administrating-target.md) | [!UICONTROL 管理]ページの新しいUIの変更を反映して、このページのリンクされたすべてのトピックのテキストを更新しました。 |
|  | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 以下の変更を加えました。 <ul><li>次のウェビナーの登録情報を追加しました。「HSBCは、Adobe TargetとAIを活用して、パーソナライズを迅速に最適化し、スケールで提供する方法」</li><li>Gartner Magic Quadrant for Personalization EnginesのリーダーになったAdobeに関する情報を追加しました。</li></ul> |
|  | [フォームベースの Experience Composer](/help/c-experiences/form-experience-composer.md) | 手順4で情報を明確にしました。場所を選択します。 |
| 24 年 7 月 | <br>[at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.js 2.3.2 に関する情報を追加しました。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：20.7.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target Standard/Premium 20.5.1（2020 年 6 月 17 日） 

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 17 年 7 月 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 7月22日のAdobe Target・コーヒー・ブレークに関する情報を追加した。 |
| 15 年 7 月 | [自動割り当てにより、手動テストよりもテスト結果が速く、収益が高くなる](/help/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md) | 新規トピックです。 |
| 14 年 7 月 | [自動割り当て](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、<br>[自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md)、<br><br>[自動パーソナライゼーションに関するFAQ](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | アクティビティの途中で目標基準を変更しないよう推奨するFAQを追加しました。 |
| 7 年 7 月 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 7月8日のAdobe Target・コーヒー・ブレークに関する情報を追加。 |
| 6月25日 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | Target Standard/Premium 20.6.1リリース（2020年7月）に関する情報を追加しました。 |
|  | [ターゲットドキュメントの概要](/help/r-release-notes/target-documentation.md) | [!DNL Target]ドキュメントの様々なソースを詳しく説明する新しいトピック。 |
| 6月23日 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 6月24日のAdobe Target・コーヒー・ブレークに関する情報を追加。 |
|  | [プロファイル属性](/help/c-target/c-visitor-profile/profile-parameters.md) | あるプロファイルスクリプトの結果を別のプロファイルスクリプトで使用する依存プロファイルスクリプトの作成はお勧めしません。 |
|  | [at.js の仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) | 次のビデオが追加されました。営業時間：at.jsのヒントと概要 |
| 6月17日 | [CNAME と Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | トピックを更新しました。 |
|  | [レスポンストークン](/help/administrating-target/response-tokens.md) | [!UICONTROL 自動ターゲット]および[!UICONTROL Automated Personalization]アクティビティのトラフィック割り当て方法の応答トークンに関する情報を追加しました。 |
|  | [アクティビティの作成](/help/c-integrating-target-with-mac/a4t/campaign-creation.md) | 自動割り当てアクティビティに対するAnalytics for Target(A4T)のサポートに関する情報を追加しました。 |
|  | [ユーザー](/help/administrating-target/c-user-management/c-user-management/user-management.md) | *役割と権限の指定*&#x200B;の下に、新しい[!UICONTROL 発行者]役割に関する情報を追加しました。 |
|  | [Enterprise 権限の設定](/help/administrating-target/c-user-management/property-channel/properties-overview.md) | *手順6で、新しい[!UICONTROL パブリッシャ]の役割に関する情報を追加しました。役割と権限を指定します*。 |
|  | [Enterprise ユーザーの権限](/help/administrating-target/c-user-management/property-channel/property-channel.md) | *営業時間へのリンクを追加しました：プレミアムワークスペースセッション*&#x200B;をターゲットにします。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：20.5.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target Standard/Premium 20.4.1（2020 年 5 月 6 日）

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 6月15日 | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | at.js 1.8.2およびat.js 2.3.1リリースに関する情報を追加しました。 |
|  | [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.js 1.8.2およびat.js 2.3.1リリースに関する情報を追加しました。 |
|  | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 20.5.1リリース（2020年6月17日）のメモを更新し、[!DNL Analysis Workspace]でのA4Tのサポートに関する情報を含めました。 |
| 6月12日 | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | `deviceIdLifetime` 設定に関する情報を追加しました。 |
|  | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | at.js 1.8.2およびat.js 2.3.1リリースに関する情報を追加しました。 |
| 6月8日 | [モバイルアプリのターゲットに関するFAQ](/help/c-target-mobile-app/target-for-mobile-apps-faq.md) | 次のFAQの更新されたテキスト：「Target Mobileは、Adobe Targetプレミアム製品SKUのみの機能ですか？」 |
|  | [レポートの表示 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | トピック全体を更新しました。 |
| 6月5日 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 6月10日のAdobe Target・コーヒー・ブレークに関する情報を追加。 |
|  | [上昇率と信頼性 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md) | 次のFAQの更新されたテキスト：「計算指標に上昇率と信頼感が表示されないのはなぜですか？」 |
| 6月4日 | [A4T レポート](/help/c-integrating-target-with-mac/a4t/reporting.md) | 「Analyticsのレポート」セクションを更新 |
| 6月1日 | [対象のお知らせ](/help/r-release-notes/target-announcements.md) | 次のターゲットイベントを発表する新しいページを追加しました。 |
|  | [レスポンシブエクスペリエンスのためのモバイルビューポート](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) | Apple iPhone 11、Apple iPhone SEおよびGoogle Pixel 2 XLモデルのビューポートサイズと解像度を更新 |
| 28 年 5 月 | [レポートの FAQ](/help/c-reports/reporting-frequently-asked-questions.md) | 以下の新しい FAQ を追加しました。 <ul><li>新規訪問者数と再訪問者数の指標はどのようにカウントされますか。</li></ul> |
| 27 年 5 月 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | 自動割り当てアクティビティに対するAnalytics for Target(A4T)のサポートに関する情報を追加しました。 |
| 26 年 5 月 | [プロファイル属性](/help/c-target/c-visitor-profile/profile-parameters.md) | 次の情報を追加しました。&quot;パラメーターは、スクリプトを無効にした後もプロファイルに残ります。 プロファイルに既にアクティビティのオーディエンスで使用されるパラメーターが含まれているユーザーは、そのアクティビティの対象となります。」 |
| 21 年 5 月 | [ターゲットエッジノードの許可](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | `mboxedge30.tt.omtrdc.net`がリストに追加されました。 |
| 20 年 5 月 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | Target Standard/Premium 20.6.1（2020年6月10日）リリースに関する情報を追加しました。 |
|  | [ホスト](/help/administrating-target/hosts.md) | 「セキュリティのベストプラクティス」セクションに注意を追加 |
| 14 年 5 月 | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | プロファイルバッチステータスAPI v2の変更点に関する情報を追加しました。 |
| 13 年 5 月 | [CNAME と Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | 「既知の制限事項」セクションを追加 |
| 11 年 5 月 | [ホスト](/help/administrating-target/hosts.md) | リダイレクトおよび許可リストでのubox機能の使用に関する情報を追加しました。 |
|  | [リダイレクターの使用](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) | オープンリダイレクトの脆弱性を回避するためのホストの使用に関する情報を追加しました。 |
|  | [Recommendations と電子メールの統合](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | オープンリダイレクトの脆弱性を回避するためのホストの使用に関する情報を追加しました。 |
|  | [電子メール：Target の実装](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md) | オープンリダイレクトの脆弱性を回避するためのホストの使用に関する情報を追加しました。 |
|  | [アクティビティ QA](/help/c-activities/c-activity-qa/activity-qa.md) | 「考慮事項」セクションを更新 |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 「設定」の下の「overrideMboxEdgeServer」行が更新されました。 |
| 6 年 5 月 | [Apple Intelligent Tracking Prevention（ITP）2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | ITP 2.3に関する情報を追加 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：20.4.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target Standard/Premium 20.2.1（2020 年 2 月 20 日） 

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 4 年 5 月 | [レポートの FAQ](/help/c-reports/reporting-frequently-asked-questions.md#uneven) | 新しいFAQを追加：「A/BまたはMVTアクティビティで、エクスペリエンス間でトラフィックが分割されるのはなぜですか？」 |
| 29 年 4 月 | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | 極端な注文で報告する既知の問題を追加。 |
| 28 年 4 月 | [プロファイルと変数の用語集](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | `user.header('x-forwarded-for')`を新しいAWSエッジと共に使用してユーザーのIPアドレスを取得する方法に関する情報を削除しました。 このコマンドは、新しいAWSエッジで動作するようになりました。 |
|  | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | Target Standard/Premiumリリース(20.4.1)の日付を5月6日に変更しました。 |
| 23 年 4 月 | [CNAME と Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | トピックを更新しました。 |
| 22 年 4 月 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | 新しいセクションを追加：*プロファイルバッチステータスAPI v2の変更（2020年5月4日）。* |
| 14 年 4 月 | [ターゲットエッジホストの許可](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | 新規トピックです。 |
| 10 年 4 月 | [シングルページアプリケーションの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md#bp) | 新しいセクションを追加：「実装のベストプラクティス」 |
| 7 年 4 月 | [上昇率と信頼性 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md#lift-condidence) | 「計算指標の上昇率と信頼性を表示できないのはなぜですか？」のテキストを更新しました。 |
| 2 年 4 月 | [プロファイルと変数の用語集](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | `user.header('x-forwarded-for')`を新しいAWSエッジと共に使用してユーザーのIPアドレスを取得する方法に関する情報を追加しました。 |
|  | [at.js 1.*x* から at.js 2.*x へのアップグレード*](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | 以下の注意を追加しました。<ul><li>ECID ライブラリ v4.3.0 以降および at.js 2.*x* をインストールしたら、一意のドメインにまたがるアクティビティを作成してユーザーを追跡できます。この機能は、セッションの有効期限が切れた後にのみ機能することに注意してください。</li></ul> |
| 3月30日 | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md#atjs) | at.js 2.2.0より前のバージョンのat.jsに影響する既知の問題が追加されました。この問題により、Adobe Analyticsコードがページエレメントに存在しない場合に、Analytics for Target(A4T)でクリックトラッキングで変換がレポートされなくなりました。 |
|  | [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.jsバージョン2.2.0の詳細に次の情報を追加しました。<ul><li>Adobe Analyticsコードがページエレメントに存在しない場合に、Analytics for Target(A4T)でクリックトラッキングで変換がレポートされない問題を修正しました。</li></ul> |
| 3月25日 | [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.jsの次の新しいバージョンに関する情報を追加しました。<ul><li>at.jsバージョン2.3.0</li><li>at.jsバージョン1.8.1</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 「設定」セクションに次の新しい行が追加されました。<ul><li>cspScriptNonce</li><li>cspStyleNonce</li></ul>以下の新しいセクションを追加しました。<ul><li>コンテンツセキュリティポリシー</li></ul> |
| 3月25日 | [Apple Intelligent Tracking Prevention（ITP）2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md#impact) | 次の影響に関する情報を追加しました。<ul><li>サードパーティIDに基づくプロファイルスクリプト</li><li>iOSデバイスでのQA/プレビューURL</li></ul> |
| 3月20日 | [ リリースノート（現行）](/help/r-release-notes/release-notes.md) | Target Standard/Premium 20.2.1リリースは2020年3月23日になる予定です。 |
| 3月13日 | [制限](/help/r-troubleshooting-target/target-limits.md) | 「配信先、アカウントごとに再利用可能」の数を更新しました。 |
| 3月12日 | [リリースノート（最新）](/help/r-release-notes/release-notes.md#summit) | オンラインのデジタル・サミット会議に無料でアクセスできるように登録情報を追加 |
| 3月9日 | [プライバシー](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | 「IPアドレスの最後のオクテットの置き換え」の節に詳細を追加しました。 |
|  | [複数値の属性の操作](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md) | *JavaScript*&#x200B;で複数値パラメーターを渡すので、更新されたコード例を参照してください。 |
|  | [カスタムエンティティの属性](/help/c-recommendations/c-products/custom-entity-attributes.md) | **&#x200B;複数値の属性の実装&#x200B;*の下にあるAPIの使用*&#x200B;に、コード例を追加しました。 |
| 3月4日 | [プロファイル属性](/help/c-target/c-visitor-profile/profile-parameters.md) | トピック全体が更新され、「ベストプラクティス」セクションが大幅に修正されました。 |
| 2月21日 | [ リリースノート（現行）](/help/r-release-notes/release-notes.md) | 新しいAdobe Experience Cloudのナビゲーションに関する情報を追加しました。 |
| 2月20日 | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | `enabled`設定の説明を更新しました。 次の設定に関する情報を追加しました。`pageLoadEnabled`と`viewsEnabled`。 |
|  | [地域](/help/c-target/c-audiences/c-target-rules/geo.md) | `mboxOverride.browserIp`はat.js 1でサポートされていることに注意してください。*x* のみで使用できます。 |
|  | [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | ターゲットチームがサポートするat.jsのバージョンを説明するテキストを明確にしました。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：20.2.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target Standard/Premium 20.1.1（2020 年 2 月 4 日） 

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 2月4日 | [リリースノート](/help/r-release-notes/release-notes.md)：20.1.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |
