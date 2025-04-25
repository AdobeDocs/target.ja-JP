---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート、現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 579ebd9bebd3faa724f0d1d542f4d23766adefe3
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 24%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target Standard/Premium] 25.4.5 （2025 年 4 月 25 日（PT））

このリリースには、次の修正および更新が含まれています。

* [!UICONTROL Activity] 設定ページと [!UICONTROL Reporting] の概要ページの間でオーディエンスのリストに不一致が生じる問題を修正しました。 （TGT-52203）
* 無効なユーザー入力エラーが原因で、アクティビティに新しいページを追加できない問題を修正しました。 （TGT-52263）
* オプションが変更されていない場合に、`OptionLocalIDs` が誤って増分される問題を修正しました。 （TGT-52187）
* オプションが変更されていないときに、`location` と `OptionLocalIDs` が誤って増加する問題を修正しました。 （TGT-52188）
* アクティビティの [!UICONTROL Overview] ページ上の場所が正しくない問題を修正しました。 （TGT-52182）
* 無効な場所に対して無効なセレクター警告が表示されなかった問題を修正しました。 （TGT-52110）
* ダウンロードしたレポートファイルでレポート UI に存在するデータが正しく表示される問題を修正しました。 （TGT-52068）
* ページ配信ルールを追加した後、バッチ操作が失敗しないように問題を修正しました。 （TGT-52097）
* [!DNL Target] が web サイトの URL からすべてのクエリパラメーターをトリミングする問題を修正しました。 （TGT-52100）
* 従来の UI と更新された [!DNL Target] UI の両方で、お客様がアクティビティを作成できなかったコンソールエラーを解決しました。 （TGT-52181）
* 顧客が新しいページを追加できず、無効なユーザー入力エラーが発生する問題を修正しました。 （TGT-52258）
* ページを追加してから「[!UICONTROL Experiences]」タブに戻ると変更が消える問題を修正しました。 （TGT-52264）
* 顧客が [!UICONTROL Experience Targeting] （XT）アクティビティのオーディエンスを変更できなかった問題を修正しました。 （TGT-52191）
* サポートされていない UI ルールが原因で XT アクティビティを編集できないエラーを修正しました。 （TGT-52273）
* 更新 [!UICONTROL Visual Experience Composer] （VEC）で、パンくずリストがエディターの下部に常に表示されず、要素を正確に選択するのが困難になる問題を修正しました。 （TGT-52169）
* [!UICONTROL Audience] ドロップダウンリストで、ページネーションが原因ですべてのオーディエンスを表示できなかった問題を修正しました。 （TGT-52204）
* [!UICONTROL Automated Personalization] （AP）アクティビティに新しいオファーを追加する際に、無効なユーザー入力メッセージが表示される問題を修正しました。 （TGT-52210）
* 顧客が A4T にアクセスできない場合でも、[!UICONTROL Analytics for Target] （A4T）が誤ってレポートソースとして選択される問題を修正しました。 （TGT-52226）
* [!UICONTROL View a Page] URL 指標を使用してアクティビティを保存できない問題を修正しました。 （TGT-52260）
* アクティビティ内でオファーを作成する際に、顧客がワークスペースを選択できなかった問題を修正しました。 （TGT-52289）
* 顧客がすべてのワークスペースでアクティビティを作成できなかった問題を修正しました。 （Tgt-52218）
* 別のエクスペリエンスに切り替えると、あるエクスペリエンスからの変更が正しく表示されない問題を修正しました。 （TGT-52184）
* アクティビティを開いたときに、[!DNL Target] UI にデフォルトオファーが正しく表示されない問題を修正しました。 （TGT-52198）

## Target 権限の更新（2025 年 4 月 22 日（PT））

この今後の更新により、[!DNL Target] インスタンス設定の組織管理が強化され、様々なテストやパーソナライゼーションチームにわたるアクティビティの配信に影響を与える可能性のある、誤った更新を防ぐことができます。

2025 年 4 月 22 日（PT）より、[!UICONTROL Product] と [!UICONTROL Solutions] の管理者のみが、ワークスペースでの役割に関係なく、[!UICONTROL Administration] セクションの設定を更新でき [!DNL Target] ようになります。 この権限を持たないユーザーは、[!UICONTROL Administration] のセクションに読み取り専用でアクセスできます。

