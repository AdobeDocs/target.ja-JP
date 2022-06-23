---
keywords: Adobe Experience Platform Web SDK;aep web sdk;web sdk;sdk;adobe experience cloud;platform edge network;adobe experience platform edge network;edge network;aep edge network
description: Adobe Experience Platform Web SDK を使用して、AEP Edge Network を通じてAdobe Experience Cloudの様々なサービスを操作する方法について説明します。
title: Experience PlatformWeb SDK を使用してを実装する方法を教えてください。
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 16%

---

# Adobe Experience Platform Web SDK

[!DNL Adobe Experience Platform Web SDK] (AEP Web SDK) は、 [!DNL Adobe Experience Cloud] Experience Cloud( [!DNL Target]) 経由 [!UICONTROL Adobe Experience Platform Edge Network]. JavaScript ライブラリに加えて、 [!DNL Adobe Experience Platform] 拡張機能を使用して Web SDK の設定を支援します。

詳しくは、 *Adobe Experience Platform Web SDK* ヘルプ：

* 包括的な情報については、 [Adobe Experience Platform Web SDK とは](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)
* 次に特有の情報： [!DNL Target]: [Target の概要](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html?lang=ja)

## チュートリアル：Platform Web SDK を使用したAdobe Experience Cloudの実装

方法を学ぶ [Adobe Experience Platform Web SDK を使用したExperience Cloudアプリケーションの実装](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target=_blank}。 Target に固有の情報については、 [Platform Web SDK での Target の設定](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-target.html){target=_blank} を参照してください。

## 推奨ドキュメント

また、 [!DNL Platform Web SDK] 前述のドキュメント。このガイドのトピックには、 [!DNL Platform Web SDK] ～に関しては [!DNL Target] 機能と機能に関する情報です。

| 機能 | 説明/リンク |
| --- | --- |
| [アクティビティ QA](/help/main/c-activities/c-activity-qa/activity-qa.md) | での QA URL の使用 [!DNL Adobe Target] 変更されないプレビューリンク、オプションのオーディエンスターゲティング、実際のアクティビティデータからセグメント化された QA レポートを使用して、簡単にエンドツーエンドのアクティビティ QA を実行できます。 [!UICONTROL アクティビティ QA] を [!DNL Target] アクティビティを開始する前に有効にしておく必要があります。<br>詳しくは、 [Target JavaScript ライブラリ QA モードの互換性](/help/main/c-activities/c-activity-qa/activity-qa.md#compatibility) および [プレビュー URL](/help/main/c-activities/c-activity-qa/activity-qa.md#preview). |
| [[!UICONTROL Analytics for Target]（A4T）](/help/main/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target]（A4T）は、[!DNL Analytics] のコンバージョン指標とオーディエンスセグメントに基づいてアクティビティを作成できるクロスソリューション統合です。A4T 統合では、[!DNL Analytics] レポートを使用して結果を確認できます。<br>詳しくは、 [サポートされるアクティビティのタイプ](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) および [Adobe Experience Platform Web SDK 実装の実装手順](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#platform). |
| [オーディエンス](/help/main/c-target/target.md) | のオーディエンス [!DNL Adobe Target] ターゲットアクティビティでコンテンツとエクスペリエンスを表示する対象を決定します。<br>詳しくは、 [オーディエンスリストの使用](/help/main/c-target/c-audiences/audiences.md#use-list) および [複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md). |
| [オーディエンスの作成](/help/main/c-target/c-audiences/audiences.md) | [!DNL Adobe Experience Platform] で作成されたオーディエンスを使用すると、よりインパクトのあるパーソナライゼーションにつながる豊富な顧客データが提供されます。<ul>詳しくは、 [次のオーディエンスを使用： [!DNL Adobe Experience Platform]](/help/main/c-target/c-audiences/audiences.md#aep). |
| [オファーの決定](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md) | Adobe Journey Optimizerで作成したオファーの決定を Target アクティビティ（手動の A/B テストまたはエクスペリエンスのターゲット設定）に追加して、Web およびモバイルで訪問者にとって次に最適なオファーを決定し配信します。 |
| [リダイレクトオファー - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | リダイレクトオファーを使用すると、訪問者のブラウザーは新しいページにリダイレクトされます。<br>詳しくは、 [を実行します。 [!DNL Adobe Experience Platform Web SDK] A4T のリダイレクトオファーをサポートしますか？](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [レスポンストークン](/help/main/administrating-target/response-tokens.md) | レスポンストークンを使用して、Target のデータをGoogle Analyticsや他のサードパーティ統合に送信できます。<br>詳しくは、 [Platform Web SDK を使用してGoogle Analyticsにデータを送信する](/help/main/administrating-target/response-tokens.md#platform-web-sdk) を参照して、このタスクを実行する方法のコードサンプルを確認してください。 |
| [シングルページアプリケーションの実装](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/spa-implementation.html?lang=en) 内 *Platform Web SDK の概要* ガイド。 | [!UICONTROL Adobe Experience Platform Web SDK] は、シングルページアプリケーション (SPA) など、次世代のクライアントサイドテクノロジーでパーソナライゼーションを実行するための機能を提供します。 |
| [TLS（Transport Layer Security）暗号化の変更](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/) | TLS(Transport Layer Security) は、最高のセキュリティ標準を維持し、顧客データの安全を促進するのに役立ちます。 |
