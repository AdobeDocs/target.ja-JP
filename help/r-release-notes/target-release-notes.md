---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 最新または今後のDNLアドビターゲットリリースの機能、拡張機能および修正に関する情報を提供するリリースノートです。
title: アドビターゲットプレリリースノート
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: ae97b36e9a5aaa0394fb3b4ab1ad40b38a0c97be
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 19%

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

## Target Standard／Premium 20.5.1（2020 年 6 月 10 日）

このリリースの詳細は、こちらを参照してください。

## プロファイルバッチステータスAPI v2の変更（日付TBD）

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
