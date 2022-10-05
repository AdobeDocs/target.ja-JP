---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれているもの
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: c5445903e7bbab210d0e72200c54ab07975c21c5
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 49%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target] Standard/Premium 22.10.1（2022 年 10 月 6 日～7 日のタッグリリース）

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **10 月 5 日**:アジア太平洋 (APAC) 地域
* **10 月 6 日**:アメリカ地域
* **10 月 8 日**:ヨーロッパ、中東、アフリカ (EMEA) 地域

このリリースには、次の新機能、機能強化および修正が含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) エクスペリエンスフラグメント | AEMエクスペリエンスフラグメント機能の更新内容は次のとおりです。<ul><li>AEMエクスペリエンスフラグメントを、 [!UICONTROL オファー] リスト。 （TGT-43121）</li><li>顧客が JSON を挿入できる問題を修正しました。 [!UICONTROL エクスペリエンスフラグメント] は、VEC を使用する際にオファーを提供します（これはサポートされていません）。 JSON オファーは、 [!UICONTROL フォームベースのエクスペリエンス] 作成者 （TGT-43846）</li></ul>詳しくは、 AEM [エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| 新規 [!UICONTROL Visual Experience Composer] Google Chrome 用拡張機能 | 新しい [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] Chrome 用 (VEC) 拡張機能は、Chrome Web Store で入手できます。<br>2023 年 1 月から、現在の [!DNL Target] Googleでは Manifest V2 を使用した拡張機能が許可されないので、VEC ヘルパー拡張機能はGoogle Chrome では動作しなくなります。 新しい拡張機能をダウンロードして、で Web サイトの視覚的なオーサリングを続行します。 [!DNL Target] 新年から始まる。<br>以下のリンクは、Chrome Web Store の 2 つの拡張機能を示しています。<ul><li>[新しい拡張機能](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[古い拡張機能](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>詳しくは、 [Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| 最適化された A4T 指標： [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット]<br>（正確なリリース日は決定されます。） | 次の変更点に注意してください。<ul><li>バイナリ指標と最大化指標のサポートを [!UICONTROL Analytics for Target] A4T レポートの対象 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ</li><li>2023 年 2 月 20 日まで、既存のアクティビティの動作が保持されました。 この日以降、既存のアクティビティを新しい動作に強制的に移行するため、アクティビティは停止されます</li><li>2023 年 2 月 20 日以降、のサポート `averagetimespentonsite`, `bouncerate`、および `entries` 指標 [!DNL Target] アクティビティは非推奨となります。</li></ul> |

* オーディエンスルールの情報が [!UICONTROL Audiences の絞り込み] 情報ウィンドウ。 （TGT-43917）
* のパフォーマンスを向上しました [!DNL Target] UI ( [ターゲット設定ルールの推奨制限](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). （TGT-43675）
* 一部のコンポーネントが [!UICONTROL 変更] パネル [!UICONTROL エクスペリエンス] ページ (VEC でアクティビティを作成または編集する際、 [!UICONTROL 作成] から [!UICONTROL 参照] モード。 （TGT-43300）
* 一部の顧客をアーカイブできない問題を修正しました [!UICONTROL A/B テスト] 使用するアクティビティ [!UICONTROL 自動ターゲット]. （TGT-40978）
* 1 つのレポートグループ内の複数の場所で 1 つのオファーを自動的に使用する機能が追加されました。 （TGT-40689）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報を表示します。<br>詳しくは、[ドキュメントの変更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](/help/main/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、[Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md)ページを参照してください。 |
