---
keywords: targetPageParams;targetpageparams;pageParams;pageparams;page params;ページパラメーター;at.js;関数
description: Adobe [!DNL Target] リクエストコードの外部からグローバル mbox にパラメーターを付加する at.js JavaScript ライブラリ。
title: targetPageParams() 関数の使用方法を教えてください。
feature: at.js
role: Developer
exl-id: 0772b400-626c-45d8-a4b5-a12691978cf3
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 72%

---

# targetPageParams()

このメソッドにより、リクエストコードの外部からグローバル mbox にパラメーターを付加できます。

この関数は、同じパラメーターのセットを複数の mbox 呼び出しに含めるのに非常に便利です。この関数は、お客様によって定義される必要があります。グローバル mbox リクエストにのみ渡されるパラメーターの配列を返す必要があります。この関数は、at.js が読み込まれる前、または **[!UICONTROL 管理]** > **[!UICONTROL 実装]** > **[!UICONTROL 編集]** > **[!UICONTROL ライブラリヘッダー]**.

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
