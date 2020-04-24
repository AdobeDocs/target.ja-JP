---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 最新または今後のDNLアドビシステムズ社のリリースの機能、拡張機能および修正に関する情報を提供するリリースターゲットです。
title: アドビターゲットプレリリースノート
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: e9a6545ab65cf1214977f8fa472904527c18a04d

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2020年4月25日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングに応じて、これらのページの情報は同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!NOTE]
>
>* **mbox.jsの廃止**:2020年8月31日に、アドビターゲットはmbox.jsライブラリをサポートしなくなります。 2020年8月30日以降、mbox.jsからの呼び出しはすべて失敗し、ターゲットアクティビティが実行されているページに影響します。 サイトで発生する可能性のある問題を回避するため、すべてのお客様は、この日より前に最新バージョンのat.jsライブラリに移行することをお勧めします。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). 詳しくは、 *Adobeターゲットスキルビルダーを参照してください。開発者チャットでは、この件に関する今後の開発者チャットへの登録について、アドビターゲットのmbox* .jsを以下のat.jsに移行してください。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリの機能の更新は提供されていません。 新しいat.jsは、mbox.jsよりも多くの利点を提供します。 特に、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化し、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアおよびサポートスタッフは、アドビが期待する新しい機能とオファーをお客様に提供できます。


## Adobeターゲットスキルビルダー：開発者チャット， Adobeターゲットのmbox.jsのat.jsへの移行 {#skill-builder}

アドビターゲットプロダクトマネージャーのDavid Son氏が、mbox.jsをat.jsに移行する利点を説明します。 最新のat.jsの更新を確認し、その機能強化と技術展開のより大きなトレンドとの整合性を確認します。また、mbox.jsからat.jsに移行する際にターゲットから最大限の価値を引き出すための実用的なヒントも紹介します。 アドビのターゲット開発者は、これを見逃したくはありません。

5月5日8:00 ～ 9:00 AM(PDT)

[今すぐ登録！](https://atskillbuilder-devchat.experienceleague.adobeevents.com/)

## Target Standard／Premium 20.4.1（2020 年 4 月 28 日）

このリリースには、次の機能強化、修正および変更が含まれています。

* デバイスのデバイスとブラウザーのタイプが正しく認識されない問題を修正しました。オーディエンス （TGT-36266）
* 幅が963ピクセル未満の画面でレポートデータを表示できない問題を修正しました。 （TGT-36549）
* 自動パーソナライゼーションレポートが正しく表示されない問題を修正しました。 （TGT-36619）
* ターゲットにAnalytics(A4t)を使用する自動配分アクティビティと自動ターゲットオプションで、互換性のない指標が選択される問題を修正しました。 （TGT-36646）
* Visual Experience Composer(VEC)の一部のオプションが正しく表示されない問題を修正しました。 （TGT-36571）
* ターゲットUIで、1つのエクスペリエンスでユーザーがコンテンツを置き換えた後に、他のRecommendationsオファープレビューが編集済みのコンテンツを表示する問題を修正しました。 （TGT-36053 および TGT-36894）
* 一部のユーザーがRecommendationsカタログから品目を削除できない問題を修正しました。 （TGT-36455）
* 複数ページのレコメンデーションで、レコメンデーション条件を保存できない問題を修正しました。アクティビティ （TGT-36249）
* 2回連続して条件を編集すると、行動データソースのラジオボタンが消える問題を修正しました。 （TGT-36796）
* Recommendationsのアルゴリズムで、拡張期間に「結果を取得中」と表示される表示の問題を修正しました。 （TGT-36550 および TGT-36551）
* 様々な言語にローカライズされた多くのUI文字列を更新しました。

## プロファイルバッチステータスAPI v2の変更（2020年5月4日）

5月4日のリリースでは、プロファイルバッチステータスは、今後行レベルの失敗データのみを返します（成功データは返されません）。 失敗したプロファイルIDは、今後APIから返されます。

以前と新しいAPIの応答は次のとおりです。

`ProfileBatchStatus Api
http://<<edge>>/m2/<<client>>/profile/batchStatus?batchId=<batchid>`

**現在、応答は次のように表示されます。**

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

**5月4日以降、次の回答が返されます。**

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
