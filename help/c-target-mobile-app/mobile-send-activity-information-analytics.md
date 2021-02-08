---
keywords: モバイル；tntVal;analytics;adobe analytics；統合；sdk；モバイルsdk;
description: Adobe Targetモバイルアプリのアクティビティ情報を、アドホック後のセグメント用にAdobe Analyticsに送信する方法について説明します。
title: モバイルアプリのアクティビティ情報をAnalyticsに送信できますか。
feature: Implement Mobile
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 24%

---


# アクティビティ情報の Adobe Analytics への送信{#send-activity-information-to-adobe-analytics}

この節では、ポストホックセグメント化のために[!DNL Target]モバイルアプリのアクティビティ情報をAdobe[!DNL Analytics]に送信する方法について説明します。

**前提条件**

* この統合には、モバイルSDKを使用して[!DNL Analytics]と[!DNL Target]を実装する必要があります。
* [!DNL Target]からのアクティビティ情報の受信がレポートスイートで有効になっていることを確認します。

   これは通常、[!DNL Target]クライアントコードを[!DNL Analytics]レポートスイートに追加することで行います。 これは、WebアクティビティにSiteCatalyst- Test&amp;Target統合を使用している場合に、既に有効になっている可能性があります。この手順については、Adobe ClientCareにお問い合わせください。

1. アクティビティ情報を取得します。

   エクスペリエンスコンテンツに次のような文字列を含めると、[!DNL Target]は[!DNL Analytics]に送信できるアクティビティ情報を返します。

   ```javascript
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   エクスペリエンスjsonコード内のテキストを次の例のように置換します。

   ```javascript
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   この例では、アクティビティ情報を取得するために、変数`tntVal`を持つノードが追加されます。 適切なタイトルとメッセージを使用して、他のエクスペリエンスに類似したコードを追加します。

   この文字列は、[!DNL Target]からの応答に数値（115110:0:0など）を配信します。 これは、アクティビティID、エクスペリエンスID、トラフィックタイプを示します。 次に、[!DNL Target]からの応答例を示します。

   ```javascript
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. JSONオブジェクトを解析します。

   コールバックで[!DNL Target]から返された応答を解析します。 `NSJSONSerialization`を使ってこの応答を解析し、辞書や配列に格納することができます。

   詳細は、[NSJSONSerializationのドキュメント](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error)を参照してください。

1. データを[!DNL Analytics]に送信します。

   解追加析されたアクティビティ情報（上記の応答の`tntVal`など）を、[!DNL Analytics]呼び出しのコンテキストデータオブジェクトに対して返します。 コンテキストデータを含むこの[!DNL Analytics]呼び出しは、すぐに呼び出すことも、次の[!DNL Analytics]呼び出しが呼び出されるまで待つこともできます。

   例えば、`targetLoadRequest` 呼び出しのコールバックでこの呼び出しを実行できます。

   ```javascript
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt`は、モバイル SDK の予約イベントキーです。[!DNL Analytics]内の`tntVal`変数の後分類は、モバイルSDKでもWeb上での動作と同じように機能します(JavaScript)。 情報を[!DNL Analytics]で処理した後は、[!DNL Analytics]インターフェイスにアクティビティ名とエクスペリエンス名が表示されます。

