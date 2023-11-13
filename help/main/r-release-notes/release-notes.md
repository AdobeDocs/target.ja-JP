---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 44ac64d0b97db4995193dea11c0c65934f386926
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 84%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!UICONTROL アクティビティ]ページのユーザーインターフェイスの更新（2023年10月25日（PT））

[!DNL Target] ユーザーのユーザーエクスペリエンスを向上させるための [!DNL Adobe Target] チームの継続的な取り組みの一環として、このリリースでは [!DNL Target] UI の[!UICONTROL アクティビティ]ページを更新しました。この更新では、以前は一貫性がなかったデザインパターンが統合および標準化されたほか、新しい機能強化が追加されています。

10月25日水曜日（PT）から、一部のお客様が新しい UI にアクセスできるようになり、今後数日以内にさらに多くのお客様が新しい UI にアクセスできるようになります。

詳しくは、[アクティビティ](/help/main/c-activities/activities.md)を参照してください。

## [!DNL Target] Standard／Premium 23.11.1（2023年11月13～14日（PT））

このリリースは、次の日に予定されています。

* **11月13日（PT）**：アジア太平洋（APAC）地域
* **11月14日（PT）**：南北アメリカ地域
* **11月14日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域

このリリースには、以下の機能強化および修正が含まれています。

* 拡張された [アクティビティ QA](/help/main/c-activities/c-activity-qa/activity-qa.md) サポートする機能 [重複するオファーの禁止](/help/main/c-activities/t-automated-personalization/managing-exclusions.md) エクスペリエンスの [!UICONTROL Automated Personalization] アクティビティ。 （TGT-46627）
* コントロールエクスペリエンスにトラフィックが割り当てられていない場合、アクティビティレポートでデータが使用できない理由をお客様が理解できるように、[!DNL Target] UI にツールチップを追加しました。ツールチップには、次の詳細情報へのリンクが含まれます。[アクティビティのレポートにデータがないのはなぜでしょうか？](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B)（TGT-46610）
* 一部のお客様の[!UICONTROL アクティビティ]ページにアクティビティが正しく表示されない問題を修正しました。（TGT-46830）
* を使用しているアクティビティに影響を与えた次の問題を修正しました。 [[!UICONTROL Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) をレポートソースとして使用する場合：
   * 一部の顧客がレポートデータを表示できない問題を修正しました。 （TGT-46557）
   * 時に [!UICONTROL Analytics で表示] アクティビティレポートページのリンクが正しく機能しない問題を修正しました。 （TGT-46731）
   * 次の期間にデータを取り込めない問題を修正しました： [!UICONTROL 上昇率] および [!UICONTROL 信頼性] 正しく表示する [!DNL Target] UI （TGT-46592、TGT-46554、TGT-46586）

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
