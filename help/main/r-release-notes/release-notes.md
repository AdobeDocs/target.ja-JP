---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれているもの
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: a03975f8f14db3cb8be0850130aab8d34c4c7fc0
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 47%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、 [!DNL Target] API、SDK、 [!DNL Adobe Experience Platform Web SDK]、at.js およびその他のプラットフォームの変更も、該当する場合は含まれます。

括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。

## Target プラットフォームリリース（2022 年 4 月 14 日）

このリリースには、次の更新が含まれています。

* プロファイルスクリプトを使用して取り込む際に、IP アドレスの最後のオクテットが適切に不明化される問題を修正しました。 （TNT-44076）

## [!DNL Target Standard/Premium] 22.3.1（ちらつきリリース、日付決定）

このリリースには、次の変更および機能強化が含まれています。

* スクリプトを編集、アクティブ化、非アクティブ化した後で、プロファイルスクリプトの編集が元の未編集スクリプトに戻る問題を修正しました。 プロファイルスクリプトは編集された状態のままになります。 （TGT-43249）
* 次のエラーメッセージが [!DNL Target] ステータスが「ドラフト」のアクティビティで使用されているオーディエンスを移動する際の UI:「お客様のご要望は、完了できません。 問題が解決しない場合は、Adobeのクライアントケアにお問い合わせください。」 （TGT-43212）
* 次の問題を修正しました： [!UICONTROL 次を含む] および [!UICONTROL 除外] アクティビティの編集時に結合オーディエンスで無効にするオプション。 （TGT-43422）
* アクティビティの編集中に、一部のお客様が利用可能なオーディエンスのリストを表示できなかった問題を修正しました。 （TGT-43404）
* 一部のお客様が「[!UICONTROL 除外する IP [!DNL Target] レポートデータ]&quot;リスト [!UICONTROL 管理] > [!UICONTROL レポート]. （TGT-43384）
* オーディエンス条件で、任意の変数が「より大きい」、「より大きいか等しい」、「より小さい」または「より小さいか等しい」であることを確認できない負の数を使用する問題を修正しました。 （TGT-43367）
* 顧客が [!UICONTROL オーディエンスの詳細] カードを使用して結合オーディエンスを作成できます。 （TGT-43303）
* 次の問題を修正しました： [!DNL Target] UI または新規 [!UICONTROL オーディエンス] 一部の顧客に対して、UI が早めにタイムアウトする。 （TGT-42590 および TGT-43273）

## [!DNL Target] Platform リリース（3 月 31 日）

このリリースで強化された機能は次のとおりです。

* クリック追跡指標では、Analytics をレポートソースに使用し (A4T)、クライアント側でイベントを処理するアクティビティの Delivery API リクエストに Analytics ペイロードが含まれます。 （TNT-43073）

## [!DNL Target Standard] オーディエンスの更新（3 月 28 日）

このリリースには、次の更新が含まれています。

* 新しい [!UICONTROL オーディエンス] UI はすべての [!DNL Target Standard] 顧客。

## Target Standard/Premium の顧客エンジニアリングの修正（2022 年 3 月 23 日）

このメンテナンスリリースで強化された機能は次のとおりです。

* が返す機能を追加しました。 [!DNL Analytics] ペイロードデータ `prefetch` ビューと `pageLoad` 使用時のクリック指標 [!UICONTROL 配信 API] を使用するアクティビティで [!UICONTROL レポートソースとしての Analytics] (A4T)。 （TNT-43198）
* ボットフィルタリングのユーザーエージェントリストが更新され、日本で一般的に使用されるブラウザータイプを許可するようになりました。 （TNT-43867）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報を表示します。<br>詳しくは、「[ドキュメントの変更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](/help/main/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、[Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md)ページを参照してください。 |
