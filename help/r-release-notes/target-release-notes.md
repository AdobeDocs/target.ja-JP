---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: DNLAdobe Targetの最新リリースまたは今後のリリースに関する機能、拡張機能、および修正に関する情報を提供するリリースノートです。
title: Adobe Targetプレリリースノート
feature: Release Notes
translation-type: tm+mt
source-git-commit: ec8aa3c2f6eca3c1f8002526cc2d2f15365f9671
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 19%

---


# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021 年 1 月 12 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングによっては、これらのページの情報が同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリ [!DNL Adobe Target] はサポートされなくなります。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに今日までに移行することをお勧めします。
>
>* **Adobe Experience PlatformウェブSDK**: [!UICONTROL Adobe Experience PlatformWeb ] SDKを使用すると、Adobe Experience Edge Networkを介して、( [!DNL Experience Cloud] 含む [!DNL Target])様々なサービスをインタラクティブに操作できます。[!DNL Adobe Experience Platform Web SDK]に移行する場合は、『*Web SDKガイド*』の[Adobe Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)とは何ですかを参照してください。 [!DNL Target]固有の情報については、[ターゲットの概要](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)を参照してください。
   >
   >
* **at.js**:at.js JavaScriptライブラリは、mbox.jsよりも多くの利点を提供します。多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。 at.jsに移行する場合は、[At.jsの仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)と[Adobe Targetスキルビルダーを参照してください。開発者チャットで、Adobe Targetのmbox.jsをat.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)に移行します。
>
>
mbox.jsは現在サポートされていますが（2021年3月31日まで）、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 すべてのお客様を[!UICONTROL Adobe Experience PlatformWeb SDK]またはat.jsに移行することで、アドビのエンジニアとサポートスタッフは、Adobeから期待される新しい機能とオファーをお客様に提供できます。

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
* [!DNL Target] UIおよびAPIのオファーのサイズ制限を1 MBに増やしました。 （TGT-38304）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html)
