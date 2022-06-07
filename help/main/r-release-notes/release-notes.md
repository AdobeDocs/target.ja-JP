---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれているもの
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 4251832a5983ea8950e54d52df5d27bf395894e0
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 83%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target Standard/Premium] カスタマーエンジニアリング修正 (stagger リリース：（2022 年 6 月 7～9 日）

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **6 月 8 日**:アジア太平洋 (APAC) 地域
* **6 月 8 日**:アメリカ地域
* **6 月 9 日**:ヨーロッパ、中東、アフリカ (EMEA) 地域

このリリースには、以下の機能強化および修正が含まれています。

* を持つ [!UICONTROL 編集者] 役割では、ライブアクティビティのオーディエンスを編集できなくなりました。 （TGT-43582）
* 新しい [!UICONTROL オーディエンス] 過去にオーディエンスが保存された古いデータベースと、バックエンドから直接情報を取得する新しいアーキテクチャとの間で、一貫性のない状態が発生するのを防ぐためのページ。 （TGT-43552）
* Target UI で「空」のコンテナが作成されると結合オーディエンスが保存されない場合がある問題を修正しました。 （TGT-43588）

## Target プラットフォームリリース（2022 年 5 月 26 日）

このリリースには、以下の機能強化および修正が含まれています。

* 追加済み [ユーザーエージェントクライアントのヒント](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/user-agent-and-client-hints.md) サポート。
* レンダリング時にタイムアウトが断続的に発生する問題を修正しました [!UICONTROL オファーの決定] in [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ （TNT-44611）

## at.js バージョン 2.9.0（2022 年 5 月 27 日）

* 追加済み [ユーザーエージェントクライアントのヒント](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/user-agent-and-client-hints.md) サポート。
* 同じページ上の複数の mbox リクエストに異なるインプレッション ID があるバグを修正しました。

## [!DNL Target Standard/Premium] 22.5.1（時差リリース、2022年5月11～13日（PT））

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **5月11日**：アジア太平洋（APAC）地域
* **5 月 13 日**:アメリカ地域
* **5月13日**：ヨーロッパ、中東、アフリカ（EMEA）地域

このリリースには、以下の機能強化および修正が含まれています。

* JavaScript エラーが発生し、一部のお客様が特定の [!UICONTROL Automated Personalization]（AP）アクティビティの詳細にアクセスできなかった問題を修正しました。（TGT-43526）
* 一部のお客様が、AP アクティビティに特定のオファーを追加（または編集）できなかった問題を修正しました。（TGT-43503）
* [!DNL Target] UI で、「グローバル mbox が同期されていない可能性があります。再保存してみてください。」というエラーメッセージが表示されることがある問題を修正しました。この問題は、UI の問題で、お客様の実装には影響しませんでした。（TGT-43475）
* 新しい[!UICONTROL オーディエンス] UI がデプロイされる前に絞り込み条件とオーディエンスが作成された場合、あるお客様がアクティビティのエクスペリエンスレベルの絞り込み条件とオーディエンスを編集できなかった問題を修正しました。（TGT-43433）
* アクティビティについてレポートするオーディエンスの編集中に、お客様が重複した [!DNL Adobe Audience Manager]（AAM）オーディエンスを選択できた問題を修正しました。（TGT-43430）
* お客様が異なるワークスペースでも重複してオーディエンスを作成できなかった問題を修正しました。（TGT-43423）
* [!UICONTROL フォームベースの Experience Composer] で作成されたアクティビティで、お客様がアドホックオファーを持つ場所を削除できなかった問題を修正しました。（TGT-43315）
* 画像オファーをクリックした後、UI を更新すると、お客様がコードオファーにアクセスできなくなっていた問題を修正しました。（TGT-43566）
* プロファイルスクリプトを編集してアクティブにし、その後非アクティブにすると、編集したスクリプトが編集前の元のスクリプトに戻る問題を修正しました。これにより、プロファイルスクリプトは、編集された状態のままになります。（TGT-43249）
* オーディエンスを別のワークスペースに移動しようとすると、以下のエラーが発生していた問題を修正しました。「リクエストを完了できません。問題が解決しない場合は、Adobe ClientCare にお問い合わせください。」（TGT-43212）
* シングルページアプリケーション（SPA）ページのカスタムコードの修正をクローンする際に発生するエラーを修正しました。（TGT-43137）
* エクスペリエンスを複製した後、プロモーションを編集すると、元のプロモーションが影響を受けていた問題を修正しました。（TGT-41775）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

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
