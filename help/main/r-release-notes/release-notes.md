---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e458793e4d0110d97f3f5124cbe6e54520d3f0e9
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 69%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target] Standard/Premium 22.15.1（2023 年 3 月 9 日）

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **3 月 9 日**:アメリカ地域
* **3 月 9 日**:ヨーロッパ、中東、アフリカ (EMEA) 地域
* **3 月 9 日**:アジア太平洋 (APAC) 地域

このリリースには、次の新機能および機能強化が含まれています。

| 機能 | 詳細 |
| --- | --- |
| 最適化された A4T 指標： [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] | [!DNL Target] を使用すると、バイナリイベントに基づいて指標を選択したり、 [!UICONTROL A4T] 対象 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ。<P>サポートされる指標に関して、次の時間的制約があることに注意してください。<ul><li>[!DNL Target] 2023 年 9 月 10 日まで、既存のアクティビティの以前の動作を保持していました。 この日以降、サポートされていない指標を使用するアクティビティは、既存のアクティビティを新しい動作に強制的に移行するために、終了します。</li></ul>詳しくは、 [サポートされる目標指標](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) in *自動配分と自動ターゲットアクティビティに対する A4T のサポート*. |
| [!UICONTROL 自動配分] using [!UICONTROL Analytics for Target] (A4T) | 新しいチュートリアル：<ul><li>[での A4T レポートの設定 [!DNL Analysis Workspace] 対象 [!UICONTROL 自動配分] アクティビティ](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| [!UICONTROL 自動ターゲット] using [!UICONTROL Analytics for Target] (A4T) | 新しいチュートリアル：<ul><li>[での A4T レポートの設定 [!DNL Analysis Workspace] 対象 [!UICONTROL 自動ターゲット] アクティビティ](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=ja){target=_blank}</li></ul> |

## at.js バージョン 2.10.2（2023 年 3 月 7日）

* 次の問題を修正しました： `trackEvent` 関数を使用して、常にエラーを返します。

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
