---
title: SDK
description: FlagsのSDK アーキテクチャと、利用可能なAEP Web SDKおよびAEP Mobile SDK拡張機能について説明します。
badge: label="Beta" type="Informative"
hide: true
exl-id: 110a440d-b52a-4e1e-a94f-86f9741a223a
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 2%

---

# SDK {#sdks}

フラグは、機能フラグをアプリケーションに統合するためのSDKを提供します。 Flagsは、AEP Web SDKおよびAEP Mobile SDKを介してデプロイされます。

## SDK アーキテクチャ {#architecture}

すべてのフラグ SDKは、同じコアアーキテクチャを共有します。

* **Initialization** — SDKは起動時に設定され、Flags サービスに登録されます。
* **機能の取得** — SDKは機能フラグデータを取得し、フラグをローカルで評価します。
* **Caching** — SDKは機能フラグデータをキャッシュし、設定可能なポーリング間隔で更新します。
* **エラー処理** — サービスが利用できない場合、SDKは引き続きローカルキャッシュから機能フラグ評価を提供します。

## 利用可能なSDK {#available-sdks}

### AEP Web SDK {#web-sdk}

Web用のフラグ拡張機能は、Adobe Experience Platform Web SDKと統合されています。

>[!NOTE]
>
>Web SDKのサポートは近日提供開始予定です。 早期アクセスガイダンスについては、Adobe担当者にお問い合わせください。

### Android拡張機能 {#android-extension}

AndroidのFlags拡張機能は、Adobe Experience Platform Mobile SDKと統合されています。

設定手順については、[Android拡張機能の統合ガイド &#x200B;](../sdk-releases/android/android-extension-integration-guide.md)を参照してください。

### iOS拡張機能 {#ios-extension}

IOSのFlags拡張機能は、Adobe Experience Platform Mobile SDKと統合されています。

設定手順については、[iOS拡張機能の統合ガイド &#x200B;](../sdk-releases/ios/ios-extension-integration-guide.md)を参照してください。

## 詳細については、 {#see-also}

* [Android拡張機能の統合ガイド](../sdk-releases/android/android-extension-integration-guide.md)
* [iOS拡張機能の統合ガイド](../sdk-releases/ios/ios-extension-integration-guide.md)
* [web拡張機能の統合ガイド](../sdk-releases/web/web-extension-integration-guide.md)

<!-- -->
