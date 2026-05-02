---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート；現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7976d43e43baeabdb68509373f1b0b72bbe723b3
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 49%

---

# [!DNL Target] リリースノート（最新）

[!DNL Adobe Target]の最新の機能、機能強化、および修正について説明します。 このリリースノートでは、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、および該当する場合はその他のプラットフォームコンポーネントのアップデートについても説明します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## 知っておく必要がある時間的制約のある更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

[!DNL Adobe Target]およびお客様の実装に関連する時間制限のある更新については、[!DNL Adobe]が[!UICONTROL Experience League]を通じて詳細なリリースノートとドキュメントを提供します。 Adobe Workfrontの導入に関する重要なハイライトを以下に示します。

### [!DNL Target] UI バージョン トグルの非推奨化

詳しくは、[[!DNL Target] UIの更新に関するFAQ](/help/main/c-intro/updated-ui-faq.md)を参照してください。

## [!DNL Target Standard/Premium] 26.4.4 （2026年4月28日）

**アクティビティ**

+++詳細を見る

* **レポートのオーディエンスフィルターでエラーが発生しました。** **[!UICONTROL Goals & Settings]**&#x200B;内でオーディエンスフィルターを変更すると、[!DNL Target] ユーザーインターフェイスの「レポート」セクションでエラーが発生する問題を修正しました。 （TGT-55006）

* **アクティビティを優先度順に並べ替え。** **[!UICONTROL Priority]**&#x200B;列ヘッダーを使用して、アクティビティ リストの優先順位による並べ替えを追加しました。昇順と降順は、他の並べ替え可能な列と一致しています。 （TGT-54948）

* **追加のアクティビティ プロパティは、保存後も保持されません。** アクティビティを保存して再度開いた後、特定の&#x200B;**[!UICONTROL Properties]**&#x200B;選択が保持されない問題を修正しました。 （TGT-53889）

+++

**ローカライズ**

+++詳細を見る

* [!UICONTROL Page Delivery]のルール演算子の&#x200B;**日本語ラベル。** 日本語UIのページ配信ルール演算子ラベルの読み取り不可能または破損した文字列を修正しました。 （TGT-53097）

+++

**API**

+++詳細を見る

* **レポート [!DNL GraphQL] `segmentId`.**&#x200B;に対するAPI サポート レポート [!DNL GraphQL] APIに`segmentId`を追加しました。 （TGT-55021）

+++

**[!UICONTROL Visual Experience Composer]（VEC）**

+++詳細を見る

* **エディターで間違ったエクスペリエンスに表示される変更。** [!UICONTROL Visual Experience Composer]でエクスペリエンスを切り替えた後、削除やその他の変更が間違ったエクスペリエンスに表示される問題を修正しました。 （TGT-54955）

* HTMLを挿入を削除すると、**変更が削除されました。** **[!UICONTROL Insert before]**&#x200B;または&#x200B;**[!UICONTROL Insert after]**&#x200B;で追加された追加の&#x200B;**[!UICONTROL HTML]** ブロックを削除すると、CSS セレクターを持たないリンクされた変更も削除される問題を修正しました。 （TGT-54530）

+++

<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)




**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

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