詳しくは、[Target の管理 ](/help/main/administrating-target/start-target.md) を参照してください。

## [!DNL Target Standard/Premium] 25.4.4 （2025 年 4 月 17 日（PT））

このリリースには、次の修正および更新が含まれています。

* アクティビティで重複オプションを解決する際にユーザーをガイドするエラーメッセージを追加しました。 （TGT-51927）
* リダイレクトオファーを使用してページまたはエクスペリエンスを削除する際に、`ClickTrack` セレクターが削除されない問題を修正しました。 （TGT-51952）
* 空の `ClickTrack` セレクターを許可することで発生する問題を修正しました。 [!DNL Target] では、セレクターフィールドを空白にすることはできないという要件が追加されました。 （TGT-52107）
* 重複した名前の指標が正しく許可されない問題を修正しました。 指標に一意の名前が必要になりました。 （TGT-52201）
* [!UICONTROL Automated Personalization] （AP）アクティビティでオファーレベルのターゲティングを編集する際に、オーディエンス定義が表示されない問題を修正しました。 （TGT-52148）
* [!UICONTROL Editor] 権限を持つお客様がアクティビティを保存できない問題を修正しました。 （TGT-52227）
* オプション `OptionLocalIDs` 変更されていないときに、が正しく増分されなくなりました。 （TGT-52139）
* アクティビティを作成しようとすると「無効な `optionLocalIds`」メッセージが表示される問題を修正しました。 （TGT-52154）
* アクティビティに対して定義され `OptionLocalIDs` アクティビティと、エクスペリエンスの定義に使用されるアクティビティとの間の不一致が修正されました。 （TGT-52215）
* A/B アクティビティを作成しようとすると検証エラーが発生する問題を修正しました。 （TGT-51923）

## [!DNL Target Standard/Premium] 25.4.3 （2025 年 4 月 11 日（PT））

このリリースには、次の修正および更新が含まれています。

* 特定の [!UICONTROL Experience Targeting] （XT）アクティビティで、お客様がオーディエンス情報ポップアップを開くことができないエラーを修正しました。 （TGT-52049）
* [!UICONTROL Visual Experience Composer] （VEC）で行われた変更に続いて、オーディエンス設定が「[!UICONTROL All Visitors]」に戻る問題を修正しました。 （TGT-52132）
* 特定のアクティビティに対してオーディエンスの絞り込みが表示されない問題を修正しました（TGT-52057）
* お客様がデフォルトワークスペースに [!UICONTROL Experience Fragment] を挿入できない問題を修正しました。 （TGT-52073）
* オファーが「コンテンツが見つかりません」と表示され、[!UICONTROL Automated Personalization] （AP）アクティビティの [!UICONTROL Offers] ページに表示されない問題を修正しました。 （TGT-52150）
* アクティビティ内で重複オーディエンスを許可する機能を追加しました。 （TGT-51200）
* 編集後に XT アクティビティの [!UICONTROL Goals & Settings] ページに間違った mbox 名が表示される問題を修正しました。 （TGT-52026）
* `experiences/optionLocations` に表示さ `defaultContent` ていないにもかかわらず、オプションに表示される問題を修正しました。 （TGT-52036）
* 空の文字列が null 値に変換されないようにする問題を修正しました。 （TGT-52037）
* 顧客が編集後に [!UICONTROL Goals & Settings] ページで [!UICONTROL Reporting Settings] の [!UICONTROL Optimization Goal] を再設定する必要がある問題を修正しました。 （TGT-52071）
* ページ配信ルールを持たないアクティビティで、[!UICONTROL Overview] のページに複数のルールが表示される問題を修正しました。 （TGT-52084）
* 基本多言語平面外の文字（絵文字など）を使用してオファーを保存しようとしたユーザーに対するエラーメッセージを追加しました。 （TGT-52105）
* アクティビティを開くと、「このアクティビティは、ソースで削除された 1 つ以上のオーディエンスを使用しています」というエラーメッセージがトリガーされる問題を修正しました。 （TGT-52120）
* 編集中に、更新された [!UICONTROL Visual Experience Composer] （VEC）にクリックトラック指標が表示されない問題を修正しました。 （TGT-52152）
* アクティビティの場所としてクエリパラメーターを含む URL において、アクティビティの [!UICONTROL Overview] ールページにクエリパラメーターが表示されない問題を修正しました。 （TGT-51635）
* [!UICONTROL Visual Experience Composer] （VEC）内でエクスペリエンス URL 全体が [!UICONTROL Browse mode] に表示されない問題を修正しました。 （TGT-52101）
* アクティビティを編集するとページ配信で URL の末尾に「/」が追加され、レンダリングが無効になる問題を修正しました。 （TGT-52114）
* [!UICONTROL Form-Based Experience Composer] の [!UICONTROL Activity QA] リンクが [!DNL Adobe Experience Cloud] ホームページに誤ってリダイレクトされる問題を修正しました。 （TGT-52055）
* 保存して再度開いた後に、[!UICONTROL A/B Test] アクティビティに追加された追加のページが保持されない問題を修正しました。 （TGT-51994）
* 顧客がインラインスタイルセクションのスタイルを削除できない問題を修正しました。 （TGT-52070）
* 従来の UI と同様に、[!UICONTROL Activity QA] 定ダイアログボックスでの [ オーディエンス定義カード ](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) へのアクセス権が復元されました。 （TGT-52056）
* 更新された UI では、変更を加えずにページやオーディエンスを保存することができませんでした。 顧客がアクティビティに新しいページやオーディエンスを追加しても、変更を加えない場合、保存時に変更さ [!DNL Target] ていないオーディエンスは破棄されます。 この動作をユーザーに通知するために、関連する場所に通知が追加されました。 （TGT-52104）

