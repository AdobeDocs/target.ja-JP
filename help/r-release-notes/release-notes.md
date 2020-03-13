---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
title: 'Adobe Target リリースノート（現行） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 51abcafed1641d073b38800d0fea756df92b3685

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。また、Target API、SDK、JavaScriptライブラリ(at.js)およびその他のプラットフォームの変更に関するリリースノートも、該当する場合は含まれています。

>[!NOTE]
>
>* **TLSサポートの変更**:2020年3月1日以降、TargetはTLS 1.1およびTLS 1.0暗号化のサポートを無効にします。 Transport Layer Security（TLS）は、ネットワークを介してデータを安全に交換する必要のある Web ブラウザや他のアプリケーションで現在使用されている、最も広く展開されているセキュリティプロトコルです。この変更は、TLS 1.2以降の一般的に認められるセキュリティコンプライアンス標準を満たすために必要です。 現在使用しているTLSのバージョンを確認します。 バージョンが1.2より前の場合は、Targetを引き続き期待どおりに使用するために、2020年3月1日より前に必要な変更を実装します。
   >
   >   
   影響の可能性と、実装を更新するために実行する必要がある可能性のある手順について詳しくは、 [TLS(Transport Layer Security)暗号化の変更を参照してください](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。
   >
   >
* **mbox.jsの廃止**:2020年8月31日に、Adobe Targetはmbox.jsライブラリをサポートしなくなります。 2020年8月30日以降、mbox.jsからのすべての呼び出しが失敗し、Targetアクティビティが実行されているページに影響します。 サイトで発生する可能性のある問題を回避するため、すべてのお客様は、この日より前に最新バージョンのat.jsライブラリに移行することをお勧めします。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリの機能の更新は提供されていません。 新しいat.jsは、mbox.jsよりも多くの利点を提供します。 特に、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化し、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアおよびサポートスタッフは、お客様に新しい機能を提供し、アドビが期待するサポートを提供できるようになります。
   >
   >
* 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。


## Summit Live:デジタル体験会議 {#summit}

Adobe Summitは仮想イベントになりました。 アドビは、2020年3月31日からデジタルのライブ体験を通じて、すべての停止点を取り除きます。 このライブエクスペリエンスには、主要段階の基調講演、最新のトレンドと進歩を取り上げたミニキーノート、業界リーダーの成功に対する洞察、および分類セッションが含まれます。

* **キーノートをライブで見る**:業界をどこでも快適な環境から変える傾向や新製品についてお聞かせください。
* **オンデマンドで100以上の分類を調査：** アドビ、お客様、パートナーが提供する100を超えるオンデマンドの内訳セッションに、無料でアクセスできます。
* **先が見えない**:Chelsea特別ゲスト・ハンドラーに参加し、当社のラボの最新の実験技術をご覧ください — Adobe Sneeksの

デジタルイベント全体への無料アクセスを登録するには、Digital Experience Conference [にアクセスします。サミット](https://www.adobe.com/summit.html) ページ

## Target Standard/Premium 20.2.1（2020年3月18日）

>[!IMPORTANT]
>
>mbox.jsの廃止に関する上記の情報を参照してください。

このリリースには、次の機能強化、修正および変更が含まれています。

* カタログ検索を実行すると、顧客がコレクションを選択できない問題を修正しました。 （TGT-36230）
* APIを介して作成され、Target UIで作成されたアクティビティで参照されていない条件がUIから誤って削除される問題を修正しました。 （TGT-35917）
* コンテンツセキュリティポリシー(CSP)のセキュリティの強化を実装しました。 （TGT-36190）
* 属性の重み付けの割合のバーを左端にスライドすると、「NaN%」が表示される問題を修正しました。 （TGT-36211）
* 様々な言語のUIテキストが正しく表示されるように、ローカリゼーションの問題を解決しました。
* 次のAdobe Analytics指標は、2020年3月のTargetリリース以降、Analytics for Target(A4T)でサポートされなくなりました。
   * 平均証拠深度
   * ボット
* 次の指標はサポートされなくなり、ユーザーが指標を含むアクティビティを初めて変更したときに、新しいバージョンの指標に自動的に変換されます。

   | 非推奨の指標 | 新しい指標 |
   |--- |--- |
   | `averagetimespentonpage` | `averagetimespentonsite` (注意：秒ではなく分単位で測定される |
   | `instances` | `occurrences` |
   | `singleaccess` | `singlepagevisits` |
   | `uniquevisitors` | `visitors` |
   | `visitorsdaily`, `visitorshourly`, `visitorsmonthly`, `visitorsquarterly`, `visitorsweekly`, `visitorsyearly` | `visitors` |

## Adobe Experience Cloudのナビゲーション（2019年2月23日）

* にログインすると、新し [!DNL Adobe Experience Cloud]いヘッダーナビゲーションが表示されます。 前のナビゲーションの上部に黒いバーが表示されているのと非常に似ていますが、次の点が改善されました。

   * (IMS)組織間の [!DNL Identity Management System] 切り替えや、別のソリューションへの切り替えが容易になりました。
   * ユーザーヘルプの改善：検索結果には、製品ドキュメントの結 [!DNL Target] 果、コミュニティフォーラムやビデオコンテンツなどが含まれ、より多くのコンテンツに簡単にアクセスして最大限の活用を図ることができま [!DNL Target]す。 また、ヘルプメニューにフィードバックのメカニズムが追加さ [!UICONTROL れ] 、問題の報告やアイデアの共有が簡単になりました。

   * ネットプロモータースコア(NPS)のフィードバック機能を改善し、調査モーダルが作業の流れを妨げないようにしました。
   * ログインのフローが改善されました。 以前は、すべての顧客 [!DNL Target] がヘッダーのアイコンをクリックした後、Targetのランディングペ [!DNL Target] ージにランディングしました。 その後、このページでは、次に示すように、顧客が次 [!DNL Target Standard/Premium]の手順に進む [!DNL Search&Promote]こと [!DNL Recommendations Classic]ができるようになりました。

      ![ランディングページ](/help/r-release-notes/assets/landing.png)

      すべてのお客様のために、このランディングページを削除しました。 新しいヘッダーナビゲーションバーのアイコンをク [!UICONTROL リックすると] 、常にアクティビティリストペ [!DNL Target] ージに直接移動するようになりました。

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
| [リリースノート — Targetサーバー側API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Adobe Targetのサーバー側APIに関するリリースノートです。 |
| [リリースノート — Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Adobe TargetのNode.js SDKに関するリリースノートです。 |
| [リリースノート — Target Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Adobe TargetのJava SDKに関するリリースノートです。 |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adobe Target at.js JavaScriptライブラリの各バージョンの変更について詳しく説明します。 |
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
| Adobe Priority Product Update リスト | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
