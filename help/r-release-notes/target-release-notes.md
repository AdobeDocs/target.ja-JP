---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: DNL Adobe Targetの最新リリースまたは今後のリリースに関する機能、拡張機能および修正に関する情報を提供するリリースノートです。
title: Adobe Targetプレリリースノート
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: bd39d7b6121eb6ccbfeb49d73a8b57618cc964ef
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 17%

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日： 2020年6月12日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングによっては、これらのページの情報が同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!NOTE]
>
>* **mbox.jsの提供終了**: 2020年8月30日に、Adobe Targetはmbox.jsライブラリをサポートしなくなります。 2020年8月30日以降は、mbox.jsからのすべての呼び出しが失敗し、ターゲットアクティビティが実行されているページに影響が及びます。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前にat.jsライブラリの最新バージョンに移行することをお勧めします。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). 詳しくは、 *Adobe Target Skill Builderを参照してください。 開発者向けチャットで、次に示すようにAdobe Targetのmbox.jsをat.js* に移行します。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsと比較して多くの利点を提供します。 多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアとサポートスタッフは、お客様がアドビから期待する新しい機能とオファーをお客様に提供できます。
   >
   >
* **ターゲットのお知らせ**: ターゲットスキルビルダーセッション、開発者チャット、ウェビナー、ターゲットイベントの休憩セッションなど、今後のセッションについて詳しくは、ターゲットのお知らせページを参照してください。 詳しくは、「 [ターゲットのお知らせ](/help/r-release-notes/target-announcements.md)」を参照してください。


## at.js 1.8.2およびat.js 2.3.1リリース（2020年6月16日）

at.jsライブラリに加えられた改善点および修正点 [!DNL Target] を次に示します。

### at.js 1.8.2

* CNAMEとエッジの上書き(at.js 1)を使用する場合の問題を修正しました。*x* ：サーバードメインが誤って作成され、 [!DNL Target] 要求が失敗する可能性があります。 （TNT-35064）

### at.js 2.3.1

* targetGlobalSettingsを使用して `deviceIdLifetime` 設定を上書き可能に [しました](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。 （TNT-36349）
* CNAMEとエッジの上書き(at.js 2)を使用する場合の問題を修正しました。*x* ：サーバードメインが誤って作成され、 [!DNL Target] 要求が失敗する可能性があります。 （TNT-35065）
* 拡張機能v2と [!DNL Target] 拡張機能を使用する場合、 [!DNL Launch] 呼び出しの [!DNL Adobe Analytics] 遅延が発生する問題を修正しました [!DNL Launch][!DNL Target][!DNL Analytics]`sendBeacon` 。 (TNT-36407、TNT-35990、TNT-36000)

## Target Standard／Premium 20.5.1（2020 年 6 月 17 日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| Analytics for Target（A4T） 自動配分アクティビティのサポート | 6月のリリースでは、自動配分テストで [Analyticsのターゲットがサポートされ](/help/c-integrating-target-with-mac/a4t/a4t.md)ます。 この統合により、自動配分のマルチアームバンディット機能を使用して、Adobe Analyticsの目標指標やAdobe Analyticsのレポート機能および分析機能を使用しながら、勝者エクスペリエンスにトラフィックを誘導できます。 A/B Test &amp; Experience Targetingアクティビティで使用するA4T [を既に](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) 実装している場合は、設定がすべて完了です。 |
| 投稿者ロール | この新しい役割は、現在の監視者の役割に似ています(アクティビティを表示することはできますが、作成または編集することはできません)。 ただし、「発行者」の役割には、アクティビティをアクティブ化する追加の権限があります。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html)
