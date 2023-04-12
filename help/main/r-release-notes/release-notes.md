---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: a791fbe805735b278f650ff1f087b85898a66a07
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 87%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target] Standard／Premium 23.3.1（2023年3月28～30日（PT））

このリリースは、次のように時間をずらして使用できます。

* **3月28日**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **3月29日**：アジア太平洋（APAC）地域
* **3月30日**：アメリカ地域

このリリースには、以下の新機能、拡張機能および修正が含まれています。

| 機能 | 詳細 |
|--- |--- |
| [!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]の最適化された A4T 指標<p>（リリース日：2023年3月30日（PT）） | [!DNL Target] では、[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]アクティビティ用の [!UICONTROL A4T] を使用すると、二項イベントに基づいて指標を選択したり、継続イベントに基づいて指標を選択したりできます。<P>サポートされる指標には、次の変更点があることに注意してください。<ul><li>[!DNL Target]2023年9月9日（PT）まで、既存のアクティビティの以前の動作が維持されます。この日以降、既存のアクティビティを新しい動作に強制的に移行するため、サポートされていない指標を使用しているアクティビティは廃止されます。</li></ul>詳しくは、 [A4T のサポート対象 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported).<br>この機能により、次のチュートリアルが更新されました。<ul><li>[ [!DNL Analysis Workspace]  での[!UICONTROL 自動配分]アクティビティ用 A4T レポートの設定](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=ja){target=_blank}</li><li>[ [!DNL Analysis Workspace]  での [!UICONTROL 自動ターゲット]アクティビティ用 A4T レポートの設定](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=ja){target=_blank}</li></ul> |

* [!DNL Adobe Experience Platform] および [!DNL Adobe Audience Manager] で作成した項目が [!DNL Target] UI でより迅速に使用できるように、オーディエンスとアクティビティの同期を強化しました。（TGT-44568）
* ユーザーが [!UICONTROL デフォルトの URL] under [!UICONTROL 管理] > [!UICONTROL Visual Experience Composer] > [!UICONTROL デフォルトの URL]. この変更により、お客様はデフォルトの URL を空の文字列に戻すことができます。以前は初回設定後にはできませんでした。（TGT-44577）
* お客様が標準のオーディエンス（予約済みの名前を持つオーディエンス）を編集または削除できないようにする制限を削除しました。（TGT-44655）
* [結合されたオーディエンス](/help/main/c-target/combining-multiple-audiences.md)を作成する際に、読み込みスピナーが [!DNL Target] UI に表示されている間、「[!UICONTROL 完了]」オプションを無効にしました。（TGT-44079）
* [!UICONTROL オーディエンス]ページの下部にある[!UICONTROL 言語]リンクを修正して、「[!UICONTROL アカウント通信環境設定]」ページに正しくリンクするようにしました。（TGT-43562）
* [!UICONTROL 管理]／[!UICONTROL レポート]／[!UICONTROL Experience Cloud のレポートソリューション]で「[!UICONTROL Adobe Analytics]」オプションを選択した後、お客様が [!UICONTROL A/B テスト]アクティビティを作成できない場合があるという問題を解決しました。（TGT-44844）
* [!UICONTROL Visual Experience Composer]（VEC）内からの多くのエクスペリエンスを含む[!UICONTROL 多変量分析テスト]アクティビティで、お客様が最後のエクスペリエンスを表示できない問題を修正しました。VEC の下部にある [DOM パス](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)により、お客様が最後のエクスペリエンスを表示できないことがありました。（TGT-44578）
* ページで認証を必要とするか、リダイレクトを呼び出す場合に、VEC の参照 URL が、通常のブラウザーセッションで表示される現在のページを反映しない問題を修正しました。（TGT-44350）
* お客様が [!UICONTROL Recommendations]／[!UICONTROL 設定]で[!UICONTROL 互換性のない条件をフィルター]設定を変更できない問題を修正しました。（TGT-44398）
* POSTリクエストの [!DNL Recommendations] フィードが [!UICONTROL Analytics 分類] と、名前にドットが含まれるレポートスイートが表示されます。 （TGT-44598）
* [!DNL Target] UI のリンクを更新して、新しい [Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)をポイントするようにしました。（TGT-44459）
* [!DNL Recommendations] フィードでのサーバーサイドリクエストフォージェリ（SSRF）の試行を防ぐためのセキュリティを強化しました。（TGT-43769）
* [!DNL Target] UI 全体でさまざまなローカライゼーションの修正を行いました。

## at.js バージョン 2.10.2（2023年3月7日（PT））

* `trackEvent` 関数が常にエラーを返す問題を修正しました。

すべての at.js リリースについて詳しくは、[at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}を参照してください。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja){target=_blank} | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| [ドキュメントの変更点](/help/main/r-release-notes/doc-change.md) | リリースノートに記載されていない、このガイドの更新点に関する詳細情報を表示します。 |
| [以前のリリースのリリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md). | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認できます。 |
| [Adobe Experience Cloud のリリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [Adobe Priority Product Update](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | への今後の製品強化に関する事前通知を受け取る [!DNL Target] その他 [!DNL Adobe Experience Cloud] ソリューション |
| [Target リリースノート — プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、今月の Target リリースに関する情報です。 |
