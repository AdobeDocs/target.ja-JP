---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 17bb53ef1f48b4c5f9f6c5caccf1fe8aa3e17286
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 73%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Adobe Target] エッジで計画されたインフラストラクチャのアップグレード {#edge}

エッジインフラストラクチャのアップグレードを計画する場合、許可リストに追加の IP またはドメインが必要です。 エッジデプロイメント 41～48 の NAT および IP/domains を確認し、許可リストに登録します。 インフラストラクチャのアップグレードは 2023 年 8 月 9 日から始まります。
&quot;

詳しくは、 [ターゲット許可リストエッジノードの](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=ja){target=_blank} 内 *Adobe Target Developer Guide*.

## [!DNL Target] Standard/Premium 23.7.1（7 月 24 日～ 26 日）

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **7 月 24 日**:ヨーロッパ、中東、アフリカ (EMEA) 地域
* **7 月 25 日**:アジア太平洋 (APAC) 地域
* **7 月 27 日**:アメリカ地域

このリリースには、以下の機能強化および修正が含まれています。

* 検索機能の向上 [DOM パスを使用した要素の移動](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) 内 [!UICONTROL Visual Experience Composer] (VEC) に変更され、シャドウ DOM 要素が含まれるようになりました。 （TGT-45262）
* が [オーバーレイを変更](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) の設定が正しく機能しない問題を修正しました。 （TGT-45202）
* 次のエラーメッセージが表示された後、一部のお客様がアクティビティレポートをダウンロードできない問題を修正しました。「ユーザーは、レポートへのアクセスを許可されていません。」 （TGT-45724 および TGT-45747）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

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
