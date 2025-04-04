---
keywords: リリースノート；リリース；アップデート；今後のリリース；機能強化；新機能；修正；アップデート；プレリリース；早期アクセス
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 0618d39fc5966c64cceea8f5bcccb625fc243ebb
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 38%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2025年4月2日（PT）**

>[!NOTE]
>
>リリース日、機能などの情報は、予告なく変更されることがあります。
>
>最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## Target 権限の更新（2025 年 4 月 22 日（PT））

この今後の更新により、[!DNL Target] インスタンス設定の組織管理が強化され、様々なテストやパーソナライゼーションチームにわたるアクティビティの配信に影響を与える可能性のある、誤った更新を防ぐことができます。

2025 年 4 月 22 日（PT）より、[!UICONTROL Product] と [!UICONTROL Solutions] の管理者のみが、ワークスペースでの役割に関係なく、[!UICONTROL Administration] セクションの設定を更新でき [!DNL Target] ようになります。 この権限を持たないユーザーは、[!UICONTROL Administration] のセクションに読み取り専用でアクセスできます。

詳しくは、[Target の管理 ](/help/main/administrating-target/start-target.md) を参照してください。

## [!DNL Target Standard/Premium] 25.4.1 （2025 年 4 月 2 日（Pt））

このリリースには、次の修正および更新が含まれています。

* エクスペリエンスオーディエンスがアクティビティから消える問題を修正しました。 （TGT-52003）
* 配信中に予期しない要素が発生する問題を修正しました。 （TGT-52011）
* オーディエンス表示ページ上のターゲティンググラフおよびアクティビティの編集中に顧客がオーディエンスを [!UICONTROL r] 示できない問題を修正しました。 （TGT-52050）
* [!UICONTROL Experience Targeting] （XT）アクティビティで、お客様がエクスペリエンスを優先順に並べ替えることができない問題を修正しました。 （TGT-52054）
* テキストスタイルの変更を元に戻すと、誤ったレンダリングが発生する問題を修正しました。 （TGT-51876）
* リダイレクトオファーを変更すると、[!DNL Target] がそのオファーに関連付けられた [!UICONTROL ClickTrack] セレクターも削除する問題を修正しました。 （TGT-51936）
* リク [!UICONTROL ClickTrack] ストのキャンセル時に [!DNL Target] がセレクターを誤って保存する問題を修正しました。 （TGT-51937）
* [!UICONTROL Goals & Settings] ページで mbox ピッカーを開いたり閉じたりしても、何も変更を加えずに「無効な名前」エラーが発生する問題を修正しました。 （TGT-51983）
* 従来の [!DNL Target] UI で作成されたアドホックオファーの編集がブロックされていた問題を修正しました。 （TGT-51984）
* カスタムコードを含むアドホックオファーがあるアクティビティの編集がブロックされていた問題を修正しました。 （TGT-51995）
* 結合されたオーディエンス定義を編集する際に、除外ルールがインクルージョンルールとして表示される問題を修正しました。 （TGT-51999）
* エクスペリエンスの編集中にカスタムコードが正しく表示されない問題を修正しました。 （TGT-52005）
* [!UICONTROL Insert Before] オプションでナビゲーションバーの前にコンテンツを挿入できない問題を修正しました。 （TGT-52031）
* レポートでデフォルトのエクスペリエンスを正しくハイライト表示できない問題を修正しました。 （TGT-51716）
* アクティビティの作成時に `default message [Invalid optionLocalIds: xx]]` メッセージがトリガーされる問題を修正しました。 （TGT-52038）

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
