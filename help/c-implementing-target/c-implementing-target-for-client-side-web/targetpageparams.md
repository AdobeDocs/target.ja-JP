---
description: 'at. jsのtargetPageParams（）関数について取り上げます。 '
keywords: adobe.target.notification;要素;セレクター;通知;拡張子
seo-description: Adobe Target at. js JavaScriptライブラリのtargetPageParams（）関数に関する情報です。
seo-title: Adobe Target at. js JavaScriptライブラリのtargetPageParams（）関数に関する情報です。
solution: 'Target '
subtopic: 導入
title: targetPageParams()
topic: Standard
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# targetPageParams() {#reference_B235C9F6DA79449ABE3E23F914FEABAE}

このメソッドにより、リクエストコードの外部からグローバル mbox にパラメーターを付加できます。

この関数は、同じパラメーターのセットを複数の mbox 呼び出しに含めるのに非常に便利です。この関数は、お客様によって定義される必要があります。グローバル mbox リクエストにのみ渡されるパラメーターの配列を返す必要があります。この関数は、at.js が読み込まれる前、または**[!UICONTROL セットアップ]**／**[!UICONTROL 実装]**／**[!UICONTROL at.js 設定]**／**[!UICONTROL コード設定]**／**[!UICONTROL ライブラリヘッダー]**で定義できます。

次のいずれかの方法で、`targetPageParams()` 関数を使用して target-global-mbox にパラメーターを渡せます。

* アンパサンド区切りのリスト
* 配列
* JSON オブジェクト

## 例

アンパサンド区切りのリスト（値は URL エンコードされている必要がある）：

```
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

配列（値を URL エンコードする必要はない）：

```
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON（値を URL エンコードする必要はない）：

```
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
