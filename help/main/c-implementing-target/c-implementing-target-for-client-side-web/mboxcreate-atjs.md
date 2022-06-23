---
keywords: mboxCreate;mboxcreate;mbox create;at.js;関数
description: Adobeに対する mboxCreate() 関数の使用 [!DNL Target] at.js JavaScript ライブラリを使用して、mboxDefault クラス名を持つ最も近い DIV にオファーを適用できます。 (at.js 1.x)
title: mboxCreate() 関数の使用方法を教えてください。
feature: at.js
role: Developer
exl-id: 821ad97a-345a-4e56-9be6-ab1c7d3a651d
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 73%

---

# mboxCreate(mbox,params) - at.js 1.x

リクエストを実行し、mboxDefault クラス名を持つ最も近い DIV にオファーを適用します。

>[!NOTE]
>
>この関数は at.js バージョン 1.*x* のみで使用できます。この関数は at.js 2.x のリリースで廃止されました。at.js 2.x で使用する場合、この関数はデフォルトコンテンツを返します。

この関数は、 [!DNL at.js] ～からの移行を容易にするために [!DNL mbox.js] （現在は非推奨）から [!DNL at.js]. 新しく `mboxCreate()` に代わるものは、`adobe.target.applyOffer()`/`adobe.target.getOffer()` または Angular ディレクティブです。

## 例

```javascript
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## メモ

`mboxCreate()` は、「標準」エンドポイントではなく「json」エンドポイントを使用し、非同期で実行されます。理由は以下のとおりです。

* [デバッグ](https://developer.adobe.com/target/implement/client-side/target-debugging-atjs/target-debugging-atjs/){target=_blank} は少し異なります。
* オファーコードが同期を必要としたり、呼び出しをブロックするのを避ける。

   例えば、サイトコードまたは後でページに表示される他の mbox によって使用される JavaScript 変数を設定するオファー。

* `mboxCreate()` を呼び出す前に `<div class="mboxDefault"></div>` があることを確認してください（[!DNL at.js] によって追加されないため）。

* 空の、ページの先頭にある `mboxCreate()` 関数は、グローバル mbox としてお勧めしません。

   [!DNL at.js] で自動作成されたグローバル mbox は、`<head>` から実行され、より早くコンテンツを返せる、より優れたオプションです。
