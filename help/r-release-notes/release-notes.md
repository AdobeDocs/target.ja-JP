---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
title: 'Adobe Target リリースノート（現行） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 1befd131034805ba81e4d68e7e976fd290041d52

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

## ターゲットat.js（2020年3月26日）

at.js JavaScriptライブラリのターゲットの次の新しいバージョンを使用できます。

* at.jsバージョン2.3.0
* at.jsバージョン1.8.1

For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## ターゲット標準/プレミアム20.2.1（2020年3月24日）

>[!IMPORTANT]
>
>mbox.jsの廃止に関する上記の情報を参照してください。

このリリースには、次の機能強化、修正および変更が含まれています。

* カタログ検索を実行すると、顧客がコレクションを選択できない問題を修正しました。 （TGT-36230）
* APIで作成され、ターゲットUIで作成されたアクティビティが参照しない条件がUIから誤って削除される問題を修正しました。 （TGT-35917）
* コンテンツセキュリティポリシー(CSP)のセキュリティの強化を実装しました。 （TGT-36190）
* 属性の重み付けの割合のバーを左端にスライドすると、「NaN%」が表示される問題を修正しました。 （TGT-36211）
* ローカライゼーションの問題を解決し、様々な言語のUIテキストが正しく表示されるようにしました。
* 現在のバージョンのAdobe Analytics APIではサポートされていないAdobe Analytics指標を廃止することで、Adobe Analyticsのターゲット(A4T)アクティビティで使用できる指標のリストを標準化しました。 これにより、今後のアドビのターゲットリリースでA4Tのサポートを拡張できます。

   次の変更が行われました。

   * 「ページでの平均滞在時間」は、「サイトでの平均滞在時間」に置き換えられました。 この指標をアクティビティの主要目標指標として使用する場合、「サイトでの平均滞在時間」が表示されます(注意：測定単位は秒ではなく分)が選択され、次回のアクティビティ編集時にプライマリ目標指標として選択されます。
   * 「訪問者」は「個別訪問者」に置き換えられました。 この指標を主目標指標として使用するアクティビティは、次にアクティビティを編集する際に、「個別訪問者」が「主目標指標」として選択されます。

* 次の指標は非推奨となり、新しいA4T指標を作成する際にプライマリ目標指標として選択できなくなりました。アクティビティ

   | 非推奨の指標 | 推奨置換指標 |
   |--- |--- |
   | 日別訪問者、時間別訪問者、月別訪問者、四半期別訪問者、週別訪問者、年別訪問者 | 実訪問者数 |
   | 訪問の深さ（平均） | 該当なし主な目標指標として提案されていない |
   | ボット | 該当なし主な目標指標として提案されていない |
   | モバイルのクラッシュ率、モバイルの平均前回のセッションの長さ、モバイルのアプリストアの平均ランク、モバイルのアプリのパフォーマンスクラッシュ率、モバイルのアプリストアの平均評価 | 該当なし主な目標指標として提案されていない |

## Adobe Experience Cloudのナビゲーション（2019年2月23日）

* にログインすると、新し [!DNL Adobe Experience Cloud]いヘッダーナビゲーションが表示されます。 前のナビゲーションの上部に黒いバーが表示されているのと非常に似ていますが、次の点が改善されました。

   * (IMS)組織間の [!DNL Identity Management System] 切り替えや、別のソリューションへの切り替えが容易になりました。
   * ユーザーヘルプの改善：検索結果には、製品ドキュメントの結 [!DNL Target] 果、コミュニティフォーラムやビデオコンテンツなどが含まれ、より多くのコンテンツに簡単にアクセスして最大限の活用を図ることができま [!DNL Target]す。 また、ヘルプメニューにフィードバックのメカニズムが追加さ [!UICONTROL れ] 、問題の報告やアイデアの共有が簡単になりました。

   * ネットプロモータースコア(NPS)のフィードバック機能を改善し、調査モーダルが作業の流れを妨げないようにしました。
   * ログインのフローが改善されました。 以前は、すべての顧客 [!DNL Target] がヘッダーのアイコンをクリックした後、ターゲットランディングページにランデ [!DNL Target] ィングしていました。 その後、このページでは、次に示すように、顧客が次 [!DNL Target Standard/Premium]の手順に進む [!DNL Search&Promote]こと [!DNL Recommendations Classic]ができるようになりました。

      ![ランディングページ](/help/r-release-notes/assets/landing.png)

      私たちはこのランディングページを全てのお客様に排除した。 新しいヘッダーナビゲーションバーのアイコンをクリッ [!UICONTROL クすると] 、常にアクティビティリストページ [!DNL Target] に直接移動するようになりました。

      使用する場合 [!DNL Recommendations Classic]は、次に示すように、ソリューションに直接移動するか、 [!UICONTROL Recommendations] タブで作成した短いリンクから移動できます。

      ![Recs Classicディープリンク](/help/r-release-notes/assets/recs-classic.png)

      を使用する場 [!DNL Search&Promote]合は、 [Search&amp;Promote URL](https://center.atomz.com/center/?ims=1) (https://center.atomz.com/center/?ims=1)に直接移動する必要があります。 の内側から到達す [!DNL Search&Promote] るパスが完 [!DNL Adobe Target] 全に削除されました。

   * の通知は、現 [!DNL Target] 在、ヘッダーの「通知」ド [!UICONTROL ロップダウン] では使用できません。
   >[!NOTE]
   >
   >新しいナビゲーションバーの展開の一部として、URLの変更もいくつか見てとれます。 以前にブックマークを付けたリンクは、引き続き機能しますが、すばやく開くために新しいリンクをブックマークすることをお勧めします。

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
