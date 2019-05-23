---
description: 'at. jsのmboxCreate（mbox， params）関数に関する情報です。 '
keywords: adobe.target.notification;要素;セレクター;通知;拡張子
seo-description: Adobe Target at. js JavaScriptライブラリのmboxCreate（mbox， params）関数に関する情報です。
seo-title: Adobe Target at. js JavaScriptライブラリのmboxCreate（mbox， params）関数に関する情報です。
solution: 'Target '
subtopic: 導入
title: mboxCreate(mbox,params) - at.js 2.x
topic: Standard
translation-type: tm+mt
source-git-commit: 126f62d8966beb8157f54f87cf68b092fe976c51

---


# mboxCreate(mbox,params) - at.js 1.x {#reference_E68805FE86C64792B2066DB17B253D74}

リクエストを実行し、mboxDefault クラス名を持つ最も近い DIV にオファーを適用します。

>[!NOTE]
>
>この関数は at.js バージョン 1.*x* のみで使用できます。この関数はat. js2. xのリリースで廃止されました。この関数は、at. js2. xと共に使用される場合、デフォルトコンテンツを返します。

この関数は、[!DNL at.js] から [!DNL mbox.js] への移行の多くを簡単にするために、[!DNL at.js] に組み込まれています。新しく `mboxCreate()` に代わるものは、`adobe.target.applyOffer()`/`adobe.target.getOffer()` または Angular ディレクティブです。

## 例

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## メモ

`mboxCreate()` は、「標準」エンドポイントではなく「json」エンドポイントを使用し、非同期で実行されます。理由は以下のとおりです。

* [デバッグ](../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) が少し異なる。
* オファーコードが同期を必要としたり、呼び出しをブロックするのを避ける。

   例えば、サイトコードまたは後でページに表示される他の mbox によって使用される JavaScript 変数を設定するオファー。

* `mboxCreate()` を呼び出す前に `<div class="mboxDefault"></div>` があることを確認してください（[!DNL at.js] によって追加されないため）。

* 空の、ページの先頭にある `mboxCreate()` 関数は、グローバル mbox としてお勧めしません。

   [!DNL at.js] で自動作成されたグローバル mbox は、`<head>` から実行され、より早くコンテンツを返せる、より優れたオプションです。