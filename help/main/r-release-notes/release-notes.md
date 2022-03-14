---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれているもの
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 100%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。

## Target Standard／Premium 22.2.1（2022年2月1日（PT）） 

このメンテナンスリリースには、今後 6 週間以内にすべての地域のお客様に公開される Target Standard／Premium 22.1.2 リリースでの提供が発表された新しい[!UICONTROL オーディエンス] UI に対する以下の修正および機能強化が含まれています。これらの修正により、 [!DNL Adobe Target Standard/Premium] で作成されたオーディエンスの機能が調整されます。

* [!DNL Adobe Experience Platform]、[!DNL Adobe Experience Cloud] および [!DNL Adobe Target Classic] からインポートしたオーディエンスをレポートオーディエンスとして割り当てることができない問題を修正しました。（TGT-43140）
* [!DNL Adobe Experience Platform]、[!DNL Adobe Experience Cloud] および [!DNL Adobe Target Classic] からインポートしたオーディエンスの[!UICONTROL オーディエンス]リストに「[!UICONTROL 削除]」オプションを追加しました。また、一括削除機能も追加しました。（TGT-42914）

## at.js バージョン 2.8.1（2022年1月28日（PT））

* [!UICONTROL オンデバイス判定]（ODD）ハイブリッド実行モードで `pageLoad` が target-global-mbox にマッピングされない問題を修正しました。
* mbox リクエストの分析の詳細に関する問題を修正しました。
* 開発用の依存コンポーネントをアップグレードして、セキュリティの脆弱性を修正しました。

## [!DNL Target Standard/Premium] 22.1.2（2022年1月26日（PT））

| 機能 | 詳細 |
| --- | --- |
| [!DNL Target] での [!DNL Adobe Experience Platform] オーディエンス | [!DNL Target] で [!DNL Adobe Experience Platform] オーディエンスを消費し使用できるようになりました。[!DNL Target] チーム、[!DNL Experience Platform] [!DNL Destinations] チームおよび [!DNL Unified Profile Service] チームから、「同一ページ ／次ページのパーソナライゼーション」ユースケースの一般公開についてお知らせします。<br>[!DNL Adobe Experience Platform] で作成されたオーディエンスを使用すると、よりインパクトのあるパーソナライゼーションにつながる豊富な顧客データが提供されます。[!DNL Adobe Experience Platform] 上に構築された [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=ja){target=_blank}（RTCP）は、企業が複数の企業ソースから既知および匿名のデータを集めて顧客プロファイルを作成するのに役立ちます。顧客プロファイルを使用すれば、パーソナライズされた顧客エクスペリエンスをすべてのチャネルとデバイスにわたってリアルタイムで提供できます。<br>詳しくは、*オーディエンスを作成*&#x200B;の [Adobe Experience Platform のオーディエンスを使用](/help/main/c-target/c-audiences/audiences.md#aep)および&#x200B;*宛先の概要*&#x200B;ガイドの[同じページおよび次のページのパーソナライゼーションの使用例](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} を参照してください。 |
| [!UICONTROL オーディエンス] UI の更新 | [!DNL Target] ユーザーのユーザーエクスペリエンスを向上させるための [!DNL Adobe Target] チームの継続的な取り組みの一環として、このリリースでは [!DNL Target] UI の[!UICONTROL オーディエンス]ページと[!UICONTROL プロファイルスクリプト]ページが更新されました。この更新では、以前は一貫性がなかったデザインパターンが統合および標準化されたほか、次のような新しい機能強化が追加されています。<ul><li>複数のオーディエンスを同時に選択および削除する機能</li><li>[オーディエンスビルダーのデザイン](/help/main/c-target/c-audiences/create-audience.md)の更新</li><li>[!UICONTROL オーディエンス]ライブラリルールビルダーでの除外ルールのサポート</li><li>新しい「オーディエンスソース」フィルターによるオーディエンス検出の迅速化</li><li>セッションの永続的な検索とフィルターオプション</li><li>[!DNL Target Premium] 顧客のワークスペース間でオーディエンスを移動する機能。</li></ul>詳しくは、[オーディエンス](/help/main/c-target/target.md)を参照してください。<br>**注意**：この機能は、今後 8 週間以内に様々な地域のお客様に公開される予定です。 |
| [!UICONTROL プロファイルスクリプト] UI の更新 | また、[!UICONTROL プロファイルスクリプト]ライブラリも更新され、更新されたインターフェイスのほか、生産性向上のための更新が含まれています。<ul><li>複数のプロファイルスクリプトを同時に選択および削除する機能</li><li>プロファイルスクリプトの新しいコードエディター</li><li>コードエディター内での構文のハイライト表示とエラーチェック</li><li>キーボードショートカットを使用したトークン（mbox またはプロファイル）パラメーターのオートコンプリート</li></ul>詳しくは、[訪問者プロファイル](/help/main/c-target/c-visitor-profile/visitor-profile.md)を参照してください。<br>**注意**：この機能は、今後 8 週間以内に様々な地域のお客様に公開される予定です。 |

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
