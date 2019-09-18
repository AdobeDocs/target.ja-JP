---
description: Adobe Target のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。
keywords: オファー、プリフェッチ、iOS、android;sdk；モバイル；モバイルsdk
seo-description: Adobe Target のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。
seo-title: プリフェッチオファーコンテンツ
solution: 'Target '
title: プリフェッチオファーコンテンツ
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: ce8a890d0d662c0eec4d7fe254da371694811822

---


# プリフェッチオファーコンテンツ{#prefetch-offer-content}

[!DNL Target] プリフェッチ機能では、iOSおよびAndroidのモバイルSDKを使用して、サーバー応答をキャッシュすることによって、可能な限り多くのオファーコンテンツを取得します。

このプロセスにより、読み込み時間が短縮され、複数のネットワーク呼び出しを防ぎ [!DNL Target] 、モバイルアプリユーザーがmboxを訪問したことを通知できます。すべてのコンテンツはプリフェッチ呼び出し中に取得およびキャッシュされ、指定したmbox名に対してキャッシュされたコンテンツを含む、以降のすべての呼び出しに対して、キャッシュから取得されます。

iOSおよびAndroid Mobile SDKでprefetchメソッドを使用する場合は、次の点を考慮してください。

* プリフェッチコンテンツは、起動間で保持されません。プリフェッチコンテンツは、アプリケーションが稼働しているか `clearPrefetchCache()` 、メソッドが呼び出されるまでキャッシュされます。
* iOSおよびAndroidのモバイルSDKでのプリフェッチ機能は、自動ターゲット、自動配分、自動パーソナライゼーションの各アクティビティタイプではサポートされていません。

プリフェッチメソッド、パブリッククラス、コードサンプルなどについて詳しくは、以下のドキュメントを参照してください。

* **** iOS: [Mobile Services iOS SDKヘルプのiOS](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) 、プリ *フェッチオファーのコンテンツ*。
* **** Android: プリフ [ェッチオファーのコンテンツは](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/c-mob-target-prefetch-android.html) 、 *Mobile Services Android SDKヘルプのAndroidで参照できます*。
