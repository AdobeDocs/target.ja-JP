---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースではどのような新機能や機能強化が追加されますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 36c05ee2531009ea74ef9085404d12e389cef743
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 76%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2022年10月5日（PT）**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target] Standard／Premium 22.10.1（時差リリース 2022年10月10～13日（PT））

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **10月10日（PT）**：アジア太平洋（APAC）地域
* **10月12日（PT）**：アメリカ地域
* **10月13日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域

このリリースには、以下の新機能、拡張機能および修正が含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) エクスペリエンスフラグメント | AEMエクスペリエンスフラグメント機能の更新内容は次のとおりです。<ul><li>AEMエクスペリエンスフラグメントを、 [!UICONTROL オファー] リスト。 （TGT-43121）</li><li>未対応の VEC の使用時に、顧客が JSON [!UICONTROL エクスペリエンスフラグメント]オファーを挿入できる問題を修正しました。JSON オファーは、[!UICONTROL フォームベースの Experience] Composer を使用する場合にのみ挿入できます。（TGT-43846）</li></ul>詳しくは、 AEM [エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| Google Chrome 用の新しい [!UICONTROL Visual Experience Composer] 拡張機能 | Chrome 用の新しい [!DNL Adobe Target] [!UICONTROL Visual Experience Composer]（VEC）拡張機能は、Chrome web ストアで入手できます。<br>2023年1月以降、Google Chrome では、現在の [!DNL Target] VEC Helper 拡張機能が動作しなくなります。これは、Google がManifest V2 を使用した拡張機能を許可しないためです。新しい拡張機能をダウンロードすれば、新年から引き続き [!DNL Target] で web サイトを視覚的に作成できます。<br>以下のリンクは、Chrome web ストアの 2 つの拡張機能を示しています。<ul><li>[新しい拡張機能](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[古い拡張機能](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>詳しくは、 [Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| ドキュメントの更新 | 主なドキュメント更新内容は次のとおりです。<ul><li>新規および更新済み [Adobe Target管理およびレポート API ドキュメント](https://developer.adobe.com/target/administer/admin-api/){target=_blank} では、プロパティ、オファー、ホスト、環境、クライアント、オーディエンス、アクティビティなど、管理 API エンドポイントとレポート API エンドポイントの包括的な機能を提供しています。<br>この他の開発者向けコンテンツは、 [[!DNL Adobe Target] [!UICONTROL 開発者ガイド]](https://developer.adobe.com/target/){target=_blank}。</li><li>[A/Bn テストの統計指標](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>この記事では、 [!DNL Adobe Target].<br>この記事の情報は、 *Adobe Target A/B テストの計算* このサイトで以前にダウンロード可能だった pdf ファイル。</li></ul> |

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


## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
