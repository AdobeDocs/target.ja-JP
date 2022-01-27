---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれる機能
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: fd1d276cd01221be1fbde7931b4350edefe1965c
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 73%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

## [!DNL Target Standard/Premium] 22.1.2（2022 年 1 月 27 日）

| 機能 | 詳細 |
| --- | --- |
| [!DNL Adobe Experience Platform] オーディエンス [!DNL Target] | 使用して、 [!DNL Adobe Experience Platform] オーディエンス [!DNL Target]. この [!DNL Target] チーム [!DNL Experience Platform] [!DNL Destinations] チームと [!DNL Unified Profile Service] チームは、「同じページ/次のページのパーソナライゼーション」の使用例の一般リリースについてお知らせします。<br>で作成されたオーディエンスの使用 [!DNL Adobe Experience Platform] より効果的なパーソナライゼーションにつながる、より豊富な顧客データを提供します。 この [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html){target=_blank} (RTCP)、 [!DNL Adobe Experience Platform] は、企業が複数のエンタープライズソースから既知の匿名データを統合し、すべてのチャネルとデバイスにわたってリアルタイムにパーソナライズされた顧客体験を提供するために使用できる顧客プロファイルを作成するのに役立ちます。<br>詳しくは、 [Adobe Experience Platformのオーディエンスを使用](/help/c-target/c-audiences/audiences.md#aep) in *オーディエンスの作成*.<br>必ずAdobeのブログを読み、ビデオを見てください。 [[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] および [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}。 |
| [!UICONTROL オーディエンス] UI の更新 | [!DNL Target] ユーザーのユーザーエクスペリエンスを向上させるための [!DNL Adobe Target] チームの継続的な取り組みの一環として、このリリースでは [!DNL Target] UI の[!UICONTROL オーディエンス]ページと[!UICONTROL プロファイルスクリプト]ページが更新されました。この更新では、以前は一貫性がなかったデザインパターンが統合および標準化されたほか、次のような新しい機能強化が追加されています。<ul><li>複数のオーディエンスを同時に選択および削除する機能</li><li>[オーディエンスビルダーのデザイン](/help/c-target/c-audiences/create-audience.md)の更新</li><li>[!UICONTROL オーディエンス]ライブラリルールビルダーでの除外ルールのサポート</li><li>新しい「オーディエンスソース」フィルターによるオーディエンス検出の迅速化</li><li>セッションの永続的な検索とフィルターオプション</li><li>のワークスペース間でオーディエンスを移動する機能 [!DNL Target Premium] 顧客。</li></ul>詳しくは、[オーディエンス](/help/c-target/target.md)を参照してください。<br>**注意**:この機能は、今後 6 週間以内に各地域のお客様に提供される予定です。 |
| [!UICONTROL プロファイルスクリプト] UI の更新 | また、[!UICONTROL プロファイルスクリプト]ライブラリも更新され、更新されたインターフェイスのほか、生産性向上のための更新が含まれています。<ul><li>複数のプロファイルスクリプトを同時に選択および削除する機能</li><li>プロファイルスクリプトの新しいコードエディター</li><li>コードエディター内での構文のハイライト表示とエラーチェック</li><li>キーボードショートカットを使用したトークン（mbox またはプロファイル）パラメーターのオートコンプリート</li></ul>詳しくは、[訪問者プロファイル](/help/c-target/c-visitor-profile/visitor-profile.md)を参照してください。<br>**注意**:この機能は、今後 6 週間以内に各地域のお客様に提供される予定です。 |

## [!DNL Target Standard/Premium] 22.1.1（2022 年 1 月 13 日）

このリリースには、今後の統合に必要なバグ修正と前提条件機能が含まれています。

## at.js バージョン 2.8.0（2022年1月7日（PT））

[!DNL Target] at.js JavaScript ライブラリは、機能の使用状況とパフォーマンスのテレメトリデータを収集するようになりました。個人データは収集されません。 この機能をオプトアウトするには、`targetGlobalSettings` で `telemetryEnabled` を false に設定します。詳しくは、[targetGlobalSettings の telemetryEnabled](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#telemetry) を参照してください。

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
| Adobe Priority Product Update | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
