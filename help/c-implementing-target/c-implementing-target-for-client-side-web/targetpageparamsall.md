---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;page params;ページパラメーター;at.js;関数
description: Adobe Target at.js JavaScript ライブラリの targetPageParamsAll() 関数について説明します。
title: Adobe Target at.js JavaScript ライブラリの targetPageParamsAll() 関数について説明します。
subtopic: 導入
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# targetPageParamsAll()

このメソッドにより、リクエストコードの外部からすべての mbox にパラメーターを付加できます。

これは、同じパラメーターのセットを複数の mbox 呼び出しに含めるのに非常に便利です。この関数は、お客様によって定義される必要があります。ページでリクエストするすべての mbox に渡されるパラメーターの配列を返す必要があります。この関数は、at.js が読み込まれる前、または&#x200B;**[!UICONTROL セットアップ]**／**[!UICONTROL 実装]**／**[!UICONTROL at.js 設定]**／**[!UICONTROL コード設定]**／**[!UICONTROL ライブラリヘッダー]**&#x200B;で定義できます。

次のいずれかの方法で、targetPageParamsAll() 関数を使用して target-global-mbox にパラメーターを渡すことができます。

* アンパサンド区切りのリスト
* 配列
* JSON オブジェクト

## 例

アンパサンド区切りのリスト（値は URL エンコードされている必要がある）：

```
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

配列（値を URL エンコードする必要はない）：

```
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON（値を URL エンコードする必要はない）：

```
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
