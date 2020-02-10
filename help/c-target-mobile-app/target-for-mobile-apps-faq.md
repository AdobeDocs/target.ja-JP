---
keywords: mobile app;frequently asked questions;faq;target mobile app
description: モバイルアプリ用Adobe targetに関するよくある質問(FAQ)です。
title: モバイルアプリ用Adobe targetに関するよくある質問(FAQ)
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 4ce4cf754ec64ec54c72bcb0557f042a92f5a8e3

---


# モバイルアプリのTarget FAQ

モバイルアプリに関するよくある質 [!DNL Target] 問のリストです。

## SDKのデプロイに使 [!DNL Adobe Experience Platform Launch][!DNL Launch]用する必要がありますか。それとも、

SDKは、 [Adobe Marketing Cloud Gitで使用できます](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)。 「起動」を使用しない場合 [は](https://docs.adobe.com/content/help/en/launch/using/overview.html)、独自の設定ファイルを管理し、アプリで管理する必要があります。

## 今日はどのSDKをご利用いただけますか。

Adobe Experience Platform Mobile SDKは、現在、iOS、AndroidおよびReactをサポートしています。 詳しくは、 [Adobe Experience Cloud Platform Mobile SDKsガイドを参照してください](https://aep-sdks.gitbook.io/docs/)。

## 緯度と経度の検証に関して、位置ベースの機能の頻度はどのくらいか。

See the [Adobe Places documentation](https://placesdocs.com/places-services-by-adobe-documentation/) for more information.

## Adobe Experience Platform Mobile SDKを動作させるにはat.jsが必要ですか。

いいえ。モバイルSDKを使用する際にat.jsは必要ありません。 at.jsは、Webサイト用の [!DNL Target] JavaScriptライブラリです。 Adobe Experience Platform Mobile SDKはモバイルアプリ用です。

## Target mobileはAdobe Target Premium製品SKUのみの機能ですか。

Adobe Target Standardのお客様は、A/B Test and Experience Targeting(XT)アクティビティに対してのみMobile SDKを使用できます。 モバイルアプリでRecommendationsまたはAIを使用する機能を使用する場合は、 [Adobe Target Premiumのライセンスが必要です](/help/c-intro/intro.md#premium) 。

## モバイルアプリ用VECでAdobe Audience Manager(AAM)のオーディエンスを活用できますか。

はい。Adobe Experience Platform Mobile SDKは [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html)、 [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html)、 [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)、Target用に構築されています。 Audience Managerのオーディエンスが共有されま [!DNL Target]す。

## Adobe Experience Manager(AEM)とTargetのモバイルアクティビティの間にモバイルアプリは統合されていますか。

私たちのロードマップには書いてありますが、まだ時間がありません。 現在、JSONエクスペリエンスフラグメント [をAEMからTargetに共有できます](/help/c-experiences/c-manage-content/aem-experience-fragments.md) 。その後、モバイルアプリアクティビティで使用する可能性があります。

## VECを使用してさらに画像を追加できますか。または、既存の画像のみを変更できますか。

現在、変更できるのは既存の画像のみです。
