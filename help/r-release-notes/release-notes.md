---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
title: 'Adobe Target リリースノート（現行） '
feature: Release Notes
translation-type: tm+mt
source-git-commit: 2dce7bbe94f20ad6f6732dfc3abceb69058a1f75
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 36%

---


# Target リリースノート（現行）

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。また、ターゲットAPI、SDK、JavaScriptライブラリ(at.js)およびその他のプラットフォームの変更に関するリリースノートも適宜含まれています。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリ [!DNL Adobe Target] はサポートされなくなります。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに今日までに移行することをお勧めします。
>
>* **Adobe Experience PlatformウェブSDK**: [!UICONTROL Adobe Experience PlatformWeb ] SDKを使用すると、Adobe Experience Edge Networkを介して、( [!DNL Experience Cloud] 含む [!DNL Target])様々なサービスをインタラクティブに操作できます。[!DNL Adobe Experience Platform Web SDK]に移行する場合は、『*Web SDKガイド*』の[Adobe Experience PlatformWeb SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)とは何ですかを参照してください。
   >
   >
* **at.js**:at.js JavaScriptライブラリは、mbox.jsよりも多くの利点を提供します。多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。 at.jsに移行する場合は、[At.jsの仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)と[Adobe Targetスキルビルダーを参照してください。開発者チャットで、Adobe Targetのmbox.jsをat.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)に移行します。
>
>
mbox.jsは現在サポートされていますが（2021年3月31日まで）、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 すべてのお客様を[!UICONTROL Adobe Experience PlatformWeb SDK]またはat.jsに移行することで、アドビのエンジニアとサポートスタッフは、Adobeから期待される新しい機能とオファーをお客様に提供できます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

## Target Standard／Premium 21.1.1（2021 年 1 月 20 日）

このメンテナンスリリースには、次の機能強化、修正および変更が含まれています。

括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

* [!UICONTROL Analyticsを[!UICONTROL 自動ターゲット]アクティビティーでレポートソース](A4T)として使用する場合の[!DNL Adobe Analytics]指標の選択時に警告を追加しました。 [!UICONTROL 自動ター] ゲットモデルは、バイナリ（コンバージョンベース）の指標を扱うように最適化されています。売上高などの連続した指標を選択すると、最適でない結果が生じる可能性があり、[!UICONTROL パーソナライゼーションインサイト]レポートが正確でない場合があります。 （TGT-38926）
* A4Tを使用する[!UICONTROL 自動ターゲット]アクティビティの[!UICONTROL 自動ターゲットの概要]レポートにステータスアイコンを追加しました。 レポートの各エクスペリエンスの横にある緑のチェックアイコンは、対象のエクスペリエンス用にパーソナライズされた機械学習モデルが作成されたことを意味します。時計アイコンは、トラフィックの量が不十分でモデルがまだ作成されていないことを意味します。（TGT-38925）
* [!UICONTROL 自動セグメント]および[!UICONTROL 重要な属性]レポートは、[!UICONTROL A4Tおよび[!DNL Analytics]コンバージョン指標を使用する自動ターゲット]アクティビティ用に生成され、レポートソースとして[!DNL Target]を使用した場合と同じように見えます。 （TGT-38931）
* [!UICONTROL Recommendations] [!UICONTROL コレクション]リストに環境フィルターオプションを追加しました。 （TGT-38353）
* [!UICONTROL Recommendations]コレクションに正しくない製品数が表示される問題を修正しました。 （TGT-39162）
* [!UICONTROL 最終更新日]フィルターを[!UICONTROL Recommendations] [!UICONTROL カタログ検索]に追加しました。 （TGT-38340）
* [!UICONTROL Recommendations]で、業種を変更すると[!UICONTROL シーケンスを作成]ページがハングする問題を修正しました。 （TGT-38160）
* Device Co-opが有効で、アクティビティが[!DNL Target]から[!DNL Analytics](A4T)にレポートソースとして変更された場合に、デバイスを保存できない問題を修正しました。 （TGT-38163）
* [!UICONTROL Automated Personalization](AP)アクティビティーのオファーーからオーディエンスを削除できない問題を修正しました。 （TGT-39058）
* 一部の顧客の[!UICONTROL オーディエンス情報]カードに正しくない時間枠(開始日と終了日)が表示される問題を修正しました。 （TGT-39150）
* 一部のお客様が、[!UICONTROL デフォルトのワークスペース]でアクティビティのリストを確認できない問題を修正しました。 （TGT-38526）

## at.js 2.4.0（2021年1月15日）

at.jsのこのリリースはメンテナンスリリースであり、次の修正が含まれています。

* 統合プロファイル/プラットフォームIDのサポートを配信APIのcustomerIdに追加しました。
* 無効なスタイルタグ挿入を修正します。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報が表示されます。<br>詳しくは、「[ドキュメントの変更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](/help/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、「 [Experience Cloudリリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)」を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update リスト | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
