---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート；現在のアップデート
description: SDK、API、JavaScript ライブラリなど、[!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: '[!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: '[!DNL Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 6774b85f9515dd093d4e54492be54f7be3e92073
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 42%
---
# [!DNL Target] リリースノート（最新）

[!DNL Adobe Target]の最新の機能、機能強化、および修正について説明します。 このリリースノートでは、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、および該当する場合はその他のプラットフォームコンポーネントのアップデートについても説明します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target Standard/Premium] 26.9.4 （2026年9月17日）

**[!UICONTROL Visual Experience Composer] （VEC）**

+++詳細を見る

* **[!UICONTROL 最も上のページ要素**&#x200B;の[!DNL Experience Fragments]に対して]の前に挿入コントロールにアクセスできません。 Visual Experience Composerで、ページの一番上の要素を選択すると、ページが上にスクロールされ、**[!UICONTROL 前に挿入]** コントロールが選択できない表示可能なビューポートの上にレンダリングされます。 （TGT-55829）

+++

## [!DNL Target Standard/Premium] 26.9.3 （2026年9月16日（PT））

**[!UICONTROL レポート]**

+++詳細を見る

* **一部の[!DNL A4T Auto-Target] レポートで[!UICONTROL 上昇率]と[!UICONTROL 信頼性]の値がありません**。 **[!UICONTROL 訪問コンバージョン率を最大化]**&#x200B;の最適化目標を使用する[!DNL A4T Auto-Target] アクティビティの場合、デフォルトの&#x200B;**[!UICONTROL マイプライマリ指標]** レポート指標が正しく解決されず、**[!UICONTROL 上昇率]**&#x200B;と&#x200B;**[!UICONTROL 信頼性]**&#x200B;が空白のままになります。 （TGT-56137）

+++

**[!UICONTROL ターゲットの分析]**

+++詳細を見る

* **[!UICONTROL レポート Source] フィールドは、[!DNL Analytics] アクセスのないライブアクティビティに対して読み取り専用になりました**。 以前は、ライブアクティビティの所有者が[!DNL Adobe Analytics]にアクセスできなかった場合、**[!UICONTROL レポートSource]** フィールドとその関連フィールドは編集可能なままでした。 （TGT-56089）

+++

## [!DNL Target Standard/Premium] 26.9.2 （2026年9月8日）


**[!UICONTROL レコメンデーション]**

+++詳細を見る

* **[!DNL New]ユーザーインターフェイスがフィード URLを誤ってエンコードしています**。 新しい[!DNL Target] インターフェイスのURLからレコメンデーションフィードを作成する際に、フィード URLが正しくエンコードされなかったため、フィードの作成が不明なエラーで失敗しました。 （TGT-56084）

+++

**[!UICONTROL レポート]**

+++詳細を見る

* **自動セグメントレポートで、属性値が一貫して表示されない**。 自動セグメントのレポートでは、[!DNL Automated Personalization]および[!DNL Auto-Target] アクティビティの属性値と範囲が一貫して表示されません。 一部の自動セグメントでは、関連付けられた値や範囲ではなく、属性名のみが表示されていました。 （TGT-55855）

+++

## [!DNL Target Standard/Premium] 26.9.1 （2026年9月1日）

**[!UICONTROL オーディエンス]**

+++詳細を見る

* **アクティビティ専用オーディエンスを含むアクティビティのコピーが保存に失敗しました**。 A/B アクティビティでアクティビティ専用（ローカル範囲）のオーディエンスルールとカスタムコードの変更を使用する場合、コピーをコピーして保存すると、「無効なオーディエンス ID」エラーが発生して失敗します。 （TGT-55785）

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
