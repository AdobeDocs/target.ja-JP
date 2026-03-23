---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート；現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 62d33419f2cbad93d99b29cef58e99f4d84a98f6
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 47%

---

# [!DNL Target] リリースノート（最新）

[!DNL Adobe Target]の最新の機能、機能強化、および修正について説明します。 このリリースノートでは、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、および該当する場合はその他のプラットフォームコンポーネントのアップデートについても説明します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## 知っておく必要がある時間的制約のある更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

[!DNL Adobe Target]およびお客様の実装に関連する時間制限のある更新については、[!DNL Adobe]が[!UICONTROL Experience League]を通じて詳細なリリースノートとドキュメントを提供します。 Adobe Workfrontの導入に関する重要なハイライトを以下に示します。

### [!DNL Target] UI バージョン トグルの非推奨化

詳しくは、[[!DNL Target] UIの更新に関するFAQ](/help/main/c-intro/updated-ui-faq.md)を参照してください。

## [!DNL Target Standard/Premium] 26.3.2（2026年3月10日（PT））

**アクティビティ**

+++詳細を見る

* **エクスペリエンスのダイレクトオファーの変更は保存されません。**&#x200B;この修正プログラムは、アクティビティ エクスペリエンス内のダイレクト オファーに対して行われた変更が保存されなかった問題を解決します。 以前は、ユーザーがダイレクトオファーを開いて変更し、保存すると、変更内容は最初に反映されたように見えましたが、オファーを再度開いたときに失われていました。 この修正により、ダイレクトオファーへの変更が適切に保存され、オファーが再度開かれたときに保持されるようになります。 （TGT-54653）

+++

**実装**

+++詳細を見る

* **実装画面のちらつき管理トグルを追加します。** フリッカー管理設定の有効化を制御するための新しい切り替えスイッチが[!UICONTROL Implementation]画面に追加されました。 この切り替えにより、管理者は実装画面から直接ちらつき管理を設定できます。 （TGT-52247）

+++

**概要**

+++詳細を見る

* **概要ページでオーディエンスとエクスペリエンスのフルネームを表示します。**&#x200B;この機能強化により、[!UICONTROL Overview] ページが更新され、オーディエンスとエクスペリエンスの完全な名前が表示されます。 以前は、長い名前は切り捨てられ、完全に表示されていなかったため、ユーザーはトリプルクリックしてすべてのテキストを選択し、完全な名前を表示する必要がありました。 このアップデートにより、完全なオーディエンス名とエクスペリエンス名が表示されるようになり、ユーザーがアクティビティ設定を識別およびレビューしやすくなります。 （TGT-53323）

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
| [Adobe Experience Cloud リリースノート &#x200B;](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [Adobe 優先製品のアップデート](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | [!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションに対する今後の製品の機能強化に関する事前通知を受信します。 |
| [Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、当月の Target リリースに関する情報です。 |
