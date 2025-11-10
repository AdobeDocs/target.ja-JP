---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート；現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 693b862bc39fc3b1b7d93988bd80cdd51657354b
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 19%

---

# [!DNL Target] リリースノート（最新）

[!DNL Adobe Target] の最新の機能、機能強化および修正点について説明します。 これらのリリースノートでは、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、その他のプラットフォームコンポーネントのアップデート（該当する場合）についても説明します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## 必要となる、時間に依存する更新 {#time-sensitive}

[!BADGE &#x200B; 重要 &#x200B;]{type=Informative}

[!DNL Adobe Target] および実装に関する、時間依存の更新については、[!DNL Adobe] が [!UICONTROL Experience League] を通じて詳細なリリースノートとドキュメントを提供します。 実装に関連する主なハイライトを次に示します。

### [!DNL Target] UI バージョンの切り替えの廃止

詳しくは、[[!DNL Target] UI の更新に関する FAQ](/help/main/c-intro/updated-ui-faq.md) を参照してください。

## [!DNL Target Standard/Premium] 25.11.1 （2025 年 11 月 10 日（PT））


**Analytics for Target（A4T）**

+++詳細を表示
* 更新 **[!UICONTROL Goals & Settings]れた UI で [!DNL Adobe Analytics] をレポートソースとして使用する場合のエラーメッセージ。** 更新された [!UICONTROL Overview] UI で、「目標」セクションに「エラーが発生しました」と表示される問題を解決しました。 要求を完了できません。 [!DNL Adobe Client Care] （A4T）がレポートソースとして選択された場合に問題が解決しない場合は、[!DNL Adobe Analytics] にお問い合わせください。」 目標が [!UICONTROL Adobe Analytics] 指標と共に正しく表示され、レポートソース間で一貫した可視性が確保されるようになりました。 （TGT-54021）

+++

**オーディエンス**

+++詳細を表示
* **更新された UI で複数のレポートオーディエンスを選択できない。** 更新後の UI で、アクティビティを編集する際に、新しく作成された複数のレポートオーディエンスを同時に選択できなかった問題を修正しました。 複数のオーディエンスを一度に割り当てることができ、レポート設定の柔軟性と効率が向上しました。 （TGT-53253）

+++

**決定のオファー**

+++詳細を表示
* **更新された UI で決定オファーを編集または置換できない。** 更新された UI で、[!UICONTROL Modifications] 定パネルから決定オファーを編集または置き換えることができない問題が解決され、オファー名が空白に表示されるようになりました。 決定オファーが完全にアクセス可能かつ編集可能になり、従来の UI と同等の機能が復元され、顧客がアクティビティ内で直接オファーを管理できるようになります。 （TGT-53884）

+++

**ローカリゼーション**

+++詳細を表示
* **韓国語 UI と日本語 UI でいくつかのローカライゼーションエラーを修正しました。** （TGT-54003、TGT-54004、TGT-54006、TGT-54007、&amp; TGT-54018）

+++

**[!UICONTROL Recommendations]**

+++詳細を表示
* **エンティティ属性が一致する属性別のプロモーションで、アクティビティの保存後にレコメンデーションキーを読み込めませんでした。** ルールタイプ [!UICONTROL Promotion by Attribute] のタイプ [!UICONTROL Entity Attribute Matching] のプロモーションを、アクティビティを保存した後に編集すると、レコメンデーションキーが読み込まれない問題を修正しました。 この問題は、`customKeyId` がGraphQL経由でリクエストされなかったことが原因です。 プロモーションの編集中にレコメンデーションキーが正しく読み込まれるようになりました。 （TGT-53117）
* **ExpB から ExpA に切り替える場合、レコメンデーションは視覚的に保持されます。** エクスペリエンス B にレコメンデーションを挿入してからエクスペリエンス A に切り替えると、レコメンデーションオファーボックスが表示されたままになる問題を解決しました。 これは視覚的な不整合のみでした。エクスペリエンスを切り替える際に変更が正しくレンダリングされるようになり、UI の正確な動作が保証されるようになりました。 （TGT-53911）
* **[!UICONTROL Promotion by Attribute] 一致の [!UICONTROL Entity Attribute] に対するレコメンデーションキーが読み込まれない。** ルールタイプ [!UICONTROL Promotion by Attribute] のタイプ [!UICONTROL Entity Attribute Matching] のプロモーションを、アクティビティを保存した後に編集すると、レコメンデーションキーが読み込まれない問題を修正しました。 レコメンデーションキーがGraphQLを介して正しく取得され、プロモーションが期待どおりに表示および機能するようになりました。 （TGT-53917）
* **更新された UI で非表示のHTML要素に対するレコメンデーションの編集が機能しない。** [!UICONTROL New Create] および VEC UI で、非表示のHTML要素に適用されたレコメンデーションアクティビティを編集できない問題を修正しました。 この機能が期待どおりに動作するようになり、レガシー UI と同等の機能が復元され、要素の表示に関係なく、レコメンデーションを変更できるようになりました。 （TGT-53953）
* **更新された UI で非表示のHTML要素に対するレコメンデーションアクティビティを編集できない。** 更新された UI で、非表示のHTML要素に適用されたレコメンデーションアクティビティを編集できなかった問題を修正しました。 この機能が期待どおりに動作するようになり、レガシー UI と同等の機能が復元され、要素の表示に関係なく、レコメンデーションを変更できるようになりました。 （TGT-53951）
* **更新された UI に属性値が断続的に欠落している Recommendation カタログ。** 更新された [!UICONTROL Recommendations] UI で、製品フィードに存在しても、カタログ検索のリストに特定の属性値（メッセージなど）が断続的に表示されなかった問題を修正しました。 列を再構成しなくても、属性値が検索結果に一貫して読み込まれるようになり、カタログ管理の信頼性と効率が向上しました。 （TGT-52769）
* 更新された UI の **[!UICONTROL Download Recommendations]アクティビティに [!DNL Recommendations] ボタンがない。** 更新された [!DNL Recommendations] UI で、レコメンデーションを使用する A/B アクティビティに「[!UICONTROL Download Recommendations]」ボタンが表示されない問題を修正しました。 ボタンが正しく表示され、レガシー UI の機能と一致するように、レコメンデーションデータを期待どおりに書き出すことができるようになりました。 （TGT-53768）
* 更新された概要 UI に **[!UICONTROL Download Recommendation Data]ボタンが表示されません。** 更新された [!UICONTROL Overview] UI で、レコメンデーションを含むアクティビティに「[!UICONTROL Download Recommendation Data]」ボタンが表示されない問題を修正しました。 ボタンが正しく表示されるようになり、ユーザーはレガシー UI に切り替えることなく、レコメンデーションデータを直接エクスポートできるようになりました。 （TGT-53772）
* **アクティビティ条件を編集すると、更新された UI で空白の画面が表示されることがありました。** 更新された UI で、特定のアクティビティで [!UICONTROL Edit Criteria in Experiences] クリックすると空白の画面が表示されることがあった問題を解決しました。 条件エディターがすべてのアクティビティで確実に読み込まれるようになり、ユーザーが中断なく編集できるようになりました。 （TGT-53961）
* **更新された UI でシーケンス条件を編集できない。** 更新された UI で、[!UICONTROL Sequence Criteria] を編集しようとすると条件ポップアップが読み込み時に停止したままになり、空白の画面が表示される問題を修正しました。 条件エディターが正しく読み込まれ、ユーザーが中断することなくシーケンス条件を編集および更新できるようになりました。 （TGT-53985）

+++

**[!UICONTROL Reports]**

+++詳細を表示
* **[!UICONTROL Multivariate Test]（MVT）の場所とグラフレポートの問題により、レポートを生成できませんでした。** Target UI で MVT アクティビティが [!UICONTROL Location Contribution] およびグラフレポートの生成に失敗し、「エラーが発生しました。 リクエストを完了できません。」 レポートが UI 内で正しく読み込まれ、完全に表示されるようになりました。 （TGT-53654）
* **貢献度レポートエラーが原因で MVT レポート [!UICONTROL Element] 読み込まれない。** Target UI で MVT アクティビティレポートを読み込めない問題を修正しました。次のエラーが表示されます。「要素貢献度レポートを取得できませんでした」 レポートが正しく表示され、要素の貢献度を完全に把握できるようになりました。 （TGT-53691）
* **[!UICONTROL Experience Targeting] （XT）アクティビティの注文の詳細を CSV 問題に書き出す。** XT アクティビティで「[!UICONTROL Export Order Details to CSV]」オプションが正しく表示されず、空のファイルが返される問題を修正しました。 このオプションは AP アクティビティに対してのみ表示されるようになり、正確な書き出し機能を確保し、混乱を防ぎます。 （TGT-53798）

+++

**[!UICONTROL Visual Experience Composer]（VEC）**

+++詳細を表示
* ボタン **[!UICONTROL Delete Modification]問題により、アクティビティの変更を削除できませんでした。** [!UICONTROL Delete Modification] UI の [!DNL Target] ボタンが機能せず、ユーザーがアクティビティ内の変更を削除できなかった問題を修正しました。 ボタンが期待どおりに動作するようになり、変更を確実に遅滞なく削除できます。 （TGT-53728）
* **更新された UI で優先セレクターが認識されません。** 更新された UI で、`data-target-component-id` などの優先セレクターが VEC 内の CSS セレクターリストに表示されない問題を解決しました。 動的に生成されるクラス名ではなく、優先する属性を確実に選択できるようになり、SPA ページのアップデート間で安定したターゲティングを確保できるようになりました。 （TGT-53908）
* **[!UICONTROL Edit] ページと [!UICONTROL Overview] ページのアクティビティの場所の配置が一致していません。** [!UICONTROL Overview] ページのアクティビティの場所の番号が [!UICONTROL &#x200B; Edit Experience] ページで行われた更新と一致しない問題を解決しました。 位置は両方のビュー間で一貫するようになり、正確な位置合わせを確保し、位置の欠落や番号の誤りを防ぐことができます。 （TGT-53960 および TGT-53954）
* **更新された VEC で [!UICONTROL Design] モードに戻すことができません。** 更新された VEC UI で、[!UICONTROL Design] モードで新しいページに移動した後、[!UICONTROL Browse] モードに戻すことができなかった問題を修正しました。 [!UICONTROL Design] の切り替えが正しく機能し、ページ間で変更をシームレスに適用できるようになりました。 （TGT-53988 および TGT-53993）
* **クエリパラメーターがアクティビティの概要に表示されない。** 更新された UI で、アクティビティの [!UICONTROL Overview] ページにクエリパラメーターが表示されず、[!UICONTROL Overview] ージとページ配信 URL で不一致が発生する問題を修正しました。 クエリパラメーターが正しく表示されるようになり、アクティビティの場所が完全に表現され、ビュー間で一貫性を持つようになりました。 （TGT-53701）

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
