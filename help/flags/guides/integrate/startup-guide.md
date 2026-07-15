---
title: スタートアップガイド
description: アクセスのリクエストから最初の機能フラグの作成まで、アプリケーションをフラグと統合するには、次の手順に従います。
hide: true
exl-id: 7aa09535-45fa-4ddf-9e3f-a23f8a8ee666
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 1%

---

# スタートアップガイド {#startup-guide}

フラグをアプリケーションに統合するには、次の手順に従います。

## 手順1：アクセスのリクエスト {#step-1-access}

フラグコンソールへのアクセスをリクエストして、チームに参加します。 詳細な手順については、[&#x200B; アクセスを要求](../console/request-access.md)を参照してください。

## 手順2：アプリケーションのオンボーディング {#step-2-onboard}

アクセスを取得したら、フラグコンソールにログインし、アプリケーションがチームの下に表示されていることを確認します。 そうでない場合は、チーム管理者に追加を依頼してください。 [&#x200B; アプリケーションのオンボーディング &#x200B;](../applications/onboard-your-application.md)を参照してください。

オンボーディングの前に、次の手順に従います。

| 要件 | 詳細 |
|---|---|
| **アプリケーション ID** | Flags APIの呼び出し時に使用される一意のクライアント ID。 使用可能な場合は、アプリケーションの既存のクライアント IDを使用します。 |
| **サーバーサイドのクライアント** | サーバーサイドのSDKと統合する場合は、適切な権限を持つ管理者クライアント IDが必要です。 |
| **デスクトップクライアント** | クライアント IDの代わりに、製品コードと製品バージョンを使用できます。 |

## 手順3：資格情報の取得 {#step-3-credentials}

必要な資格情報は、統合パスによって異なります。

* **Webとモバイル（タグベース）:**&#x200B;公開されたタグプロパティから&#x200B;**環境ファイル ID**&#x200B;を使用します。 この方法については、手順4aを参照してください。
* **サーバーサイド SDK:** **サービストークン クライアント ID**&#x200B;をリクエストし、SDKからAPI呼び出しを行う前に、Flagsでサポートされているトークンを許可リストに加えるしてください。
* **デスクトップ：** クライアント IDの代わりに、製品コードと製品バージョンを使用できます。

## ステップ 4:SDKを使用した統合 {#step-4-integrate}

アプリケーションの種類に応じて[統合手順](integration-steps.md)に従います。 スタックに合ったパスを選択：

* **Web サービス** → Java SDKまたはNode.js SDK
* **Webおよびモバイルアプリ** → AEP Mobile SDK — [iOS](../sdk-releases/android/android-extension-integration-guide.md)および[Android](../sdk-releases/ios/ios-extension-integration-guide.md) ガイドを参照
* **デスクトップアプリ** → SDK（近日リリース予定）

## 手順4a：データ収集の設定と設定の公開 {#step-4a-data-collection}

タグベースのアプローチ（webまたはモバイル）を使用して統合する場合は、SDKを初期化する前にタグプロパティを設定します。

1. [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)で、モバイルまたはweb プロパティを開きます。
1. **Edge Network**&#x200B;拡張機能をインストールし、次に&#x200B;**Experience Rollout**&#x200B;拡張機能を（その順序で）インストールします。
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
* [統合ステップ](integration-steps.md)
* [SDK](sdks.md)

<!-- -->
