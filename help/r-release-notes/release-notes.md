---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
title: 'Adobe Target リリースノート（現行） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: d45a38376ebe98d212fba3097159a7b89b792c53

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。また、ターゲットAPI、SDK、JavaScriptライブラリ(at.js)およびその他のプラットフォームの変更に関するリリースノートも、該当する場合は含まれます。

>[!NOTE]
>
>* **mbox.jsの廃止**:2020年8月31日に、アドビターゲットはmbox.jsライブラリをサポートしなくなります。 2020年8月30日以降、mbox.jsからの呼び出しはすべて失敗し、ターゲットアクティビティが実行されているページに影響します。 サイトで発生する可能性のある問題を回避するため、すべてのお客様は、この日より前に最新バージョンのat.jsライブラリに移行することをお勧めします。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). 詳しくは、 *Adobeターゲットスキルビルダーを参照してください。開発者チャットでは、この件に関する今後の開発者チャットへの登録について、アドビターゲットのmbox* .jsを以下のat.jsに移行してください。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリの機能の更新は提供されていません。 新しいat.jsは、mbox.jsよりも多くの利点を提供します。 特に、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化し、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアおよびサポートスタッフは、アドビが期待する新しい機能とオファーをお客様に提供できます。


括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## Adobeターゲットスキルビルダー：開発者チャット， Adobeターゲットのmbox.jsのat.jsへの移行 {#skill-builder}

アドビターゲットプロダクトマネージャーのDavid Son氏が、mbox.jsをat.jsに移行する利点を説明します。 最新のat.jsの更新を確認し、その機能強化と技術展開のより大きなトレンドとの整合性を確認します。また、mbox.jsからat.jsに移行する際にターゲットから最大限の価値を引き出すための実用的なヒントも紹介します。 アドビのターゲット開発者は、これを見逃したくはありません。

5月5日8:00 ～ 9:00 AM(PDT)

[今すぐ登録！](https://atskillbuilder-devchat.experienceleague.adobeevents.com/)

## Target Standard／Premium 20.4.1（2020 年 4 月 28 日）

このリリースには、次の機能強化、修正および変更が含まれています。

* デバイスのデバイスとブラウザーのタイプが正しく認識されない問題を修正しました。オーディエンス （TGT-36266）
* 幅が963ピクセル未満の画面でレポートデータを表示できない問題を修正しました。 （TGT-36549）
* 自動パーソナライゼーションレポートが正しく表示されない問題を修正しました。 （TGT-36619）
* Visual Experience Composer(VEC)の一部のオプションが正しく表示されない問題を修正しました。 （TGT-36571）
* ターゲットUIで、1つのエクスペリエンスでユーザーがコンテンツを置き換えた後に、他のRecommendationsオファープレビューが編集済みのコンテンツを表示する問題を修正しました。 （TGT-36053 および TGT-36894）
* 一部のユーザーがRecommendationsカタログから品目を削除できない問題を修正しました。 （TGT-36455）
* 複数ページのレコメンデーションで、レコメンデーション条件を保存できない問題を修正しました。アクティビティ （TGT-36249）
* 2回連続して条件を編集すると、行動データソースのラジオボタンが消える問題を修正しました。 （TGT-36796）
* Recommendationsのアルゴリズムで、拡張期間に「結果を取得中」と表示される表示の問題を修正しました。 （TGT-36550 および TGT-36551）
* 様々な言語にローカライズされた多くのUI文字列を更新しました。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート —ターゲットサーバー側API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | アドビのサーバー側APIに関するターゲットのリリースノートです。 |
| [リリースノート —ターゲットNode.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | AdobeターゲットのNode.js SDKに関するリリースノートです。 |
| [リリースノート —ターゲットJava SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | アドビのJava SDKに関するターゲットのリリースノートです。 |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.js JavaScriptライブラリの各バージョンのAdobeターゲットの変更について詳しく説明します。 |
| [mbox.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | このページには、mbox.js の各バージョンに対する変更が表示されます。<br>mbox.jsライブラリは開発されなくなります。 すべてのお客様が mbox.js から at.js に移行する必要があります。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート {#section_1BC5F5208DA548E9B4344A0836E4B943}

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報が表示されます。<br>詳しくは、「[ドキュメントの変更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](../r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、 [Experience Cloudリリースノートを参照してください](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update リスト | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
