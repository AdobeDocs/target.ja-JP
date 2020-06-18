---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 最新または今後のDNLAdobe Targetリリースの機能、拡張機能、および修正に関する情報を提供するリリースノートです。
title: Adobe Targetのプレリリースノート
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: a55aeb18e86a4428187faa5ecba6c66d11feda6d
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 14%

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日： 2020年6月17日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングによっては、これらのページの情報が同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!NOTE]
>
>* **mbox.jsの提供終了**: 2020年8月30日をもって、Adobe Targetはmbox.jsライブラリをサポートしなくなります。 2020年8月30日以降は、mbox.jsからのすべての呼び出しが失敗し、Targetアクティビティが実行されているページに影響が及びます。 サイトに発生する可能性のある問題を回避するため、すべてのお客様に、この日より前にat.jsライブラリの最新バージョンに移行することをお勧めします。 詳しくは、at.jsの仕組み [および](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)[Adobe Targetスキルビルダーを参照してください。 開発者チャットで、Adobe Targetのmbox.jsをat.jsに移行します](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   mbox.jsは現在サポートされていますが、2017年7月以降、このライブラリに対する機能の更新は提供されていません。 新しいat.jsは、mbox.jsと比較して多くの利点を提供します。 多くのメリットがある中でも、at.jsは、Web実装のページ読み込み時間を改善し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。
   >
   >   
   すべてのお客様をat.jsに移行することで、アドビのエンジニアとサポートスタッフは、お客様がアドビから期待する新しい機能とオファーをお客様に提供できます。
   >
   >
* **Targetのお知らせ**: Targetスキルビルダーセッション、開発者チャット、ウェビナー、Targetイベントの休憩セッションなど、今後のセッションについて詳しくは、Targetのお知らせページを参照してください。 詳しくは、「 [Targetのお知らせ](/help/r-release-notes/target-announcements.md)」を参照してください。


## Target Standard／Premium 20.5.1（2020 年 6 月 17 日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| Analytics for Target（A4T） 自動配分 [!UICONTROL アクティビティのサポート] | [!UICONTROL 自動配分] アクティビティで、 [AnalyticsがTargetに対応するようになりました](/help/c-integrating-target-with-mac/a4t/a4t.md)。<br>この統合では、 [!UICONTROL 自動配分] 、マルチアームバンディット機能を使用して、 [!UICONTROL AdobeAnalytics] 目標指標や [!UICONTROL AdobeAnalytics] レポート機能および分析機能を使用しながら、勝者エクスペリエンスにトラフィックを誘導できます。<br>A/B Test &amp; Experience Targetingアクティビティで使用するA4T [を既に](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) 実装している場合は、設定がすべて完了です。<br>詳しくは、 [Analyticsを参照して、](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) アクティビティ作成時の自動配分アクティビティのTarget(A4T)サポートを確認してください **。 |
| 自動Targetと自動パーソナライゼーションアクティビティのトラフィック配分方法の応答トークン | 自動 [Target](/help/administrating-target/response-tokens.md) と [!UICONTROL 自動パーソナライゼーション] アクティビティに2つの応答トークンが追加され、訪問者が「制御」または「ターゲット」トラフィックに割り当てられた結果として特定のエクスペリエンスを受け取ったかどうかを判断できるようになりました。<ul><li>`experience.trafficAllocationId` は、訪問者が「コントロール」トラフィックからエクスペリエンスを受け取った場合は0を、「ターゲット」トラフィックの配布から訪問者がエクスペリエンスを受け取った場合は1を返します。</li><li>`experience.trafficAllocationType` は、&quot;control&quot;または&quot;targeted&quot;を返します。</li></ul>コントロールとターゲットトラフィックの比較について詳しくは、「自動パーソナライゼーションまたは自動Targetアクティビティのコントロールの [選択](/help/c-activities/t-automated-personalization/experience-as-control.md)」を参照してください。 |
| [!UICONTROL 投稿者] ロール | この新しい役割は、現在の [!UICONTROL 監視者] (Observer)の役割に似ています(表示アクティビティは可能ですが、作成または編集はできません)。 ただし、 [!UICONTROL 投稿者] ロールには、アクティビティをアクティブ化する追加の権限があります。<br>詳しくは、次を参照してください。 <ul><li>**Target Standardユーザー: [「](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) ユーザー **」で役割と権限を指定します。</li><li>**Targetプレミアムユーザー**: [手順6: ロールと権限の指定は](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) 、「エンタープライズ権限の *設定*」で行います。</li></ul> |
| 2020年 [!DNL Analysis Workspace]<br>6月25日のA4Tのサポート | [!UICONTROL でTarget分析] (A4T)がサポートされるようになり [!DNL Analysis Workspace]ました。 Target用 [!UICONTROL Analytics(A4T)パネル] では、での [!DNL Adobe Target] アクティビティとエクスペリエンスを分析でき [!DNL Analysis Workspace]ます。<br>詳しくは、「 [A4TレポートのAnalytics](/help/c-integrating-target-with-mac/a4t/reporting.md) の *レポート* 」および「Analyticsツールガイド [」パネルのTarget用(A4T)(A4T)](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html)** Analyticsのレポート」を参照してください。 |

### 機能強化、修正および変更

* 「個別訪問者数」ではなく、「訪問者数」指標がアクティビティの定義に保存される問題を修正しました。 （TGT-37098）
* 垂直スクロールバーが [!DNL Target] オーディエンス [!UICONTROL ページで正しく機能しない原因となっていた] UIの問題を修正しました。 （TGT-36968）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html)
