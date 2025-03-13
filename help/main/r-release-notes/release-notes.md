---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート、現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 729b88c3db9e88a5cd428587e34614c5d56542da
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 45%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target Standard/Premium] 25.3.5 （2025 年 3 月 11 日（PT））

このリリースには、次の修正および更新が含まれています。

* [!UICONTROL Modifications] ールパネルでユーザーがオファーを変更できない問題を修正しました。 （TGT-51800）
* [!UICONTROL ClickTrack] モードを含め、エクスペリエンスとオーディエンスの左側のパネルにアクションが正しく表示されない問題を修正しました。 （TGT-51895）
* [!UICONTROL ClickTrack] セレクターが正しいオーディエンスページに適用されない問題を解決しました。 （TGT-51871）

## [!DNL Target Standard/Premium] 25.3.4 （2025 年 3 月 7 日（PT））

このリリースには、次の修正および更新が含まれています。

* アクティビティのみのオーディエンスが [!UICONTROL Audiences] ールパネルに表示されず、編集や再利用ができない問題を修正しました。 （TGT-51860）
* [!DNL Target Standard] 顧客が [!UICONTROL Analytics for Target] （A4T）レポートを使用してアクティビティを作成できなかった問題を修正しました。 （TGT-51854）
* バッチの作成および編集操作中にペイロードからローカル ID カウンターを除外する問題を修正しました。 （TGT-51867）

## [!DNL Target Standard/Premium] 25.3.2 （2025 年 3 月 6 日（PT））

このリリースには、次の修正および更新が含まれています。

* アクティビティのみのオーディエンスを持つアクティビティをコピーしたときに、新しいアクティビティを作成できず、元のアクティビティのオーディエンスが誤って使用されていた問題を修正しました。 （TGT-51855）
* アクティビティのみのオーディエンスを含む [!UICONTROL Experience Targeting] （XT） アクティビティを編集できない問題を修正しました。 （TGT-51846）
* [!UICONTROL Visual Experience Composer] （VEC）が最初の編集でエクスペリエンスに変更を正しく適用できなかった問題を修正しました。 （TGT-51843）
* VEC 内の特定の要素をクリックすると「ID」エラーがトリガーされる問題を修正しました。 （TGT-51814）
* アクティビティ作成時の VEC のエラー処理を更新しました。 （TGT-51759）
* [!UICONTROL Modifications] パネルに表示が見つからない場合、アクティビティの保存時に「無効なユーザー入力」エラーが発生する問題を修正しました。 （TGT-51827）
* Recommendations 条件を作成できない問題を修正しました。 （TGT-51834）
* 別の URL にリダイレクトする前に確認メッセージを追加しました。 （TGT-51703）
* オファーおよびフォルダー内のGraphQL統合テストの問題を修正しました。 （TGT-51839）

## [!DNL Target Standard/Premium] 25.3.1 （2025 年 3 月 3 日）

このリリースには、次の修正および更新が含まれています。

* 結合されたオーディエンスには、サブグループを含めることができ、それぞれに複数のオーディエンスを含めることができます。 このリリースでは、サブグループオーディエンスが [!UICONTROL Rules] ダイアログボックスに表示されない問題を修正しました。 （TGT-51813）
* 古いアクティビティを開く際に、一部のエクスペリエンスオーディエンスが [!UICONTROL All Visitors] に置き換えられた問題を修正しました。 （TGT-51812）
* アクティビティのみのオーディエンスを含むアクティビティを編集できない問題を修正しました。 （TGT-51807）
* 更新された [!DNL Target] UI でページ先頭の変更を編集できない問題を修正しました。 （TGT-51797）
* エクスペリエンスを複製し、別のエクスペリエンスを削除してから、アクティビティを保存しようとすると発生していた null エラーを解決しました。 （TGT-51796）
* アクティビティを作成する [!UICONTROL Targeting] の手順で、オーディエンスの情報パネルにオーディエンス除外ルールが表示されない問題を解決しました。 （TGT-51579）
* エラーメッセージを韓国語にローカライズしました。 （TGT-51701 および TGT-51699）

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
| [Adobe Experience Cloud のリリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [アドビ優先製品アップデート](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | [!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションに対する今後の製品の機能強化に関する事前通知を受信します。 |
| [Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、当月の Target リリースに関する情報です。 |
