---
description: この節では、Target モバイルアプリアクティビティ情報を Adobe Analytics に送信して、ポストアドホックセグメント化する方法について説明します。
seo-description: この節では、Target モバイルアプリアクティビティ情報を Adobe Analytics に送信して、ポストアドホックセグメント化する方法について説明します。
seo-title: アクティビティ情報の Adobe Analytics への送信
title: アクティビティ情報の Adobe Analytics への送信
uuid: 2ca1ebfe-5008-4a73-a032-1ad81f062925
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# アクティビティ情報の Adobe Analytics への送信{#send-activity-information-to-adobe-analytics}

この節では、Target モバイルアプリアクティビティ情報を Adobe Analytics に送信して、ポストアドホックセグメント化する方法について説明します。

**前提条件**

* 統合には、モバイルSDKを使用してAnalyticsとTargetが実装されている必要があります。
* レポートスイートがTargetからアクティビティ情報を受け取ることが有効になっていることを確認します。

   これは通常、TargetクライアントコードをAnalyticsレポートスイートに追加することでおこなわれます。これは、WebアクティビティにSiteCatalyst- Test&amp;Target統合を使用している場合に、既に有効になっている可能性があります。この手順については、Adobe ClientCareにお問い合わせください。

1. アクティビティ情報を取得します。

   エクスペリエンスコンテンツに次のような文字列を含めると、Analyticsに送信できるキャンペーン情報がTargetによって返されます。

   ```
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   エクスペリエンスjsonコード内のテキストを次の例のように置換します。

   ```
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   この例では、変数&#39; `tntVal`&#39;を持つノードが追加され、アクティビティ情報が取得されます。適切なタイトルとメッセージを使用して、他のエクスペリエンスに類似したコードを追加します。

   この文字列は、Targetからの応答に数値（115110: 0: 0など）を配信します。これは、アクティビティID、エクスペリエンスIDおよびトラフィックタイプを示します。Targetからのスワイデント応答は次のとおりです。

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. JSONオブジェクトを解析します。

   コールバックでTargetから返された応答を解析します。NSSonsSerializationを使用してこの応答を解析し、dictまたは配列に格納できます。

   Refer to the [NSJSONSerialization documentation](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) for more information.
1. データをAnalyticsに送信します。

   解析呼び出しのコンテキストデータオブジェクトに、解析されたアクティビティ情報（上記の応答 `tntVal` など）を追加します。コンテキストデータを含むAnalytics呼び出しは、即座に実行することも、次のAnalytics呼び出しが実行されるまで待機することもできます。

   例えば、`targetLoadRequest` 呼び出しのコールバックでこの呼び出しを実行できます。

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt`は、モバイルSDKの予約イベントキーです。Analyticsで `tntVal` の変数の分類は、Web上のと同様にモバイルSDKでも機能します(JavaScript)。Analyticsで情報が処理されると、Analyticsインターフェイスにアクティビティ名とエクスペリエンス名が表示されます。

