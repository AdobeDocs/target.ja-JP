---
keywords: adobe.target.applyOffer;applyOffer;applyoffer;apply offer;at.js;関数
description: Adobeには、 adobe.target.applyOffer() 関数を使用します [!DNL Target] at.js JavaScript ライブラリを使用して、応答コンテンツを適用します。
title: adobe.target.applyOffer() 関数の使用方法を教えてください。
feature: at.js
role: Developer
exl-id: d230d48f-0d6c-4f55-96a0-681dd31e8d16
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 73%

---

# adobe.target.applyOffer(options)

この関数は、応答コンテンツを [!DNL Adobe Target].

>[!NOTE]
>
>`applyOffer` には `mbox` パラメーターが必要です。mbox 名が指定されていないと、エラーが発生します。

options パラメーターは必須で、以下の構造を持ちます。

| キー | タイプ | 必須 | 説明 |
|--- |--- |--- |--- |
| mbox | 文字列 | ○ | mbox 名<br>at.js 1.3.0 以降の場合、Target では mbox キーが強制的に使用されます。これまでもこのキーは必須でしたが、Target では、適切な検証がおこなわれ、お客様がこの関数を正しく利用するために、使用が強制されるようになりました。 |
| selector | 文字列または DOM 要素 | × | Target がオファーコンテンツを配置する必要がある HTML 要素を特定するために使用される HTML 要素または CSS セレクター。セレクターが指定されていない場合、Target は、HTML要素でセレクターHEADを使用する必要があると想定します。 |
| オファー | 配列 | ○ | 要素に適用される配列アクション。 |

## 例 {#section_D8D6A17B73DE4542937CDB687193A5CC}

次の例に、`getOffer` と `applyOffer` を一緒に使用する方法を示します。

```javascript
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
