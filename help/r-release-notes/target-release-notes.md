---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 最新または今後のDNLAdobe Targetリリースの機能、拡張機能、および修正に関する情報を提供するリリースノートです。
title: Adobe Targetのプレリリースノート
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 1280d152b749442fe9337dc9eba7321d33f17723
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 16%

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2020 年 7 月 13 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングによっては、これらのページの情報が同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!NOTE]
>
>* **mbox.jsの提供終了**: 2020年8月30日をもって、Adobe Targetはmbox.jsライブラリをサポートしなくなります。 2020年8月30日以降は、mbox.jsからのすべての呼び出しが適切に失敗し、デフォルトコンテンツを提供することで実行されるTargetアクティビティを持つページに影響します。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前にat.jsライブラリの最新バージョンに移行することをお勧めします。 詳しくは、at.jsの仕組み [および](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)[Adobe Targetスキルビルダーを参照してください。 開発者チャットで、Adobe Targetのmbox.jsをat.jsに移行します](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsと比較して多くの利点を提供します。 多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアとサポートスタッフは、お客様がアドビから期待する新しい機能とオファーをお客様に提供できます。
   >
   >
* **Targetのお知らせ**: Targetスキルビルダーセッション、開発者チャット、ウェビナー、Targetイベントの休憩セッションなど、今後のセッションについて詳しくは、Targetのお知らせページを参照してください。 詳しくは、「 [Targetのお知らせ](/help/r-release-notes/target-announcements.md)」を参照してください。


## Target Standard／Premium 20.7.1（2020 年 7 月 21 日）

このリリースで強化された機能は次のとおりです。

### [!UICONTROL 管理] ・セクションのUIの更新

パフォーマンスを向上させ、新機能のリリース時に必要なメンテナンス時間を短縮し、製品全体でのユーザーエクスペリエンスを向上させるために、新しいテクニカルスタックを使用して [!DNL Target] UI全体を徐々に書き換えていきます。 最初に更新されたセクションは [!UICONTROL 「セットアップ] 」セクションで、 [!UICONTROL 「管理」という名前に変更されました]。

この更新の一環として、次のように、 [!UICONTROL 管理] セクションのページを使用して簡単に多くのアクションを実行できます。

* 「 [!UICONTROL 実装] 」タブ(**[!UICONTROL 管理]** / **[!UICONTROL 実装]**)から最新のat.jsファイルをダウンロードします。
* at.js設定をカスタマイズし、変更を簡単に確認できるようにします(**[!UICONTROL 管理]** / **[!UICONTROL 実装]**)。
* デフォルトのレポートおよびタイムゾーン、レポートから除外するIPなど、拡張通貨設定を変更します。 (**[!UICONTROL 管理]** / **[!UICONTROL レポート]**)
* プライバシー上の理由で訪問者のIPアドレスを不明化(**[!UICONTROL 管理]** / **[!UICONTROL 導入]**)
* AdobeAdmin Console(**[!UICONTROL 管理]** / **[!UICONTROL ユーザー]**)で管理する前に、ワークスペースごとの既存のリストとそのロールを表示します。
* 「 [!UICONTROL 管理] 」セクションのすべてのテーブルを検索してフィルターします。

### 機能強化、修正および変更

このリリースには、次の機能強化、修正および変更が含まれています。

* 更新後にサイトの環境設定が保持されない問題を修正しました。 （TGT-37239）
* 「後に [!UICONTROL 挿入] 」 [!UICONTROL /「] 画像」がScalable Vector Graphics(SVG)画像で正しく機能しない問題を修正しました。 （TGT-37242）
* ドラフトアクティビティを削除できなかった、 [!UICONTROL 投稿] ロールを持つユーザーの問題を修正しました。 （TGT-37358）
* 「す [!UICONTROL べてのワークスペース] 」が選択されている場合にアクティビティを編集できない問題を修正しました。 （TGT-37276）
* 既存のプロファイルスクリプト情報カードにオーディエンス使用状況情報が強化されました。 （TGT-37302）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html)
