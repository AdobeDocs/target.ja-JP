---
keywords: mboxCreate;mboxcreate;mbox create;at.js;関数
description: Adobe Target at.js JavaScript ライブラリの mboxCreate(mbox,params) 関数について説明します。
title: Mboxcreate(Mbox,Params) - at.js 1.x
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 97%

---


# mboxCreate(mbox,params) - at.js 1.x {#reference_E68805FE86C64792B2066DB17B253D74}

リクエストを実行し、mboxDefault クラス名を持つ最も近い DIV にオファーを適用します。

>[!NOTE]
>
>この関数は at.js バージョン 1.*x* のみで使用できます。この関数は at.js 2.x のリリースで廃止されました。at.js 2.x で使用する場合、この関数はデフォルトコンテンツを返します。

この関数は、[!DNL at.js] から [!DNL mbox.js] への移行の多くを簡単にするために、[!DNL at.js] に組み込まれています。新しく `mboxCreate()` に代わるものは、`adobe.target.applyOffer()`/`adobe.target.getOffer()` または Angular ディレクティブです。

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

* [デバッグ](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) が少し異なる。
* オファーコードが同期を必要としたり、呼び出しをブロックするのを避ける。

   例えば、サイトコードまたは後でページに表示される他の mbox によって使用される JavaScript 変数を設定するオファー。

* `mboxCreate()` を呼び出す前に `<div class="mboxDefault"></div>` があることを確認してください（[!DNL at.js] によって追加されないため）。

* 空の、ページの先頭にある `mboxCreate()` 関数は、グローバル mbox としてお勧めしません。

   [!DNL at.js] で自動作成されたグローバル mbox は、`<head>` から実行され、より早くコンテンツを返せる、より優れたオプションです。