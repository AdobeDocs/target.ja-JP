---
keywords: offer;prefetch;iOS;android;sdk;mobile;mobile sdk
description: Adobe Target のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。
title: プリフェッチオファーコンテンツ
feature: null
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 62%

---


# プリフェッチオファーコンテンツ{#prefetch-offer-content}

[!DNL Target] のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。

このプロセスにより、読み込み時間が短縮され、複数のネットワーク呼び出しを防ぎ [!DNL Target] 、モバイルアプリユーザーがmboxを訪問したことを通知できます。プリフェッチ呼び出し中にすべてのコンテンツが取得され、キャッシュされます。このコンテンツは、指定された mbox 名のキャッシュされたコンテンツを含む今後のすべての呼び出しに対してキャッシュから取得されます。

iOSおよびAndroid Mobile SDKでプリフェッチメソッドを使用する場合は、次の制限事項を考慮してください。

* プリフェッチコンテンツは、起動間で保持されません。プリフェッチコンテンツは、アプリケーションが稼働しているか `clearPrefetchCache()` 、メソッドが呼び出されるまでキャッシュされます。
* プリフェッチ機能は、 [!UICONTROL 自動配分] と自動ターゲット [!UICONTROL ・トラフィック割当て方法(] Automated Personalization・ [!UICONTROL Recommendations・アクティビティ・タイプ、または][](/help/c-recommendations/recommendations-as-an-offer.md)・レコメンデーション・オファー・タイプ(A/Bアクティビティ・・タイプ)ではサポートされません。

プリフェッチメソッド、パブリッククラス、コードサンプルなどについて詳しくは、以下のドキュメントを参照してください。

* **iOS:** [Mobile Services iOS SDKヘルプのiOS](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html)*、プリフェッチオファーのコンテンツ*。
* **Android:** [Mobile Services Android SDKヘルプのAndroid](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/c-mob-target-prefetch-android.html) ( *Mobile Services Android SDKヘルプ*)のオファーコンテンツをプリフェッチします。
