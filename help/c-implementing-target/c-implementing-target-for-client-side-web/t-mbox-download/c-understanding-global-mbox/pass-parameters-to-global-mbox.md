---
keywords: グローバル mbox パラメーター;targetPageParams;クエリ文字列;配列;json;DTM;Dynamic Tag Management
description: targetPageParams関数を使用して、追加のターゲット設定またはコンテキスト情報をAdobe Targetのグローバルmboxに渡す方法について説明します。
title: グローバルmboxにパラメーターを渡す方法
feature: at.js
role: 開発者
translation-type: tm+mt
source-git-commit: a638da983bf39361be36a9cd68f3ef9f7eb39013
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 63%

---


# グローバル mbox にパラメーターを渡す

[!DNL Adobe Target]内のグローバルmboxにパラメーターを渡すには、JavaScript `targetPageParams`関数を使用します。 これは、追加のターゲット設定/コンテキスト情報を[!DNL Target]に渡す場合に必要です。

例えば、[!DNL Recommendations]アクティビティーでは、表示中の現在の製品またはカテゴリを表すパラメーターを使用します。

グローバルmboxがat.jsの一部として呼び出される場合でも、ページのコードに手動で組み込まれる場合でも、JavaScript関数を呼び出すコードは、ページ上のグローバルmboxの前に記述する必要があります。

>[!NOTE]
>
>グローバルmboxだけでなく、ページ上のすべてのmboxにパラメーターを追加する場合は、[targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md)関数を使用します。

次のいずれかの方法で、`targetPageParams()` 関数を使用して `target-global-mbox` にパラメーターを渡せます。

* 配列
* JSON オブジェクト
* アンパサンド区切りのリスト

これら 3 つの方法を使用して、パラメーターが正しく渡されていることを確認できます。また、[Adobe Experience Cloud デバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)を使用して、パラメーターの受け渡しを確認することもできます。

ページにグローバル mbox を追加する前に、JavaScript 関数を定義する必要があります。名前は `targetPageParams` とします。

## クエリ文字列

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
          return "p1=v1&p2=v2&p3=hello%20world";
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

## 配列

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

## JSON

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
* `profile.memberStatus`=ゴールド
* `profile.country.city`=San Francisco