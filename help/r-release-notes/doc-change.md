---
keywords: target documentation change log;documentation updates;new topics;edits;updates;update
description: このページでは、リリース順に並べられた、Adobe Targetのドキュメントに対する重要な変更をリストしています。
title: Adobe Target 製品ドキュメントの変更
topic: Standard
uuid: 6fba75e2-0a93-488d-9010-fffa423600c0
translation-type: tm+mt
source-git-commit: 4287c93058e279da6de262a19fbabb4bbacdf7ad
workflow-type: tm+mt
source-wordcount: '1856'
ht-degree: 29%

---


# ドキュメントの変更点{#documentation-changes}

This page lists important changes made to the [!DNL Adobe Target] product documentation.

## Adobe Target Standard/Premium 20.7.1（2020 年 7 月 27 日） 

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 8月12日 | [ターゲットのUIについて](/help/c-intro/understand-the-target-ui.md) | 新規トピックです。 |
|  | [Adobe TargetAPIの概要](/help/api/api-overview.md) | 新規トピックです。 |
| 8月10日 | [CNAME と Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | CNAMEを使用する場合にcookieヘッダーのサイズが増えることを示すテキストを追加しました。 |
|  | [ターゲットとAdobe Audience Managerの統合](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) | 新規トピックです。 |
|  | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 以下のアーカイブされたウェビナーの表示へのリンクを追加しました。「HSBCは、Adobe TargetとAIを活用して、パーソナライゼーションを迅速にスケールで最適化および提供する方法」 |
| 8月6日 | [自動ターゲット](/help/c-activities/auto-target-to-optimize.md#how-long) | 次のFAQのテキストを更新しました。「モデルが作成されるまで、どのくらい待つ必要がありますか？」 |
|  | [分類 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-classifications.md) | targettypeのテキストを更新しました。 |
| 8月5日 | [Target の Cookie の削除](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cookie-deleting.md) | トピック全体を更新しました。 |
| 8月4日 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 8月13日に予定されている「人工知能とAdobe Targetを使用したパーソナライゼーション戦略」ウェビナーに関する登録情報を追加しました。 |
|  | [ブラウザーで混合コンテンツを有効にする](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/mixed-content.md) | トピックを更新しました。 |
| 8月3日 | [成功指標](/help/c-activities/r-success-metrics/success-metrics.md) | 訪問者数と訪問数に関する「 [!UICONTROL カウントを] 増分」オプションの意味を明確にする注記を追加しました。 |
| 31 年 7 月 | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | 新しい既知の問題を追加しました。&quot;画像オファーに&quot;処理中&quot;のラベルが表示されています。&quot; |
|  | [adobe.target.getOffers(options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | pageLoadの実行に使用するコードサンプル `getoffers()` を追加しました。 |
|  | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 8月5日に予定されているAdobe Targetコミュニティのコーヒーブレークに関する登録情報を追加しました。 |
| 28 年 7 月 | [パーソナライゼーションインサイトレポート](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md),<br>[自動セグメントレポート](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md),<br>および [重要な属性レポート](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) | トピックの先頭にある注記のテキストを更新しました。 |
|  | [自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 次の FAQ を追加しました。<ul><li>自動配分アクティビティの実行中に「レポートデータをリセット」オプションを使用できますか。</li><li>自動配分は、環境に関するモデルをどのように構築しますか？</li></ul> |
|  | [自動ターゲット](/help/c-activities/auto-target-to-optimize.md) | 以下の FAQ を追加しました。<ul><li>自動ターゲットアクティビティの実行中に「レポートデータをリセット」オプションを使用できますか。</li></ul>「考慮事項」の節のテキストを更新しました。 |
|  | [Automated PersonalizationFAQ](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | 次の FAQ を追加しました。<ul><li>Automated Personalizationアクティビティの実行中に「レポートデータをリセット」オプションを使用できますか。</li><li>Automated Personalizationは環境に関するモデルをどのようにして作り上げているか。</li></ul> |
|  | [サポートされているブラウザー](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md) | Internet Explorerおよび不明な要素に関する情報を追加しました。 |
|  | [顧客属性](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | Updated following paragraph:<br>[!DNL Adobe] does not guarantee that 100% of customer attribute (visitor profile) data from CRM databases will be onboarded to the [!DNL Experience Cloud] and, thus, be available for use for targeting in [!DNL Target]. 現在の設計では、小さな割合のデータ（大規模な生産バッチの0.1 %まで）はオンボードされない可能性があります。 |
| 27 年 7 月 | [Target の管理](/help/administrating-target/administrating-target.md) | このページのすべてのリンクされたトピックのテキストを更新し、 [!UICONTROL 管理] ページの新しいUIの変更を反映しました。 |
|  | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 以下の変更を加えました。 <ul><li>次のウェビナーの登録情報を追加しました。「HSBCは、Adobe TargetとAIを活用して、パーソナライゼーションを迅速にスケールで最適化および提供する方法」</li><li>パーソナライゼーションエンジンに関するGartner Magic Quadrantで、Adobeがリーダーに再び選出されたことに関する情報を追加しました。</li></ul> |
|  | [フォームベースの Experience Composer](/help/c-experiences/form-experience-composer.md) | 手順4の情報を明確にしました。場所を選択します。 |
| 24 年 7 月 | <br>[at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.js 2.3.2 に関する情報を追加しました。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：20.7.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target Standard/Premium 20.5.1（2020 年 6 月 17 日） 

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 17 年 7 月 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 7月22日のAdobe Target・コーヒーブレークに関する情報を追加。 |
| 15 年 7 月 | [自動配分は、手動テストよりも速いテスト結果と高い売上高を提供します](/help/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md) | 新規トピックです。 |
| 14 年 7 月 | [自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md),<br>[自動ターゲット](/help/c-activities/auto-target-to-optimize.md),<br><br>[および自動パーソナライゼーションFAQ](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | アクティビティの途中で目標指標を変更しないことをお勧めするFAQを追加しました。 |
| 7 年 7 月 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 7月8日のAdobe Target・コーヒーブレークに関する情報を追加。 |
| 6月25日 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | Target Standard/Premium 20.6.1リリース（2020年7月）に関する情報を追加しました。 |
|  | [ターゲットドキュメントの概要](/help/r-release-notes/target-documentation.md) | ドキュメントの様々なソースについて詳しく説明する新しいト [!DNL Target] ピックです。 |
| 6月23日 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 6月24日のAdobe Target・コーヒー・ブレークに関する情報を追加。 |
|  | [プロファイル属性](/help/c-target/c-visitor-profile/profile-parameters.md) | あるプロファイルスクリプトの結果を別のプロファイルスクリプトで使用する依存プロファイルスクリプトを作成することはお勧めしません。 |
|  | [at.js の仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) | 次のビデオを追加しました。勤務時間：at.jsのヒントと概要 |
| 6月17日 | [CNAME と Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | トピックを更新しました。 |
|  | [レスポンストークン](/help/administrating-target/response-tokens.md) | [!UICONTROL 自動ターゲットおよび] Automated Personalization  アクティビティのトラフィック配分方法の応答トークンに関する情報を追加しました。 |
|  | [アクティビティの作成](/help/c-integrating-target-with-mac/a4t/campaign-creation.md) | 自動配分アクティビティのターゲット用のAnalytics(A4T)のサポートに関する情報を追加しました。 |
|  | [ユーザー](/help/administrating-target/c-user-management/c-user-management/user-management.md) | 「ロールと権限の [!UICONTROL 指定] 」に、新しい *投稿者*&#x200B;ロールに関する情報を追加しました。 |
|  | [Enterprise 権限の設定](/help/administrating-target/c-user-management/property-channel/properties-overview.md) | [!UICONTROL 手順6で、新しい] 投稿者 *役割に関する情報を追加しました。役割と権限を指定します*。 |
|  | [Enterprise ユーザーの権限](/help/administrating-target/c-user-management/property-channel/property-channel.md) | 次の *Office時間へのリンクを追加しました。ターゲットプレミアムワークスペースセッション*。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：20.5.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target Standard/Premium 20.4.1（2020 年 5 月 6 日）

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 6月15日 | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | at.js 1.8.2およびat.js 2.3.1リリースに関する情報を追加しました。 |
|  | [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.js 1.8.2およびat.js 2.3.1リリースに関する情報を追加しました。 |
|  | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | 20.5.1リリース（2020年6月17日）のノートを更新し、 [!DNL Target Standard/Premium] でのA4Tのサポートに関する情報を含め [!DNL Analysis Workspace]ました。 |
| 6月12日 | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | `deviceIdLifetime` 設定に関する情報を追加しました。 |
|  | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | at.js 1.8.2およびat.js 2.3.1リリースに関する情報を追加しました。 |
| 6月8日 | [モバイルアプリのターゲットに関するFAQ](/help/c-target-mobile-app/target-for-mobile-apps-faq.md) | 次のFAQのテキストを更新しました。「ターゲットモバイルは、Adobe Targetプレミアム製品SKUの機能のみですか？」 |
|  | [レポートの表示 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | トピック全体を更新しました。 |
| 6月5日 | [ターゲットのお知らせとイベント](/help/r-release-notes/target-announcements.md) | 6月10日のAdobe Target・コーヒー・ブレークに関する情報を追加。 |
|  | [上昇率と信頼性 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md) | 次のFAQのテキストを更新しました。「計算指標で上昇率と信頼性が表示されないのはなぜですか？」 |
| 6月4日 | [A4T レポート](/help/c-integrating-target-with-mac/a4t/reporting.md) | 「Analyticsのレポート」節を更新しました。 |
| 6月1日 | [ターゲットのお知らせ](/help/r-release-notes/target-announcements.md) | 今後のターゲットイベントを発表する新しいページを追加しました。 |
|  | [レスポンシブエクスペリエンスのためのモバイルビューポート](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) | Apple iPhone 11、Apple iPhone SE、Google Pixel 2 XLの各モデルのビューポートのサイズと解像度を更新しました。 |
| 28 年 5 月 | [レポートの FAQ](/help/c-reports/reporting-frequently-asked-questions.md) | 以下の新しい FAQ を追加しました。 <ul><li>新規訪問者指標と再訪問者指標はどのようにカウントされますか。</li></ul> |
| 27 年 5 月 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | 自動配分アクティビティのターゲット用のAnalytics(A4T)のサポートに関する情報を追加しました。 |
| 26 年 5 月 | [プロファイル属性](/help/c-target/c-visitor-profile/profile-parameters.md) | 次の情報を追加しました。「スクリプトを無効にした後も、パラメーターはプロファイルに残ります。 プロファイルに既にアクティビティのオーディエンスーで使用されているパラメーターが含まれている場合、そのアクティビティの資格が得られます。」 |
| 21 年 5 月 | [許可リストターゲットエッジノード](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | リスト `mboxedge30.tt.omtrdc.net` に追加されました。 |
| 20 年 5 月 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | Target Standard/Premium 20.6.1（2020年6月10日）リリースに関する情報を追加しました。 |
|  | [ホスト](/help/administrating-target/hosts.md) | 「セキュリティのベストプラクティス」の節に注意を追加しました。 |
| 14 年 5 月 | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | プロファイルバッチステータスAPI v2の変更に関する情報を追加しました。 |
| 13 年 5 月 | [CNAME と Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | 「既知の制限事項」節を追加しました。 |
| 11 年 5 月 | [ホスト](/help/administrating-target/hosts.md) | リダイレクトおよび許可リストでのubox機能の使用に関する情報を追加しました。 |
|  | [リダイレクターの使用](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) | オープンリダイレクトの脆弱性を回避するためのホストの使用に関する情報を追加しました。 |
|  | [Recommendations と電子メールの統合](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | オープンリダイレクトの脆弱性を回避するためのホストの使用に関する情報を追加しました。 |
|  | [電子メール：Target の実装](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md) | オープンリダイレクトの脆弱性を回避するためのホストの使用に関する情報を追加しました。 |
| 7 年 5 月 | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | 2020年8月30日にmbox.jsの廃止が予定されているので、Adobe Target製品マネージャーのDavid Son氏が最近、開発者チャットを開催し、mbox.jsをat.jsに移行する利点について話し合いました。 ウェビナーを今後30日間視聴できるリンクがあります。 |
|  | [アクティビティ QA](/help/c-activities/c-activity-qa/activity-qa.md) | 「考慮事項」節を更新しました。 |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 「設定」の下の「overrideMboxEdgeServer」行を更新しました。 |
| 6 年 5 月 | [Apple Intelligent Tracking Prevention（ITP）2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | ITP 2.3に関する情報を追加しました。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：20.4.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target Standard/Premium 20.2.1（2020 年 2 月 20 日） 

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 4 年 5 月 | [レポートの FAQ](/help/c-reports/reporting-frequently-asked-questions.md#uneven) | 新しいFAQを追加しました。「A/BまたはMVTアクティビティで、エクスペリエンス間のトラフィック分割が不均等なのはなぜですか。」 |
| 29 年 4 月 | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | 極端な注文を含むレポートに関する既知の問題を追加しました。 |
| 28 年 4 月 | [プロファイルと変数の用語集](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | 新しいAWSエッジ `user.header('x-forwarded-for')` を使用してユーザーのIPアドレスを取得する方法に関する情報を削除しました。 このコマンドは、新しいAWSエッジで動作するようになりました。 |
|  | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | Target Standard/Premiumリリース(20.4.1)の日付を5月6日に変更しました。 |
| 23 年 4 月 | [CNAME と Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | トピックを更新しました。 |
| 22 年 4 月 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | 次の節を追加しました。 *プロファイルバッチステータスAPI v2の変更（2020年5月4日）* |
| 20 年 4 月 | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | 次の節を追加しました。 *Adobe Targetスキルビルダー：開発者チャットでは、Adobe Targetのmbox.jsをat.jsに移行します。* |
| 14 年 4 月 | [許可リストターゲットエッジホスト](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | 新規トピックです。 |
| 10 年 4 月 | [シングルページアプリケーションの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md#bp) | 次の節を追加しました。「導入のベストプラクティス」 |
| 7 年 4 月 | [上昇率と信頼性 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md#lift-condidence) | 「計算指標の上昇率と信頼性を表示できないのはなぜですか？」のテキストを更新しました。 |
| 2 年 4 月 | [プロファイルと変数の用語集](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | 新しいAWSエッジ `user.header('x-forwarded-for')` を使用してユーザーのIPアドレスを取得する方法に関する情報を追加しました。 |
|  | [at.js 1.*x* から at.js 2.*x へのアップグレード&#x200B;*](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | 以下の注意を追加しました。<ul><li>ECID ライブラリ v4.3.0 以降および at.js 2.*x* をインストールしたら、一意のドメインにまたがるアクティビティを作成してユーザーを追跡できます。この機能は、セッションの有効期限が切れた後にのみ機能することに注意してください。</li></ul> |
| 3月30日 | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md#atjs) | at.js 2.2.0より前のat.jsバージョンに影響する既知の問題を追加しました。この問題により、Adobe Analyticsコードがページエレメントに存在しない場合に、クリック追跡がAnalyticsでターゲット(A4T)のコンバージョンをレポートしませんでした。 |
|  | [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.jsバージョン2.2.0の詳細に次の情報を追加しました。<ul><li>Adobe Analyticsコードがページエレメントに存在しない場合に、クリック追跡で、ターゲット用のAnalytics(A4T)のコンバージョンがレポートされない問題を修正しました。</li></ul> |
| 3月25日 | [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 次のat.jsの新しいバージョンに関する情報を追加しました。<ul><li>at.jsバージョン2.3.0</li><li>at.jsバージョン1.8.1</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | 「設定」セクションに次の新しい行を追加しました。<ul><li>cspScriptNonce</li><li>cspStyleNonce</li></ul>以下の新しいセクションを追加しました。<ul><li>コンテンツセキュリティポリシー</li></ul> |
| 3月25日 | [Apple Intelligent Tracking Prevention（ITP）2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md#impact) | 次の影響に関する情報を追加しました。<ul><li>サードパーティIDに基づくプロファイルスクリプト</li><li>iOSデバイスでのQA/プレビューURL</li></ul> |
| 3月20日 | [ リリースノート（現行）](/help/r-release-notes/release-notes.md) | Target Standard/Premium 20.2.1リリースが2020年3月23日になることを示しました。 |
| 3月13日 | [制限](/help/r-troubleshooting-target/target-limits.md) | 「アカウントごとに再利用可能なオーディエンス」の数を更新しました。 |
| 3月12日 | [リリースノート（最新）](/help/r-release-notes/release-notes.md#summit) | オンラインのデジタルサミット会議に、無料でアクセスできる登録情報を追加しました。 |
| 3月9日 | [プライバシー](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | 詳しくは、「IPアドレスの最終オクテットの置き換え」の節に説明を追加しました。 |
|  | [複数値の属性の操作](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md) | JavaScriptの複数値パラメーターの *渡しのコードサンプルを更新しました*。 |
|  | [カスタムエンティティの属性](/help/c-recommendations/c-products/custom-entity-attributes.md) | 複数値の属性の *実装の下のAPIの* 使用 *にコードサンプルを追加しました*。 |
| 3月4日 | [プロファイル属性](/help/c-target/c-visitor-profile/profile-parameters.md) | トピック全体を更新し、「ベストプラクティス」の節を大幅に改訂しました。 |
| 2月21日 | [ リリースノート（現行）](/help/r-release-notes/release-notes.md) | 新しいAdobe Experience Cloudナビゲーションに関する情報を追加しました。 |
| 2月20日 | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Updated the description for the `enabled` setting. 次の設定に関する情報を追加しました。 `pageLoadEnabled` と `viewsEnabled`。 |
| 2 月 20 日 | [ リリースノート ](/help/r-release-notes/release-notes.md) | mbox.jsライブラリの今後の廃止に関する情報を追加しました。 |
|  | [地域](/help/c-target/c-audiences/c-target-rules/geo.md) | at.js 1でサポートさ `mboxOverride.browserIp` れていることに関する注意を追加しました。*x* のみで使用できます。 |
|  | [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | ターゲットチームがサポートするat.jsのバージョンを説明するテキストを明確にしました。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：20.2.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe Target Standard/Premium 20.1.1（2020 年 2 月 4 日） 

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 2月4日 | [リリースノート](/help/r-release-notes/release-notes.md)：20.1.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |
