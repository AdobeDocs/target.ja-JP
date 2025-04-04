---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート、現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 0618d39fc5966c64cceea8f5bcccb625fc243ebb
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 47%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

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

## at.js バージョン 2.11.8 （2025 年 3 月 31 日）

* サイズ変更および移動操作中のエッジケースを防ぐために、文字列サフィックス検証で CodeQL が識別する脆弱性を解決しました。 （TNT-51516）

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
