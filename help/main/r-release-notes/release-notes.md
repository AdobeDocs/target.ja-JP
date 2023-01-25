---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれているもの
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 50703e9709d515cbee18569fedb6139e9bf18ccd
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 91%

---

# [!DNL Target]リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target] Standard／Premium 22.13.3（2023年1月25〜26日（PT）） 

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **1 月 25 日**:ヨーロッパ、中東、アフリカ (EMEA) 地域
* **1 月 25 日**:アジア太平洋 (APAC) 地域
* **1 月 27 日**:アメリカ地域

このリリースには、以下の新機能、拡張機能および修正が含まれています。

| 機能 | 詳細 |
| --- | --- |
| [JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md) Automated Personalization(AP) でのサポート | フォームベースの Experience Composer を使用して、[!UICONTROL Automated Personalization]（AP）アクティビティで JSON オファーのサポートを追加しました。（TGT-41460） |
| Recommendations | のわかりやすい名前 [!UICONTROL Analytics for Target] A4T レポートが使用できるようになりました。 以前は、[!DNL Target] にはエクスペリエンス ID のみがリストされていました。この機能強化により、[!DNL Adobe Analytics] と [!DNL Target] の間でレポートが調整され、顧客が A4T でレポート作成を合理化するのに役立ちます。（TGT-41853） |
| [AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | 次の項目を区別する機能を追加しました。 [!DNL Adobe Experience Manager] に書き出されるフラグメント (AEM XF) タイプ [!DNL Target]. 「エクスペリエンスフラグメント」オプションの代わりに、 [!DNL Target] では、「HTMLXF」と「JSON XF」でフィルタリングおよび検索できます。 （TGT-44132） |

* 推奨事項を含む [!UICONTROL A/B テスト]および[!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティで「500 エラー」が発生する問題を修正しました。この問題は、[!DNL Target] が [!DNL Target] UI や [!DNL Recommendations] バックエンドから使用されていない条件オブジェクトを削除できなかったことが原因です。（TGT-44383）
* [!UICONTROL Automated Personalization]アクティビティの[!UICONTROL オファー レベル]レポートに表示されるオファー名から場所を削除しました。この変更により、レポートが読みやすくなります。 （TGT-44294）
* [!DNL Target] UI の AP および[!UICONTROL 自動ターゲット][!UICONTROL パーソナライゼーションインサイト]と[!UICONTROL 重要な属性]レポートから 45 日間と 90 日間のカレンダーオプションを削除しました。使用パターンおよびパフォーマンス向上のため、これらの日付範囲は非推奨（廃止予定）になりました。現在許可されている範囲（15 日、30 日および 60 日）を反映するように UI を更新しました。（TGT-39357）
* アクティビティがライブになった後、[!UICONTROL 目標と設定]ページで[!UICONTROL 最適化目標と同じ]設定を変更する機能を無効にしました。（TGT-43923）
* [!DNL Target Standard] から [!DNL Target Premium] へのアップグレード時に、[!DNL Target] バックエンドのデフォルトワークプレースで発生する問題を修正しました。（TGT-44081 および TGT-44306）
* サポート対象のすべての SDK（Node.js、Java、.NET、および Python）でオンデバイス決定の使用方法を説明するページを指すように、「オンデバイス決定による実装方法」の[!UICONTROL 実装]ページ（[!UICONTROL 管理]／[!UICONTROL 実装]）のリンクを変更をしました。詳しくは、[Target SDK の開始方法](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}を参照してください。
* [!DNL Scene7] および [!DNL Target] を使用する際のファイルのアップロードに関する問題を修正しました。
* 内部のユーザビリティ監査の結果を使用して、障害のあるユーザー向けの [!DNL Target] UI のアクセシビリティを強化しました。これらのアクセシビリティの強化には、以前はキーボードからアクセスできなかった機能へのアクセス、代替テキストの機能強化、UI の一部をより使いやすくするためのズーム機能、キーボードフォーカスの改善などが含まれます。   （TGT-42759）
* [!DNL Target] UI 全体でさまざまなローカライゼーションの修正を行いました。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報を表示します。<br>詳しくは、[ドキュメントの変更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](/help/main/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、[Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md)ページを参照してください。 |
