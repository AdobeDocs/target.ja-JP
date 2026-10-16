---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート；現在のアップデート
description: SDK、API、JavaScript ライブラリなど、[!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: '[!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: '[!DNL Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: 'https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
  - id: c5abb976-5170-45d6-bcac-66d15d10a4d4
    internal-label: Release notes
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 06cdc2613d49e3c71c2d29c6ee1307d39215ac84
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 42%
---
# [!DNL Target] リリースノート（最新）

[!DNL Adobe Target]の最新の機能、機能強化、および修正について説明します。 このリリースノートでは、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、および該当する場合はその他のプラットフォームコンポーネントのアップデートについても説明します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target Standard/Premium] 26.10.2 （2026年10月15日（PT））

**[!UICONTROL アクティビティ]**

+++詳細を見る

* **アクティビティの概要**&#x200B;に表示される目標設定が正しくありません。 アクティビティの&#x200B;**[!UICONTROL 概要]** ページに表示されている目標設定が正しくない問題を修正しました。 例えば、`https://`がページ URLに追加され、実際の目標設定が正しいにもかかわらず、**[!UICONTROL URL contains]**&#x200B;条件が表示されませんでした。 （TGT-56326）

+++

**[!UICONTROL レコメンデーション]**

+++詳細を見る

* **ライブアクティビティでプロモーションが更新された後に表示されるバックアップの推奨事項**。 ライブ [!DNL Recommendations] アクティビティでプロモーションを編集すると、定義が変更されていなくても[!DNL Target]が新しいプロモーションとレコメンデーションユニットを作成する問題を修正しました。 （TGT-56369）

+++

**[!UICONTROL レポート]**

+++詳細を見る

* **レポートプリセットは2週間後に削除されました**。 アクティビティ用に保存されたレポートプリセットが、約2週間後に自動的に削除される問題を修正しました。 （TGT-56374）

+++

**[!UICONTROL Visual Experience Composer] （VEC）**

+++詳細を見る

* **Safariのサポートが[!DNL Adobe Target]**&#x200B;に追加されました。 [!DNL Target]は[!DNL Safari] ブラウザーでサポートされるようになりました。 Visual Experience Composerと[!DNL Enhanced Experience Composer]は、[!DNL Safari]ではサポートされていません。 その結果、[!DNL VEC]にオーバーレイが表示され、エディターを使用するには[!DNL Chrome]に切り替える必要があることをユーザーに通知できるようになりました。 （TGT-55853）

+++


## [!DNL Target Standard/Premium] 26.10.1 （2026年10月13日（PT））

**[!UICONTROL ターゲットの分析]**

+++詳細を見る

* **A4T レポートが「エラーが発生しました」エラーで失敗します**。 新しく追加されたレポートスイートを使用する[!DNL A4T] アクティビティで、結果ではなく[!DNL Target] レポートに「エラーが発生しました」エラーが表示される問題を修正しました。 Analytics ]**で**[!UICONTROL &#x200B;表示をクリックすると、[!DNL Analytics for Target]分類情報が欠落している「互換性のないレポートスイート」メッセージも表示されました。 （TGT-56389）

+++

**[!UICONTROL Visual Experience Composer] （VEC）**

+++詳細を見る

* mbox **を通じて配信された[!DNL Experience Fragments]のオファー名の代わりに** Raw HTMLが表示されます。 [!DNL Experience Fragment]がmboxを通じて配信されたときに、**[!UICONTROL 変更]** パネルにオファー名ではなく生のHTML/コードが表示される問題を修正しました。 （TGT-56241）

+++

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
| [Adobe Experience Cloud リリースノート ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [Adobe 優先製品のアップデート](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | [!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションに対する今後の製品の機能強化に関する事前通知を受信します。 |
| [Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、当月の Target リリースに関する情報です。 |
