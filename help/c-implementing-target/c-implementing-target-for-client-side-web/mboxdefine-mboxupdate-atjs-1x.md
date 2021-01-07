---
keywords: mboxDefine;mboxdefine;mbox define;mboxUpdate;mboxupdate;mbox update;at.js;functions;function
description: Adobe Target at.js JavaScript ライブラリの mboxDefine() 関数と mboxUpdate() 関数について説明します。
title: mboxDefine() と mboxUpdate() - at.js 1.x
feature: at.js
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 100%

---


# mboxDefine() と mboxUpdate() - at.js 1.x

Adobe Target で mbox を定義し更新します。

>[!NOTE]
>
>これらの関数は at.js バージョン 1.*x* のみで使用できます。これらの関数は at.js 2.x のリリースで廃止されました。at.js 2.x で使用する場合、これらの関数はデフォルトコンテンツを返します。

`mboxDefine()` と `mboxCreate()` は、オファーが表示される HTML DIV 要素に結び付けられています。これらの HTML DIV 要素は、`mboxDefault` クラスを持つ必要があります。HTML 要素にこのクラスが付加されない場合、顕著なちらつきが表示される可能性があります。

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

nodeId と mbox 名の間の内部マッピングを作成しますが、リクエストを実行しません。`mboxUpdate()` () と共に使用されます。[!DNL mbox.js] から [!DNL at.js] への移行の多くを簡単にするために、[!DNL at.js] に組み込まれています。

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

リクエストを実行し、`nodeId` () の `mboxDefine()` によって識別される要素にオファーを適用します。また、`mboxCreate` によって開始された mbox を更新するために使用できます。[!DNL at.js] から [!DNL mbox.js] への移行の多くを簡単にするために、[!DNL at.js] に組み込まれています。`mboxDefine()`／`mboxUpdate()` は、セレクターオプションを使用する [adobe.target.getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) および [adobe.target.applyOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) に置き換えられます。

## 例 {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```javascript
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
