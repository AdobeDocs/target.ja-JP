---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート、現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5f41bcebce4e103fada006f53cd3ccd297769d0d
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 28%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target Standard/Premium] 25.6.1（2025年6月6日（PT））

このリリースには、次の修正および更新が含まれています。

* QA リンクで、関連するアクティビティに対して正しいエクスペリエンスが提供されなかった問題を修正しました。 （TGT-52163 および TGT-52790）
* QA リンクで、関連するオーディエンス ID が欠落していた問題を修正しました。 （TGT-52722）
* 設定されたページ配信 URL 条件が正確に満たされた場合にのみエクスペリエンスが配信される問題を修正しました。 （TGT-52696）
* お客様が [!DNL Recommendations] デザインテンプレートを作成できない問題を修正しました。 テンプレートを作成しようとすると、「スクリプト内でエンティティ変数が少なくとも 1 つ使用されている必要があります」というエラーがトリガーされました。 （TGT-52395）
* Velocity 配列を使用して [!DNL Recommendations] デザインを保存できない問題を修正しました。 「スクリプト内で使用されるエンティティ変数が 1 つ以上あるはずです」というエラーメッセージが誤ってトリガーされていました。 （TGT-52734）
* 内部 web ページのページを読み込めない場合に、[!UICONTROL Visual Experience Composer] （VEC）で変更にアクセスできない問題を修正しました。 （TGT-52488 &amp;TGT-52470）
* VEC の小さい画面サイズで [!UICONTROL Modifications] パネルが表示されない問題を修正しました。 （TGT-52470）
* 更新された VEC で、[!UICONTROL Browse] モードから [!UICONTROL Design] モードに切り替えるとコンソールエラーが発生し、それ以上のインタラクションが妨げられる問題を修正しました。 （TGT-52532）
* VEC で、特定の要素をクリックすると意図せずサイズが拡大される問題を修正しました。 （TGT-52497）
* VEC で特定のページ要素の読み込みまたは認識に失敗し、ボタンやバナーの選択などのインタラクションが発生したり、アクティビティの正確なイベント追跡が中断されたりする問題を修正しました。 （TGT-52663）
* [!UICONTROL Automated Personalization] （AP）アクティビティで、お客様がオファーを削除できない問題を修正しました。 （TGT-52690）
* 複数ページアクティビティでアクティビティの選定動作に一貫性がなかった問題を修正しました。 （TGT-52694）
* アクティビティの [!UICONTROL Overview] ページに [!UICONTROL Activity Location] の無効な URL が表示される問題を修正しました。 （TGT-52695）
* 更新された [!DNL Target] UI で、アクティビティの場所に重複するエントリが表示される問題を修正しました。 （TGT-52693）
* `getAudiencesV3` エラーをトリガーして、顧客がアクティビティを編集またはコピーできなかった問題を修正しました。 （TGT-52709）
* [!UICONTROL Experience Fragments] またはHTML オファーをアクティビティに追加する際に、「無効なペイロードです」エラーが発生する問題を修正しました。 （TGT-52779 および TGT-52773）
* 更新された [!DNL Target] UI で、無効な入力エラーが原因で E[!UICONTROL xperience Fragments] が正しく表示されなかった問題を修正しました。 （TGT-52701）
* 無効なユーザーエラーが原因で、お客様が [!UICONTROL Form-based Experience Composer] でアクティビティを編集できない問題を修正しました。 （TGT-52470）
* 以前の翻訳で基本多言語平面外の文字が使用されていた韓国語のローカライゼーションの問題を修正しました。 更新された翻訳では、意図した意味を正確に伝える適切な文字を使用しています。 （TGT-52508 および TGT-52509）
* 韓国語ローカライゼーションの問題を修正しました。アクティビティの開始日と終了日を選択する際に、「日付」の翻訳が一貫していませんでした。 （TGT-52510）

## Target UI バージョンの切り替えの廃止（2025 年 5 月 23 日（PT）） {#toggle}

新しい [!DNL Target] ユーザーインターフェイスのロールアウトは、**2025 年 5 月 27 日（PT）** までに完了します。 その時点で、すべてのお客様が最新の UI バージョンにアクセスできます。

**2025 年 6 月 22 日** 以降、UI バージョンの切り替えが削除されます。 すべてのユーザーは新しいインターフェイスに永続的に移行しますが、以前のバージョンに戻すオプションはありません。

### UI バージョンの切り替えに関する重要な情報

切り替えボタンを使用して、更新された [!DNL Target] UI とレガシーバージョンを切り替えることができる一時機能を提供しています。 このオプションは、UI ロールアウトの最終フェーズでのみ使用できます。

![Target UI のバージョン切り替え ](/help/main/r-release-notes/assets/toggle.png)

ロールアウトが完了すると、切り替えが削除され、すべてのユーザーは更新済み UI に永続的に移行します **2025 年 6 月 22 日（PT）**。 この機能は間もなく廃止される予定なので、Adobeでは、事前に計画することをお勧めします。

### UI の切り替え動作の制限

* **新しいアクティビティの表示**：レガシー UI に切り替えた場合、更新された UI で作成されたアクティビティは表示されません。
* **既存のアクティビティの編集**：更新された UI の使用中に既存のアクティビティ（元々はレガシー UI で作成したもの）に加えられた変更が、web サイトに公開されます。 ただし、これらの更新は、戻してもレガシー UI には表示されません。レガシー UI から最後に作成された更新のみが表示されます。
* **アクティビティ詳細の一貫性**：使用する UI に関係なく、最新の変更がライブ web サイトに反映されます。 ただし、レガシー UI に表示されるのは、そのバージョン内で行われた最新の変更のみです。 更新された UI で編集されたアクティビティが、レガシー UI で表示されるものとは異なる表示になる場合は、混乱を招く可能性があります。

### 更新された UI に関する詳細情報

* [[!DNL Target Standard/Premium] 25.2.1 （2025 年 2 月 17 日（PT））リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2):[!UICONTROL Activities]、[!UICONTROL Recommendations] および [!UICONTROL Visual Experience Composer] （VEC）の [!DNL Target] の主な UI の変更点の概要を説明します。

* [[!DNL Target Standard/Premium] 25.1.1 （2025 年 1 月 9 日（PT））リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1):[!UICONTROL Offers Library] の [!DNL Target] での主な UI の変更点の概要を説明します。

* [ [!DNL Target] UI について ](/help/main/c-intro/understand-the-target-ui.md):[!DNL Target] に慣れるのに役立つ概要と、より詳細な情報と手順を説明するリンクを提供します。

* [[!UICONTROL Visual Experience Composer] の変更点 ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1 リリース（2015 年 2 月 17 日（PT））では、更新された [!UICONTROL Visual Experience Composer] （VEC）が導入されています。 この記事では、VEC のレガシーバージョンと更新バージョンの違いについて説明します。

* [[!UICONTROL Visual Experience Composer] options](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：この記事では、更新された VEC UI とそのオプションについて説明します。

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
