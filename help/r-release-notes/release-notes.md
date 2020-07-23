---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
title: 'Adobe Target リリースノート（現行） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: fe68bfb124a5c8c58fbc6822d31b49257a0cfc0b
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 31%

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。また、TargetAPI、SDK、JavaScriptライブラリ(at.js)およびその他のプラットフォームの変更に関するリリースノートも適宜含まれています。

>[!IMPORTANT]
>
>* **アドビは、パーソナライゼーションエンジンのGartner Magic Quadrantでリーダーに再び選出**: アドビは、2020年パーソナライゼーションエンジンの3年目の年次Gartner Magic Quadrantで再びリーダーに選ばれました。 パーソナライゼーションエンジンのGartner Magic Quadrantは、2つのカテゴリに分かれる15の基準に基づいてベンダーを評価しました。 ビジョンと実行能力の完全性 [Adobe Blogで確認してください](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.jsの提供終了**: 2020年8月30日をもって、Adobe Targetはmbox.jsライブラリをサポートしなくなります。 2020年8月30日以降は、mbox.jsからのすべての呼び出しが適切に失敗し、デフォルトコンテンツを提供することで実行されるTargetアクティビティを持つページに影響します。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前にat.jsライブラリの最新バージョンに移行することをお勧めします。 詳しくは、at.jsの仕組み [および](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)[Adobe Targetスキルビルダーを参照してください。 開発者チャットで、Adobe Targetのmbox.jsをat.jsに移行します](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsと比較して多くの利点を提供します。 多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアとサポートスタッフは、お客様がアドビから期待する新しい機能とオファーをお客様に提供できます。
   >
   >
* **Targetのお知らせ**: Targetスキルビルダーセッション、開発者チャット、ウェビナー、Targetイベントの休憩セッションなど、今後のセッションについて詳しくは、Targetのお知らせページを参照してください。 詳しくは、「 [Targetのお知らせ](/help/r-release-notes/target-announcements.md)」を参照してください。


括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## Target Standard／Premium 20.7.1（2020 年 7 月 28 日）

このリリースには、次のような変更が含まれています。

### [!UICONTROL 管理] ・セクションのUIの更新

パフォーマンスを向上させ、新機能のリリース時に必要なメンテナンス時間を短縮し、製品全体でのユーザーエクスペリエンスを向上させるために、新しいテクニカルスタックを使用して [!DNL Target] UI全体を徐々に書き換えていきます。 最初に更新されたセクションは [!UICONTROL 「セットアップ] 」セクションで、 [!UICONTROL 「管理」という名前に変更されました]。

この更新の一環として、次のように、 [!UICONTROL 管理] セクションのページを使用して簡単に多くのアクションを実行できます。

* 「 [!UICONTROL 実装] 」タブ(**[!UICONTROL 管理]** / **[!UICONTROL 実装]**)から最新のat.jsファイルをダウンロードします。
* at.js設定をカスタマイズし、変更を簡単に確認できるようにします(**[!UICONTROL 管理]** / **[!UICONTROL 実装]**)。
* デフォルトのレポートおよびタイムゾーン、レポートから除外するIPなど、拡張通貨設定を変更します。 (**[!UICONTROL 管理]** / **[!UICONTROL レポート]**)
* プライバシー上の理由で訪問者のIPアドレスを不明化(**[!UICONTROL 管理]** / **[!UICONTROL 導入]**)
* AdobeAdmin Console(**[!UICONTROL 管理]** / **[!UICONTROL ユーザー]**)で管理する前に、ワークスペースごとの既存のリストとそのロールを表示します。
* 「 [!UICONTROL 管理] 」セクションのすべてのテーブルを検索してフィルターします。

詳しくは、「 [管理Targetの概要](/help/administrating-target/administrating-target.md)」を参照してください。

### 機能強化、修正および変更

このリリースには、次の機能強化、修正および変更が含まれています。

* 更新後にサイトの環境設定が保持されない問題を修正しました。 （TGT-37239）
* 「後に [!UICONTROL 挿入] 」 [!UICONTROL /「] 画像」がScalable Vector Graphics(SVG)画像で正しく機能しない問題を修正しました。 （TGT-37242）
* ドラフトアクティビティを削除できなかった、 [!UICONTROL 投稿] ロールを持つユーザーの問題を修正しました。 （TGT-37358）
* 「す [!UICONTROL べてのワークスペース] 」が選択されている場合にアクティビティを編集できない問題を修正しました。 （TGT-37276）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート —Targetサーバー側API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Adobe Targetのサーバー側APIに関するリリースノートです。 |
| [リリースノート —TargetNode.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Adobe TargetのNode.js SDKに関するリリースノートです。 |
| [リリースノート —TargetJava SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Adobe TargetのJava SDKに関するリリースノートです。 |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.js JavaScriptライブラリの各Adobe Targetの変更点について詳しく説明します。 |
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
