---
keywords: オファー；プリフェッチ；iOS;android;sdk；モバイル；モバイルsdk
description: iOSおよびAndroid Mobile SDKのAdobe Targetプリフェッチ機能を使用すると、サーバーレスポンスをキャッシュして、オファーコンテンツをできるだけ少なく取得できます。
title: モバイルアプリ用のオファーコンテンツをプリフェッチできますか？
feature: Implement Mobile
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 47%

---


# プリフェッチオファーコンテンツ{#prefetch-offer-content}

[!DNL Target] のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。

このプロセスにより、読み込み時間が短縮され、複数のネットワーク呼び出しを防ぎ [!DNL Target] 、モバイルアプリユーザーがmboxを訪問したことを通知できます。プリフェッチ呼び出し中にすべてのコンテンツが取得され、キャッシュされます。このコンテンツは、指定された mbox 名のキャッシュされたコンテンツを含む今後のすべての呼び出しに対してキャッシュから取得されます。

iOSおよびAndroid Mobile SDKでプリフェッチメソッドを使用する場合は、次の制限事項を考慮してください。

* プリフェッチコンテンツは、起動間で保持されません。プリフェッチコンテンツは、アプリケーションが稼働しているか `clearPrefetchCache()` 、メソッドが呼び出されるまでキャッシュされます。
* プリフェッチ機能は、[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット]のトラフィック割り当て、[!UICONTROL Automated Personalization]や[!UICONTROL Recommendations]のアクティビティタイプ、またはA/BやXTアクティビティ](/help/c-recommendations/recommendations-as-an-offer.md)内の[recommendationsオファーに対してはサポートされません。

プリフェッチメソッド、パブリッククラス、コードサンプルなどについて詳しくは、以下のドキュメントを参照してください。

* **iOS:**  [Mobile Services iOS SDKヘルプのiOSの](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) オファーコンテンツを *プリフェッチ*。
* **Android:**  [Mobile Services Android SDKヘルプのAndroidでの](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) プリフェッチオファーのコンテンツ **。