## [!DNL Target Standard/Premium] 25.4.1 （2025 年 4 月 2 日（Pt））

このリリースには、次の修正および更新が含まれています。

* エクスペリエンスオーディエンスがアクティビティから消える問題を修正しました。 （TGT-52003）
* 配信中に予期しない要素が発生する問題を修正しました。 （TGT-52011）
* オーディエンス表示ページ上のターゲティンググラフおよびアクティビティの編集中に顧客がオーディエンスを [!UICONTROL r] 示できない問題を修正しました。 （TGT-52050）
* [!UICONTROL Experience Targeting] （XT）アクティビティで、お客様がエクスペリエンスを優先順に並べ替えることができない問題を修正しました。 （TGT-52054）
* テキストスタイルの変更を元に戻すと、誤ったレンダリングが発生する問題を修正しました。 （TGT-51876）
* リダイレクトオファーを変更すると、[!DNL Target] がそのオファーに関連付けられた [!UICONTROL ClickTrack] セレクターも削除する問題を修正しました。 （TGT-51936）
* リク [!UICONTROL ClickTrack] ストのキャンセル時に [!DNL Target] がセレクターを誤って保存する問題を修正しました。 （TGT-51937）
* [!UICONTROL Goals & Settings] ページで mbox ピッカーを開いたり閉じたりしても、何も変更を加えずに「無効な名前」エラーが発生する問題を修正しました。 （TGT-51983）
* 従来の [!DNL Target] UI で作成されたアドホックオファーの編集がブロックされていた問題を修正しました。 （TGT-51984）
* カスタムコードを含むアドホックオファーがあるアクティビティの編集がブロックされていた問題を修正しました。 （TGT-51995）
* 結合されたオーディエンス定義を編集する際に、除外ルールがインクルージョンルールとして表示される問題を修正しました。 （TGT-51999）
* エクスペリエンスの編集中にカスタムコードが正しく表示されない問題を修正しました。 （TGT-52005）
* [!UICONTROL Insert Before] オプションでナビゲーションバーの前にコンテンツを挿入できない問題を修正しました。 （TGT-52031）
* レポートでデフォルトのエクスペリエンスを正しくハイライト表示できない問題を修正しました。 （TGT-51716）
* アクティビティの作成時に `default message [Invalid optionLocalIds: xx]]` メッセージがトリガーされる問題を修正しました。 （TGT-52038）

## at.js バージョン 2.11.8 （2025 年 3 月 31 日）

* サイズ変更および移動操作中のエッジケースを防ぐために、文字列サフィックス検証で CodeQL が識別する脆弱性を解決しました。 （TNT-51516）

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
