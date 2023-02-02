---
keywords: ターゲットドキュメントの変更ログ;ドキュメントの更新;新しいトピック;編集;アップデート;更新
description: ' [!DNL Adobe Target]  ドキュメントへの重要な追加や変更について、常に最新の情報を把握します。'
title: ' [!DNL Target] のドキュメントのアップデートはどこで確認できますか？'
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 6c58b7627d776bccf36165b80ed30f8537fc8f5e
workflow-type: tm+mt
source-wordcount: '1960'
ht-degree: 97%

---

# ドキュメントの変更点

このページでは、[!DNL Adobe Target] 製品キュメントに加えられた重要な変更を一覧表示します。

## [!DNL Target] Standard／Premium 22.13.3（2023年1月25日（PT）） 

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 2月2日（PT） | [Visual Experience Composer に関連する問題のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md#section_FA2A18E8FD6A4274B2E395DBAA2FB407) | 以下の節が更新されました。<ul><li>参照モードを使用すると、VEC が壊れているように見えます</li></ul> |
| 1月31日（PT） | [制限](/help/main/r-troubleshooting-target/target-limits.md#mbox-names) | mbox 名に使用できる文字と使用できない文字のリストを追加しました。 |
| 1月25日（PT） | [JSON オファーの作成](/help/main/c-experiences/c-manage-content/create-json-offer.md) | での JSON オファーのサポートを示した [!UICONTROL Automated Personalization] (AP) フォームベースの Experience Composer を使用するアクティビティが利用できるようになりました。 |
|  | [Adobe Target のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 以下のイベントに関する情報を追加しました。<ul><li>[!DNL Adobe Target] コミュニティ Q&amp;A コーヒーブレーク:エクスペリエンスの最適化のためのモバイルおよび認証済みのユースケース</li></ul> |
|  | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.13.3 リリースに関するリリースノートを追加しました。 |

## [!DNL Adobe Target] Standard／Premium 22.10.1（時差リリース 2022年10月10～13日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 1月13日（PT） | [Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) | 「よくある質問」の節を追加しました。 |
| 1月12日（PT） | [Visual Experience Composer ヘルパー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) | 現在の [!UICONTROL Visual Experience Composer] ヘルパー拡張機能のステータスを説明する重要な注記を更新しました。 |
|  | [ターゲットとオーディエンスに関する FAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md) | [!UICONTROL テンプレートルール]によって追加されたオーディエンス URL ターゲティングと URL ターゲティングが、URL ターゲティングとして評価されることを説明する情報を追加しました。 |
|  | [Target リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) |  22.13.3 リリースに関するプレリリースノートを追加しました。 |
| 12月21日（PT） | [Velocity を使用したデザインのカスタマイズ](/help/main/c-recommendations/c-design-overview/customizing-a-template.md) | 「複数値」属性を除いて、`productPage` mbox または CSV アップロードで [!DNL Recommendations] に送信されたエンティティ属性をデザインに表示できることを明確にしました。 |
| 12月20日（PT） | [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md) のオファーレポートグループ | 「注意事項」の下のレポートグループに関する情報を追加しました。 |
| 12月14日（PT） | [レポート設定](/help/main/c-reports/c-report-settings/report-settings.md#environment) | 「環境」の節に、[!DNL Adobe Experience Platform]（AEP）を使用して指標データを [!DNL Target] に送信することに関しての注記を追加しました。 |
| 11月29日（PT） | [地域](/help/main/c-target/c-audiences/c-target-rules/geo.md) | 次の段落を追加して、テキストを明確にしました。<ul><li>訪問者の地域情報は、[!DNL Target] 場所リクエスト（mbox リクエスト）の発信元 IP アドレスから決定されます。IP-to-geo 解決は、新しいセッションの最初の呼び出しに対して行われます。つまり、訪問者の IP アドレスが訪問のセッション中に変更された場合でも、地域情報は最初の呼び出しの IP アドレスに基づきます。</li></ul> |
| 11月28日（PT） | *Adobe Target 開発者ガイド*&#x200B;の [Models API（ブロックリストへの登録）の概要](https://developer.adobe.com/target/before-administer/models-api/){target=_blank} | 新しい Models API。<br>機能は [!DNL Target] 機械学習アルゴリズムからブロックし、[!UICONTROL 自動ターゲット]または [!UICONTROL Automated Personalization] モデルまたはアクティビティで使用されないようにすることができます。 |
|  | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | Models API リリース（2022年11月23日）に関する情報を追加しました。 |
| 11月23日（PT） | [at.js を使用して Analytics for Target（A4T）を実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md) | [Experience Cloud 統合プロビジョニングフォーム](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}へのリンクを更新しました。  |
| 11月16日（PT） | [Adobe Target のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 次のイベントの登録情報を追加しました。<ul><li>[!DNL Adobe Target] コミュニティ Q＆A コーヒーブレイク（11月29日（PT））</li></ul> |
| 11月8日（PT） | [A/B テストを実行すべき期間はどのくらいですか？](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) | 正確な結果を得るには、ページを再読み込みしてから、[!DNL Adobe Target] [!UICONTROL サンプルサイズ計算ツール]のパラメーター数値を変更する必要があるという重要な注記を追加しました。また、実際の[計算ツール](https://experienceleague.adobe.com/tools/calculator/testcalculator.html?lang=ja){target=_blank}に注記を追加しました。 |
|  | [リダイレクトオファー - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682) | テーブルの `adobe_mc_sdid` パラメーターの説明を更新しました。 |
|  | [アクティビティのトラブルシューティング](/help/main/c-activities/c-troubleshooting-activities/troubleshooting-activities.md) | 「アクティビティのコンバージョン後、訪問者はどのエクスペリエンスにも含まれない」という新しい節を追加しました。 |
|  | [カスタムパラメーター](/help/main/c-target/c-audiences/c-target-rules/custom-parameters.md) | 「[!UICONTROL フィルター条件]」ドロップダウンリストから選択した mbox は、アクティビティの作成時には保存されないという注記を追加しました。このオプションを使用すると、選択した mbox に基づいてパラメーターをフィルター処理できます。 |
| 11月2日（PT） | 既知の問題と解決された問題 | ページを削除し、関連する問題を適切なページに移動して、情報がコンテキスト内に表示されるようにしました。 |
| 10月25日（PT） | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.10.3 リリースに関するリリースノートを追加しました。 |
| 10月19日（PT） | [カテゴリの親和性](/help/main/c-target/c-visitor-profile/category-affinity.md#section_8B86C7FF50294208866ABF16F07D5EB9) | 1 回の mbox 呼び出し内で複数のカテゴリが渡される場合のスコアリングを説明する注記を追加しました。 |
| 10月18日（PT） | [[!UICONTROL Automated Personalization] アクティビティの作成](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) | AP テストでは最大 30,000 件までエクスペリエンスを作成できますが、アルゴリズムが最高のパフォーマンスを発揮するのは、使用される個別のエクスペリエンスが 10,000 件未満の場合であることを明示するように、テキストを更新しました。アクティビティで「[!UICONTROL 重複を許可しない]」オプションが有効になっている場合でも、この同じ制限が適用されます。 |
|  | [Automated Personalization に関する FAQ](/help/main/c-activities/t-automated-personalization/automated-personalization-faq.md) | AP テストでは最大 30,000 件までエクスペリエンスを作成できますが、アルゴリズムが最高のパフォーマンスを発揮するのは、使用される個別のエクスペリエンスが 10,000 件未満の場合であることを明示するように、テキストを更新しました。アクティビティで「[!UICONTROL 重複を許可しない]」オプションが有効になっている場合でも、この同じ制限が適用されます。 |
| 10月14日（PT） | [[!DNL Adobe Target] のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | [!DNL Adobe Target] コミュニティ Q&amp;A コーヒーブレークに関する登録情報を追加しました（2022年10月26日（PT））。 |
| 10月10日（PT） | [[!UICONTROL Visual Editing Helper] 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) | 新しい記事。 |
|  | [Visual Experience Composer に関連する問題のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md) | 「[VEC にページが表示されません（VEC のみ）](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md#does-not-load)」の節を更新しました。 |
| 10月4日（PT） | [A/Bn テストでの統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md) | 新規トピックです。<br>この記事の情報は、以前このサイトでダウンロード可能だった *Adobe Target A/B テストの計算*&#x200B;の PDF ファイルに代わるものです。 |
|  | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.10.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Adobe Target] Standard／Premium 22.9.1（時差リリース 2022年9月13日～15日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 10月3日（PT） | [Target リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 22.10.1 リリースの日付を更新しました。 |
| 9月22日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 以下のイベントに関する情報を追加しました。<ul><li>[!DNL Adobe Target] コミュニティ Q&amp;A コーヒーブレーク（2022年9月28日（PT））</li></ul> |
| 9月15日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 以下のウェビナーに関する情報を追加しました。<ul><li>AI を利用したパーソナライゼーションの微調整：[!DNL Adobe Target] の新機能（2022年10月11日（PT））</li></ul> |
| 9月13日（PT） | [ [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md) について | [!DNL Recommendations] フィードが失敗したときの通知に関する情報を追加しました。 |
|  | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.9.1 リリースに関するリリースノートを追加しました。 |

## Adobe Target Standard／Premium 22.8.1（時差リリース：2022年8月17～18日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 8月22日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 以下のお知らせに関する情報を追加しました。<ul><li>Gartner Magic Quadrant for Personalization Engines（2022）のリーダーに [!DNL Target] が選出される</li></ul>以下に今後のイベントに関する情報を追加しました。<ul><li>[!DNL Adobe Target] コミュニティ Q&amp;A コーヒーブレーク（2022年8月31日（PT））</li><li>シェフのコレクション：パーソナライゼーションのレシピ（2022年8月30日（PT））</li><li>[!DNL Adobe Target] スキルビルダー - モバイルエクスペリエンスの最適化（2022年9月6日（PT））</li><li>[!DNL Adobe Target] スキルビルダー - AI 駆動型パーソナライゼーションと推奨事項（2022年9月15日（PT））</li></ul>以下に過去のウェビナーセッションの録画リンクを追加しました。<ul><li>アドビ：パーソナライゼーション業界インサイダー - 小売（2022年8月11日（PT））</li></ul> |
| 8月22日（PT） | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.8.1 リリースに関するリリースノートを追加しました。 |

## Adobe Target Standard／Premium 22.6.1（時差リリース：2022年6月7～9日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 6月30日（PT） | [Adobe Target 開発者ガイド](https://developer.adobe.com/target/){target=_blank} | *Adobe Target 開発者ガイド*&#x200B;が公開され、すべての [!DNL Target] 開発者向けコンテンツが 1 つの便利なポータルにまとめられました。ポータルには、[!DNL Target] と [!DNL Recommendations]、[!DNL Target] SDK、および [!DNL Target] API の実装に関する情報が掲載されています。 |
|  | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.6.2 リリースに関するリリースノートを追加しました。 |
|  | [Target のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 過去のウェビナーセッションの録画リンクを追加しました。 |
| 6月14日（PT） | [Recommendations の計画と実装](https://developer.adobe.com/target/implement/recommendations/){target=_blank} | 次のセクションのコードサンプルを更新しました。<ul><li>買い物かごへの追加／買い物かごの表示／チェックアウトページ</li><li>訪問者の買い物かごにすでに入っている品目を除く</li></ul> |
| 6月7日（PT） | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.6.1 リリースに関するリリースノートを追加しました。 |

## Adobe Target Standard／Premium 22.5.1（時差リリース、2022年5月11～13日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 6月7日（PT） | [Target リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 22.6.1 リリースに関するプレリリース情報を追加しました。 |
| 5月31日（PT） | [Target のお知らせとイベント](/help/main/r-release-notes/target-announcements.md#webinar-series) | 次回の [!DNL Adobe Target] Community Coffee Break（2022年6月29日（PT）開催）に関する情報を追加しました |
| 5月25日（PT） | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target] プラットフォームリリース（2022年5月25日（PT））および at.js 2.9.0 リリース（2022年5月27日（PT））に関する情報を追加しました。 |
|  | [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | at.js 2.9.0 リリースに関する情報を追加しました。 |
|  | [User-agent と Client Hints](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank}をインストールします。 | 新規トピックです。 |
|  | [Target のお知らせとイベント](/help/main/r-release-notes/target-announcements.md#webinar-series) | ウェビナー「Dick&#39;s Sporting Goods：パーソナライゼーションと小売業界の変化（2022年5月19日（PT））」の録画へのリンクを追加しました。 |
| 5月23日（PT） | [Target リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | at.js バージョン 2.9.0（2022年5月25日（PT））のプレリリースノートを追加しました。 |
| 5月11日（PT） | [Target のお知らせとイベント](/help/main/r-release-notes/target-announcements.md#webinar-series) | 以下のウェビナーに関する情報および登録リンクを追加しました。<ul><li>Dick&#39;s Sporting Goods：パーソナライゼーションと小売業界の変化</li><li>アドビ：パーソナライゼーション業界インサイダー - 金融サービスと保険</li><li>シティナショナルバンク：デジタル最適化でトップ 1％を達成する方法</li><li>アドビ：精度の高いパーソナライゼーション - [!DNL Adobe Analytics] および [!DNL Target]</li><li>シティナショナルバンク：ゼロからのヒーロー - パーソナライゼーションプログラムの開始と拡大</li><li>アドビ：効果的な最適化の機会を探る</li><li>アドビ：パーソナライゼーション業界インサイダー - 小売</li></ul>以下のウェビナーの録画を追加しました。<ul><li>[!DNL Adobe Target] によるリアルタイムパーソナライゼーション</li></ul> |
|  | [コンテンツセキュリティポリシー（CSP）指令](https://developer.adobe.com/target/before-implement/privacy/content-security-policy/){target=_blank}をインストールします。 | FAQ 節を追加しました。 |
|  | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.5.1 および Target プラットフォーム（2022年5月11～13日（PT））リリースに関する情報を追加しました。 |

## Adobe Target Standard／Premium 22.4.1（4月28日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 5月10日（PT） | [Target リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 22.5.1 リリースに関するプレリリース情報を追加しました。 |
| 4月28日（PT） | [Enterprise ユーザーの権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#move-audience) | 以下の FAQ を追加しました。<ul><li>オーディエンスを別のワークスペースに移動させることはできますか？</li></ul> |
|  | [[!UICONTROL 自動配分の]概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#section_0E72C1D72DE74F589F965D4B1763E5C3) | 以下の FAQ を追加しました。<ul><li>[!UICONTROL 自動配分]アクティビティでは、テストの過程でルックバックウィンドウを調整して、経時的なトレンドの変化を考慮することはできますか？</li><li>[!UICONTROL 自動配分]では、訪問者がアクティビティの資格を得る際に閲覧したものとは異なる勝者エクスペリエンスを再訪問者に表示しますか？</li></ul> |
|  | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.4.1 および Target プラットフォーム（2022年4月27日（PT））リリースに関する情報を追加しました。 |

## Adobe Target Standard／Premium 22.3.1（4月5日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 4月26日（PT） | [Target のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 以下のイベントに関する情報を追加しました。<ul><li>ウェビナー：Adobe Targetを使用したリアルタイムパーソナライゼーション（2022年4月28日（PT））</li><li>[!DNL Adobe Target] コミュニティ Q ＆ A コーヒーブレイク（2022年5月25日（PT））</li></ul> |
|  | [リダイレクトオファー - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#discrepancies) | 以下の FAQ を追加しました。<ul><li>A4T アクティビティでリダイレクトオファーを使用する際に、トラフィック配分の不一致を最小限に抑えるには、どうすればよいですか？</li></ul> |
|  | [AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | 以下の節を追加しました。<ul><li>Target に書き出したエクスペリエンスフラグメントから ClientLibs と不要な HTML を削除する</li></ul> |
| 4月21日（PT） | [Target リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | 2022年4月17日（PT）に予定されている [!DNL Target] プラットフォームリリースに関する情報を追加しました。 |
| 4月20日（PT） | [Target リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 22.4.1 リリースに関するプレリリース情報を追加しました。 |
| 4月14日（PT） | [Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) | 「並べ替え」の節に、DOM 要素の遅延読み込みによる[!UICONTROL 移動]アクションと[!UICONTROL 並べ替え] アクションでの VEC 動作が一貫しない問題の対処方法を説明する情報を追加しました。 |
| 4月13日（PT） | [Target のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 以下のイベントに関する情報を追加しました。<ul><li>[!DNL Adobe Target] コミュニティ Q&amp;A コーヒーブレーク（2022年4月27日（PT））</li></ul> |
|  | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target] Platform リリースに関するリリース情報を追加しました。 |
| 4月4日（PT） | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.3.1 リリースに関する情報を更新しました。 |

## Adobe Target Standard／Premium 22.2.1（2022年2月1日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 3月30日（PT） | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target] Platform リリースに関するリリース情報を追加しました。 |
| 3月28日（PT） | [Target リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target] Platform リリースに関するリリース情報を追加しました。 |
| 3月22日（PT） | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | リリースに関する [!DNL Target Standard/Premium] カスタマーエンジニアリング修正リリース情報を追加しました。 |
|  | [Target リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 22.3.1 リリースに関するプレリリース情報を追加しました。 |
| 3月17日（PT） | [Target リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] カスタマーエンジニアリング修正リリースに関するプレリリース情報を追加しました。 |
|  | [mbox3rdPartyId のリアルタイムプロファイル同期](/help/main/c-target/c-visitor-profile/3rd-party-id.md) | プロファイルの同期に関する「更新は 5～10 分ごとにプロファイルストアと同期されます」の文章を変更しました。 |
| 3月8日（PT） | [Target のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 以下のイベントに関する情報を追加しました。<ul><li>[!DNL Adobe Target] コミュニティ Q&amp;A コーヒーブレーク（2022年3月30日（PT））</li></ul> |
| 3月7日（PT） | [オーディエンスの作成](/help/main/c-target/c-audiences/audiences.md#aep) | 「[!DNL Adobe Experience Platform] のオーディエンスを使用」の下に新しい節を追加しました。<ul><li>パーソナライズ機能の使用例</li></ul> |
| 2月25日（PT） | [自動配分と自動ターゲットアクティビティに対する A4T のサポート](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) | 以下の節を更新しました。<ul><li>[自動配分と自動ターゲット](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#both)</li><li>[自動配分](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa)</li></ul> |
|  | [自動配分レポートの解釈](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | 新しい FAQ を追加しました。<ul><li>[!UICONTROL レポートソースとしての Analytics]（A4T）を使用する[!UICONTROL 自動配分]アクティビティでは、「勝者なし」、「勝者」および「星」バッジを使用できますか？</li></ul> |
|  | [アクティビティのみのオーディエンスの作成](/help/main/c-target/creating-activity-only-audience.md) | 除外ルールに関する「考慮事項」の節に情報を追加しました。 |
| 2月10日（PT） | [Visual Experience Composer ヘルパー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) | Visual Experience Composer（VEC）での Service Workers を使用した web サイトの読み込みに関する情報を追加しました。 |
| 2月7日（PT） | [Target のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 以下のイベントに関する情報を追加しました。<ul><li>[!DNL Adobe Target] コミュニティ Q&amp;A コーヒーブレーク（2022年2月23日（PT））</li></ul> |
| 2月3日（PT） | [オーディエンスの作成](/help/main/c-target/c-audiences/audiences.md#RTCDP) | 新しい節と「ビデオ：Real-time CDP と [!DNL Adobe Target] による次のヒットのパーソナライゼーション」のビデオを追加しました。 |
| 2月2日（PT） | [コンテンツ配信のトラブルシューティング](/help/main/c-activities/c-troubleshooting-activities/content-trouble.md#escape) | 「[!DNL Target] プロファイル属性値の二重引用符のエスケープが期待どおりに機能しない」の節を追加しました。 |
| 2月1日（PT） | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.2.1 リリースに関する情報を追加しました。 |

## [!DNL Adobe Target Standard/Premium] 22.1.1（2022年1月12日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 1月31日（PT） | [Target リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 22.2.1 リリースに関するプレリリース情報を追加しました。 |
| 1月28日（PT） | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | at.js 2.8.1 リリースに関する情報を追加しました。 |
|  | [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}をインストールします。 | at.js 2.8.1 リリースに関する情報を追加しました。 |
| 1月27日（PT） | [AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | トピックを更新し、[!DNL AEM as a Cloud Service] および [!DNL Adobe I/0] に関する情報を追加しました。 |
| 1月26日（PT） | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.1.2 リリースに関する情報を追加しました。 |
|  | [オーディエンスの作成](/help/main/c-target/c-audiences/audiences.md) | [!DNL Adobe Experience Platform] オーディエンスに関する情報を追加しました。 |
|  | [複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md) | [!DNL Adobe Experience Platform] オーディエンスに関する情報を追加しました。 |
| 1月21日（PT） | [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | at.js 1.8.3 リリースに関する情報を追加しました。 |
| 1月19日（PT） | [at.js 1.*x* から at.js 2.*x*](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 以下の節を追加しました。「at.js 2.*x* では、vst を使用したオーディエンスの作成はサポートされていません。サポートされていません」 |
| 1月12日（PT） | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.1.1 リリースに関する情報を追加しました。 |
|  | [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank} | Web SDK で [!DNL Adobe Experience Cloud] を実装する手順を示すチュートリアルへのリンクを追加しました。 |
