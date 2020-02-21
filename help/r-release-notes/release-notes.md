---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes
description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
title: 'Adobe Target リリースノート（現行） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 687e5c50ab494e35c746b691f00512702c5dd59b

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。また、Target API、SDK、JavaScriptライブラリ(at.js)およびその他のプラットフォームの変更に関するリリースノートも、該当する場合は含まれます。

>[!NOTE]
>
>* **TLSサポートの変更**:2020年3月1日以降、TargetはTLS 1.1およびTLS 1.0暗号化のサポートを無効にします。 Transport Layer Security（TLS）は、ネットワークを介してデータを安全に交換する必要のある Web ブラウザや他のアプリケーションで現在使用されている、最も広く展開されているセキュリティプロトコルです。この変更は、TLS 1.2以降の一般的に認められるセキュリティコンプライアンス標準を満たすために必要です。 現在使用しているTLSバージョンを確認します。 バージョンが1.2より前の場合は、Targetを引き続き期待どおりに使用するために、2020年3月1日より前に必要な変更を実装します。
   >
   >   
   影響の可能性と実装を更新するために必要な手順について詳しくは、 [TLS(Transport Layer Security)暗号化の変更を参照してください](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。
   >
   >
* **mbox.jsの廃止**:2020年8月30日に、Adobe targetはmbox.jsライブラリをサポートしなくなります。 2020年8月30日以降、mbox.jsからの呼び出しはすべて失敗し、Targetアクティビティを実行しているページに影響します。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前に最新バージョンのat.jsライブラリに移行することをお勧めします。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsに比べて多くの利点を提供します。 特に、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化し、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアおよびサポートスタッフは、お客様がアドビから期待される新しい機能を提供し、サポートを提供できるようになります。
   >
   >
* 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。


## Adobe Experience cloudナビゲーション（2019年2月23日）

* にログインすると、新しいヘ [!DNL Adobe Experience Cloud]ッダーナビゲーションが表示されます。 前のナビゲーションの上部に黒いバーが表示されているのと非常に似ていますが、次の点が改善されました。

   * (IMS)組織間 [!DNL Identity Management System] または別のソリューションへの切り替えが容易になりました。
   * ユーザーヘルプの改善：検索結果には、製品ドキュメントの結 [!DNL Target] 果、コミュニティフォーラムやビデオコンテンツなどが含まれ、より多くのコンテンツに簡単にアクセスして最大限の活用を図ることができま [!DNL Target]す。 また、ヘルプメニューにフィードバックのメカニズムが追加さ [!UICONTROL れ] 、問題の報告やアイデアの共有が簡単になりました。

   * ネットプロモータースコア(NPS)のフィードバック機能が改善され、調査モーダルが作業の流れを妨げないようになりました。
   * ログインフローが改善されました。 以前は、すべての顧客 [!DNL Target] はヘッダーのアイコンをクリックした後、Targetのランディングペ [!DNL Target] ージにランディングしました。 その後、このページでは、次のように、顧客が [!DNL Target Standard/Premium]、、、ま [!DNL Search&Promote]たは [!DNL Recommendations Classic]を進めることができました。

      ![ランディングページ](/help/r-release-notes/assets/landing.png)

      このランディングページをすべてのお客様に対して削除しました。 新しいヘッダーナビゲーションバーのアイコンをクリ [!UICONTROL ックすると] 、常にアクティビティリスト [!DNL Target] ページに直接移動するようになりました。

      使用する場合は、 [!DNL Recommendations Classic]次に示すように、ソリューションに直接移動するか、「 [!UICONTROL Recommendations] 」タブで作成した短いリンクから移動できます。

      ![Recs Classicディープリンク](/help/r-release-notes/assets/recs-classic.png)

      使用する場 [!DNL Search&Promote]合は、 [Search&amp;Promote URL](https://center.atomz.com/center/?ims=1) (https://center.atomz.com/center/?ims=1)に直接移動する必要があります。 の内側から到達す [!DNL Search&Promote] るパスが完全 [!DNL Adobe Target] に削除されました。

   * の通知は、現 [!DNL Target] 在、ヘッダーの「通知  」ドロップダウンでは使用できません。
   >[!NOTE]
   >
   >新しいナビゲーションバーの展開の一部として、URLの変化にも気付きます。 以前にブックマークされたリンクは、引き続き機能しますが、すばやく開くために新しいリンクをブックマークすることをお勧めします。

## Target Standard／Premium 20.2.1（2020 年 2 月 19 日） 

>[!IMPORTANT]
>
>mbox.jsの廃止に関する上記の情報を参照してください。

このリリースには、次の機能強化および修正が含まれています。

* カタログ検索を実行すると、顧客がコレクションを選択できない問題を修正しました。 （TGT-36230）
* APIを使用して作成された条件が、Target UIで作成されたアクティビティで参照されていない場合、UIから誤って削除される問題が修正されました。 （TGT-35917）
* コンテンツセキュリティポリシー(CSP)のセキュリティの強化を実装しました。 （TGT-36190）
* 属性の重み付けの割合バーを左端にスライドすると、「NaN%」が表示される問題を修正しました。 （TGT-36211）
* 様々な言語のUIテキストが正しく表示されるように、ローカリゼーションの問題を解決しました。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート — Targetサーバー側API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Adobe targetのサーバー側APIに関するリリースノートです。 |
| [リリースノート — Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Adobe targetのNode.js SDKに関するリリースノートです。 |
| [リリースノート — Target Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Adobe targetのJava SDKに関するリリースノートです。 |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adobe Target at.js javaScriptライブラリの各バージョンの変更に関する詳細。 |
| [mbox.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | このページには、mbox.js の各バージョンに対する変更が表示されます。<br>mbox.jsライブラリは開発されなくなります。 すべてのお客様が mbox.js から at.js に移行する必要があります。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート {#section_1BC5F5208DA548E9B4344A0836E4B943}

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報が表示されます。<br>詳しくは、「[ドキュメントの変更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](../r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、 [Experience cloudリリースノートを参照してください](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update リスト | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
