---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;page params;ページパラメーター;at.js;関数
description: Adobeの targetPageParamsAll() 関数の使用 [!DNL Target] at.js JavaScript ライブラリを使用して、リクエストコードの外部からすべての mbox にパラメーターを付加できます。
title: targetPageParamsAll() 関数の使用方法を教えてください。
feature: at.js
role: Developer
exl-id: 58fbb62e-30da-486f-b771-6452ad5e27e6
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 72%

---

# targetPageParamsAll()

このメソッドにより、リクエストコードの外部からすべての mbox にパラメーターを付加できます。

これは、同じパラメーターのセットを複数の mbox 呼び出しに含めるのに非常に便利です。この関数は、お客様によって定義される必要があります。ページでリクエストするすべての mbox に渡されるパラメーターの配列を返す必要があります。この関数は、at.js が読み込まれる前、または **[!UICONTROL 管理]** > **[!UICONTROL 実装]** > **[!UICONTROL 編集]** > **[!UICONTROL コード設定]** > **[!UICONTROL ライブラリヘッダー]**.

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
