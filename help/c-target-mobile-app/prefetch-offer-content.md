---
description: Adobe Target のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。
keywords: オファー、プリフェッチ、iOS、android;;sdk;mobile;モバイルSDK
seo-description: Adobe Target のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。
seo-title: プリフェッチオファーコンテンツ
solution: 'Target '
title: プリフェッチオファーコンテンツ
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: 95bf4b2070cc2de235ac09ac164f0f9ec48dd6cd

---


# プリフェッチオファーコンテンツ{#prefetch-offer-content}

[!DNL Target] プリフェッチ機能では、iOSおよびAndroidのモバイルSDKを使用して、サーバー応答をキャッシュすることによって、可能な限り多くのオファーコンテンツを取得します。

このプロセスにより、読み込み時間が短縮され、複数のネットワーク呼び出しを防ぎ [!DNL Target] 、モバイルアプリユーザーがmboxを訪問したことを通知できます。すべてのコンテンツはプリフェッチ呼び出し中に取得およびキャッシュされ、このコンテンツは、指定したmbox名にキャッシュされたコンテンツを含むすべての後の呼び出しのキャッシュから取得されます。

iOSおよびAndroidのモバイルSDKを使用してプリフェッチメソッドで使用する場合は、次の点に注意してください。

* プリフェッチコンテンツは、起動間で保持されません。プリフェッチコンテンツは、アプリケーションが稼働しているか `clearPrefetchCache()` 、メソッドが呼び出されるまでキャッシュされます。
* iOSおよびAndroidのモバイルSDKのプリフェッチ機能は、自動ターゲット、自動割り当ておよび自動パーソナライゼーションアクティビティタイプではサポートされていません。

プリフェッチメソッド、パブリッククラス、コードサンプルなどについて詳しくは、以下のドキュメントを参照してください。

* **iOS：**『[Experience Cloud ソリューション用 iOS SDK 4.x](https://marketing.adobe.com/resources/help/en_US/mobile/ios/c_mob_target-prefetch_ios.html)』ガイドの *iOS のプリフェッチオファーコンテンツ*。
* **Android：**『[Experience Cloud ソリューション用 Android SDK 4.x](https://marketing.adobe.com/resources/help/en_US/mobile/android/c_mob_target-prefetch_android.html)』ガイドの *Android のプリフェッチオファーコンテンツ*。
