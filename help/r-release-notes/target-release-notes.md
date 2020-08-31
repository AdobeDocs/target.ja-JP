---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: DNLAdobe Targetの最新リリースまたは今後のリリースに関する機能、拡張機能、および修正に関する情報を提供するリリースノートです。
title: Adobe Targetプレリリースノート
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 405715f1ee1afd1d298dc7f1ef0cd3599620cbca
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 11%

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2020 年 8 月 31 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングによっては、これらのページの情報が同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>* **AdobeがパーソナライゼーションエンジンのGartner Magic Quadrantで再びリーダーに** Adobeは、2020年のパーソナライゼーション・エンジンに関する3年目の年次Gartner Magic Quadrantで再びリーダーに選ばれました。 パーソナライゼーションエンジンのGartner Magic Quadrantは、2つのカテゴリに分かれる15の基準に基づいてベンダーを評価しました。ビジョンと実行能力の完全性 [Adobeブログ](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.jsの提供終了**:2021年1月18日に、Adobe Targetはmbox.jsライブラリをサポートしなくなります。 2021年1月18日以降、mbox.jsからのすべての呼び出しが正常に失敗し、デフォルトコンテンツを提供することで実行されているターゲットアクティビティを持つページに影響します。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前にat.jsライブラリの最新バージョンに移行することをお勧めします。 詳しくは、at.jsの [仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) および [Adobe Targetスキルビルダーを参照してください。開発者チャットでは、Adobe Targetのmbox.jsをat.jsに移行します](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsと比較して多くの利点を提供します。 多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアとサポートスタッフは、お客様がAdobeから期待する新しい機能とオファーをお客様に提供できます。
   >
   >
* **ターゲットのお知らせ**:ターゲットスキルビルダーセッション、開発者チャット、ウェビナー、ターゲットイベントの休憩セッションなど、今後のセッションについて詳しくは、ターゲットのお知らせページを参照してください。 詳しくは、「 [ターゲットのお知らせ](/help/r-release-notes/target-announcements.md)」を参照してください。


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
* 条件の最終変更日の値が正しくない問題を修正しました [!DNL Recommendations] 。 （TGT-37666）
* mbox名ではなくmboxドロップダウンリストーにmbox IDが表示される問題を修正しました。 （TGT-37739）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html)
