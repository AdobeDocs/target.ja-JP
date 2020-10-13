---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: DNLAdobe Targetの最新リリースまたは今後のリリースに関する機能、拡張機能、および修正に関する情報を提供するリリースノートです。
title: Adobe Targetプレリリースノート
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 55860d360cf69415ad41807144a3cbe4657eedad
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 13%

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2020年10月7日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングによっては、これらのページの情報が同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>* **AdobeがパーソナライゼーションエンジンのGartner Magic Quadrantで再びリーダーに** Adobeは、2020年のパーソナライゼーション・エンジンに関する3年目の年次Gartner Magic Quadrantで再びリーダーに選ばれました。 パーソナライゼーションエンジンのGartner Magic Quadrantは、2つのカテゴリに分かれる15の基準に基づいてベンダーを評価しました。ビジョンと実行能力の完全性 [Adobeブログ](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.jsの提供終了**:2021年1月18日に、Adobe Targetはmbox.jsライブラリをサポートしなくなります。 2021年1月18日以降、mbox.jsからのすべての呼び出しが正常に失敗し、デフォルトコンテンツを提供することで実行されているターゲットアクティビティを持つページに影響します。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前にat.jsライブラリの最新バージョンに移行することをお勧めします。 詳しくは、at.jsの [仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) および [Adobe Targetスキルビルダーを参照してください。開発者チャットでは、Adobe Targetのmbox.jsをat.jsに移行します](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsと比較して多くの利点を提供します。 多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアとサポートスタッフは、お客様がAdobeから期待する新しい機能とオファーをお客様に提供できます。
   >
   >
* **ターゲットのお知らせ**:ターゲットスキルビルダーセッション、開発者チャット、ウェビナー、ターゲットイベントの休憩セッションなど、今後のセッションについて詳しくは、ターゲットのお知らせページを参照してください。 詳しくは、「 [ターゲットのお知らせ](/help/r-release-notes/target-announcements.md)」を参照してください。


## Target Standard／Premium 20.10.1（2020 年 10 月 27 日）

このリリースには、次の新機能が含まれています。

| 機能 | 詳細 |
| --- | --- |
| デバイス上の意思決定 | デバイス上での意思決定では、マーケターと製品開発者の両方が、実験や機械学習に基づくパーソナライゼーションを、チャネル内から、ほぼゼロの遅延で提供できます。<br>スピードとパフォーマンスは重要です。顧客の洞察とユーザー満足度に関して。 デバイス上での意思決定を使用すると、マーケティング担当者や現在の製品開発者は、ユーザーのデバイス内でエクスペリエンスをテストおよび最適化でき、リアルタイムのコンテキストエクスペリエンスの判断と読み込み時間をほぼゼロにできます。<br>デバイス上での意思決定では、すべてのパーソナライズおよび実験の指示をコンパイルし、お客様のデバイスにロードされる「最適化アーティファクト」に取り込むことができます。 遅延がゼロのアーティファクトは、マーケターに対して1対1のパーソナライゼーション、行動リターゲティング、リアルタイムの製品とコンテンツの推奨事項を提供します。また、開発者や製品所有者は、テストユーザーの体験とターゲットとフェーズ製品の起動、リアルタイムの絞り込みを行います。 また、デバイス上での意思決定は [!DNL Adobe Experience Cloud] 製品とネイティブに結び付くので、 [!DNL Target] ユーザーは迅速な分析を得られ、エクスペリエンスの反復処理を迅速に行うことができます。<br>**今すぐライブウェビナーに登録します。** Adobe Target製品のエキスパートが、遅延なしでローカルに実行するための重要なエクスペリエンス最適化決定の動きについて話し合うと、新しい使用例への扉が開かれ、お客様のサイトパフォーマンスが向上します。<ul><li>2020年11月10日</li><li>午前10時PT/午後12時CT/午後1時ET</li><li>[登録はこちら](https://www.adobeeventsonline.com/Target/2020/OnDeviceDecisions/invite.html)</li></ul> |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html)
