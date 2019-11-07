---
keywords: オファー；プリフェッチ；iOS;android;sdk；モバイル；モバイルsdk
description: Adobe Target のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。
title: プリフェッチオファーコンテンツ
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# プリフェッチオファーコンテンツ{#prefetch-offer-content}

[!DNL Target] のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。

このプロセスにより、読み込み時間が短縮され、複数のネットワーク呼び出しを防ぎ [!DNL Target] 、モバイルアプリユーザーがmboxを訪問したことを通知できます。プリフェッチ呼び出し中にすべてのコンテンツが取得され、キャッシュされます。このコンテンツは、指定された mbox 名のキャッシュされたコンテンツを含む今後のすべての呼び出しに対してキャッシュから取得されます。

プリフェッチメソッドを iOS および Android Mobile SDK で使用する際には、次を考慮します。

* プリフェッチコンテンツは、起動間で保持されません。プリフェッチコンテンツは、アプリケーションが稼働しているか `clearPrefetchCache()` 、メソッドが呼び出されるまでキャッシュされます。
* iOS および Android Mobile SDK のプリフェッチ機能は、自動ターゲット、自動割り当ておよび自動パーソナライゼーションアクティビティタイプではサポートされていません。

プリフェッチメソッド、パブリッククラス、コードサンプルなどについて詳しくは、以下のドキュメントを参照してください。

* **** iOS: [Mobile Services iOS SDKヘルプのiOS](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) 、プリ *フェッチオファーのコンテンツ*。
* **** Android: プリフ [ェッチオファーのコンテンツは](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/c-mob-target-prefetch-android.html) 、 *Mobile Services Android SDKヘルプのAndroidで参照できます*。
