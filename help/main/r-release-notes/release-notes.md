---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能拡張；機能拡張；修正；バグ修正；アップデート；現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
hold: true
source-git-commit: 44d9cd4de7ff2064e6005a4d7ece7f37194fbf2f
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 42%

---

# [!DNL Target] リリースノート（最新）

[!DNL Adobe Target]の最新の機能、機能強化、修正をご確認ください。 これらのリリースノートでは、[!DNL Target]個のAPI、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、その他のプラットフォームコンポーネント（該当する場合）に対する更新も提供されています。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## 知っておく必要がある、時間に依存する更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

[!DNL Adobe Target]およびお客様の実装に関連する時間依存の更新については、[!DNL Adobe]が[!UICONTROL Experience League]を通じて詳細なリリースノートとドキュメントを提供します。 お客様の導入に関連する主なハイライトを次に示します。

### [!DNL Target] UIバージョンの切り替えの廃止

詳細については、[[!DNL Target] UIアップデートに関するFAQ](/help/main/c-intro/updated-ui-faq.md)を参照してください。

## [!DNL Target Standard/Premium] 26.3.2（2026年3月10日（PT））

**アクティビティ**

+++詳細を見る

* **直接提供のエクスペリエンスの変更は保存されません。**&#x200B;この修正により、アクティビティエクスペリエンス内で直接提供に対して行った変更が保存されない問題が解決されます。 以前は、ユーザーが直接オファーを開き、変更を加えて保存すると、変更は最初は反映されていましたが、オファーを再度開くと失われました。 この修正により、直接オファーに対する変更が適切に保存され、オファーが再度開いたときにも維持されます。 （TGT-54653）

+++

**実装**

+++詳細を見る

* **実装画面のちらつき管理切り替えを追加します。** [!UICONTROL Implementation]画面に新しい切り替えスイッチが追加され、ちらつき管理設定の有効化を制御できるようになりました。 この切り替えにより、管理者は実装画面から直接ちらつき管理を設定できます。 （TGT-52247）

+++

**概要**

+++詳細を見る

* **概要ページで、対象ユーザーの氏名とエクスペリエンスを表示します。**&#x200B;この機能強化により、[!UICONTROL Overview]ページが更新され、対象ユーザーとエクスペリエンスの完全な名前が表示されます。 以前は、長い名前は切り捨てられ、完全には表示されていなかったため、ユーザーはすべてのテキストをトリプルクリックして完全な名前を表示する必要がありました。 このアップデートにより、完全なオーディエンス名とエクスペリエンス名が表示され、ユーザーがアクティビティ設定を簡単に識別してレビューできるようになります。 （TGT-53323）

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++詳細を見る

* **VECの変更がシャドウDOM （Salesforce Lightning Webコンポーネント）を使用しているサイトに反映されません。**&#x200B;この修正により、Adobe Targetで行われた変更（CTAカラーの変更など）が、Lightning Web Components(LWC)を使用しているSalesforceベースのサイトのライブサイトに保存または反映されない問題が解決されます。 CMSは対象のアクティビティからの更新を受け入れていませんでした。この問題は、A/Bテストおよびその他のアクティビティタイプで一貫して発生しました。 （TGT-54059）

+++

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
| [Adobe Experience Cloudリリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [Adobe 優先製品のアップデート](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | [!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションに対する今後の製品の機能強化に関する事前通知を受信します。 |
| [Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、当月の Target リリースに関する情報です。 |
