---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート；現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: d5d7a57ce6a3188f02e680c24849d773cb53457a
workflow-type: tm+mt
source-wordcount: 630
ht-degree: 43%

---

# [!DNL Target] リリースノート（最新）

[!DNL Adobe Target]の最新の機能、機能強化、および修正について説明します。 このリリースノートでは、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、および該当する場合はその他のプラットフォームコンポーネントのアップデートについても説明します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）


## 最新アップデート - 2026年5月12日（PT）

**[!DNL Adobe Target]MCP サーバー（パブリック Beta）**

[!DNL Adobe Target]は、MCP互換アプリケーション内で実験、パーソナライゼーション、レポート操作を直接表示するMCP （Model Context Protocol） サーバーを提供するようになりました。 この統合により、マーケティング部門と技術部門のペルソナは、A/B テストの検査、パフォーマンスレポートの分析、オーディエンスとオファーの調査を行うことができます。これらはすべて、複数のUI画面を移動したり、REST APIに対してクエリを記述したりするのではなく、自然言語のプロンプトを使用します。 [!DNL Adobe Target]この機能は現在、**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**、および&#x200B;**ChatGPT**&#x200B;で利用できます。

この機能は、パブリック Betaのすべてのユーザーが利用できます。

詳しくは、[[!DNL Adobe Target] MCP サーバー](../c-integrating-target-with-mac/mcp/target-mcp.md)を参照してください。


## [!DNL Target Standard/Premium] 26.5.1 （2026年5月7日）

**統合**

+++詳細を見る

* Experimentation Acceleratorの&#x200B;**[!DNL Adobe Target]管理。** Experimentation Accelerator サンドボックスに[!DNL Target]個のワークスペースを割り当てるためのサポートが追加され、Experimentation Acceleratorの[!DNL Adobe Target]の実験を1か所で確認できるようになりました。 [詳細情報](../c-integrating-target-with-mac/experimentation-accelerator.md)

+++

**アクティビティ**

+++詳細を見る

* テーブルとダウンロードの同期が&#x200B;**[!UICONTROL Graph View]から失われました。** **[!UICONTROL Table View]**&#x200B;とダウンロードしたレポートに正しい値が表示されていても、一部の日付範囲の&#x200B;**[!UICONTROL Graph View]**&#x200B;でアクティビティレポートに欠落またはゼロの指標が表示される場合がある問題を修正しました。 （TGT-54998）

+++

**[!UICONTROL Audiences]**

+++詳細を見る

* **オーディエンス使用リストが完全にレンダリングされていません。** オーディエンスの詳細の&#x200B;**[!UICONTROL Usage]** セクションで、追加のアクティビティがそのオーディエンスに関連付けられている場合でも、マッピングされたアクティビティのサブセットのみを表示できる問題を修正しました。 （TGT-55094）

+++

**[!UICONTROL Administration]**

+++詳細を見る

* **最後のオクテット IPの難読化に関する確認がより明確になります。** **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**&#x200B;で&#x200B;**[!UICONTROL Obfuscate Visitor IP addresses]**&#x200B;を&#x200B;**[!UICONTROL Last octet]**&#x200B;に変更すると、確認ダイアログに、[!DNL Target]が訪問者IP アドレスの最後のオクテットを非表示にすることが説明されるようになりました。 （TGT-44821）

+++

**[!UICONTROL Visual Experience Composer]（VEC）**

+++詳細を見る

* **拡張Experience Composer （EEC）を使用した空白または不完全なページ。** **[!UICONTROL Enhanced Experience Composer]**&#x200B;が有効になっているときに[!UICONTROL Visual Experience Composer]がエディターでサイトを読み込めない問題を修正しました。 （TGT-54576）

+++


<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)




**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## 知っておく必要がある時間的制約のある更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

[!DNL Adobe Target]およびお客様の実装に関連する時間制限のある更新については、[!DNL Adobe]が[!UICONTROL Experience League]を通じて詳細なリリースノートとドキュメントを提供します。 Adobe Workfrontの導入に関する重要なハイライトを以下に示します。

### [!DNL Target] UI バージョン トグルの非推奨化

詳しくは、[[!DNL Target] UIの更新に関するFAQ](/help/main/c-intro/updated-ui-faq.md)を参照してください。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| [ドキュメントの変更点](/help/main/r-release-notes/doc-change.md) | リリースノートに記載されていない、このガイドの更新点に関する詳細情報を表示します。 |
| [以前のリリースのリリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 以前のリリースの Target Standard および Target Premium の新機能および拡張機能に関する情報を確認できます。 |
| [Adobe Experience Cloud リリースノート ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [Adobe 優先製品のアップデート](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | [!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションに対する今後の製品の機能強化に関する事前通知を受信します。 |
| [Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、当月の Target リリースに関する情報です。 |
