---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート；現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: aab659046a6583aeedaf8ec34803b0751bebe3c6
workflow-type: tm+mt
source-wordcount: 546
ht-degree: 49%

---

# [!DNL Target] リリースノート（最新）

[!DNL Adobe Target]の最新の機能、機能強化、および修正について説明します。 このリリースノートでは、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、および該当する場合はその他のプラットフォームコンポーネントのアップデートについても説明します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target Standard/Premium] 26.6.8 （2026年6月24日）

**アクティビティ**

+++詳細を見る

* **APIおよびMCP用のSource フィルターがリソースを作成しました。** [!UICONTROL Adobe Target API]または[!UICONTROL Adobe Target MCP]によるフィルタリングが、アクティビティ、オーディエンス、およびオファーのリストページで機能しない問題を修正しました。 （TGT-55236）

* **アクティビティソースフィルターの値。** [!UICONTROL Adobe Target API]または[!UICONTROL Adobe Target MCP] ソースフィルターで新しく作成されたオーディエンスが表示されない問題を修正しました。 （TGT-55237）

+++

**ローカライズ**

+++詳細を見る

* [!UICONTROL JSON オファーの作成] モーダルの&#x200B;**ローカライズされていない文字列。** [!UICONTROL 名前]と[!UICONTROL Workspace]を含む[!UICONTROL Create JSON Offer] モーダルの文字列が、アクティビティの作成中にローカライズされない問題を修正しました。 （TGT-50084）

* [!UICONTROL Recommendations] アクティビティの&#x200B;**ローカライズされていないトーストメッセージ。** フォームベースの[!UICONTROL Recommendations] アクティビティでレコメンデーションを追加する際に、ローカライズされていないトーストメッセージが表示される問題を修正しました。 （TGT-50463）

* [!UICONTROL &#x200B; コレクション &#x200B;]および[!UICONTROL 除外] ダイアログの&#x200B;**ローカライズされていない文字列。** [!UICONTROL Recommendations]の[!UICONTROL &#x200B; コレクション &#x200B;]および[!UICONTROL 除外] ダイアログで「項目ペイロード」文字列がローカライズされない問題を修正しました。 （TGT-51542）

* **ローカライズされていない「承認者」文字列（[!UICONTROL &#x200B; オーディエンス &#x200B;] タブ）。** [!UICONTROL Audience Library] ページの[!UICONTROL Workspace]列で「承認者」文字列がローカライズされない問題を修正しました。 （TGT-51751）

+++

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
| [Adobe Experience Cloud リリースノート &#x200B;](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [Adobe 優先製品のアップデート](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | [!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションに対する今後の製品の機能強化に関する事前通知を受信します。 |
| [Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、当月の Target リリースに関する情報です。 |
