---
title: スタートアップガイド
description: アクセスのリクエストから最初の機能フラグの作成まで、アプリケーションをフラグと統合するには、次の手順に従います。
hide: true
exl-id: 7aa09535-45fa-4ddf-9e3f-a23f8a8ee666
source-git-commit: 9a4e16418c93fa163d821409a0eecb251f2a9929
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 1%

---

# スタートアップガイド {#startup-guide}

フラグをアプリケーションに統合するには、次の手順に従います。

## 手順1：アクセスのリクエスト {#step-1-access}

フラグコンソールへのアクセスをリクエストして、チームに参加します。 詳細な手順については、[ アクセスを要求](../console/request-access.md)を参照してください。

## 手順2：アプリケーションのオンボーディング {#step-2-onboard}

アクセスを取得したら、フラグコンソールにログインし、アプリケーションがチームの下に表示されていることを確認します。 そうでない場合は、チーム管理者に追加を依頼してください。 [ アプリケーションのオンボーディング ](../applications/onboard-your-application.md)を参照してください。

オンボーディングの前に、次の手順に従います。

| 要件 | 詳細 |
|---|---|
| **アプリケーション ID** | Flags APIの呼び出し時に使用される一意のクライアント ID。 使用可能な場合は、アプリケーションの既存のクライアント IDを使用します。 |

## 手順3：環境ファイル IDを取得する {#step-3-credentials}

必要な環境ファイル IDは、統合パスによって異なります。

* **Webとモバイル（タグベース）:**&#x200B;公開されたタグプロパティから&#x200B;**環境ファイル ID**&#x200B;を使用します。 この方法については、手順4aを参照してください。

## ステップ 4:SDKを使用した統合 {#step-4-integrate}

お使いのアプリケーションタイプの統合ガイドに従ってください。 スタックに合ったパスを選択：

* **Web アプリとモバイルアプリ** – 統合ガイド セクションの[Android](../sdk-releases/android/android-extension-integration-guide.md)、[iOS](../sdk-releases/ios/ios-extension-integration-guide.md)、[Web](../sdk-releases/web/web-extension-integration-guide.md) ガイドを参照してください。

## 手順4a：データ収集の設定と設定の公開 {#step-4a-data-collection}

タグベースのアプローチ（webまたはモバイル）を使用して統合する場合は、SDKを初期化する前にタグプロパティを設定します。

1. [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)で、モバイルまたはweb プロパティを開きます。
1. **Edge Network**&#x200B;拡張機能をインストールし、次に&#x200B;**フラグ**&#x200B;拡張機能を（その順序で）インストールします。
1. **データストリーム**&#x200B;とエッジドメインを選択します（Customer Journey Analytics データセットを含める必要があります）。
1. 実稼動環境&#x200B;**の**&#x200B;開発→ ステージングを通じて設定→公開します。
1. **環境ファイル ID**&#x200B;を&#x200B;**環境** タブからコピーします。これを使用して、SDKを初期化します。

>[!IMPORTANT]
>
>**ステージング**&#x200B;環境では、環境ファイル IDの先頭に`staging/`を付けます。つまり、`staging/<environmentId>`を使用します。 **本番**&#x200B;で、環境ファイル IDを直接使用します。

## 手順5：最初の機能フラグを作成してテストする {#step-5-feature-flag}

統合が完了したら、コンソールに最初の機能フラグを作成してテストします。

* [最初の機能フラグを作成](../feature-flags/create-your-first-feature-flag.md)

## 詳細については、 {#see-also}

* [アプリにフラグを統合](integrating-in-your-app.md)
* [SDK](sdks.md)

<!-- -->
