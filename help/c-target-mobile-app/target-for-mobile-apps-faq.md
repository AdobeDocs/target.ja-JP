---
keywords: モバイルアプリ；よくある質問；faq;targetモバイルアプリ
description: モバイルアプリのAdobe [!DNL Target] に関するよくある質問とその回答を表示します。
title: 'モバイルアプリに関して<A0/>に関するよくある質問は何ですか。 [!DNL Target] '
feature: モバイルの実装
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: fd7d3900f9e5d1a6c3d13fd2452de8528f8fd248
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 1%

---

# モバイルアプリ用 Target に関する FAQ

モバイルアプリの[!DNL Target]に関するよくある質問のリストです。

## [!DNL Adobe Experience Platform Launch]を使用してSDKをデプロイする必要がありますか。それとも、[!DNL Launch]を使用せずにSDKをデプロイできますか。

SDKは、[Adobe Marketing Cloud Git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)で入手できます。 Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html)で[タグを使用しない場合は、独自の設定ファイルを管理し、アプリで管理する必要があります。

## 現在利用可能なSDKの種類

Adobe Experience Platform Mobile SDKは、現在、iOS、AndroidおよびReactをサポートしています。 詳しくは、[Adobe Experience Cloud Platform Mobile SDKガイド](https://aep-sdks.gitbook.io/docs/)を参照してください。

## 緯度と経度に関する検証の観点から、場所ベースの機能の頻度はどれくらいですか？

詳しくは、[AdobePlacesのドキュメント](https://placesdocs.com/places-services-by-adobe-documentation/)を参照してください。

## Adobe Experience Platform Mobile SDKを動作させるには、at.jsが必要ですか？

いいえ。モバイルSDKを使用するのにat.jsは必要ありません。 at.jsは、Webサイト用の[!DNL Target] JavaScriptライブラリです。 Adobe Experience Platform Mobile SDKは、モバイルアプリ用です。

## [!DNL Target]モバイルはAdobe[!DNL Target] Premium製品SKUの機能のみですか。

いいえ。[!DNL Adobe Target Standard]のお客様は、A/Bテストおよびエクスペリエンスターゲット設定(XT)アクティビティ用のMobile SDKを[!DNL Target Standard]モバイルアプリアドオンと共に使用できます。 RecommendationsまたはAIを利用した機能をモバイルアプリで使用する場合は、[Adobe Target Premium](/help/c-intro/intro.md#premium)ライセンスが必要です。

## Adobe Experience Manager(AEM)と[!DNL Target]モバイルアクティビティの間にモバイルアプリ統合はありますか？

これは我々のロードマップ上にありますが、まだタイムラインはありません。 現在、AEMからTargetにJSON [エクスペリエンスフラグメント](/help/c-experiences/c-manage-content/aem-experience-fragments.md)を共有でき、モバイルアプリアクティビティで使用できる可能性があります。
