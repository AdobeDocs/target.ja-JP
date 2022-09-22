---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれているもの
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 3d8da94a52046e70a89dc24d7923f743bee5c458
workflow-type: ht
source-wordcount: '632'
ht-degree: 100%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target] Standard／Premium 22.9.1（時差リリース 2022年9月13日～15日（PT））

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **9月13日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **9月14日（PT）**：アメリカ地域
* **9月15日（PT）**：アジア太平洋（APAC）地域

このリリースには、以下の機能強化および修正が含まれています。

* at.js 2.10.0（およびそれ以降）のダウンロード時に、サードパーティ Cookie の設定を許可または無効にする[!UICONTROL クロスドメイン]オプションを追加しました。（TGT-43674）
* [!DNL Recommendations] フィードの読み込みが失敗した場合に、顧客に通知する [!DNL Target] UI の通知を更新しました。（TGT-35811）
* [!UICONTROL オファーの決定]が [!UICONTROL Visual Experience Composer]（VEC）内で正常に機能しない問題を修正しました。（TGT-43866）
* [!UICONTROL 多変量分析テスト]（MVT）アクティビティを作成する際、「[!UICONTROL 要素をクリック]」のコンバージョン目標を選択するとエラーメッセージが表示される問題を修正しました。（TGT-43842）
* [!UICONTROL 自動パーソナライゼーション]（AP）アクティビティで、ダウンロードした CSV レポートファイル内に[!UICONTROL インプレッション]列が表示されない問題を修正しました。（TGT-43780）
* [!UICONTROL フォームベースの Experience Composer] を使用する場合に、エクスペリエンスを複製した後に HTML／JSON オファーを編集できない問題を修正しました。（TGT-43633）
* ユーザーが [!UICONTROL A/B テスト]アクティビティをデフォルト以外のワークスペースから別のデフォルトでないワークスペースにコピーできない問題を修正しました。（TGT-41910）
* 顧客が [!UICONTROL A/B テスト] および [!UICONTROL エクスペリエンスのターゲット設定]（XT）アクティビティで、レコメンデーションを含む [!DNL Recommendations] オブジェクト（デザイン、条件、コレクションなど）の使用状況を適切に表示し、また [!DNL Target] UI および [!DNL Recommendations] バックエンドから使用されていない条件オブジェクトを削除できるように問題を修正しました。（TGT-42331）
* パラメーターを取得するときにネットワークタイムアウトアラートが [!DNL Target] UI に表示される問題を修正しました。（TGT-43737）
* 特定のドラッグ＆ドロップアクションにキーボードからアクセスできるように UI を更新しました。（TGT-42969）
* テキスト文字列が適切にローカライズされるように UI を更新しました。

## at.js バージョン 2.10.0（2022年9月13日（PT））

* at.js 2.10.0（およびそれ以降）のダウンロード時に、サードパーティ Cookie の設定を許可または無効にする[!UICONTROL クロスドメイン]オプションを追加しました。（TGT-43674）

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
