---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
title: 'Adobe Target リリースノート（現行） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: a24d932f02d49ff11da6299eb46d73f4f385b866
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 21%

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。また、ターゲットAPI、SDK、JavaScriptライブラリ(at.js)およびその他のプラットフォームの変更に関するリリースノートも適宜含まれています。

>[!NOTE]
>
>* **mbox.jsの提供終了**: 2020年8月30日に、アドビターゲットはmbox.jsライブラリをサポートしなくなります。 2020年8月30日以降は、mbox.jsからのすべての呼び出しが失敗し、ターゲットアクティビティが実行されているページに影響が及びます。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前にat.jsライブラリの最新バージョンに移行することをお勧めします。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). 詳しくは、 *Adobeターゲットスキルビルダーを参照してください。 開発者向けチャットで、アドビターゲットのmbox.jsを次のat.js* に移行してください。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsと比較して多くの利点を提供します。 多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアとサポートスタッフは、お客様がアドビから期待する新しい機能とオファーをお客様に提供できます。


括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## Adobeターゲットスキルビルダー： 開発者チャット，アドビターゲットのmbox.jsをat.jsに移行 {#skill-builder}

2020年8月30日にmbox.jsの廃止が予定されているので、アドビターゲット製品マネージャーのDavid Son氏が最近、開発者チャットを開催し、mbox.jsをat.jsに移行する利点について話し合いました。 次の30日間は、ウェビナーの録画を [表示できます](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。

## at.jsターゲット（2020年3月25日）

at.js JavaScriptライブラリの次の新しいターゲットを使用できます。

* at.jsバージョン2.3.0
* at.jsバージョン1.8.1

For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## ターゲット標準/プレミアム20.2.1（2020年3月23日）

>[!IMPORTANT]
>
>上記のmbox.jsの廃止に関する情報を参照してください。

このリリースには、次の機能強化、修正および変更が含まれています。

* カタログ検索を実行する際に、顧客がコレクションを選択できない問題を修正しました。 （TGT-36230）
* APIを介して作成された条件が、ターゲットUIで作成されたアクティビティで参照されていない場合に、UIから誤って削除される問題が修正されました。 （TGT-35917）
* コンテンツセキュリティポリシー(CSP)のセキュリティの強化を実装しました。 （TGT-36190）
* 属性の重み付けの割合バーを左端にスライドすると、「NaN%」と表示される問題を修正しました。 （TGT-36211）
* 様々な言語のUIテキストが正しく表示されるようにローカライゼーションの問題を解決しました。
* 現在のバージョンのAdobe Analytics APIではサポートされていないAdobe Analytics指標を非推奨とすることで、Adobe Analyticsターゲット(A4T)アクティビティの使用可能な指標のリストを標準化しました。 これにより、今後のAdobeターゲットリリースでA4Tのサポートを拡張できます。

   次の変更が行われました。

   * 「ページでの平均滞在時間」は、「サイトでの平均滞在時間」に置き換えられました。 この指標を主要目標指標として使用するアクティビティは、「サイトでの平均滞在時間」を持ちます(注意： アクティビティを次回編集する際に、主要目標指標として選択される値（秒ではなく分単位）です。
   * 「訪問者」は、「個別訪問者」に置き換えられました。 この指標を主要目標指標として使用するアクティビティは、次回アクティビティを編集する際に、「一意の訪問者」が「主要目標指標」として選択されます。

* 次の指標は非推奨となり、新しいA4Tアクティビティを作成する際に主目標指標として選択できなくなりました。

   | 非推奨の指標 | 推奨置換指標 |
   |--- |--- |
   | 日別訪問者、時間別訪問者、月別訪問者、四半期別訪問者、週別訪問者、年別訪問者 | 実訪問者数 |
   | 訪問の深さ（平均） | 該当なし 主な目標指標として提案されていません |
   | ボット | 該当なし 主な目標指標として提案されていません |
   | モバイルのクラッシュ率、モバイルの平均前回セッションの長さ、モバイルのアプリストアの平均ランク、モバイルのアプリのパフォーマンスクラッシュ率、モバイルのアプリストアの平均評価 | 該当なし 主な目標指標として提案されていません |

## Adobe Experience Cloudナビゲーション（2019年2月23日）

* にログインすると、新しいヘッダーナビゲーション [!DNL Adobe Experience Cloud]に移動します。 前のナビゲーションの上部に黒いバーが表示されている場合と非常に似ていますが、次の点が改善されています。

   * IMS(Adobe Suite Cloud Management)組織間 [!DNL Identity Management System] または別のソリューション間の切り替えが容易になりました。
   * ユーザーヘルプの改善： 検索結果には、 [!DNL Target] 製品ドキュメントの結果、コミュニティフォーラムやビデオコンテンツなどが含まれ、より多くのコンテンツにアクセスしやすくなり、最大限の利用を可能に [!DNL Target]します。 また、 [!UICONTROL ヘルプ] メニューにフィードバックのメカニズムが追加され、問題の報告やアイデアの共有が容易になりました。

   * ネットプロモータースコア(NPS)のフィードバック機能が強化され、調査モーダルが作業の流れを妨げないようになりました。
   * ログインフローが改善されました。 以前は、すべての [!DNL Target] 顧客は、ヘッダー内の [!DNL Target] アイコンをクリックした後、ターゲットランディングページにランディングしていました。 その後、このページでは、次のように、 [!DNL Target Standard/Premium]、、 [!DNL Search&Promote][!DNL Recommendations Classic]またはを使用して先に進むことができました。

      ![ランディングページ](/help/r-release-notes/assets/landing.png)

      私たちはこのランディングページをすべてのお客様に対して削除しました。 新しいヘッダーナビゲーションバーの [!UICONTROL アイコンをクリックすると、常に] アクティビティリスト [!DNL Target] ページに直接移動できるようになりました。

      使用する場合 [!DNL Recommendations Classic]は、ソリューションに直接アクセスするか、次に示すように、「 [!UICONTROL Recommendations] 」タブで作成された短縮リンクからアクセスできます。

      ![Recs Classicディープリンク](/help/r-release-notes/assets/recs-classic.png)

      を使用する場合 [!DNL Search&Promote]は、 [Search&amp;Promote URL](https://center.atomz.com/center/?ims=1) (https://center.atomz.com/center/?ims=1)に直接アクセスする必要があります。 の内側から到達するパス [!DNL Search&Promote] は完全に削除 [!DNL Adobe Target] されました。

   * の通知は、現在、ヘッダー [!DNL Target] の「 [!UICONTROL 通知] 」ドロップダウンで使用できません。
   >[!NOTE]
   >
   >新しいナビゲーションバーの展開の一環として、URLの変更にも気付きます。 以前にブックマークを付けたリンクは、引き続き機能しますが、すばやく開くために新しいリンクをブックマークすることをお勧めします。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート —ターゲットサーバー側API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | アドビターゲットのサーバー側APIに関するリリースノートです。 |
| [リリースノート —ターゲットNode.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | アドビターゲットのNode.js SDKに関するリリースノートです。 |
| [リリースノート —ターゲットJava SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | アドビターゲットのJava SDKに関するリリースノートです。 |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adobeターゲットat.js JavaScriptライブラリの各バージョンの変更について詳しく説明します。 |
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
