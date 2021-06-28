---
keywords: mbox定義;mbox定義;mbox 定義;mboxUpdate;mboxupdate;mbox update;at.js;関数
description: Adobe [!DNL Target] at.js JavaScriptライブラリのmboxDefine()関数とmboxUpdate()関数を使用して、mboxを定義または更新します。 (at.js 1.x)
title: mboxDefine()関数とmboxUpdate()関数の使用方法を教えてください。
feature: at.js
role: Developer
exl-id: 48261be0-c4d0-4961-9712-ef7e0d2cb1c0
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 86%

---

# mboxDefine() と mboxUpdate() - at.js 1.x

Adobe Target で mbox を定義し更新します。

>[!NOTE]
>
>これらの関数は at.js バージョン 1.*x* のみで使用できます。これらの関数は at.js 2.x のリリースで廃止されました。at.js 2.x で使用する場合、これらの関数はデフォルトコンテンツを返します。

`mboxDefine()` と `mboxCreate()` は、オファーが表示される HTML DIV 要素に結び付けられています。これらの HTML DIV 要素は、`mboxDefault` クラスを持つ必要があります。HTML 要素にこのクラスが付加されない場合、顕著なちらつきが表示される可能性があります。

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

nodeId と mbox 名の間の内部マッピングを作成しますが、リクエストを実行しません。`mboxUpdate()` () と共に使用されます。[!DNL at.js] から [!DNL mbox.js] への移行の多くを簡単にするために、[!DNL at.js] に組み込まれています。

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
