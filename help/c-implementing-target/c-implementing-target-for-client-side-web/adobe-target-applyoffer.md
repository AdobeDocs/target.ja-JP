---
description: 'at. jsのadobe. target. applyOffer（options）関数について取り上げます。 '
keywords: adobe.target.notification;要素;セレクター;通知;拡張子
seo-description: Adobe Target at. js JavaScriptライブラリのadobe. target. applyOffer（options）関数について取り上げます。
seo-title: Adobe Target at. js JavaScriptライブラリのadobe. target. applyOffer（options）関数について取り上げます。
solution: 'Target '
subtopic: 導入
title: adobe.target.applyOffer(options)
topic: Standard
translation-type: tm+mt
source-git-commit: 15da223709bfceecb094b6c9f9e78ba5ce0d8256

---


# adobe.target.applyOffer(options) {#reference_BBE83F513B5B4E03BBC3F50D90864245}

この関数は、応答内容を適用するために使用します。

>[!NOTE]
>
>`applyOffer` には `mbox` パラメーターが必要です。mbox 名が指定されていないと、エラーが発生します。

options パラメーターは必須で、以下の構造を持ちます。

| キー | タイプ | 必須 | 説明 |
|--- |--- |--- |--- |
| mbox | 文字列 | ○ | mbox NameName<br>at. js1.3.0（およびそれ以降） mboxキーが適用されます。これまでもこのキーは必須でしたが、Target では、適切な検証がおこなわれ、お客様がこの関数を正しく利用するために、使用が強制されるようになりました。 |
| selector | 文字列または DOM 要素 | × | Target がオファーコンテンツを配置する必要がある HTML 要素を特定するために使用される HTML 要素または CSS セレクター。セレクターがない場合、Target は、使用する必要がある HTML 要素が HTML HEAD であると仮定します。 |
| offer | 配列 | ○ | 要素に適用される配列アクション。 |

## 例 {#section_D8D6A17B73DE4542937CDB687193A5CC}

次の例に、`getOffer` と `applyOffer` を一緒に使用する方法を示します。

```
adobe.target.getOffer({   
  "mbox": "mbox",   
  "success": function(offers) {           
        adobe.target.applyOffer( {  
           "mbox": "mbox", 
           "offer": offers  
        } ); 
  },   
  "error": function(status, error) {           
      if (console && console.log) { 
        console.log(status); 
        console.log(error); 
      } 
  }, 
 "timeout": 5000 
}); 
```
