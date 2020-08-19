---
keywords: global mbox parameters;targetPageParams;query string;array;json;dtm;dynamic tag management
description: グローバル mbox にパラメーターを渡すには、JavaScript の targetPageParams 関数を使用します。Target に追加のターゲット設定／コンテキスト情報を渡す場合は、常にこの関数が使用されます。
title: グローバル mbox にパラメーターを渡す
feature: null
subtopic: Getting Started
topic: Standard
uuid: 058f0ef5-037a-4daf-8a1e-a9c7ecc7f0bd
translation-type: tm+mt
source-git-commit: 8bf89f30fec597b983067ec4604dba09a9ec2832
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 73%

---


# グローバル mbox にパラメーターを渡す{#pass-parameters-to-a-global-mbox}

グローバル mbox にパラメーターを渡すには、JavaScript の `targetPageParams` 関数を使用します。This is needed in any scenario where additional targeting/context information is to be passed into [!DNL Target].

For example, in a [!DNL Recommendations] activity, use the parameters to represent the current product or category that is being viewed.

グローバルmboxがat.jsの一部として呼び出される場合でも、ページのコードに手動で組み込まれる場合でも、JavaScript関数を呼び出すコードは、ページ上のグローバルmboxの前に記述する必要があります。

>[!NOTE]
>
>If you want to add parameters to all mboxes on the page, not just to the global mbox, use the [targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) function.

次のいずれかの方法で、`targetPageParams()` 関数を使用して `target-global-mbox` にパラメーターを渡せます。

* 配列
* JSON オブジェクト
* アンパサンド区切りのリスト

これら 3 つの方法を使用して、パラメーターが正しく渡されていることを確認できます。また、[Adobe Experience Cloud デバッガー](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)を使用して、パラメーターの受け渡しを確認することもできます。

ページにグローバル mbox を追加する前に、JavaScript 関数を定義する必要があります。名前は `targetPageParams` とします。

**クエリ文字列**

```
p1=v1&p2=v2&p3=hello%20world
```

* 名前: `targetPageParams`
* 戻り値：パラメーターの値が URL エンコードされた、「&amp;」文字で区切られた一連のパラメーター

   例：

   この例では、p3 の値は `hello world` です。この値は、URL エンコードされています。

次に、ページのコードの例を示します。

```
<html> 
  <head> 
    <title>Title here..</title> 
    <script type="text/javascript"> 
        function targetPageParams() { 
           
<b>return "p1=v1&p2=v2&p3=hello%20world"</b>; 
        } 
    </script> 
    <script src="mbox.js" type="text/javascript"></script> 
  </head> 
  <body>Body here... 
  </body> 
</html>
```

この例では、次のデータを mbox エッジに送ります。

* p1=v1
* p2=v2
* p3=hello world

**配列**

```
<!--window.-->targetPageParams = function() { 
  return ["a=1", "b=2", "c=hello world"]; 
}; 
```

値を URL エンコードする必要はありません。例えば、値にスペースが含まれている場合でも、スペースをエンコードする必要はありません。

この例では、次のデータを mbox エッジに送ります。

* a=1
* b=2
* c=hello world

**JSON**

JSON は、パラメーターを渡すための強力な機能を備えています。Target は、JSON オブジェクトのキーを使用して、複雑な構造をシンプルなパラメーターへとフラット化します。

```
<!--window.-->targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
                  "memberStatus": Gold, 
                  "country": { 
                                "city": "San Francisco" 
                            } 
              } 
  }; 
}; 
```

値を URL エンコードする必要はありません。例えば、「San Francisco」という値でも、スペースをエンコードする必要はありません。普通にスペースを挿入するだけです。

この例では、次のデータを mbox エッジに送ります。

* a=1
* b=2
* `profile.age`=26
* `profile.country.city`=San Francisco