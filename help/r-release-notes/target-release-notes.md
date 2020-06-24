---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 最新または今後のDNLAdobe Targetリリースの機能、拡張機能、および修正に関する情報を提供するリリースノートです。
title: Adobe Targetのプレリリースノート
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: a6bcaac474927ddd0a14d4cb274c0460e6002a9b
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 15%

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日： 2020年6月24日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングによっては、これらのページの情報が同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!NOTE]
>
>* **mbox.jsの提供終了**: 2020年8月30日をもって、Adobe Targetはmbox.jsライブラリをサポートしなくなります。 2020年8月30日以降は、mbox.jsからのすべての呼び出しが失敗し、Targetアクティビティが実行されているページに影響が及びます。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前にat.jsライブラリの最新バージョンに移行することをお勧めします。 詳しくは、at.jsの仕組み [および](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)[Adobe Targetスキルビルダーを参照してください。 開発者チャットで、Adobe Targetのmbox.jsをat.jsに移行します](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsと比較して多くの利点を提供します。 多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアとサポートスタッフは、お客様がアドビから期待する新しい機能とオファーをお客様に提供できます。
   >
   >
* **Targetのお知らせ**: Targetスキルビルダーセッション、開発者チャット、ウェビナー、Targetイベントの休憩セッションなど、今後のセッションについて詳しくは、Targetのお知らせページを参照してください。 詳しくは、「 [Targetのお知らせ](/help/r-release-notes/target-announcements.md)」を参照してください。


## Target Standard/Premium 20.6.1（2020年7月、正確な日付は未定）

このリリースで強化された機能は次のとおりです。

### Target用Analytics( [!UICONTROL 自動Target] アクティビティ用A4T)のサポート

[!UICONTROL 自動Target] アクティビティは、 [AnalyticsのTargetをサポートするようになりました](/help/c-integrating-target-with-mac/a4t/a4t.md)。

この統合では、高度な機械学習を使用して、複数のパフォーマンスの高いマーケティング担当者が定義したエクスペリエンスから選択し、コンテンツをパーソナライズし、コンバージョンを促進します。 個々の顧客プロファイルや同様のプロファイルを持つ過去の訪問者の行動に基づいて、各訪問者に最適なエクスペリエンスを提供します。

A/Bテストアクティビティで使用するA4T [を既に実装している場合](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) 、設定はすべて完了です。

### [!UICONTROL 管理] ・セクションのUIの更新

パフォーマンスを向上させ、新機能のリリース時に必要なメンテナンス時間を短縮し、製品全体でのユーザーエクスペリエンスを向上させるために、新しいテクニカルスタックを使用して [!DNL Target] UI全体を徐々に書き換えていきます。 最初に更新されたセクションは [!UICONTROL 「セットアップ] 」セクションで、 [!UICONTROL 「管理」という名前に変更されました]。

この更新の一環として、次のように、 [!UICONTROL 管理] セクションのページを使用して簡単に多くのアクションを実行できます。

* 「 [!UICONTROL 実装] 」タブ(**[!UICONTROL 管理]** / **[!UICONTROL 実装]**)から最新のat.jsファイルをダウンロードします。
* at.js設定をカスタマイズし、変更を簡単に確認できるようにします(**[!UICONTROL 管理]** / **[!UICONTROL 実装]**)。
* デフォルトのレポートおよびタイムゾーン、レポートから除外するIPなど、拡張通貨設定を変更します。 (**[!UICONTROL 管理]** / **[!UICONTROL レポート]**)
* プライバシー上の理由で訪問者のIPアドレスを不明化(**[!UICONTROL 管理]** / **[!UICONTROL 導入]**)
* AdobeAdmin Console(**[!UICONTROL 管理]** / **[!UICONTROL ユーザー]**)で管理する前に、ワークスペースごとの既存のリストとそのロールを表示します。
* 「 [!UICONTROL 管理] 」セクションのすべてのテーブルを検索してフィルターします。

次のような大きな変更点があります。

* **[!UICONTROL Visual Experience Composer]ページ&#x200B;**: この新しいページ(**[!UICONTROL 管理&#x200B;]**/**[!UICONTROL Visual Experience Composer ]**)では、次のことができます。

   * VECの一般設定の指定(デフォルトURLの指定、 [!UICONTROL 拡張Experience Composerの有効化]、混合コンテンツの読み込み、アクティビティフロー図でのエクスペリエンススナップショットの生成)
   * モバイルビューポートの設定
   * CSSセレクターの設定

* **[!UICONTROL レポート]ページ&#x200B;**: この新しいページ(**[!UICONTROL 管理&#x200B;]**/**[!UICONTROL レポート&#x200B;]**)では、アカウント全体に適用する[!DNL Target][!DNL Target]レポートで使用する一般設定を設定できます。

   以下の設定を使用できます。

   * レポートに使用する [!DNL Adobe Experience Cloud] ソリューション
   * レポートに使用するタイムゾーン
   * レポートに使用する通貨
   * レポートから除外するIPアドレス
   * レポートの売上高の予測上昇を表示するかどうか
   * 優先度の細かい設定を有効にするかどうか

* 前の [!UICONTROL ホスト] ・ページは、2つの新しいページに分割されています。

   * [!UICONTROL ホスト]
   * [!UICONTROL 環境]

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html)
