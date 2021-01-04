---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: DNLAdobe Targetの最新リリースまたは今後のリリースに関する機能、拡張機能、および修正に関する情報を提供するリリースノートです。
title: Adobe Targetプレリリースノート
feature: null
translation-type: tm+mt
source-git-commit: 10d8f47dcca1d09654405c8382c70adc0b828e50
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 10%

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2020 年 10 月 28 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングによっては、これらのページの情報が同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>* **AdobeがパーソナライゼーションエンジンのGartner Magic Quadrantで再びリーダーに** Adobeは、2020年のパーソナライゼーション・エンジンに関する3年目の年次Gartner Magic Quadrantで再びリーダーに選ばれました。パーソナライゼーションエンジンのGartner Magic Quadrantは、2つのカテゴリに分かれる15の基準に基づいてベンダーを評価しました。ビジョンと実行能力の完全性 [Adobeブログ](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.jsの提供終了**:2021年3月31日に、Adobe Targetはmbox.jsライブラリをサポートしなくなります。2021年3月31日以降は、mbox.jsからのすべての呼び出しが正常に失敗し、デフォルトコンテンツを提供することで実行されるターゲットアクティビティを持つページに影響します。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前にat.jsライブラリの最新バージョンに移行することをお勧めします。 詳しくは、[At.jsの仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)および[Adobe Targetスキルビルダーを参照してください。開発者チャットで、Adobe Targetのmbox.jsをat.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)に移行します。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsと比較して多くの利点を提供します。 多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアとサポートスタッフは、お客様がAdobeから期待する新しい機能とオファーをお客様に提供できます。
   >
   >
* **ターゲットのお知らせ**:ターゲットスキルビルダーセッション、開発者チャット、ウェビナー、ターゲットイベントの休憩セッションなど、今後のセッションについて詳しくは、ターゲットのお知らせページを参照してください。詳しくは、[ターゲットのお知らせ](/help/r-release-notes/target-announcements.md)を参照してください。


## Target Standard／Premium 20.10.1（2020 年 10 月 27 日）

このリリースには、次の新機能が含まれています。

| 機能 | 詳細 |
| --- | --- |
| [オンデバイス判定](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) | デバイス上の判定機能を使用すると、マーケターと製品開発者は、実験と機械学習に基づくパーソナライゼーションを、ユーザーのデバイス内から、チャネル全体にわたって、ほぼゼロの遅延で提供できます。<br>スピードとパフォーマンスは重要です。顧客の洞察とユーザー満足度に関して。<br>On-device decisioningを使用すると、A/B Test and Experience Targeting(XT)アクティビティタイプで主要なパーソナライゼーションおよび実験の手順をコンパイルして、CDN経由で顧客のデバイスに読み込まれる「optimization artifacts:」 JSONオブジェクトを生成できます。また、オンデバイス判定は[!DNL Adobe Experience Cloud]製品とネイティブに接続されるので、[!DNL Target]ユーザーは迅速な分析を得られ、エクスペリエンスの反復速度が速くなります。<br>詳しくは、「*[オンデバイスの判定](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md)」を参照してください。 |

このリリースには、次の機能強化、修正および変更が含まれています。

* [!UICONTROL 平均上昇率の信頼区間]と[!UICONTROL 信頼性]が[!DNL Auto-Target]レポートーに表示されない[!UICONTROL 合計]行の問題を修正しました。 測定値は、すべてのエクスペリエンスで正しく表示されました。 （TGT-37301）
* 9月15日午後2時30分以降の[!DNL Adobe Target Premium]ユーザーの[!UICONTROL 自動ターゲット]レポートに影響する問題を修正しました。(PDT)～10月6日午前9時25分(PDT)。 影響を受けたコンバージョン指標のレポート（「[!UICONTROL ページ]を表示した」または「[!UICONTROL mbox]をクリックした」オプションを使用して設定）を表示すると、コンバージョン率が誤ってレポートされます。 現時点では、配信に関する既知の問題はありません。 レポートを再同期して修正する方法について詳しくは、*既知の問題と解決された問題*&#x200B;の&#x200B;*解決された問題*&#x200B;の[自動ターゲットレポート](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics)を参照してください。
* [!UICONTROL カタログ検索]テーブルの選択可能な[!UICONTROL 最終更新日]列と[!UICONTROL 最終更新日]フィルターが追加されました。 この機能強化により、個々の項目を開いて最後に更新された日時を確認する必要がなく、項目が最後に更新された日時でフィルターできるので、時間と労力を節約できます。

   ![列とフィルターの図での最終更新](/help/r-release-notes/assets/column-and-filter.png)

* ターゲットUIが[Webコンテンツアクセシビリティガイドライン](https://www.w3.org/WAI/standards-guidelines/wcag/) 2.0レベルAおよびAA成功基準(WCAG 2.0 AA)に準拠するように更新されました。 （TGT-34384 および TGT-24679）
* コンテンツセキュリティポリシー(CSP)の機能が強化されました。 （TGT-37035）
* CNAMEを使用するお客様のパラメーターとしてクライアントコードを指定する方法が導入されました。 （TNT-38571）
* [!DNL Adobe Experience Cloud] ドキュメントの移動先 [!DNL Experience League]。10月中に、すべてのリリースノート、記事、ビデオ、およびチュートリアルが現在の場所(`docs.adobe.com`)から[!DNL Experience League]に移動します。 この移行により、すべての学習、セルフヘルプ、イネーブルメント、コミュニティのコンテンツが1か所で提供されます。 この変更が発生した場合は、すべてのリンクが[!DNL Experience League]にリダイレクトされるので、必要な作業はありません。 カウントオーバーが始まったら、リリースノートを更新します。

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html)
