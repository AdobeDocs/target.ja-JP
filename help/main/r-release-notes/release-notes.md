---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれているもの
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 9489655d18170c581f2abf8502f01c7b7e0626b7
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 47%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、 [!DNL Target] API、SDK、 [!DNL Adobe Experience Platform Web SDK]、at.js およびその他のプラットフォームの変更も、該当する場合は含まれます。

括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。

## [!DNL Target Standard/Premium] 22.5.1 (stagger リリース；2022 年 5 月 11 日～13 日 )

このリリースは、次のように時間をずらして提供される予定です。

* **5 月 11 日**:アジア太平洋 (APAC) 地域
* **5 月 13 日**:北米（北米）地域
* **5 月 14 日**:ヨーロッパ、中東、アフリカ (EMEA) 地域

このリリースには、次の機能強化および修正が含まれています。

* JavaScript エラーが発生し、一部のお客様が特定のアクティビティの詳細にアクセスできない問題を修正しました [!UICONTROL Automated Personalization] (AP) アクティビティ （TGT-43526）
* 一部の顧客が AP アクティビティに特定のオファーを追加（または編集）できなかった問題を修正しました。 （TGT-43503）
* の [!DNL Target] 次のエラーメッセージを表示した UI。「グローバル mbox が同期していない可能性があります。 再保存してみてください。」というエラーメッセージが表示されることがある問題を修正しました。この問題は UI の問題で、お客様の実装には影響しませんでした。 （TGT-43475）
* 新しい [!UICONTROL オーディエンス] UI がデプロイされました。 （TGT-43433）
* 顧客が重複を選択できる問題を修正しました [!DNL Adobe Audience Manager] (AAM) オーディエンスを編集する際に使用します。 （TGT-43430）
* お客様が別のワークスペースでも重複したオーディエンスを作成できなかった問題を修正しました。 （TGT-43423）
* アクティビティでアドホックオファーを持つ場所を、 [!UICONTROL フォームベースの Experience Composer]. （TGT-43315）
* 画像オファーをクリックして UI を更新した後に、コードオファーにアクセスできない問題を修正しました。 （TGT-43566）
* 指標のリストが [!DNL Target] を使用するアクティビティを作成する際の UI [!DNL Analytics for Target] (A4T) は、 [!DNL Adobe Analytics]. （TGT-43294）
* スクリプトを編集、アクティブ化、非アクティブ化した後で、プロファイルスクリプトの編集が元の未編集スクリプトに戻る問題を修正しました。 プロファイルスクリプトは編集された状態のままになります。 （TGT-43249）
* オーディエンスを別のワークスペースに移動しようとすると次のエラーが発生する問題を修正しました。「お客様のご要望は、完了できません。 問題が解決しない場合は、AdobeClientCare にお問い合わせください。」 （TGT-43212）
* シングルページアプリ (SPA) ページのカスタムコード変更の複製時にエラーが発生するエラーを修正しました。 （TGT-43137）
* エクスペリエンスを複製してプロモーションを編集すると、元のプロモーションが影響を受ける問題を修正しました。 （TGT-41775）

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
