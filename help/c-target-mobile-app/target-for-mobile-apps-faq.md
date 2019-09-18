---
description: モバイルアプリ用Adobe targetに関するよくある質問(FAQ)です。
keywords: モバイルアプリ；よくある質問；faq;targetモバイルアプリ
seo-description: モバイルアプリ用Adobe targetに関するよくある質問(FAQ)です。
seo-title: モバイルアプリ用Adobe targetに関するよくある質問(FAQ)
title: モバイルアプリ用Adobe Target FAQ
topic: 'Target '
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 43a00c7ade1f2e10a023ffdcb2e75cf2483e6907

---


# モバイルアプリのTarget FAQ

モバイルアプリに関するよくある質 [!DNL Target] 問の一覧です。

## SDKのデプロイに使 [!DNL Adobe Experience Platform Launch][!DNL Launch]用する必要がありますか。それとも、

SDKは、 [Adobe Marketing Cloud Gitで使用できます](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)。 「起動」を使用しない場合 [は](https://docs.adobe.com/content/help/en/launch/using/overview.html)、独自の設定ファイルを管理し、アプリで管理する必要があります。

## モバイルアプリ用のVisual Experience Composer(VEC)は、Adobe Experience Platform SDK v5のReact-Nativeサポートと共に使用できますか。

ネイティブモ [バイルアプリ用のVECは](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) 、現在、Reactネイティブアプリをサポートしていません。 フォームベースのExperience Composer [を使用する必要があります](/help/c-experiences/form-experience-composer.md)。

## Mobile SDKの統合により、新しいモバイル機能のロールアウトが可能になりますか。 新しいコードを導入せずに機能フラグをオン/オフにすることはできますか。

はい。モバイルSDKを使用して、機能を徐々に展開できます。

## より複雑なロジックを使用する場合、Mobile VECを使用する代わりに、アプリで直接開発する必要がありますか。 その場合は、どの開発言語を使用すればよいですか。

現在、VECは、画像、テキスト、色の変更など、一般的な使用例をサポートしています。 アプリのレイアウトのパーソナライズなど、より高度な使用例の場合は、コードにリクエスト/場所( [!DNL Target] mbox)を挿入し、 [Form-Based Experience Composerを使用してエクスペリエンスを設計し、トラフィックを割り当てる必要があります](/help/c-experiences/form-experience-composer.md) 。 モバイルSDKは、Java、Objective cおよびSwiftをサポートしています。 言語を選択するのは、チームの好みとリソースによって異なります。

## 今日はどのSDKをご利用いただけますか。

Adobe Experience Platform Mobile SDKは、現在、iOS、AndroidおよびReactをサポートしています。 詳しくは、 [Adobe Experience Cloud Platform Mobile SDKsガイドを参照してください](https://aep-sdks.gitbook.io/docs/)。

## 緯度と経度の検証に関して、位置ベースの機能の頻度はどのくらいか。

See the [Adobe Places documentation](https://placesdocs.com/places-services-by-adobe-documentation/) for more information.

## どのネイティブクラスがモバイルの「ビュー」をサポートしているか。 NSObject派生クラス（または任意のAndroidオブジェクト）、または単にNSViewControllerとアクティビティをサポートしているか。

詳しくは、Androidのドキュメントを参照して、ビューの宣 [言方法を手動で確認してください](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views)。

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
