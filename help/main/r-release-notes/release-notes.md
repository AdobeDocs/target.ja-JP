---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート、現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 0f96fb2a74a0716542308037d183847c91b1dc04
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 52%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target Standard/Premium] 25.5.1 （2025 年 5 月 5 日）

このリリースには、次の修正および更新が含まれています。

* 更新された UI で、特定のアクティビティに対してオーディエンスの絞り込みが表示されない問題を修正しました。 （TGT-52057）
* アクティビティで結合オーディエンスを使用できない問題を修正しました。 （TGT-52346）
* 同じワークスペースのアクティビティ専用オーディエンスを使用して、デフォルト以外のワークスペースに新しいアクティビティを作成できなかった問題を修正しました。 （TGE-52349）
* 新しいオーディエンスを作成および選択した後、アクティビティのみのオーディエンスが更新された UI に表示されない問題を修正しました。 （TGT=52091）
* アクティビティで重複したオーディエンスを使用できない問題を修正しました。 （TGT-51200 および TGT-52057）
* 更新された UI で、オーディエンスの絞り込みとアクティビティオーディエンスが元に戻される問題を修正しました。 （TGT-52158）
* ユーザー入力エラー「このユーザーにはデフォルト以外のワークスペースは許可されていません」が原因で新しいアクティビティを作成できない問題を修正しました。 （TGT-52267）
* デフォルトのワークスペースとデフォルト以外のワークスペースの両方で、更新された UI にオファーが表示されない問題を修正しました。 [!DNL Target] では、両方のワークスペースのオファーを表示するようになりました。 （TGT-52339）
* アクティビティを編集し、変更され [!DNL Target]web サイト要素を変更した場合に、顧客に警告しなかった問題を修正しました。 （TGT-52100）
* アドホックオファーを使用してオファーを編集すると、既存のオファーが更新されるのではなく、新しいオファーが作成される問題を修正しました。 （TGT-52135）
* オファーをフォルダーに移動する際に、「無効なペイロード」エラーが発生する問題を修正しました。 （TGT-52325）
* オファーをフォルダーに移動する際に、ユーザー入力エラーが発生する問題を修正しました。 （TGT-52296）
* 各アクティビティに `audienceMetadata` フィールドを追加し、アクティビティの編集時に読み取られ、更新されていることを確認しました。 （TGT-51004）

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
| [Adobe Experience Cloud リリースノート ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [Adobe 優先製品のアップデート](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | [!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションに対する今後の製品の機能強化に関する事前通知を受信します。 |
| [Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、当月の Target リリースに関する情報です。 |
