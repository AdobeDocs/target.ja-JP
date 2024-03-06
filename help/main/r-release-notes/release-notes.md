---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 784f41a73941877135a5902f2331972ba9d0e880
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 63%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## の更新 `Browser:iPad` および `Browser:iPhone` in [!UICONTROL Browser] オーディエンス属性（2024 年 4 月 31 日）

| 更新 | 詳細 |
|--- |--- |
| [!UICONTROL Browser:iPad] および [!UICONTROL Browser:iPhone] 更新： [ブラウザー属性](/help/main/c-target/c-audiences/c-target-rules/browser.md) オーディエンスを作成する際に使用します。 | [!DNL Adobe Target] 以下が可能です。 [複数のカテゴリ属性のいずれかに対するターゲット](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)( 特定の [ブラウザーまたはブラウザーのオプション](/help/main/c-target/c-audiences/c-target-rules/browser.md) 訪問者がページを訪問したとき。<P>の使用を開始する [!DNL Target] Standard/Premium 24.3.1（2024 年 3 月 4～6 日）:Target UI を使用して作成された組み込みオーディエンス ( 例： `Browser:iPad` および `Browser:iPhone` の適切なターゲティングを実行するために更新されます [!DNL iPad] および [!DNL iPhone] using `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` および `profile.mobile.isTablet`.<P>この更新では、お客様側での操作は必要ありません。<p><B>重要</b>：顧客が [!DNL iPad] および [!DNL iPhone] プロファイルスクリプト（および JavaScript セグメント）では、手動での変更は、 **2024 年 4 月 31 日**. 手動で変更する必要がある代替設定の例については、 [の更新 [!DNL iPad] および [!DNL iPhone] in [!UICONTROL Browser] オーディエンス属性](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

## [!DNL Target] Standard/Premium 24.3.1（2024 年 3 月 4 日～6 日）

このリリースは、次の日に予定されています。

* **3月4日**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **3月5日**：アジア太平洋（APAC）地域
* **3月6日**：アメリカ地域

このリリースには、以下の機能強化および修正が含まれています。

* アクティビティ内の一意のセレクターの数を計算するロジックを修正しました。 （TGT-47878）
* 次の問題を修正しました： [!UICONTROL Multivariate] (MVT) アクティビティが [!UICONTROL Analytics for Target] (A4T) レポートが正しく表示されない問題を修正しました。 （TGT-47490）
* トラフィックのないエクスペリエンスがコントロールエクスペリエンスとして使用された場合にレポートに表示される警告メッセージを改善しました。 （TGT-47537）
* バックエンドおよびローカリゼーションに関する修正を多く追加しました。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

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
