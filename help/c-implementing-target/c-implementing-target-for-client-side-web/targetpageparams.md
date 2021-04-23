---
keywords: targetPageParams;targetpageparams;pageParams;pageparams;page params;ページパラメーター;at.js;関数
description: Adobe [!DNL Target] at.js JavaScriptライブラリのtargetPageParams()関数を使用して、リクエストコードの外部からグローバルmboxにパラメーターをアタッチします。
title: targetPageParams()関数の使用方法を教えてください。
feature: at.js
role: Developer
exl-id: 0772b400-626c-45d8-a4b5-a12691978cf3
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 72%

---

# targetPageParams()

このメソッドにより、リクエストコードの外部からグローバル mbox にパラメーターを付加できます。

この関数は、同じパラメーターのセットを複数の mbox 呼び出しに含めるのに非常に便利です。この関数は、お客様によって定義される必要があります。グローバル mbox リクエストにのみ渡されるパラメーターの配列を返す必要があります。この関数は、at.jsが読み込まれる前、または&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 実装]** > **[!UICONTROL 編集]** > **[!UICONTROL ライブラリヘッダー]**&#x200B;に定義できます。

次のいずれかの方法で、`targetPageParams()` 関数を使用して target-global-mbox にパラメーターを渡せます。

* アンパサンド区切りのリスト
* 配列
* JSON オブジェクト

## 例

アンパサンド区切りのリスト（値は URL エンコードされている必要がある）：

```javascript
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

配列（値を URL エンコードする必要はない）：

```javascript
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON（値を URL エンコードする必要はない）：

```javascript
targetPageParams = function() { 
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
