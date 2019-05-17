---
description: mbox.js で実装するときに使用する mbox.js 関数のリスト。
keywords: mbox 関数
seo-description: mbox.js で実装するときに使用する mbox.js 関数のリスト。
seo-title: mbox.js 関数
solution: 'Target '
title: mbox.js 関数
uuid: f503bc44-a664-4d09-82dc-80a1198ad9d0
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# mbox.js 関数{#mbox-js-functions}

mbox.js で実装するときに使用する mbox.js 関数のリスト。

>[!NOTE]
>
>[!DNL at.js] を使用している場合、これらのメソッドは適用されません。

| メソッド | メモ |
|--- |--- |
| `mbox.getName()` |
| `mbox.getURL()` |
| `mbox.getDiv()` | mbox に関連付けられた div（デフォルトコンテンツまたはオファーを含む）を返す |
| `mbox.getParameters()` | 名前と値の 2 つのフィールドを持つパラメーターの配列 |
| `mbox.setOnError()` | 例:<br>`mbox.setOnError(function() { alert(this.getName() +" had error"});` |
| `mbox.setMessage(message)` | デバッグウィンドウのメッセージを確認できます |
| `mboxCurrent.activate()` |
| `mboxCurrent.cancelTimeout()` |
| `mboxCurrent.finalize()` |
| `mboxCurrent.getDefaultDiv()` |
| `mboxCurrent.getDiv()` | mbox に関連付けられた div（デフォルトコンテンツまたはオファーを含む）を返す |
| `mboxCurrent.getEventTimes()` |
| `mboxCurrent.getFetcher()` |
| `mboxCurrent.getId()` |
| `mboxCurrent.getImportName()` |
| `mboxCurrent.getName()` |
| `mboxCurrent.getOffer()` |
| `mboxCurrent.getParameters()` | 名前と値の 2 つのフィールドを持つパラメーターの配列 |
| `mboxCurrent.getURL()` |
| `mboxCurrent.getURLBuilder()` |
| `mboxCurrent.hide()` |
| `mboxCurrent.isActivated`() |
| `mboxCurrent.load()` |
| `mboxCurrent.loaded()` |
| `mboxCurrent.setEventTime()` |
| `mboxCurrent.setFetcher()` |
| `mboxCurrent.setMessage()` |
| `mboxCurrent.setMessage(message)` | デバッグウィンドウにメッセージを表示します |
| `mboxCurrent.setOffer()` |
| `mboxCurrent.setOnError()` | 例:<br>`mboxCurrent.setOnError(function(){ alert(this.getName() +" had error"});` |
| `mboxCurrent.setOnLoad()` | 例:<br>`mboxCurrent.setOnLoad(function(){alert(this.getName()+" loaded")});` |
| `mboxCurrent.show()` |
| `mboxCurrent.showContent()` |
| `mboxFactoryDefault.addOnLoad(action)` | ページの読み込み時にアクションが呼び出されます |
| `mboxFactoryDefault.getMboxes().each()` | 例:<br>`mboxFactoryDefault.getMboxes().each(function() { alert(mbox.getName()) };` |
| `mboxFactoryDefault.getMboxes().length()` |
| `mboxFactoryDefault.getPageId()` |
| `mboxFactoryDefault.getPCId().getId()` |
| `mboxFactoryDefault.getSessionId().getId()` |
| `mboxFactories.get('default').getSessionId()​.forceId("1276011116668");` |
| `mboxFactories.get('default').getPCId()​.forceId("1276011116668");` |
| `mboxFactoryDefault.create()` |
| `mboxFactoryDefault.disable()` |
| `mboxFactoryDefault.enable()` |
| `mboxFactoryDefault.get()` |
| `mboxFactoryDefault.getCookieManager()` |
| `mboxFactoryDefault.getDisableReason()` |
| `mboxFactoryDefault.getEllapsedTime()` |
| `mboxFactoryDefault.getEllapsedTimeUntil()` |
| `mboxFactoryDefault.getMboxes()` | `mboxList` を返します。 |
| `mboxFactoryDefault.getSignaler()` |
| `mboxFactoryDefault.getURLBuilder()` |
| `mboxFactoryDefault.isAdmin()` |
| `mboxFactoryDefault.isDomLoaded()` |
| `mboxFactoryDefault.isEnabled()` |
| `mboxFactoryDefault.isSupported()` |
| `mboxFactoryDefault.limitTraffic()` |
| `mboxFactoryDefault.update()` |
| `mboxFactoryDefault.getCookieManager()​.getCookie("name")//!= null) {` |
| `mboxFactoryDefault.getCookieManager()​.setCookie(_name,_value, _duration);` |