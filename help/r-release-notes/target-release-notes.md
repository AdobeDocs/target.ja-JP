---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 最新または今後のDNLアドビターゲットリリースの機能、拡張機能および修正に関する情報を提供するリリースノートです。
title: アドビターゲットプレリリースノート
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: a24d932f02d49ff11da6299eb46d73f4f385b866
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 14%

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2020 年 5 月 4 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングによっては、これらのページの情報が同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!NOTE]
>
>* **mbox.jsの提供終了**: 2020年8月30日に、アドビターゲットはmbox.jsライブラリをサポートしなくなります。 2020年8月30日以降は、mbox.jsからのすべての呼び出しが失敗し、ターゲットアクティビティが実行されているページに影響が及びます。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前にat.jsライブラリの最新バージョンに移行することをお勧めします。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). 詳しくは、 *Adobeターゲットスキルビルダーを参照してください。 開発者向けチャットで、アドビターゲットのmbox.jsを次のat.js* に移行してください。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsと比較して多くの利点を提供します。 多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアとサポートスタッフは、お客様がアドビから期待する新しい機能とオファーをお客様に提供できます。


## Adobeターゲットスキルビルダー： 開発者チャット，アドビターゲットのmbox.jsをat.jsに移行 {#skill-builder}

2020年8月30日にmbox.jsの廃止が予定されているので、アドビターゲット製品マネージャーのDavid Son氏が最近、開発者チャットを開催し、mbox.jsをat.jsに移行する利点について話し合いました。 次の30日間は、ウェビナーの録画を [表示できます](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。

## Target Standard／Premium 20.4.1（2020 年 5 月 6 日）

このリリースには、次の機能強化、修正および変更が含まれています。

* オーディエンスのデバイスとブラウザーのタイプが正しく認証されない問題を修正しました。 （TGT-36266）
* 幅が963ピクセル未満の画面でレポートデータを表示できない問題を修正しました。 （TGT-36549）
* 自動パーソナライゼーションレポートが正しく表示されない問題を修正しました。 （TGT-36619）
* Analyticsをターゲット(A4t)に使用する自動配分および自動ターゲットアクティビティで、互換性のない指標を選択できる問題を修正しました。 （TGT-36646）
* Visual Experience Composer(VEC)の一部のオプションが正しく表示されない問題を修正しました。 （TGT-36571）
* ターゲットUIで、1つのエクスペリエンスでコンテンツを置き換えた後に、他のRecommendationsオファープレビューに編集済みのコンテンツが表示される問題を修正しました。 （TGT-36053 および TGT-36894）
* 一部のユーザーがRecommendationsカタログから品目を削除できない問題を修正しました。 （TGT-36455）
* 複数ページのアクティビティでレコメンデーション条件を保存できない問題を修正しました。 （TGT-36249）
* 2回連続して条件を編集すると、行動データソースのラジオボタンが消える問題を修正しました。 （TGT-36796）
* レコメンデーションのアルゴリズムで、長期間「結果を取得」と表示される問題を修正しました。 （TGT-36550 および TGT-36551）
* 様々な言語にローカライズされた多くのUI文字列を更新しました。

## プロファイルバッチステータスAPI v2の変更点（2020年5月12日）

5月4日のリリースでは、プロファイルバッチステータスは、今後行レベルの失敗データのみを返します（成功データは返されません）。 失敗したプロファイルIDは、今後APIから返されます。

前回と新しいAPIの応答は次のとおりです。

`ProfileBatchStatus Api
http://<<edge>>/m2/<<client>>/profile/batchStatus?batchId=<batchid>`

**現在のところ、応答は次のようになります。**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>1514187733806-729395</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>1573612762055-214017</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

**5月4日以降の回答は次のとおりです。**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html)
