---
keywords: オファー；プリフェッチ；iOS;android;sdk；モバイル；モバイル sdk
description: Adobe [!DNL Target] iOSおよび Android Mobile SDK のプリフェッチ機能を使用して、サーバーからの応答をキャッシュすることで、可能な限り少ない回数でオファーコンテンツを取得できます。
title: モバイルアプリ用のオファーコンテンツをプリフェッチできますか？
feature: Implement Mobile
role: Developer
exl-id: 83a96a41-cf27-4ed8-8169-277f3ef3f249
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 54%

---

# プリフェッチオファーコンテンツ

[!DNL Target] のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。

このプロセスにより、読み込み時間が短縮され、複数のネットワーク呼び出しを防ぎ [!DNL Target] 、モバイルアプリユーザーがmboxを訪問したことを通知できます。プリフェッチ呼び出し中にすべてのコンテンツが取得され、キャッシュされます。このコンテンツは、指定された mbox 名のキャッシュされたコンテンツを含む今後のすべての呼び出しに対してキャッシュから取得されます。

iOSおよび Android Mobile SDK でプリフェッチメソッドを使用する際は、次の制限を考慮してください。

* プリフェッチコンテンツは、起動間で保持されません。プリフェッチコンテンツは、アプリケーションが稼働しているか `clearPrefetchCache()` 、メソッドが呼び出されるまでキャッシュされます。

プリフェッチメソッド、パブリッククラス、コードサンプルなどについて詳しくは、以下のドキュメントを参照してください。

* **iOS:**  [iOSでのオファーコンテンツのプリフェッチ](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) 内 *Mobile Services iOS SDK ヘルプ*.
* **Android:**  [Android でのオファーコンテンツのプリフェッチ](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) 内 *Mobile Services Android SDK ヘルプ*.
