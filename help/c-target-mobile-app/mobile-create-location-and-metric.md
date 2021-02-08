---
keywords: モバイルアプリ;　モバイルアプリの場所;　targetモバイルアプリ;　モバイルターゲット場所;　モバイルアプリ成功指標
description: Adobe Targetを使用してアプリをパーソナライズし、最適化できるように、iOSアプリで場所と成功指標を作成する方法を学ぶための表示サンプルコードです。
title: iOSアプリでターゲットの場所と成功指標を作成する方法を教えてください。
feature: Implement Mobile
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 83%

---


# iOS - Target の位置と成功指標の作成{#ios-create-a-target-location-and-success-metric}

モバイルアプリで Target を使用するには、場所と成功指標を作成します。

この節では、アプリのテンプレートとして使用できるサンプルコードを紹介します。この節のサンプルには、iOS 用のコードがあります。Android でも同じパターンを使用します。Android 専用の構文は [](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/target-main.html)Experience Cloud 用 Android SDK 4.xソリューションガイドで紹介しています。

>[!NOTE]
>
>使用可能なすべてのターゲットメソッドのリストについては、[モバイルドキュメント](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-target-methods.html)を参照してください。

アプリで Target 位置を作成してリクエストをおこなうためのメソッドには、主に次の 2 種類があります。

* `targetCreateRequestWithName`
* `targetLoadRequest`

1. Target 位置を作成します。

   リクエストを作成するためのサンプル呼び出しを以下に示します。

   ```
   // make your request 
   ADBTargetLocationRequest *myRequest = [ADBMobile targetCreateRequestWithName:@"heroBanner" 
                                                    defaultContent:@"default.png" 
                                                    parameters:nil];
   ```

   | パラメーター | 説明 |
   |---|---|
   | `ADBTargetLocationRequest *myRequest` | `myRequest` をアプリの `targetLocation` の名前に置き換えます。 |
   | `targetCreateRequestWithName:@"heroBanner"` | `heroBanner` を Target の `targetLocation` の名前に置き換えます。これは mbox 名と同じです。このヒーローバナーは Target インターフェイスに表示されます。 |
   | `defaultContent:@"default.png"` | 「`default.png`」を Target が応答しない場合にアプリが使用する値に置き換えます。 |
   | `parameters:nil` | プロファイルまたは mbox パラメーターを指定します。詳しくは「カスタムデータの引き渡し」を参照してください。 |

   リクエストを読み込むサンプルコードを以下に示します。

   ```
   // load your request 
   [ADBMobile targetLoadRequest:myRequest callback:^(NSString *content) { 
                                        // do something with content 
                                        heroImage.image = [UIImage imageNamed:content]; 
   }];
   ```

   | パラメーター | 説明 |
   |---|---|
   | `targetLoadRequest:myRequest` | `myRequest` をアプリの `targetLocation` の名前に置き換えます。 |
   | `NSString *content` | 「content」を Adobe から返される実際のコンテンツに置き換えます。文字列は XML、JSON、プレーン文字列のいずれかにできます。コードのこの部分を使用して、変数の定義、画像パスの設定、コントローラーフローやトランザクションポイントの表示などの任意の作業ができます。Target は UI で入力されたコンテンツを完全に同じ形式で返します。 |
   | `heroImage.image = [UIImage imageNamed:content];` | 例えば、コンテンツを取得して、ヒーローイメージのパスを設定します。 |

1. 成功指標を作成します。

   `targetCreateOrderConfirmRequestWithName` メソッドを使用して、アプリのコンバージョンや成功指標を追跡することができます。

   ```
   ADBTargetLocationRequest *req = [ADBMobile targetCreateOrderConfirmRequestWithName: "orderConfirm" 
                                              orderId: orderId 
                                              orderTotal: @"39.95" 
                                              productPurchasedId: _galleryItem.title 
                                              parameters: nil]; 
   [ADBMobile targetLoadRequest: req callback: nil];
   ```

   | パラメーター | 説明 |
   |---|---|
   | `orderId` | 一意の注文 ID を表す動的変数に置き換えます。 |
   | `@"39.95"` | 一意の注文合計額を表す動的変数に置き換えます。 |
   | `_galleryItem.title` | 購入商品のコンマ区切りのリストを表す動的変数に置き換えます。 |
   | `parameters: nil` | 追加パラメーターのオプションの辞書。 |

1. アプリを構築します。

   ステップ結果ターゲット場所の作成と成功指標のタグ付けが完了したら、A/Bテストを作成します。このアクティビティはフォームベースの Experience Composer を使用して作成できます。
