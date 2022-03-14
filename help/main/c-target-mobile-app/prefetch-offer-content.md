---
keywords: オファー；プリフェッチ；iOS;android;sdk；モバイル；モバイル sdk
description: Adobe [!DNL Target] iOSおよび Android Mobile SDK のプリフェッチ機能を使用して、サーバーからの応答をキャッシュすることで、可能な限り少ない回数でオファーコンテンツを取得できます。
title: モバイルアプリ用のオファーコンテンツをプリフェッチできますか？
feature: Implement Mobile
role: Developer
exl-id: 83a96a41-cf27-4ed8-8169-277f3ef3f249
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 47%

---

# プリフェッチオファーコンテンツ

[!DNL Target] のプリフェッチ機能では、iOS および Android Mobile SDK を使用してサーバーからの応答をキャッシュすることにより、可能な限り少ない回数でオファーコンテンツを取得できます。

このプロセスにより、読み込み時間が短縮され、複数のネットワーク呼び出しを防ぎ [!DNL Target] 、モバイルアプリユーザーがmboxを訪問したことを通知できます。プリフェッチ呼び出し中にすべてのコンテンツが取得され、キャッシュされます。このコンテンツは、指定された mbox 名のキャッシュされたコンテンツを含む今後のすべての呼び出しに対してキャッシュから取得されます。

iOSおよび Android Mobile SDK でプリフェッチメソッドを使用する際は、次の制限を考慮してください。

* プリフェッチコンテンツは、起動間で保持されません。プリフェッチコンテンツは、アプリケーションが稼働しているか `clearPrefetchCache()` 、メソッドが呼び出されるまでキャッシュされます。
* プリフェッチ機能は、次の用にサポートされていません： [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] トラフィック配分方法、 [!UICONTROL Automated Personalization] または [!UICONTROL Recommendations] アクティビティのタイプ、または [A/B または XT アクティビティ内の recommendations オファー](/help/main/c-recommendations/recommendations-as-an-offer.md).

プリフェッチメソッド、パブリッククラス、コードサンプルなどについて詳しくは、以下のドキュメントを参照してください。

* **iOS:**  [iOSでのオファーコンテンツのプリフェッチ](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) 内 *Mobile Services iOS SDK ヘルプ*.
* **Android:**  [Android でのオファーコンテンツのプリフェッチ](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) 内 *Mobile Services Android SDK ヘルプ*.
