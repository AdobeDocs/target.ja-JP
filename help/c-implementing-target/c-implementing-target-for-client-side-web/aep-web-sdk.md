---
keywords: Adobe Experience Platform Web SDK;aep web sdk;web sdk;sdk;adobe experience cloud;platform edge network;adobe experience platform edge network;edge network;aep edge network
description: Adobe Experience Platform Web SDKを使用して、AEP Edgeネットワークを通じてAdobe Experience Cloudの様々なサービスとやり取りする方法について説明します。
title: Experience PlatformWeb SDKを使用してを実装する方法を教えてください。
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: a2b3bf75e8b14c3068b8dba59f31d2577d9cec29
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 6%

---

# Adobe Experience Platform Web SDK

[!DNL Adobe Experience Platform Web SDK] (AEP Web SDK)は、のお客様が [!DNL Adobe Experience Cloud] Adobe Experience Platform Edge Network [!DNL Target]を通じてExperience Cloud内の様々なサービス( を含む)を操作できる、クライアントサイドJavaScriptライブラリです。JavaScriptライブラリに加えて、Web SDKの設定に役立つ[!DNL Experience Platform Launch]拡張機能があります。

詳しくは、*Adobe Experience Platform Web SDK*&#x200B;のヘルプの次のリンクを参照してください。

* 包括的な情報：[Adobe Experience Platform Web SDKとは](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)
* [!DNL Target]に固有の情報：[Targetの概要](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)

## このガイドの推奨ドキュメント

上記の[!DNL Platform Web SKD]ドキュメントに加えて、このガイドのトピックには[!DNL Platform Web SDK]に固有の情報も含まれています。[!DNL Target]の機能に関する情報も含まれています。

| 機能 | 説明/リンク |
| --- | --- |
| [[!DNL Adobe Analytics] as the reporting source for [!DNL Adobe Target] （A4T）](/help/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T)は、コンバージョン指標とオーディエンスセグメントに基づいてアクティビティを作成できる、クロスソリ [!DNL Analytics] ューションの統合です。A4T統合により、[!DNL Analytics]レポートを使用して結果を調べることができます。<br>「  [Adobe Experience Platform Web SDKの実装でサ](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) ポートされるアクテ [ィビティのタイプ」と「実装手順」を参照してください](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform)。 |
| [アクティビティ QA](/help/c-activities/c-activity-qa/activity-qa.md) | [!DNL Adobe Target]のQA URLを使用して、変更のないプレビューリンク、オプションのオーディエンスターゲティング、ライブアクティビティデータからセグメント化されたまま残るQAレポートを使用して、簡単なエンドツーエンドのアクティビティQAを実行します。 [!UICONTROL アクティビテ] ィQAを使用すると、アクティビティをライ [!DNL Target] ブに開始する前に、完全にテストできます。<br>詳しく [は、「 Target JavaScriptライブラリQAモ](/help/c-activities/c-activity-qa/activity-qa.md#compatibility) ードの互換性」および「プレ [ビューURL 」を](/help/c-activities/c-activity-qa/activity-qa.md#preview) 参照してください。 |
| [オーディエンス](/help/c-target/target.md) | [!DNL Adobe Target]のオーディエンスは、誰がターゲットアクティビティでコンテンツやエクスペリエンスを表示するかを決定します。<br>詳しく [は、オーディエンスリス](/help/c-target/c-audiences/audiences.md#use-list) トの使 [用複数のオーディエンスの結合](/help/c-target/combining-multiple-audiences.md)を参照してください。 |
| [リダイレクトオファー - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | リダイレクトオファーを使用すると、訪問者のブラウザーが新しいページにリダイレクトされます。<br>「 A4T [用のサ [!DNL Adobe Experience Platform Web SDK] ポートされたリダイレクトオファーはありますか？](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [レスポンストークン](/help/administrating-target/response-tokens.md) | レスポンストークンを使用して、TargetのデータをGoogle Analyticsや他のサードパーティ統合に送信できます。<br>このタス [クを実行する方法のコードサンプルについては、「 Platform Web SDKを](/help/administrating-target/response-tokens.md#platform-web-sdk) 使用したGoogle Analyticsへのデータ送信」を参照してください。 |
| [TLS（Transport Layer Security）暗号化の変更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | TLS(Transport Layer Security)は、最高のセキュリティ標準を維持し、顧客データの安全を促進するのに役立ちます。 |
