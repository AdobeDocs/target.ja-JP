---
description: Adobe Target のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。
keywords: オファー、プリフェッチ、iOS、android
seo-description: Adobe Target のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。
seo-title: プリフェッチオファーコンテンツ
solution: 'Target '
title: プリフェッチオファーコンテンツ
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# プリフェッチオファーコンテンツ{#prefetch-offer-content}

[!DNL Adobe Target] プリフェッチ機能では、iOSおよびAndroidのモバイルSDKを使用して、サーバー応答をキャッシュすることによって、可能な限り多くのオファーコンテンツを取得します。

このプロセスにより、読み込み時間が短縮され、複数のネットワーク呼び出しを防ぎ [!DNL Target] 、モバイルアプリユーザーがmboxを訪問したことを通知できます。プリフェッチ呼び出し中にすべてのコンテンツが取得され、キャッシュされます。このコンテンツは、指定された mbox 名のキャッシュされたコンテンツを含む今後のすべての呼び出しに対してキャッシュから取得されます。

プリフェッチコンテンツは、起動間で保持されません。プリフェッチコンテンツは、アプリケーションが稼働しているか `clearPrefetchCache()` 、メソッドが呼び出されるまでキャッシュされます。

プリフェッチメソッド、パブリッククラス、コードサンプルなどについて詳しくは、以下のドキュメントを参照してください。

* **iOS:**[iOS SDK4. x for Experience Cloud Solutions*ガイド](https://marketing.adobe.com/resources/help/en_US/mobile/ios/c_mob_target-prefetch_ios.html) のiOSのプリフェッチオファーコンテンツを参照してください。
* **Android：**『[Experience Cloud ソリューション用 Android SDK 4.x](https://marketing.adobe.com/resources/help/en_US/mobile/android/c_mob_target-prefetch_android.html)』ガイドの *Android のプリフェッチオファーコンテンツ*。