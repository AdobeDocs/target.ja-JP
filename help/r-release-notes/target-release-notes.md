---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: DNLAdobe Targetの最新リリースまたは今後のリリースに関する機能、拡張機能、および修正に関する情報を提供するリリースノートです。
title: Adobe Targetプレリリースノート
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 6ca8aa18c8b9deca1345f09db3a1f85b13840c28
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 22%

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2020 年 8 月 5 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングによっては、これらのページの情報が同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>* **AdobeがパーソナライゼーションエンジンのGartner Magic Quadrantで再びリーダーに** Adobeは、2020年のパーソナライゼーション・エンジンに関する3年目の年次Gartner Magic Quadrantで再びリーダーに選ばれました。 パーソナライゼーションエンジンのGartner Magic Quadrantは、2つのカテゴリに分かれる15の基準に基づいてベンダーを評価しました。 ビジョンと実行能力の完全性 [Adobeブログ](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.jsの提供終了**: 2020年8月30日に、Adobe Targetはmbox.jsライブラリをサポートしなくなります。 2020年8月30日以降は、mbox.jsからのすべての呼び出しが適切に失敗し、デフォルトコンテンツを提供することで実行されるターゲットアクティビティを持つページに影響します。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前にat.jsライブラリの最新バージョンに移行することをお勧めします。 詳しくは、at.jsの [仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) および [Adobe Targetスキルビルダーを参照してください。 開発者チャットでは、Adobe Targetのmbox.jsをat.jsに移行します](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsと比較して多くの利点を提供します。 多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアとサポートスタッフは、お客様がAdobeから期待する新しい機能とオファーをお客様に提供できます。
   >
   >
* **ターゲットのお知らせ**: ターゲットスキルビルダーセッション、開発者チャット、ウェビナー、ターゲットイベントの休憩セッションなど、今後のセッションについて詳しくは、ターゲットのお知らせページを参照してください。 詳しくは、「 [ターゲットのお知らせ](/help/r-release-notes/target-announcements.md)」を参照してください。


## Target Standard/Premium 20.9.1（2020 年 9 月 2 日）

このターゲットリリースの新機能または強化された機能は次のとおりです。

| 機能／拡張機能 | 説明 |
| --- | --- |
| Analytics for Target（A4T） 自動 [!UICONTROL ターゲット] アクティビティのサポート | [!UICONTROL 自動ターゲット] アクティビティは、 [!UICONTROL Analytics forターゲット] (A4T)をサポートします。<br>この統合により、 [!UICONTROL 自動ターゲットの高度な機械学習を使用して、複数のパフォーマンスの高いマーケティング担当者定義のエクスペリエンスから選択し、コンテンツをパーソナライズし、コンバージョンを促進しながら、] Adobe Analytics [!UICONTROL 目標指標や][!DNL Adobe Analytics] レポート機能や分析機能を使用できます。 [!UICONTROL 個々の顧客プロファイルや同様のプロファイルを持つ過去の訪問者の行動に基づいて、各訪問者に最適なエクスペリエンスを提供します。]<br>A/Bテストで使用するA4T [を既に](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) 実装している場合 [!UICONTROL 、]自動配分 [!UICONTROL 、エクスペリエンスターゲット設定のアクティビティで使用するA4Tを] A/Bテストで使用する場合は、すべてのを設定しています。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html)
