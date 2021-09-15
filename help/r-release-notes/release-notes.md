---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれる新機能
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 57%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

>[!IMPORTANT]
>
>**mbox.js のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しは失敗し、デフォルトのコンテンツを表示して [!DNL Target] アクティビティを実行しているページには影響があります。
>
>サイトに起こりうる問題を回避するため、新しい [!DNL Adobe Experience Platform Web SDK] の最新バージョンまたは at.js JavaScript ライブラリの最新バージョンに移行してください。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

## [!DNL Target Standard/Premium] 21.9.1（2021年9月15日）

このメンテナンスリリースには、以下の機能強化、修正および変更が含まれています。

* 一部のWebブラウザーで、サードパーティCookieのセキュリティポリシーが新しく設定されたため、お客様が[!UICONTROL Visual Experience Composer](VEC)にログインできなかった問題を修正しました。 この問題は、Visual Experience Composerと拡張Experience Composerに関連する問題のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)の「Google Chromeバージョン80以降を使用する場合のVisual Experience Composer(VEC)または拡張Experience Composer(EC)での読み込まれないページ」で説明されました。[
* VECのオファー名に、オファーのわかりやすい名前ではなくオファーのパスが表示される問題を修正しました。 （TGT-41300）
* エクスペリエンス名がA4Tアクティビティの[!DNL Analysis Workspace]に反映されるようになりました(TGT-38674)
* 元のアクティビティに複製されたアクティビティのプロモーションで、誤って適用されたエンティティIDの変更が発生する問題を[!DNL Recommendations]で修正しました。 （TGT-41482）
* VECの[!DNL Recommendations]アクティビティの[!UICONTROL エクスペリエンス]ページに「条件を編集」ボタンが正しく表示されない問題を修正しました。 （TGT-39512）
* 複製してテストワークスペースにコピーした場合に、アクティビティの同期ができない問題を修正しました。 （TGT-40686）
* VECで「[!UICONTROL 後に挿入]」を使用している場合に、[エクスペリエンスフラグメント](/help/c-experiences/c-manage-content/aem-experience-fragments.md)でセレクターを変更できなかった問題を修正しました。 （TGT-41802）
* オファー内の空のJSONコンテンツがバックエンドに送信されない問題を修正しました。 [!DNL Target] は、空の場合でもJSONオブジェクトを送信するようになりました。（TGT-41555）
* レポートの表示中に「[!UICONTROL Analyticsで表示]」をクリックすると、従来の[!DNL Analytics]レポートが[!DNL Analysis Workspace]ではなく開く問題を修正しました。 （TGT-41867）
* 顧客が[!UICONTROL Automated Personalization]アクティビティのレポートソースとして[!DNL Analytics]を選択(A4T)しようとした場合に表示されるUIメッセージに明確な説明を追加しました。 メッセージには、「[!DNL Target]は[!UICONTROL Automated Personalization]アクティビティでサポートされている唯一のソースです」と記載されています。 （TGT-41954）
* お客様がホストをコンマではなく「改行」で区切る場合のエラーメッセージに説明を追加しました。 （TGT-40671）
* 一部のアクティビティの「[!UICONTROL 最終更新日]」の日付が、スペイン語および日本語のお客様の英語のUIと異なる問題を修正しました。 （TGT-38980）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報を表示します。<br>詳しくは、「[ドキュメントの変更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](/help/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、[Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe 優先製品のアップデート | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
