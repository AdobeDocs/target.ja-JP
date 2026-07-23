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
source-git-commit: c74d8b09fba181fcded2f982d99a03f1e7f3a07a
workflow-type: tm+mt
source-wordcount: 927
ht-degree: 29%

---

# [!DNL Target] リリースノート（最新）

[!DNL Adobe Target]の最新の機能、機能強化、および修正について説明します。 このリリースノートでは、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、および該当する場合はその他のプラットフォームコンポーネントのアップデートについても説明します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target Standard/Premium] 26.7.4 （2026年7月23日（PT））

**レポート**

+++詳細を見る

* **特定のモバイルオーディエンスのコンバージョン率グラフは使用できません。** 特定のモバイルオーディエンスに対して[!UICONTROL &#x200B; コンバージョン率] グラフがレンダリングされない問題を修正しました。 （TGT-55611）

* **「表示されたmbox」のコンバージョン目標は、ドロップダウンから選択すると機能しません。** 「[!UICONTROL 目標と設定]」でドロップダウンからmboxを選択すると、mbox名が正しく保存されず、コンバージョンが記録されない問題を修正しました。 （TGT-55588）

+++

**オーディエンス**

+++詳細を見る

* オーディエンスライブラリページの&#x200B;**レイアウトの問題。** サイドナビゲーションが折りたたまれている間に、[!UICONTROL &#x200B; オーディエンスライブラリ &#x200B;] ページでフィルターが有効になったときに発生したレイアウトの問題を修正しました。 （TGT-55502）

+++

**[!UICONTROL Visual Experience Composer] （VEC）**

+++詳細を見る

* **モバイルバージョンが正しく読み込まれません。** [!UICONTROL Visual Experience Composer]で更新する方法が提供されず、モバイルビューが正しく読み込まれない問題を修正しました。 （TGT-54408）

* **変更アクションの編集または削除が機能しません。** 「[!UICONTROL &#x200B; エクスペリエンスを編集]」ビューから変更を編集または削除しても機能しない問題を修正しました。 （TGT-55250）

* **アクティビティの読み込み後、参照モードが応答しません。** 変更を含むエクスペリエンスに対して[!UICONTROL 参照] モードが応答しなくなり、それ以上のナビゲーションとオーサリングが妨げられる問題を修正しました。 （TGT-55306）

* **Salesforce LWC （Shadow DOM）内の要素を選択できません。** [!UICONTROL Visual Experience Composer]が、Shadow DOMを使用してSalesforce Lightning Web コンポーネント内にネストされた要素を選択できず、「セレクターが見つかりません」というエラーが発生する問題を修正しました。 （TGT-54956）

* **重複オファーが[!UICONTROL Visual Experience Composer]に表示されました。** 変更とオファーがアクティビティのオーサリング UIで断続的に重複して表示される問題を修正しました。 （TGT-55685）

+++

**管理**

+++詳細を見る

* **コンテンツ生成アシスタントの名前を[!UICONTROL &#x200B; コンテンツを生成].**&#x200B;に変更しました 「AI アシスタント」コンテンツ生成機能の名前を[!DNL Target]のUI サーフェス全体で[!UICONTROL &#x200B; コンテンツを生成]に変更しました。 （TGT-55689）

+++

**レコメンデーション**

+++詳細を見る

* **プロファイル属性を使用した人気ベースのレコメンデーション。** [!DNL Target]は、国、優先言語、メンバーシップ レベルなどの訪問者プロファイル属性によって、人気レコメンデーションのグループ化、最も閲覧された販売者および上位セラーを動的にサポートするようになりました。 （TAPER-7614）

* **レコメンデーションコレクションが[!UICONTROL &#x200B; コレクション &#x200B;]とアクティビティ設定との間で一致しません。** [!UICONTROL Recommendations] > [!UICONTROL &#x200B; コレクション &#x200B;] ビューと比較して、[!UICONTROL Recommendations] コレクションがアクティビティ設定から表示された際に追加の非適格エンティティを返す問題を修正しました。 （TGT-55554）

+++

## [!DNL Target Standard/Premium] 26.7.2 （2026年7月16日）

**アクティビティ**

+++詳細を見る

* **アクティビティの概要 ページの目標情報が正しくありません。** [!DNL Automated Personalization] アクティビティの[!UICONTROL &#x200B; アクティビティの概要] ページで、最適化目標ではなく追加の目標が表示される問題を修正しました。 （TGT-55553）

* [!UICONTROL 参照] モードでページを移動すると、**応答しない画面が表示されます。** [!UICONTROL 参照] モードでページ間を移動すると、画面が応答しなくなる問題を修正しました。 （TGT-55565）

+++

**ホームページ**

+++詳細を見る

* [!UICONTROL &#x200B; トップパフォーマー]と[!UICONTROL 保存]の&#x200B;**UIの変更。** トップパフォーマーのUIを更新し、エクスペリエンスを節約しました。 （TGT-54975）

+++

**オーディエンス**

+++詳細を見る

* **プロファイルスクリプトを作成[!UICONTROL &#x200B; ダイアログでローカライズされていない文字列。** &#x200B;]&#x200B;[!UICONTROL &#x200B; プロファイルスクリプトを作成] ダイアログの文字列がローカライズされない問題を修正しました。 （TGT-51527）

+++

## [!DNL Target Standard/Premium] 26.7.1 （2026年7月9日）

**アクティビティ**

+++詳細を見る

* **アクティビティ 、[!UICONTROL &#x200B; オーディエンス &#x200B;]、[!UICONTROL &#x200B; オファー] ページにわたってソース表示に一貫性がありません。** ソースが[!UICONTROL &#x200B; アクティビティ &#x200B;]、[!UICONTROL &#x200B; オーディエンス &#x200B;]、[!UICONTROL &#x200B; オファー] ページにわたって一貫して表示されない問題を修正しました。 （TGT-55247）

* **UIを介した編集時にアクティビティソースが変更される。** UIを使用してアクティビティを編集すると、元のアクティビティソースが変更される問題を修正しました。 （TGT-55248）

+++

**オーディエンス**

+++詳細を見る

* **オーディエンスの編集時の既定のワークスペースが正しくありません。** オーディエンスを編集した後にデフォルトのワークスペースが正しくない問題を修正しました。 （TGT-55510）

+++

**レポート**

+++詳細を見る

* 5月のレポートの&#x200B;**CSVのダウンロードに失敗しました。** 5月のCSV レポートのダウンロードに失敗する問題を修正しました。 （TGT-55524）

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
| [Adobe Experience Cloud リリースノート &#x200B;](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [Adobe 優先製品のアップデート](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | [!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションに対する今後の製品の機能強化に関する事前通知を受信します。 |
| [Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、当月の Target リリースに関する情報です。 |
