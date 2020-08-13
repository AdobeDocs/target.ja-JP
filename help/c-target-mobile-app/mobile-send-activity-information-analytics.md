---
keywords: mobile;tntVal;analytics;adobe analytics;integration;sdk;mobile sdk;
description: ここでは、Adobe Targetのモバイルアプリアクティビティ情報をAdobe Analyticsに送信してポストアホックセグメントを作成する方法について説明します。
title: Adobe Targetアクティビティ情報をAdobe Analyticsに送る
feature: mobile implementation
uuid: 2ca1ebfe-5008-4a73-a032-1ad81f062925
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 25%

---


# アクティビティ情報の Adobe Analytics への送信{#send-activity-information-to-adobe-analytics}

This section describes how to send [!DNL Target] mobile app activity information to Adobe [!DNL Analytics] for post hoc segmentation.

**前提条件**

* This integration requires that [!DNL Analytics] and [!DNL Target] are implemented using the mobile SDK.
* Ensure that your report suite is enabled to receive activity information from [!DNL Target].

   This is usually done by adding the [!DNL Target] client code to the [!DNL Analytics] report suite. これは、WebアクティビティにSiteCatalyst- Test&amp;Target統合を使用している場合に、既に有効になっている可能性があります。この手順については、Adobe ClientCareにお問い合わせください。

1. アクティビティ情報を取得します。

   If you include a string like the following in your experience content, [!DNL Target] returns the activity information that you can send to [!DNL Analytics]:

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

   In this example, a node with the variable `tntVal` is added to obtain the activity information. 適切なタイトルとメッセージを使用して、他のエクスペリエンスに類似したコードを追加します。

   This string delivers a number (such as 115110:0:0) in the response from [!DNL Target]. これは、アクティビティID、エクスペリエンスID、トラフィックタイプを示します。 The following is a sample response from [!DNL Target]:

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. JSONオブジェクトを解析します。

   Parse the response that came back from [!DNL Target] in the callback. You can use `NSJSONSerialization` to parse this response and store it in a dictionary or an array.

   詳細は、 [NSJSONSerializationのドキュメント](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) を参照してください。

1. Send the data to [!DNL Analytics].

   Add the parsed activity information (such as `tntVal` in the above response) to your context data object in an [!DNL Analytics] call. This [!DNL Analytics] call containing the context data can be fired immediately or it can wait until the next [!DNL Analytics] call is fired.

   例えば、`targetLoadRequest` 呼び出しのコールバックでこの呼び出しを実行できます。

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt`は、モバイル SDK の予約イベントキーです。The post-classification of the `tntVal` variable in [!DNL Analytics] works in the same way in the mobile SDK as it does on the web (JavaScript). After the information is processed in [!DNL Analytics], you should see activity and experience names in the [!DNL Analytics] interface.

