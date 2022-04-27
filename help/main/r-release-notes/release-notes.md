---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれているもの
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 25dac5f4712fec80323df9b0e00feb9750f5b155
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 56%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、 [!DNL Target] API、SDK、 [!DNL Adobe Experience Platform Web SDK]、at.js およびその他のプラットフォームの変更も、該当する場合は含まれます。

括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。

## [!DNL Target] プラットフォームリリース（2022 年 4 月 28 日）

このリリースには、次の変更が含まれています。

* このリリースでは、次の用にコンテンツをプリフェッチできます： [!UICONTROL 自動パーソナライゼーション] (AP) および [!UICONTROL 自動ターゲット] (AT) アクティビティ（以前はから返されていませんでした） [!DNL Target]) をクリックします。 AP/AT アクティビティが配信パス上にあり、コンテンツ配信に同じ場所を使用する他の AB/XT アクティビティよりも優先度が高い場合、プリフェッチ呼び出し（「実行」フローに対する変更なし）の場合にエンドユーザーに表示されるエクスペリエンスが変更されます。

## Target プラットフォームリリース（2022 年 4 月 14 日）

このリリースには、次の更新が含まれています。

* プロファイルスクリプトを使用して取り込む際に、IP アドレスの最後のオクテットが適切に不明化される問題を修正しました。 （TNT-44076）

## [!DNL Target Standard/Premium] 22.3.1（2022 年 4 月 6 日）

このリリースには、次の変更および機能強化が含まれています。

* 次の問題を修正しました： [!UICONTROL 次を含む] および [!UICONTROL 除外] アクティビティの編集時に結合オーディエンスで無効にするオプション。 （TGT-43422）
* アクティビティの編集中に、一部のお客様が利用可能なオーディエンスのリストを表示できなかった問題を修正しました。 （TGT-43404）
* 一部のお客様が「[!UICONTROL 除外する IP [!DNL Target] レポートデータ]&quot;リスト [!UICONTROL 管理] > [!UICONTROL レポート]. （TGT-43384）
* オーディエンス条件で、任意の変数が「より大きい」、「より大きいか等しい」、「より小さい」または「より小さいか等しい」であることを確認できない負の数を使用する問題を修正しました。 （TGT-43367）
* 顧客が [!UICONTROL オーディエンスの詳細] カードを使用して結合オーディエンスを作成できます。 （TGT-43303）

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
