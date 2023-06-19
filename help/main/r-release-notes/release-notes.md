---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 3349b3a948186a18093adfc4580c5134e9ef7fc7
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 98%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target] Standard／Premium 23.5.2（2023年5月31日（PT））

このリリースには、以下の機能強化および修正が含まれています。

* Profile API 認証トークンの生成時に空のページが表示される問題を修正しました。（TGT-45387 および TGT-45423）
* 画像名に GB 18030 文字が含まれている場合、[!UICONTROL デザインを作成]パネルに画像が表示されない問題を修正しました。（TGT-44614）
* エクスペリエンスのテキスト／HTML で、一部の GB 18030 記号文字が正しくエスケープされなかった問題を修正しました。（TGT-44600）
* 分析中に[!UICONTROL 自動パーソナライゼーション]アクティビティのレポートがフリーズする問題を修正しました。（TGT-44820）
* アクティビティ名に角括弧（[!UICONTROL  または ]）が含まれている場合、[アクティビティ]ページでアクティビティを検索できない問題を修正しました。（TGT-44777）
* アクティビティの目標に特殊文字が含まれる場合、アクティビティを同期できない問題を修正しました。（TGT-44982）
* 特定の顧客のデフォルトワークスペースの [!DNL Target] UI にアクティビティが表示されない問題を修正しました。（TGT-45286）
* 「重複を許可しない」フラグの動作を更新しました。除外された繰り返しオファーのフラグが更新され、デフォルトコンテンツオファー（API v3、v4 の場合）の場合は繰り返しオファーを許可し、オプションがデフォルトコンテンツオファーを参照していてテンプレートが定義されていない場合は重複オプションを許可するようになりました。（TNT-46617）
* URL にクエリパラメーターが追加され、[!UICONTROL Visual Experience Composer]（VEC）でページが読み込めなくなる問題を修正しました。（TGT-44873）
* [!DNL Target] UI 全体で様々なローカライゼーションの修正を行いました。

## Real-Time CDPプロファイル属性の共有先 [!DNL Target] [!UICONTROL Real-Time CDP Profile Attributes] （2023 年 6 月 14 日）

このリリースで強化された機能は次のとおりです。

| 機能 | 詳細 |
|--- |--- |
| [!DNL Target] と共有される Real-Time CDP プロファイル属性 | [!UICONTROL Real-Time CDP プロファイル属性]は、HTML オファーと JSON オファーで使用するために [!DNL Target] と共有できます。<P>詳しくは、[Real-Time CDP プロファイル属性の [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes) との共有を参照してください。 |

## [!DNL Target] Standard／Premium 23.5.1（2023年5月23～25日（PT））

このリリースは、以下の時差スケジュールに従って利用できるようになります。

5月23日（PT）：ヨーロッパ、中東、アフリカ（EMEA）地域
5月24日（PT）：アジア太平洋（APAC）地域
5月25日（PT）：アメリカ地域

このリリースには、以下の新しい機能強化および修正が含まれています。

* 特定の顧客が、「次よりも大きい」または「次よりも小さい」演算子を使用して訪問者プロファイルを含むオーディエンスを作成できなかった問題を修正しました。（TGT-45271）
* [!DNL Target] UI 全体で様々なローカライゼーションの修正を行いました。
* 今後の UI の更新に備え、様々な場所で Target UI を更新しました（アップデートがリリースされるまで、変更は機能フラグの背後にあります）。

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
