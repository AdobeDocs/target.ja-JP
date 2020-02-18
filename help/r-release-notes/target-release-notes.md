---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes
description: DNL Adobe targetの最新リリースまたは今後のリリースに関する機能、拡張機能および修正に関する情報を提供するリリースノートです。
title: Adobe targetプレリリースノート
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: f710882392f54c13a2161a97b7530796f9a99283

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2020 年 2 月 18 日**

>[!NOTE]
>
>* この記事にはプレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。
   >
   >
* 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。
   >
   >
* **TLSサポートの変更**:2020年3月1日以降、TargetはTLS 1.1およびTLS 1.0暗号化のサポートを無効にします。 Transport Layer Security（TLS）は、ネットワークを介してデータを安全に交換する必要のある Web ブラウザや他のアプリケーションで現在使用されている、最も広く展開されているセキュリティプロトコルです。この変更は、TLS 1.2以降の一般的に認められるセキュリティコンプライアンス標準を満たすために必要です。 現在使用しているTLSバージョンを確認します。 バージョンが1.2より前の場合は、Targetを引き続き期待どおりに使用するために、2020年3月1日より前に必要な変更を実装します。
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

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
