---
description: 'at. jsのtargetPageParamsAll（）関数について取り上げます。 '
keywords: adobe.target.notification;要素;セレクター;通知;拡張子
seo-description: Adobe Target at. js JavaScriptライブラリのtargetPageParamsAll（）関数について取り上げます。
seo-title: Adobe Target at. js JavaScriptライブラリのtargetPageParamsAll（）関数について取り上げます。
solution: 'Target '
subtopic: 導入
title: targetPageParamsAll()
topic: Standard
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# targetPageParamsAll()

このメソッドにより、リクエストコードの外部からすべての mbox にパラメーターを付加できます。

これは、同じパラメーターのセットを複数の mbox 呼び出しに含めるのに非常に便利です。この関数は、お客様によって定義される必要があります。ページでリクエストするすべての mbox に渡されるパラメーターの配列を返す必要があります。この関数は、at.js が読み込まれる前、または**[!UICONTROL セットアップ]**／**[!UICONTROL 実装]**／**[!UICONTROL at.js 設定]**／**[!UICONTROL コード設定]**／**[!UICONTROL ライブラリヘッダー]**で定義できます。

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
