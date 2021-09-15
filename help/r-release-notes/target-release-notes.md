---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースで追加される新機能
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 41%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021 年 9 月 14 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.js のサポート**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しはエラーなく失敗し、デフォルトコンテンツを提供することで [!DNL Target] アクティビティを実行しているページに影響を与えます。
>
>サイトで発生する可能性のある問題を回避するには、 [!DNL Adobe Experience Platform Web SDK] または at.js JavaScript ライブラリの最新バージョンに移行します。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

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

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
