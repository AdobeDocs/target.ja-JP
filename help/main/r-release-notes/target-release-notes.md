---
keywords: リリースノート；リリース；アップデート；今後のリリース；機能強化；新機能；修正；アップデート；プレリリース；早期アクセス
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7924bf0238eeba92be286441f537bfe84e93060e
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 41%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2025年3月6日（PT）**

>[!NOTE]
>
>リリース日、機能などの情報は、予告なく変更されることがあります。
>
>最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

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

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
