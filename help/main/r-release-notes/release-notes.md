---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート；現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
hold: true
source-git-commit: cad8c365028b28bd9349d2d283370e2c8a750180
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 35%

---

# [!DNL Target] リリースノート（最新）

[!DNL Adobe Target]の最新の機能、機能強化、および修正について説明します。 このリリースノートでは、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、および該当する場合はその他のプラットフォームコンポーネントのアップデートについても説明します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## 知っておく必要がある時間的制約のある更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

[!DNL Adobe Target]およびお客様の実装に関連する時間制限のある更新については、[!DNL Adobe]が[!UICONTROL Experience League]を通じて詳細なリリースノートとドキュメントを提供します。 Adobe Workfrontの導入に関する重要なハイライトを以下に示します。

### [!DNL Target] UI バージョン トグルの非推奨化

詳しくは、[[!DNL Target] UIの更新に関するFAQ](/help/main/c-intro/updated-ui-faq.md)を参照してください。


## [!DNL Target Standard/Premium] 26.4.1（2026年4月2日（PT））

**アクティビティ**

+++詳細を見る

* アクティビティ ビューに&#x200B;**オーディエンス属性が表示されます。** **[!UICONTROL Activity]**&#x200B;から表示されたオーディエンスルールの詳細で、同じオーディエンスを&#x200B;**[!UICONTROL Audiences]** セクションから開いたときに表示された特定の属性が表示されない問題を修正しました。 （TGT-54742）

* **追加のビューに適用すると、カスタムコードが保持されます。**&#x200B;同じ&#x200B;**[!UICONTROL View]**&#x200B;内の別の&#x200B;**[!UICONTROL View]**&#x200B;のカスタムコードを追加または保存する際に、1つの&#x200B;**[!UICONTROL Activity]**&#x200B;に適用されたカスタムコードが削除される問題を修正しました。 （TGT-53933）

* **アクティビティとオーディエンスのリストページでCSVを書き出します。** **[!UICONTROL Export CSV]** アクションを追加しました。これにより、日常的な書き出しのAPIのみに依存することなく、フィルターの適用時を含め、ユーザーインターフェイスからアクティビティリストを書き出すことができます。 （TGT-51466）

* **セレクターが見つからない場合、エクスペリエンスの変更がフラグ付けされます。** エクスペリエンスの変更で、セレクターの存在チェックが実行されるようになりました。ページにセレクターが見つからない場合、変更は無効としてフラグ付けされます。 （TGT-54815）

* **[!UICONTROL Automated personalization]件のアクティビティ。**&#x200B;自動パーソナライゼーションアクティビティの作成、編集、管理をユーザーが確実に行うことができず、キャンペーンの設定がブロックされ、パーソナライゼーションのユースケースが遅れる、インターフェイスとアクティビティの読み込みの問題が修正されました。 （TGT-54421）

+++

**オーディエンス**

+++詳細を見る

* アクティビティからオーディエンスを作成する際に、**オーディエンス名と説明が表示されます。** アクティビティフローからオーディエンスを作成または編集する際に、**[!UICONTROL Name]**&#x200B;の直下にオーディエンスを作成する場合と比較して、オーディエンス **[!UICONTROL Description]**&#x200B;と&#x200B;**[!UICONTROL Audiences]**&#x200B;のフィールドが明確に表示されない問題を修正しました。 （TGT-54837）

+++

**インサイト**

+++詳細を見る

* **[!UICONTROL Live Activities]はインサイトを利用しています。** インサイトダッシュボードの&#x200B;**[!UICONTROL Live Activities]**&#x200B;指標が、**[!UICONTROL All Activities]**&#x200B;にライブとして表示されたアクティビティの数よりも多い合計を報告する可能性がある問題を修正しました。 （TGT-54788）

+++

**レコメンデーション**

+++詳細を見る

* **の[!UICONTROL Global Exclusions]長いID リスト。** **[!UICONTROL Global Exclusions]**&#x200B;のIDの長いリストを貼り付けたり入力したりすると、更新されたインターフェイスでレガシーと比較して切り捨てられる問題を修正し、不完全な除外リストが発生します。 （TGT-54422）

+++

**[!UICONTROL Visual Experience Composer]（VEC）**

+++詳細を見る

* **の[!UICONTROL Visual Experience Composer]Enhanced Experience Composer （EEC） ステータスインジケーター。** EEC インジケーターは、拡張Experience Composerが有効かどうかを示します。 表示が修正され、インタラクティブではないステータス表示としてのみ機能するため、インタラクティブなトグルに似なくなりました。 （TGT-54828）

* **折りたたみ可能な左側のパネル（[!UICONTROL Visual Experience Composer]）。** アクティビティが編集用に開いている間に、左側のパネルを折りたたむことができるようになりました。 これにより、小さなディスプレイを含め、複数のオーディエンスとページを含むアクティビティの&#x200B;**[!UICONTROL Components]**&#x200B;と&#x200B;**[!UICONTROL Properties]**&#x200B;へのアクセスが改善されます。 （TGT-54269）

+++

## [!DNL Target Standard/Premium] 26.3.7（2026年3月26日（PT））

**オーディエンス**

+++詳細を見る

* オーディエンス インターフェイスで&#x200B;**オーディエンス ソース ラベルの精度。** Adobe Experience PlatformのAdobe Target v2の宛先から来たオーディエンスが、**Adobe Experience Platform**&#x200B;ではなく&#x200B;**Adobe Experience Cloud**&#x200B;をソースとして表示される問題を修正しました。 このアップデートにより、オーディエンスをフィルタリングおよびレビューする際のソースラベルの一貫性が向上します。 （TGT-54802）

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
