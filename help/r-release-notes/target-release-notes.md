---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes
description: DNL Adobe Targetの最新リリースまたは今後のリリースに関する機能、拡張機能および修正に関する情報を提供するリリースノートです。
title: Adobe Targetプレリリースノート
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 336726bef7a8a3a8cf4abed37ccdeb63b8efa369

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2020 年 2 月 18 日**

>[!NOTE]
>
>* この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。
   >
   >
* 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。
   >
   >
* **TLSサポートの変更**:2020年3月1日以降、TargetはTLS 1.1およびTLS 1.0暗号化のサポートを無効にします。 Transport Layer Security（TLS）は、ネットワークを介してデータを安全に交換する必要のある Web ブラウザや他のアプリケーションで現在使用されている、最も広く展開されているセキュリティプロトコルです。この変更は、TLS 1.2以降の一般的に認められるセキュリティコンプライアンス標準を満たすために必要です。 現在使用しているTLSのバージョンを確認します。 バージョンが1.2より前の場合は、Targetを引き続き期待どおりに使用するために、2020年3月1日より前に必要な変更を実装します。
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


## Target Standard/Premium 20.2.1（2020年3月4日）

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

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
