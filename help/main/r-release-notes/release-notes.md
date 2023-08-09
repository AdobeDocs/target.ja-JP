---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e130c68c838e799228956c598c583038a2f68ecf
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 75%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Adobe Target] エッジで予定されているインフラストラクチャのアップグレード {#edge}

予定されているエッジインフラストラクチャのアップグレードでは、追加の IP またはドメインを許可リストに登録する必要があります。エッジデプロイメント 41～48 の NAT と IP／ドメインを確認して許可リストに登録します。インフラストラクチャのアップグレードは、2023年8月9日（PT）に開始されます。


詳しくは、*Adobe Target 開発者ガイド*&#x200B;の [Target のエッジノードを許可リストに登録](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=ja){target=_blank}を参照してください。

## [!DNL Target] Standard/Premium 23.8.1（2023 年 8 月 10 日）

このリリースには、以下の機能強化および修正が含まれています。

* アクティビティが正しく同期されない場合がある問題を修正しました (「[!UICONTROL ステータス]」列 [!UICONTROL アクティビティ] リストページに表示されます。 （TGT-46010 および TGT-44831）
* 「[!UICONTROL Analytics で表示]」リンクが [!UICONTROL レポート] 使用するアクティビティのページ [!UICONTROL Analytics for Target] (A4T) をレポートソースとして使用する場合。 （TGT-45808）
* 表内の値の表示を調整し、小数点以下の数字ではなくパーセンテージで表示するようにしました。 例えば、.08 ではなく 8%を指定します。 （TGT-45548）
* キーボードフォーカスを使用して [!UICONTROL 目標と設定] ～のページ [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ （TGT-44526）
* 「[!UICONTROL オーディエンスを追加]」ダイアログが表示されます。 （TGT-44525）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| [ドキュメントの変更点](/help/main/r-release-notes/doc-change.md) | リリースノートに記載されていない、このガイドの更新点に関する詳細情報を表示します。 |
| [以前のリリースのリリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 以前のリリースの Target Standard および Target Premium の新機能および拡張機能に関する情報を確認できます。 |
| [Adobe Experience Cloud のリリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [アドビ優先製品アップデート](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | [!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションに対する今後の製品の機能強化に関する事前通知を受信します。 |
| [Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、当月の Target リリースに関する情報です。 |
