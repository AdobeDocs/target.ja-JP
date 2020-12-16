---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;page params;page parameters;at.js;functions;function
description: Adobe Target at.js JavaScript ライブラリの targetPageParamsAll() 関数について説明します。
title: targetPageParamsAll()
feature: client-side
translation-type: tm+mt
source-git-commit: a841c492e5d9e4bfedb20133ba32e37daf738c57
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 87%

---


# targetPageParamsAll()

このメソッドにより、リクエストコードの外部からすべての mbox にパラメーターを付加できます。

これは、同じパラメーターのセットを複数の mbox 呼び出しに含めるのに非常に便利です。この関数は、お客様によって定義される必要があります。ページでリクエストするすべての mbox に渡されるパラメーターの配列を返す必要があります。この関数は、at.jsが読み込まれる前、または&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 実装]** > **[!UICONTROL 編集]** > **[!UICONTROL コード設定]** > **[!UICONTROL ライブラリヘッダー]**&#x200B;に定義できます。

次のいずれかの方法で、targetPageParamsAll() 関数を使用して target-global-mbox にパラメーターを渡すことができます。

* アンパサンド区切りのリスト
* 配列
* JSON オブジェクト

## 例

アンパサンド区切りのリスト（値は URL エンコードされている必要がある）：

```javascript
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

配列（値を URL エンコードする必要はない）：

```javascript
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON（値を URL エンコードする必要はない）：

```javascript
targetPageParamsAll = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
        "age": 26, 
        "country": { 
          "city": "San Francisco" 
        } 
      } 
  }; 
};
```
