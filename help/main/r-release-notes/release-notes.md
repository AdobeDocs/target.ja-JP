---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート；現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 391653c7a45a48c311c6a6cff358bd077f8c47b7
workflow-type: tm+mt
source-wordcount: 652
ht-degree: 41%

---

# [!DNL Target] リリースノート（最新）

[!DNL Adobe Target]の最新の機能、機能強化、および修正について説明します。 このリリースノートでは、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、および該当する場合はその他のプラットフォームコンポーネントのアップデートについても説明します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target Standard/Premium] 26.6.1 （2026年6月4日）

**アクティビティ**

+++詳細を見る

* **アクティビティの概要[!UICONTROL に関する不完全なアクティビティ URL].** アクティビティの完全なURLが[!UICONTROL &#x200B; アクティビティ概要]に表示されない問題を修正しました。 （TGT-54029）

* **アクティビティレポートのローカライズされていない日付形式。** 「**[!UICONTROL プリセット日付範囲]**」ドロップダウンリストから「**過去X日間**」オプションを選択した際に、日付形式が「**[!UICONTROL レポート]**」タブにローカライズされない問題を修正しました。 （TGT-51637）

* **特定のGB18030文字を含むフォームベースのアクティビティを[!UICONTROL 場所].**&#x200B;に保存できません **[!UICONTROL 場所]** フィールドに特定のGB18030文字が含まれている場合に、フォームベースのアクティビティを保存できない問題を修正しました。 （TGT-46980）

+++

**[!UICONTROL オーディエンス]**

+++詳細を見る

* **簡体字中国語と繁体字中国語のオーディエンスフローの作成のカレンダーがローカライズされていません。** 「オーディエンスを作成」フロー中に、**[!UICONTROL 時間枠]**&#x200B;属性の&#x200B;**[!UICONTROL 開始]**&#x200B;および&#x200B;**[!UICONTROL 終了]** フィールドのカレンダーが簡体字中国語（CHS）および繁体字中国語（CHT）ロケールでローカライズされない問題を修正しました。 （TGT-50619）

+++

**[!UICONTROL Visual Experience Composer] （VEC）**

+++詳細を見る

* **更新されたActivity Builderのローカライズされていないツールヒント。** 更新された[!UICONTROL Visual Experience Composer] アクティビティビルダーで&#x200B;**[!UICONTROL 改良]**&#x200B;および&#x200B;**[!UICONTROL コンテンツ]**&#x200B;情報ツールヒントがローカライズされなかったローカライズの問題を修正しました。 （TGT-53721）

* [!UICONTROL Experience Audiences]の&#x200B;**ローカライズされていない[!UICONTROL すべての訪問者]。** 左側のレールの&#x200B;**[!UICONTROL Experience Audiences]**&#x200B;の&#x200B;**[!UICONTROL すべての訪問者]**&#x200B;文字列が[!UICONTROL Visual Experience Composer]にローカライズされない問題を修正しました。 （TGT-50086）

+++

**[!UICONTROL レポート]**

+++詳細を見る

* **プリセットを作成[!UICONTROL &#x200B; ウィンドウでローカライズされていない日付形式]。** 「**[!UICONTROL プリセットを作成]**」ウィンドウの「**[!UICONTROL 日付範囲]**」フィールドの日付形式がローカライズされない問題を修正しました。 （TGT-49239）

+++

**ローカライズ**

+++詳細を見る

* **GB18030文字が複数の領域に表示されます。** 一部のプライベート使用領域の文字が、**[!UICONTROL Audience]** UI、**[!UICONTROL 管理]** > **[!UICONTROL プロパティ]**&#x200B;の文字として正しく表示されない問題、モバイルビューポート設定、およびトースト通知を修正しました。 （TGT-49622、TGT-49623、TGT-49624、およびTGT-49625）

+++

<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)

**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## 知っておく必要がある時間的制約のある更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

[!DNL Adobe Target]およびお客様の実装に関連する時間制限のある更新については、[!DNL Adobe]が[!UICONTROL Experience League]を通じて詳細なリリースノートとドキュメントを提供します。 Adobe Workfrontの導入に関する重要なハイライトを以下に示します。

### [!DNL Target] UI バージョン トグルの非推奨化

詳しくは、[[!DNL Target] UIの更新に関するFAQ](/help/main/c-intro/updated-ui-faq.md)を参照してください。

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
