---
description: 以下のリリースノートでは、Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
keywords: リリースノート、プレリリース版
seo-description: これらのリリースノートでは、Adobe Target Standard およびTarget Premiumの各リリースの機能、機能強化、修正および既知の問題について説明します。
seo-title: Target リリースノート（現行）
solution: 'Target '
title: Target リリースノート（現行）
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。

## 発表

以下の重要なお知らせに注意してください。

* 2019年2月21日に、ヨーロッパ、日本、APACの各地域でAdobe Targetインフラストラクチャがアップグレードされ、TLS1.1以降をサポートしていない古いデバイスまたはWebブラウザーを使用したエンドユーザーからデータを収集することがなくなりました。このアップグレードは、2019年4月1日の **北米地域向けに予定**されています。TLS 1.2 への移行により、セキュリティが向上します。重要なのは、詳細を調べて、スムーズな移行を実現するためにITチームによる変更を計画することです。詳しくは [、TLS（Transport Layer Security）暗号化の変更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)を参照してください。
* [!DNL Target] と [!DNL Adobe Marketing Cloud] は、2019 年 3 月に Microsoft Internet Explorer 11 のサポートを終了します。この変更は [!DNL Target] オーサリングにのみ影響します。この変更は、エクスペリエンス配信に影響しません。Microsoft Edge か別のブラウザーに切り替えてください。詳しくは、「[サポートされているブラウザー](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)」を参照してください。

## Mobile App Visual Experience Composer（2019年5月14日）{mobile- vec}

| 機能/拡張機能 | 説明 |
| --- | --- |
| Mobile App Visual Experience Composer（VEC） | Mobile App VECを使用すると、継続的な開発依存関係やアプリリリースサイクルを使用せずに、アクティビティを作成し、ネイティブモバイルアプリケーションにコンテンツをパーソナライズできます。<br>詳しくは、以下を参照してください。<ul><li>[モバイルアプリケーション Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - モバイルアプリケーションのセットアップ](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - モバイルアプリケーションのセットアップ](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[モバイル VEC でのクリック追跡のセットアップ](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li></ul> |

## [!DNL Target] Standard/Premium19.4.2（2019年4月30日） {#release-19-4-2}

このリリースには、次の機能、変更および機能強化が含まれています。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます）。

### 機能の更新

| 機能/拡張機能 | 説明 |
| --- | --- |
| [!UICONTROL Visual Experience Composer] | [!UICONTROL Visual Experience Composer] （VEC）には、次の機能強化が含まれていて、作業を迅速かつ効率的に行うことができます。<ul><li>クリック追跡の設定時にDOMパス機能が使用できるようになりました。<br>詳しくは [、クリック追跡](/help/c-activities/r-success-metrics/click-tracking.md#considerations)を参照してください。</li><li>スタイルパネルを使用して、選択した要素の既存のスタイルの値を表示または編集します。さらに、スタイル設定を追加することもできます。<br>スタイルパネルにアクセスするには、VEC内からページ要素をクリックし、 [!UICONTROL 編集] / [!UICONTROL スタイルをクリック]します。<br>スタイルパネルは、VECの右側に表示されます。パネルには、選択した要素を編集または追加できるスタイルのリストが含まれています。リアルタイムCSSエディターを使用すると、カスケーディングスタイルシート（CSS）を使用する場合や開発者からコードを受け取った場合に、変更を表示したりスタイルを追加したりできます。<br>詳しくは、Visual Experience [Composerのオプション](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles) の *スタイル*を参照してください。</li><li>リッチテキストエディターで、ネストされたHTML5要素がサポートされるようになりました。<br>HTML5仕様では、ネスト用の新しいタグの組み合わせが可能です。以前のバージョンのリッチテキストエディターは、HTML5仕様で許可されているタグの新しいネストをサポートしていませんでした。その結果、VECで選択されたネストされた要素が正しく処理されず、不要なHTMLが変更されていました。（TGT-33618）<br>詳しくは、Visual Experience [Composerのオプション](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#edit-text-html) の *テキスト/HTMLの編集を参照*してください。</li> |

### 機能強化、修正、変更点

* VEC を使用してアセットを削除する際のワークフローを改善しました。削除されたアセットは [!UICONTROL 、オファーライブラリ] から削除されるようになりました [!DNL Scene7] （該当する場合）。削除されたアセットは、検索結果に表示されなくなりました。（TGT-31981）
* アセットが含まれていても、アセットフォルダを削除できるようになりました。（TGT-33265）

   以前は、Target画像から空でないフォルダを削除できませんでした（[!UICONTROL オファー] / [!UICONTROL 画像オファー]）。「フォルダーが空ではありません!&quot;と表示されます。通知が表示されます。この機能を使用すると、フォルダーの削除を実行して、任意の数のアセットとサブフォルダーを含むフォルダー全体を削除する機能を追加できます。この機能は、Adobe Experience Cloud Assets UIでもTarget UIで使用できます。

   * 画像オファーライブラリ内の空のフォルダは削除できます。フォルダー内のすべての画像がどのアクティビティでも参照されていない場合、フォルダー全体とそのコンテンツが削除されます。フォルダー内の一部の画像がどのアクティビティでも参照されている場合、参照されていないすべての画像は削除されますが、参照画像とそれらの画像を含むフォルダは保持されます。
   * 画像アセットピッカーでの画像オファーのレンダリングは、高速で効率的に実行できます。
   詳しくは、ライブラリ内の [コンテンツの操作](/help/c-experiences/c-manage-content/assets-working.md)を参照してください。（TGT-32897）

* アセットピッカーの画像オファーのレンダリングを改善しました。画像オファーの表示および選択がよりすばやく効率的になりました。（TGT-32897）
* VEC 内でページの読み込みをキャンセルする際の URL へのリダイレクトの処理を改善しました。（TGT-33815）
* コレクションピッカーから [!UICONTROL Recommendations] コレクションを選択した後、 [!UICONTROL 「保存」] ボタンをクリックする必要があります。このワークフローは、他 [!DNL Target]のワークフローと一致しています。（TGT-33205）
* インサイトレポートの小さなセットが実際のコンバージョン率ではなく0%のコンバージョン率を返す問題を修正しました。（TNT-32125）

## [!DNL Target] Standard/Premium19.4.1（2019年4月16日） {#release-19-4-1}

このリリースは、メンテナンスリリースです。以下のような変更が含まれています。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます）。

* ブランディングと製品の変更を反映する [!DNL Adobe Experience Cloud] ようにUIを更新しました。（TGT-33546、TGT-33272 および TGT-33331）

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート {#section_1BC5F5208DA548E9B4344A0836E4B943}

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報が表示されます。<br>詳しくは [、「ドキュメントの変更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、以前のリリースの [リリースノート](../r-release-notes/release-notes-for-previous-releases.md)を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは [、Experience Cloudリリースノート](https://marketing.adobe.com/resources/help/en_US/whatsnew/)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update リスト | Targetおよびその他のAdobe Experience Cloudソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Updateにサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |