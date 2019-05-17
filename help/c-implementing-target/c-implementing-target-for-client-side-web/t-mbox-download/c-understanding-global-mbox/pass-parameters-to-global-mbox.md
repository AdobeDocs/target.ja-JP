---
description: グローバル mbox にパラメーターを渡すには、JavaScript の targetPageParams 関数を使用します。Target に追加のターゲット設定／コンテキスト情報を渡す場合は、常にこの関数が使用されます。
keywords: グローバル mbox パラメーター;targetPageParams;クエリ文字列;配列;json;DTM;Dynamic Tag Management
seo-description: グローバル mbox にパラメーターを渡すには、JavaScript の targetPageParams 関数を使用します。Target に追加のターゲット設定／コンテキスト情報を渡す場合は、常にこの関数が使用されます。
seo-title: グローバル mbox にパラメーターを渡す
solution: 'Target '
subtopic: 導入
title: グローバル mbox にパラメーターを渡す
topic: Standard
uuid: 058f0ef5-037a-4daf-8a1e-a9c7ecc7f0bd
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# グローバル mbox にパラメーターを渡す{#pass-parameters-to-a-global-mbox}

グローバル mbox にパラメーターを渡すには、JavaScript の targetPageParams 関数を使用します。Target に追加のターゲット設定／コンテキスト情報を渡す場合は、常にこの関数が使用されます。

例えば、Recommendations アクティビティでは、表示されている現在の製品またはカテゴリを示すために、これらのパラメーターを使用します。

グローバル mbox が mbox.js の一部として呼び出される場合でも、ページのコードに手作業で組み込まれる場合でも、JavaScript 関数を呼び出すコードは、ページ上のグローバル mbox の前に記述する必要があります。

>[!NOTE]
>
>グローバル mbox だけでなく、ページのすべての mbox にパラメーターを追加する場合、[targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) 関数を使用します（at.js のみ）。

次のいずれかの方法で、`targetPageParams()` 関数を使用して `target-global-mbox` にパラメーターを渡せます。

* 配列
* JSON オブジェクト
* アンパサンド区切りのリスト

これら 3 つの方法を使用して、パラメーターが正しく渡されていることを確認できます。また、[Adobe Experience Cloud デバッガー](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html)を使用して、パラメーターの受け渡しを確認することもできます。

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