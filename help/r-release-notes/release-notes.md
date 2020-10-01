---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
title: 'Adobe Target リリースノート（現行） '
feature: release notes
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 1397891d4451d9e66a25e018e6bd7078e70cfd3f
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 23%

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。また、ターゲットAPI、SDK、JavaScriptライブラリ(at.js)およびその他のプラットフォームの変更に関するリリースノートも適宜含まれています。

>[!IMPORTANT]
>
>* **AdobeがパーソナライゼーションエンジンのGartner Magic Quadrantで再びリーダーに** Adobeは、2020年のパーソナライゼーション・エンジンに関する3年目の年次Gartner Magic Quadrantで再びリーダーに選ばれました。 パーソナライゼーションエンジンのGartner Magic Quadrantは、2つのカテゴリに分かれる15の基準に基づいてベンダーを評価しました。ビジョンと実行能力の完全性 [Adobeブログ](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.jsの削除**:2021年1月18日に、Adobe Targetはmbox.jsライブラリをサポートしなくなります。 2021年1月18日以降、mbox.jsからのすべての呼び出しが正常に失敗し、デフォルトコンテンツを提供することで実行されているターゲットアクティビティを持つページに影響します。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前にat.jsライブラリの最新バージョンに移行することをお勧めします。 詳しくは、at.jsの [仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) および [Adobe Targetスキルビルダーを参照してください。開発者チャットでは、Adobe Targetのmbox.jsをat.jsに移行します](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsと比較して多くの利点を提供します。 多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアとサポートスタッフは、お客様がAdobeから期待する新しい機能とオファーをお客様に提供できます。
   >
   >
* **ターゲットのお知らせ**:ターゲットスキルビルダーセッション、開発者チャット、ウェビナー、ターゲットイベントの休憩セッションなど、今後のセッションについて詳しくは、ターゲットのお知らせページを参照してください。 詳しくは、「 [ターゲットのお知らせ](/help/r-release-notes/target-announcements.md)」を参照してください。


括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## Target Standard/Premium 20.9.1（2020 年 9 月 30 日）

このメンテナンスリリースには、次の機能強化、修正および変更が含まれています。

* キーボードのみのユーザーのナビゲーションと機能が改善されました。 (TGT-34487、TGT-34516、TGT-34517、TGT-34514)
* 支援テクノロジーを使用するユーザーを支援するために、UIにラベルを追加しました。 (TGT-34500、TGT-34501、TGT-34502、TGT-24504)
* UIの画像とテキストのテキストとカラーコントラストが改善されました。 （TGT-34513）

## Target Standard/Premium 20.8.3（2020 年 9 月 15 日）

| 機能 | 詳細 |
| --- | --- |
| ![自動ターゲットアクティビティ用のターゲット用プレミアムバッジ](/help/assets/premium.png) (A4T)のサポート | [!UICONTROL 自動ターゲット] アクティビティで、 [Analyticsのターゲットがサポートされるようになりました](/help/c-integrating-target-with-mac/a4t/a4t.md)。<br>この統合により、 [!UICONTROL 自動ターゲット] ・アンサンブル機械学習アルゴリズムを使用して、プロファイル、行動およびコンテキストに基づいて各訪問者に最適なエクスペリエンスを選択できます。<br>A/B Test &amp; Experience Targetingアクティビティで使用するA4T [を既に](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) 実装している場合は、設定がすべて完了です。<br>詳しくは、 [アクティビティ作成の自動配分と自動ターゲットアクティビティの](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) Analytics forターゲット(A4T)のサポートを参照してください **。 |

## Target Standard/Premium 20.8.2（2020 年 9 月 10 日）

| 機能 | 詳細 |
| --- | --- |
| ![条件のシーケンス内のPremiumバッジ](/help/assets/premium.png) Control Recommendationsスロット | 条件のシーケンスを使用すると、各レコメンデーション条件で使用されるスロット数を制御できるようになりました。異なるタイプの品目や異なるアルゴリズムロジックを組み合わせて一致させることができます。<br>詳しくは、条件のシーケンス [の作成](/help/c-recommendations/c-algorithms/create-criteria-sequence.md#sequence) （英語）を参照してください。 |

## Target Standard/Premium 20.8.1（2020 年 9 月 2 日）

このリリースには、次の機能強化、修正および変更が含まれています。

* 組織を切り替えた後に新しい [!UICONTROL 管理] ページを読み込むと、エラーが表示される問題を修正しました。 （TGT-37730）
* 表示で、 [!UICONTROL 管理/導入] ページに正しくないクライアントコードが表示される問題を修正しました。 （TGT-37849）
* VECの読み込みが成功した後、 [!UICONTROL Visual Experience Composer] (VEC)の編集機能が使用できない場合がある問題を修正しました。 （TGT-37162）
* VEC Helper拡張機能がインストールされている場合でも、VECおよび拡張Experience Composer(EEC)でページが読み込めない問題を修正しました。 これは、Google Chrome 80以降の変更が原因でした。 更新されたVEC Helper [拡張機能をダウンロードします](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)。 （TGT-37893）
* 組織を切り替えた後に、 [!UICONTROL 管理/実装] ページからat.jsをダウンロードできない場合がある問題を修正しました。 （TGT-37668）
* ユーザーがダウンロードボタンを複数回クリックした場合に複数のリクエストが送信されるのを防ぐため、at.jsのダウンロードボタンが読み込み中に無効にな [!DNL Target] りました。 （TGT-37633）
* エクスペリエンスのターゲット設定  (XT)アクティビティで、エクスペリエンスに長期間「結果を取得」と表示される問題を修正しました。 （TGT-37684）
* キーボードのみのユーザーのナビゲーションと機能が改善されました。 （TGT-34479 および TGT-34473）
* 支援テクノロジーを使用するユーザーを支援するために、UIにラベルを追加しました。 （TGT-34480）
* アクティビティで現在使用されているモバイルビューポートを削除する際のエラーメッセージを改善。 次のようなエラーメッセージが表示されます。「このビューポートは現在、1つまたは複数のアクティビティに関連付けられています。 ビューポートを削除する前に、これらのアクティビティからビューポートを削除する必要があります。」 （TGT-37030）
* VECでのサポートが追加され、ページ内の複数の要素に一致するcssセレクターのクリック追跡が可能になりました。 （TGT-37323）
* 特定のユーザーが [!UICONTROL アクティビティ] リストを表示できない問題を修正しました。 次のエラーメッセージが表示されました。&quot;URLの提案を取得できません。&quot; AdobeバックエンドシステムのFirstName (FirstName/r/n)でキャリッジリターンを使用しているユーザーに対してエラーが発生しました。 （TGT-37330）
* ワークスペース名(Enterprise用の [!UICONTROL Adobe Admin Consoleで指定)にアポストロフィが含まれる場合に、] アクティビティ ページが表示されない問題を修正しました。 （TGT-37709）
* 最適化指標とコンバージョン指標を選択する際の [!UICONTROL 自動配分] アクティビティで、レポートスイートが既に指定されている場合でも、エラーメッセージが誤ってレポートスイートを選択するようユーザーに通知する問題を修正しました。 （TGT-37689）
* ター [!UICONTROL ゲット設定ページに移動してから戻った後で、] 目標と設定  ページの指標が空白になる場合がある問題を修正しました。 （TGT-37691）
* 条件の最終変更値が正しくない問題を修正しました [!DNL Recommendations] 。 （TGT-37666）
* mbox名ではなくmboxドロップダウンリストーにmbox IDが表示される問題を修正しました。 （TGT-37739）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート —ターゲットサーバー側API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Adobe Targetのサーバー側APIに関するリリースノートです。 |
| [リリースノート —ターゲットNode.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Adobe TargetのNode.js SDKに関するリリースノートです。 |
| [リリースノート —ターゲットJava SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Adobe TargetのJava SDKに関するリリースノートです。 |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adobe Targetのat.js JavaScriptライブラリの各バージョンの変更について詳しく説明します。 |
| [mbox.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | このページには、mbox.js の各バージョンに対する変更が表示されます。<br>mbox.jsライブラリは開発されなくなります。 すべてのお客様が mbox.js から at.js に移行する必要があります。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート {#section_1BC5F5208DA548E9B4344A0836E4B943}

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報が表示されます。<br>詳しくは、「[ドキュメントの変更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](../r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、「 [Experience Cloudリリースノート](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)」を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update リスト | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
