---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
title: 'Adobe Target リリースノート（現行） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: a55aeb18e86a4428187faa5ecba6c66d11feda6d
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 28%

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。また、TargetAPI、SDK、JavaScriptライブラリ(at.js)およびその他のプラットフォームの変更に関するリリースノートも適宜含まれています。

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


括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## Target Standard／Premium 20.5.1（2020 年 6 月 17 日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| Analytics for Target（A4T） 自動配分 [!UICONTROL アクティビティのサポート] | [!UICONTROL 自動配分] アクティビティで、 [AnalyticsがTargetに対応するようになりました](/help/c-integrating-target-with-mac/a4t/a4t.md)。<br>この統合では、 [!UICONTROL 自動配分] 、マルチアームバンディット機能を使用して、 [!UICONTROL AdobeAnalytics] 目標指標や [!UICONTROL AdobeAnalytics] レポート機能および分析機能を使用しながら、勝者エクスペリエンスにトラフィックを誘導できます。<br>A/B Test &amp; Experience Targetingアクティビティで使用するA4T [を既に](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) 実装している場合は、設定がすべて完了です。<br>詳しくは、 [Analyticsを参照して、](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) アクティビティ作成時の自動配分アクティビティのTarget(A4T)サポートを確認してください **。 |
| 自動Targetと自動パーソナライゼーションアクティビティのトラフィック配分方法の応答トークン | 自動 [Target](/help/administrating-target/response-tokens.md) と [!UICONTROL 自動パーソナライゼーション] アクティビティに2つの応答トークンが追加され、訪問者が「制御」または「ターゲット」トラフィックに割り当てられた結果として特定のエクスペリエンスを受け取ったかどうかを判断できるようになりました。<ul><li>`experience.trafficAllocationId` は、訪問者が「コントロール」トラフィックからエクスペリエンスを受け取った場合は0を、「ターゲット」トラフィックの配布から訪問者がエクスペリエンスを受け取った場合は1を返します。</li><li>`experience.trafficAllocationType` は、&quot;control&quot;または&quot;targeted&quot;を返します。</li></ul>コントロールとターゲットトラフィックの比較について詳しくは、「自動パーソナライゼーションまたは自動Targetアクティビティのコントロールの [選択](/help/c-activities/t-automated-personalization/experience-as-control.md)」を参照してください。 |
| [!UICONTROL 投稿者] ロール | この新しい役割は、現在の [!UICONTROL 監視者] (Observer)の役割に似ています(表示アクティビティは可能ですが、作成または編集はできません)。 ただし、 [!UICONTROL 投稿者] ロールには、アクティビティをアクティブ化する追加の権限があります。<br>詳しくは、次を参照してください。 <ul><li>**Target Standardユーザー**: [「](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) ユーザー **」で役割と権限を指定します。</li><li>**Targetプレミアムユーザー**: [手順6: ロールと権限の指定は](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) 、「エンタープライズ権限の *設定*」で行います。</li></ul> |
| 2020年 [!DNL Analysis Workspace]<br>6月25日のA4Tのサポート | [!UICONTROL でTarget分析] (A4T)がサポートされるようになり [!DNL Analysis Workspace]ました。 Target用 [!UICONTROL Analytics(A4T)パネル] では、での [!DNL Adobe Target] アクティビティとエクスペリエンスを分析でき [!DNL Analysis Workspace]ます。<br>詳しくは、「 [A4TレポートのAnalytics](/help/c-integrating-target-with-mac/a4t/reporting.md) の *レポート* 」および「Analyticsツールガイド [」パネルのTarget用(A4T)(A4T)](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html)** Analyticsのレポート」を参照してください。 |

### 機能強化、修正および変更

* 「個別訪問者数」ではなく、「訪問者数」指標がアクティビティの定義に保存される問題を修正しました。 （TGT-37098）
* 垂直スクロールバーが [!DNL Target] オーディエンス [!UICONTROL ページで正しく機能しない原因となっていた] UIの問題を修正しました。 （TGT-36968）

## at.js 1.8.2およびat.js 2.3.1リリース（2020年6月16日）

at.jsライブラリに加えられた改善点および修正点 [!DNL Target] を次に示します。

| 機能／拡張機能 | 説明 |
| --- | --- |
| at.js 1.8.2 | at.jsのこのリリースはメンテナンスリリースであり、次の修正が含まれています。<ul><li>CNAMEとエッジの上書き(at.js 1)を使用する場合の問題を修正しました。*x* ：サーバードメインが誤って作成され、 [!DNL Target] 要求が失敗する可能性があります。 （TNT-35064）</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
| at.js 2.3.1 | at.js のこのリリースはメンテナンスリリースで、次の機能強化および修正が含まれています。<ul><li>targetGlobalSettingsを使用して `deviceIdLifetime` 設定を上書き可能に [しました](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。 （TNT-36349）</li><li>CNAMEとエッジの上書き(at.js 2)を使用する場合の問題を修正しました。*x* ：サーバードメインが誤って作成され、 [!DNL Target] 要求が失敗する可能性があります。 （TNT-35065）</li><li>拡張機能v2と [!DNL Target] 拡張機能を使用する場合、 [!DNL Launch] 呼び出しの [!DNL Adobe Analytics] 遅延が発生する問題を修正しました [!DNL Launch][!DNL Target][!DNL Analytics]`sendBeacon` 。 (TNT-36407、TNT-35990、TNT-36000)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート —Targetサーバー側API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Adobe Targetのサーバー側APIに関するリリースノートです。 |
| [リリースノート —TargetNode.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Adobe TargetのNode.js SDKに関するリリースノートです。 |
| [リリースノート —TargetJava SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Adobe TargetのJava SDKに関するリリースノートです。 |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.js JavaScriptライブラリの各Adobe Targetの変更点について詳しく説明します。 |
| [mbox.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | このページには、mbox.js の各バージョンに対する変更が表示されます。<br>mbox.jsライブラリは開発されなくなります。 すべてのお客様が mbox.js から at.js に移行する必要があります。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート {#section_1BC5F5208DA548E9B4344A0836E4B943}

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報が表示されます。<br>詳しくは、「[ドキュメントの変更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](../r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、「 [Experience Cloudリリースノート](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)」を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update リスト | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
