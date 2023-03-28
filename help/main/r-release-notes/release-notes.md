---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: a29a52c38e80781697a9925bc1dd88bf9d99ebe1
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 60%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target] Standard/Premium 23.3.1（2023 年 3 月 29 日～30 日）

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **3月28日**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **3月29日**：アジア太平洋（APAC）地域
* **3月30日**：アメリカ地域

このリリースには、以下の新機能、拡張機能および修正が含まれています。

| 機能 | 詳細 |
|--- |--- |
| [!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]の最適化された A4T 指標<p>（リリース日：2023 年 3 月 30 日） | [!DNL Target] では、[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]アクティビティ用の [!UICONTROL A4T] を使用すると、二項イベントに基づいて指標を選択したり、継続イベントに基づいて指標を選択したりできます。<P>サポートされる指標には、次の変更点があることに注意してください。<ul><li>[!DNL Target]2023年9月9日（PT）まで、既存のアクティビティの以前の動作が維持されます。この日以降、既存のアクティビティを新しい動作に強制的に移行するため、サポートされていない指標を使用しているアクティビティは廃止されます。</li></ul>この機能と共に、次のチュートリアルが更新されました。<ul><li>[ [!DNL Analysis Workspace]  での[!UICONTROL 自動配分]アクティビティ用 A4T レポートの設定](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=ja){target=_blank}</li><li>[ [!DNL Analysis Workspace]  での [!UICONTROL 自動ターゲット]アクティビティ用 A4T レポートの設定](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=ja){target=_blank}</li></ul> |

* オーディエンスとアクティビティの同期が強化され、 [!DNL Adobe Experience Platform] および [!DNL Adobe Audience Manager] は [!DNL Target] UI を迅速に実行できます。 （TGT-44568）
* ユーザーが [!UICONTROL デフォルトの URL] under [!UICONTROL 管理] > [!UICONTROL Visual Experience Composer] > [!UICONTROL デフォルトの URL]. この変更により、お客様はデフォルトの URL を空の文字列に戻すことができます。これは、初回設定後は、以前は使用できませんでした。 （TGT-44577）
* 標準のオーディエンス（予約名のオーディエンス）を顧客が編集または削除できない制限を削除しました。 （TGT-44655）
* 「[!UICONTROL 完了]「 」オプションは、編集ボックスをロードする際に、 [!DNL Target] 作成時の UI [結合オーディエンス](/help/main/c-target/combining-multiple-audiences.md). （TGT-44079）
* 修正された [!UICONTROL 言語] の下部にあるリンク [!UICONTROL オーディエンス] ページで[!UICONTROL アカウント通信環境設定]」ページに貼り付けます。 （TGT-43562）
* お客様が [!UICONTROL A/B テスト] 選択後のアクティビティ [!UICONTROL Adobe Analytics] のオプション [!UICONTROL 管理] > [!UICONTROL レポート] > [!UICONTROL レポートExperience Cloudソリューション]. （TGT-44844）
* 顧客が [!UICONTROL 多変量分析テスト] 内から多くのエクスペリエンスを持つアクティビティ [!UICONTROL Visual Experience Composer] (VEC) を参照してください。 この [DOM パス](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) が VEC の最下部にある場合、顧客が最後のエクスペリエンスを表示できないことがありました。 （TGT-44578）
* ページで認証が必要な場合、またはリダイレクトを呼び出す場合に、VEC の参照 URL に現在のページが反映されない問題を修正しました。このページは通常のブラウザーセッションで表示されます。 （TGT-44350）
* 顧客が [!UICONTROL 非互換の条件をフィルター] 設定 [!UICONTROL Recommendations] > [!UICONTROL 設定]. （TGT-44398）
* 新しい [!DNL Recommendations] フィードが [!UICONTROL Analytics 分類] と、名前にドットが含まれるレポートスイートが表示されます。 （TGT-44598）
* 更新された [!DNL Target] 新しい [Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). （TGT-44459）
* でのサーバーサイドリクエストフォージェリ (SSRF) の試行を防ぐためのセキュリティの強化 [!DNL Recommendations] フィード。 （TGT-43769）
* お客様が [!DNL Recommendations] 画像名にが含まれる場合にデザイン [GB18030文字](https://en.wikipedia.org/wiki/GB_18030){target=_blank}. （TGT-44614）
* 一部の [GB18030文字](https://en.wikipedia.org/wiki/GB_18030){target=_blank} 逃げ出す [!UICONTROL 変更] 編集中のパネル [!UICONTROL テキスト/HTML] 活動の [!UICONTROL エクスペリエンス] ページ。 （TGT-44600）
* [!DNL Target] UI 全体でさまざまなローカライゼーションの修正を行いました。

## at.js バージョン 2.10.2（2023年3月7日（PT））

* `trackEvent` 関数が常にエラーを返す問題を修正しました。

すべての at.js リリースについて詳しくは、[at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}を参照してください。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに記載されていない、このガイドの更新点に関する詳細情報を表示します。<br>詳しくは、[ドキュメントの変更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認できます。<br>詳しくは、「[以前のリリースのリリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、[Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md)ページを参照してください。 |
