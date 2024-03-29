---
keywords: ターゲットドキュメントの変更ログ;ドキュメントの更新;新しいトピック;編集;アップデート;更新
description: ' [!DNL Adobe Target]  ドキュメントへの重要な追加や変更について、常に最新の情報を把握します。'
title: ' [!DNL Target] のドキュメントのアップデートはどこで確認できますか？'
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 31ad1682fc85f65fb80e96d7303cce55e36a442f
workflow-type: tm+mt
source-wordcount: '1573'
ht-degree: 76%

---

# ドキュメントの変更点

このページでは、[!DNL Adobe Target] 製品キュメントに加えられた重要な変更を一覧表示します。

## [!DNL Target] Standard/Premium 24.3.1（2024 年 3 月 4 日～6 日）

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 3月22日（PT） | [Target のエッジノードを許可リストに登録](https://experienceleague.adobe.com/en/docs/target-dev/developer/implementation/privacy/allowlist-edges){target=_blank} | エッジノード 31 ～ 38 への参照が削除されました。このノードは存在しなくなったからです。 が最新許可リストに加えるであることを確認します。 |
|  | [サードパーティ Cookie の廃止が Target(at.js) に与える影響](https://experienceleague.adobe.com/docs/target-dev/assets/third_party_cookie_deprecation){target=_blank} | Googleでのサードパーティ cookie の廃止予定が、お客様にとってどのような意味を持つかを説明する新しいブログ投稿です。 [!DNL Adobe Target] at.js の実装。 |
| 3月14日（PT） | [[!DNL Target] リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | リリースノートを追加しました。 [!DNL Adobe Experience Platform Visual Editing Helper] 対象： [!DNL Google Chrome]. |
| 3 月 14 日 | [[!UICONTROL Time Frame]](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | 夏時間 (DST) に対応するために、時間ベースのオーディエンスを再保存するための情報を追加しました。 |
| 3月6日（PT） | [ブラウザー](/help/main/c-target/c-audiences/c-target-rules/browser.md) | 次の節の情報を更新しました：「 [!DNL iPad] および [!DNL iPhone] in [!UICONTROL Browser] オーディエンス属性（2024 年 4 月 30 日）」と呼ばれる変数です。 |
|  | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | セクション全体を更新しました：「 `Browser:iPad` および `Browser:iPhone` in [!UICONTROL Browser] オーディエンス属性（2024 年 4 月 30 日）」と呼ばれる変数です。 |
|  | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 24.1.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 24.1.1（2024年1月22日、23日、25日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 2月28日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | 次に関する情報を追加しました： [!DNL Target] Standard/Premium 24.3.1（2024 年 3 月 4 日～6 日）リリースです。 |
| 2月26日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 今後の [!UICONTROL Adobe Target Community] コーヒーブレーク（2024 年 2 月 28 日）。 |
| 2月23日（PT） | [が使用する IP アドレス [!DNL Recommendations] フィード処理サーバー](/help/main/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md) | 次の重要な注意事項と、する必要がある新しい IP アドレスを追加しまし許可リストに加えるた。<P>**重要**: [!DNL Target] チームは現在、ダウンロード用に NAT ゲートウェイアドレスを更新しています [!DNL Recommendations] フィード。 IP許可リストに加えるを実装する場合は、次の新しいAWSホ許可リストに加えるストを必ずしてください。 既存のホストは 2024 年 6 月 30 日に廃止される予定です。 スムーズな移行を実現するには、9 つのアド許可リストに加えるレスをすべてします。 既存のアドレスを削除する緊急度はありません。 |
| 2月8日（PT） | [プリフェッチ](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/prefetch.html?lang=ja){target=_blank} | 新しい節「Analytics for Target（A4T）を使用した際の clickTrack 指標による mbox のプリフェッチ」を追加しました。 |
| 2月5日（PT） | [Analytics をレポートソースとして使用するアクティビティの作成](/help/main/c-integrating-target-with-mac/a4t/campaign-creation.md) | を使用する際に、別々のワークスペースから 2 つのアクティビティに同じアクティビティ名を使用できないことを示すテキストを追加しました。 [!UICONTROL Analytics for Target] (A4T) をレポートソースとして使用する場合。 |
|  | [アクティビティの設定 - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md) | を使用する際に、別々のワークスペースから 2 つのアクティビティに同じアクティビティ名を使用できないことを示すテキストを追加しました。 [!UICONTROL Analytics for Target] (A4T) をレポートソースとして使用する場合。 |
|  | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 2024年2月7日（PT）に予定されている Adobe Target コミュニティのコーヒーブレイクに関する情報を追加しました。 |
| 1月24日（PT） | [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | at.js バージョン 2.11.4 のリリースノートを追加しました。 |
|  | [ブラウザー](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | 2 つの新しいプロファイルがまだ使用できません。これらのメモは、これらのプロファイルが使用可能になると更新されます。 |
|  | [at.js に関するよくある質問](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-faq.html?lang=ja){target=_blank} | Ionic アプリ環境での at.js に関する FAQ を追加しました。この実装は、テストされていないか、推奨されていません。 |
| 1月22日（PT） | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | iPadとiPhoneの廃止に関する重要な情報を、 [!UICONTROL Browser] 2024 年 4 月 30 日より前に、お客様の部分の変更を必要とするオーディエンス属性。 |
|  | [ブラウザー](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | 以下の新しいセクションを追加しました。 <ul><li>ブラウザーオーディエンス属性からの iPad と iPhone の非推奨（廃止予定）（2024年4月30日（PT））</li></ul> |
|  | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 24.1.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.11.1（2023年11月13～14日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 1月18日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | 今後の [!DNL Target Standard/Premium] 24.1.1 リリースに関するプレリリースノートを追加しました。 |
| 12月13日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | [!DNL Adobe Target] 2024 パーソナライゼーション成熟度ウェビナーシリーズに関する情報を追加しました。 |
|  | [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html?lang=ja){target=_blank} | 次の 2 つの新しいオプション設定を追加しました。 <ul><li>aepSandboxId</li><li>aepSandboxName</li></ul> |
| 12月4日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 「機械学習および AI レポートと分析」の [!DNL Adobe Target Community] コーヒーブレークセッション（2023年12月6日水曜日（PT））に関する登録情報を追加しました。 |
| 12月1日（PT） | [Adobe Target プロファイル更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html?lang=ja){target=_blank} | 従来の API ドキュメントを次の記事に移動しました。<ul><li>[Adobe Target プロファイル API の概要](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html?lang=ja){target=_blank}</li><li>[Adobe Target 単一プロファイル更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-single-api.html?lang=ja){target=_blank}</li><li>[Adobe Target プロファイル一括更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-bulk-api.html?lang=ja){target=_blank}</li></ul> |
| 11月29日（PT） | [プロファイル一括更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html?lang=ja){target=_blank} | 方法の違いを明確にしました [!DNL Target] は、ユーザーのプロファイルを作成する際に顧客属性を処理します [!DNL Target] は、 [!UICONTROL Bulk Profile Update API] v1 に対する v2。 |
| 11 月 21 日 | [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | at.js 2.11.3 のリリースノートを追加しました。 |
| 11 月 17 日 | [管理者の最初の手順](/help/main/administrating-target/start-target.md) | 次の重要な注意点を追加しました。<ul><li>次の条件を持つユーザー [!UICONTROL Product Admin] または [!UICONTROL System Admin] 権限 [!DNL Adobe Admin Console] では、 [!UICONTROL Administration] 次のページ [!DNL Target]、それらに関係なく [!DNL Target] 役割。 を使用しないユーザー [!UICONTROL Product Admin] または [!UICONTROL System Admin] 権限 [!DNL Adobe Admin Console] は、特定の [!DNL Target] これらの変更を行うロール。1.</li></ul> |
|  | [制限](/help/main/r-troubleshooting-target/target-limits.md#in-mbox) | [!DNL Target] が at.js で切り捨てを処理する方法に関する情報を含むセクションを更新しました。*x* と [!DNL Adobe Experience Platform Web SDK]。 |
|  | [配信 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html?lang=ja){target=_blank} | 現在の配信 API ドキュメントにリダイレクトを追加し、従来のドキュメント（`http://developers.adobetarget.com/api/delivery-api/`）を非推奨にしました。必要に応じて、ブックマークを更新してください。 |
| 11 月 16 日 | [プロファイル一括更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html?lang=ja){target=_blank} | 次の注意事項を追加しました。「通常、更新は 1 時間未満でおこなわれますが、反映されるまでに 24 時間かかる場合があります。」 |
| 11 月 13 日 | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.11.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.10.2（2023年10月24日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 11月11日（PT） | [Recommendations API リファレンス](https://developer.adobe.com/target/administer/recommendations-api/){target=_blank} | [!DNL Adobe Target] [!DNL Recommendations] API は、[!DNL Adobe Developer] web サイトに移動しました。必要に応じてブックマークを更新してください。 |
|  | [時間枠](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | [!DNL Target] の時間のオーディエンスには夏時間（DST）の変更が考慮されていないというメモを追加しました。DST の変更を考慮するには、オーディエンスを手動で更新する必要があります。 |
| 11月8日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | 今後の [!DNL Target Standard/Premium] 23.11.1 リリースに関するプレリリースノートを追加しました。 |
| 10月28日（PT） | [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | at.js 2.11.2 リリースに関する詳細を追加しました。 |
| 10月25日（PT） | [[!DNL Target] リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | 次に関する情報を追加しました： [!UICONTROL Activities] ページユーザーインターフェイスの更新（2023 年 10 月 26 日） |
| 10月24日（PT） | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.10.2 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.9.1（2023年9月6日～11日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 10月17日（PT） | [レポートの FAQ](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B) | 次の FAQ を更新しました。「アクティビティのレポートにデータがないのはなぜでしょうか。」 |
| 10月11日（PT） |  [!DNL Adobe Target]  のレポートソースとしての [[!DNL Adobe Analytics] （A4T）](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) | [!DNL Adobe Experience Platform Web SDK] の A4T サポートに関する情報を更新しました。 |
| 10月10日（PT） | [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | at.js バージョン 2.11.0 のリリースノートを追加しました。 |
| 10月6日（PT） | [レスポンストークン](/help/main/administrating-target/response-tokens.md) | すべてのコードサンプルを更新しました。 |
|  | [での A4T レポートの設定 [!DNL Analysis Workspace] 対象： [!UICONTROL Auto-Allocate] アクティビティ](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=ja){target=_blank} | のチュートリアル全体を更新しました。 *[!UICONTROL Adobe Target Tutorials]* ガイド。 |
| 10月4日（PT） | [アクティビティ](/help/main/c-activities/activities.md) | [!DNL Target] 23.9.4 リリースに含まれる UI の更新を反映するために、テキストと画像を更新しました。 |
|  | [フィード](/help/main/c-recommendations/c-products/feeds.md) | [!DNL Target] 23.9.4 リリースに含まれる UI の更新を反映するために、テキストと画像を更新しました。 |
| 10月2日（PT） | [[!DNL Target] リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.9.3 リリースに関するリリースノートを追加しました。 |
|  | [[!DNL Recommendations] 実装パターン](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html?lang=ja){target=_blank} | at.js *のアーティクルを使った新しい* Recommendations の実装パターンは、at.js JavaScript ライブラリを使うときに、[!DNL Adobe Target Recommendations] の実装を理解して作成するのに役立ちます。<P>[!DNL Target] パターンに関する一般的な情報については、*Adobe Target 開発者ガイド*&#x200B;の[実装パターンの概要](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/pattern-overview.html?lang=ja){target=_blank}を参照してください。<P>新しい Recommendations の実装パターンは、次の記事で構成されています。<ul><li>[at.js を使用した Recommendations 実装パターンの概要](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html?lang=ja){target=_blank}</li><ul><li>[SDK の初期化](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/initialize-sdk.html?lang=ja){target=_blank}</li><li>[データ収集の設定](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/data-collection.html?lang=ja){target=_blank}</li><li>[エクスペリエンスのレンダリング](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/render-experiences.html?lang=jp){target=_blank}</li><li>[通知 [!DNL Target]](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/notify-target.html?lang=jp){target=_blank}</li></ul></ul> |
| 9月30日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 23.9.3 リリースに関するプレリリースノートを追加しました。 |
|  | [Java SDK の初期化](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html?lang=ja){target=_blank} | 表に以下の新規パラメーターを追加しました。<ul><li>`connectionTtlMs`</li><li>`idleConnectionValidationMs`</li><li>`evictIdleConnectionsAfterSecs`</li></ul> |
| 9月22日（PT） | [に関連する問題のトラブルシューティング [!UICONTROL Enhanced Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF) | IP アドレスのリストを更新し、許可リストに加えました。 |
| 9月18日（PT） | [[!DNL Target] リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.9.3 リリースに関するリリースノートを追加しました。 |
| 9月15日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 23.9.3 リリースに関するプレリリースノートを追加しました。 |
| 9月12日（PT） | [[!DNL Target] リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.9.2 リリースに関するリリースノートを追加しました。 |
|  | [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | at.js バージョン 2.10.3 のリリースノートを追加しました。 |
| 9月11日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 23.9.2 リリースに関するプレリリースノートを追加しました。 |
| 9月6日（PT） | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.9.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.8.1（2023年8月9日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 9月1日（PT） | [環境](/help/main/administrating-target/environments.md##section_4F8539B07C0C45E886E8525C344D5FB0) | 「レポート用のデフォルト環境を設定」のメモを更新しました。 |
| 8月30日（PT） | [プライバシー](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/privacy.html?lang=ja#aep){target=_blank} | 新しい節「Adobe Experience Platform Web SDK を使用する場合のデータストリームレベルの IP 難読化」を追加しました。 |
|  | [アクティビティの設定 - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md#section_9F8092BE4225442896F926540292F221) | 次の FAQ のレポートにデータが表示されると予想される時間枠を修正しました。「アクティビティを作成しました。データが表示されないのはなぜですか？」 |
| 8月29日（PT） | [オンデバイス判定でサポートされる機能](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/supported-features.html?lang=ja){target=_blank} | クライアントサイドでオンデバイス判定（ODD）を使用する場合のターゲティングでサポートされる地域属性のリストを追加しました。 |
|  | [オンデバイス判定の概要](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=ja){target=_blank} | サーバーサイドでオンデバイス判定（ODD）を使用する場合のターゲティングでサポートされる地域属性のリストを追加しました。 |
|  | [Web ビューを使用したネイティブアプリでの AEP Mobile SDK による Target の実装](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/native-app.html?lang=ja){target=_blank} | 新しい記事。 |
|  | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 今後の Adobe Target コミュニティコーヒーブレーク（2023年8月30日（PT））に関する次の情報を追加しました：「ピークシーズンに備えて ROI 効果を最大化するための戦略化」ウェビナーのフォローアップ。 |
| 8月15日 | [アクティビティ QA](/help/main/c-activities/c-activity-qa/activity-qa.md) | 空の値を含むページをサイトに読み込んでもブラウザーから QA cookie が削除され&#x200B;*ない*&#x200B;ことを明確にする情報を追加しました（at.js 2.*x* がデプロイされている場合）。 |
|  | [A/Bn テストでの統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md) | 「信頼性」の定義を更新しました。 |
|  | [オファー](/help/main/c-experiences/c-manage-content/manage-content.md) | 画像オファーが [!UICONTROL Enterprise User Permissions] モデル。 |
| 8月9日（PT） | [Target モバイルのプレビュー](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=ja){target=_blank} | [!DNL Adobe Experience Platform Mobile SDK] の現在のバージョンに関する情報を含むトピックを更新しました。 |
| 8月9日（PT） | [Target モバイルのプレビュー](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=ja){target=_blank} | [!DNL Adobe Experience Platform Mobile SDK] の現在のバージョンに関する情報を含むトピックを更新しました。 |
|  | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 2023年8月17日（PT）に予定されている&#x200B;*ピークシーズンに備えて ROI 効果を最大化するための戦略化*&#x200B;のウェビナーに関する情報を追加しました。 |
|  | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.8.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.7.1（2023年7月24～26日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
|  | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 2023年8月17日（PT）に予定されている&#x200B;*ピークシーズンに備えて ROI 効果を最大化するための戦略化*&#x200B;のウェビナーに関する情報を追加しました。 |
| 8月7日（PT） | [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | at.js のサポート対象バージョンに関する情報を明確にしました。 |
| 7月25日（PT） | [[!DNL Target] リリースノート（最新）](/help/main/r-release-notes/release-notes.md#edge) | 2023年8月9日（PT）に予定されているエッジインフラストラクチャのアップグレードに関する情報を追加しました。 |
|  | [Target のエッジノードを許可リストに登録](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=ja){target=_blank} | エッジデプロイメント 41～48 の NAT と IP／ドメインを更新しました。 |
| 7 月 25 日 | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.7.1 リリースに関するリリースノートを追加しました。 |
