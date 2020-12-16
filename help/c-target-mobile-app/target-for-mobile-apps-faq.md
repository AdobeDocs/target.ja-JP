---
keywords: mobile app;frequently asked questions;faq;target mobile app
description: モバイルアプリ用Adobe Targetに関するよくある質問(FAQ)です。
title: モバイルアプリ用Adobe Targetに関するよくある質問(FAQ)
feature: mobile implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---


# モバイルアプリのターゲットに関するFAQ

モバイルアプリ用[!DNL Target]に関するよくある質問のリストです。

## [!DNL Adobe Experience Platform Launch]を使用してSDKをデプロイする必要がありますか。それとも[!DNL Launch]を使用せずにSDKをデプロイできますか。

SDKは、[Adobe Marketing Cloudgit](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)で使用できます。 [「](https://experienceleague.adobe.com/docs/launch/using/overview.html)起動&lt;a1/>」を使用しない場合は、独自の設定ファイルを管理し、アプリで管理する必要があります。

## 現在、どのSDKを利用できますか。

Adobe Experience PlatformモバイルSDKは、現在、iOS、Android、Reactをサポートしています。 詳しくは、『[Adobe Experience CloudプラットフォームモバイルSDKガイド](https://aep-sdks.gitbook.io/docs/)』を参照してください。

## 緯度と経度に関する検証の観点から、場所ベースの機能の頻度はどのくらいか。

詳しくは、[Adobeの場所のドキュメント](https://placesdocs.com/places-services-by-adobe-documentation/)を参照してください。

## Adobe Experience PlatformモバイルSDKを動作させるには、at.jsが必要ですか？

いいえ。モバイルSDKを使用する際にat.jsは必要ありません。 at.jsは、Webサイト用の[!DNL Target] JavaScriptライブラリです。 Adobe Experience PlatformモバイルSDKは、モバイルアプリ用です。

## ターゲットモバイルは、Adobe Targetプレミアム製品SKUの機能のみですか。

いいえ。[!DNL Adobe Target Standard]様の場合は、Mobile SDKをA/B Test and Experience Targeting(XT)アクティビティ用に使用できるのは[!DNL Target Standard]モバイルアプリアドオンのみです。 モバイルアプリでRecommendationsまたはAIを利用した機能を使用する場合は、[Adobe Targetプレミアム](/help/c-intro/intro.md#premium)ライセンスが必要です。

## Adobe Experience Manager(AEM)とターゲットのモバイルアクティビティの間にモバイルアプリ統合はありますか。

ロードマップに進んでいますが、まだ日程はありません。 現在、AEMからターゲットにJSON [エクスペリエンスフラグメント](/help/c-experiences/c-manage-content/aem-experience-fragments.md)を共有でき、モバイルアプリアクティビティで使用できる可能性があります。
