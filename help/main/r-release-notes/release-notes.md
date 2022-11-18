---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれているもの
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 8c348f40be8df5018d63c6b6fe75e1f8e804eafc
workflow-type: ht
source-wordcount: '1001'
ht-degree: 100%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target] Standard／Premium 22.10.3（時差リリース 2022年10月25～27日（PT））

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **10月25日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **10月26日（PT）**：アジア太平洋（APAC）地域
* **10月27日（PT）**：アメリカ地域

このリリースには、以下の新機能、拡張機能および修正が含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]<br>用に最適化された A4T 指標（一部のお客様がテストを利用できます。 今後のリリースで、すべてのお客様が利用できるようになります。) | 次の変更点に注意してください。<ul><li>[!UICONTROL Analytics for Target] A4T レポートで、[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]アクティビティの非バイナリ指標と最大化指標のサポートを追加</li><li>2023年2月（PT）まで、既存のアクティビティの動作が維持されます。この日以降、既存のアクティビティを新しい動作に強制的に移行するため、アクティビティは廃止されます</li><li>2023年2月20日以降（PT）、[!DNL Target] アクティビティの `averagetimespentonsite`、`bouncerate`および  `entries` 指標のサポートは廃止されます。</li></ul> |

* [!DNL Target] UI にツールチップを追加して、顧客がオーディエンスビルダーをより効率的にナビゲートし、なじみのない機能の使用方法を学習できるようにしました。（TGT-44139）
* サポートされていない指標を使用しているために [!DNL Target] で無効にされたアクティビティを、顧客が編集できないようにする機能を追加しました。UI のメッセージは、顧客にアクティビティを複製してコンバージョン指標を更新するように指示します。

   このリリースでは、[!DNL Target] アクティビティの `averagetimespentonsite`、`bouncerate`、および `entries` 指標は新しいアクティビティに対して非推奨になります。 既存のアクティビティでは、2023年5月までこれらの指標を引き続き使用できます。

* [!DNL Target] UI にツールチップを追加しました。これにより、A4T を使用する[!UICONTROL 自動ターゲット]アクティビティの作成または編集中に顧客が最適化条件を選択できるようにします。

## [!DNL Target] Standard／Premium 22.10.1（時差リリース 2022年10月10～13日（PT））

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **10月10日（PT）**：アジア太平洋（APAC）地域
* **10月12日（PT）**：アメリカ地域
* **10月13日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域

このリリースには、以下の新機能、拡張機能および修正が含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!DNL Adobe Experience Manager]（AEM）エクスペリエンスフラグメント | AEM エクスペリエンスフラグメント機能の更新内容は次のとおりです。<ul><li>[!UICONTROL オファー]リストでタイプ（HTML または JSON）別に AEM エクスペリエンスフラグメントをフィルタリングできる機能が追加されました。（TGT-43121）</li><li>未対応の VEC の使用時に、顧客が JSON [!UICONTROL エクスペリエンスフラグメント]オファーを挿入できる問題を修正しました。JSON オファーは、[!UICONTROL フォームベースの Experience] Composer を使用する場合にのみ挿入できます。（TGT-43846）</li></ul>詳しくは、AEM [エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)を参照してください。 |
| Google Chrome 用の新しい [!UICONTROL Visual Experience Composer] 拡張機能 | Chrome 用の新しい [!DNL Adobe Target] [!UICONTROL Visual Experience Composer]（VEC）拡張機能は、Chrome web ストアで入手できます。<br>2023年1月以降、Google Chrome では、現在の [!DNL Target] VEC Helper 拡張機能が動作しなくなります。これは、Google がManifest V2 を使用した拡張機能を許可しないためです。新しい拡張機能をダウンロードすれば、新年から引き続き [!DNL Target] で web サイトを視覚的に作成できます。<br>以下のリンクは、Chrome web ストアの 2 つの拡張機能を示しています。<ul><li>[新しい拡張機能](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[古い拡張機能](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>詳しくは、[Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)を参照してください。 |
| ドキュメントの更新 | ドキュメントの主な更新内容は次のとおりです。<ul><li>新規および更新済みの [Adobe Target 管理 API およびレポート API ドキュメント](https://developer.adobe.com/target/administer/admin-api/){target=_blank}では、プロパティ、オファー、ホスト、環境、クライアント、オーディエンス、アクティビティなどの、管理 API エンドポイントとレポート API エンドポイントについて包括的に説明しています。<br>この開発者向けコンテンツとその追加コンテンツについては、[[!DNL Adobe Target] [!UICONTROL 開発者ガイド]](https://developer.adobe.com/target/){target=_blank}を参照してください。</li><li>[A/Bn テストの統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>この記事では、[!DNL Adobe Target] の手動 A/Bn テストで使用される統計計算を詳しく説明しています。<br>この記事の情報は、このサイトで以前にダウンロード可能だった *Adobe Target A/B テストの計算*&#x200B;の PDF ファイルに代わるものです。</li></ul> |

* オーディエンスルールの情報が[!UICONTROL オーディエンスの絞り込み]情報ウィンドウに正しく表示されない問題を修正しました。（TGT-43917）
* [ターゲティングルールの推奨制限](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules)に近づくオーディエンスを読み込む際の [!DNL Target] UI のパフォーマンスを改善しました。（TGT-43675）
* [!UICONTROL 作成]モードから[!UICONTROL 参照]モードに切り替えた後、VEC でアクティビティを作成または編集する際に、一部のコンポーネントが[!UICONTROL エクスペリエンス]ページの[!UICONTROL 変更]パネルに正しく表示されない問題を修正しました。 （TGT-43300）
* 一部の顧客が「[!UICONTROL 自動ターゲット]」を使用する [!UICONTROL A/B テスト]アクティビティをアーカイブできない問題を修正しました。（TGT-40978）
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
