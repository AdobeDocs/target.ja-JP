---
keywords: カスタムイベント;at.js;request failed;request succeeded;content rendering failed;content rendering succeeded;library loaded;request start;content rendering start;content rendering no offers;content rendering rediret
description: Adobeにカスタムイベントを使用 [!DNL Target] at.js JavaScript ライブラリ：mbox リクエストまたはオファーが失敗または成功した場合に通知されます。
title: at.js カスタムイベントの使用方法
feature: at.js
role: Developer
exl-id: 4073210b-b782-48a7-8b69-29eb5cd98fd5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 61%

---

# at.js カスタムイベント

mbox リクエストまたはオファーの失敗や成功を把握するための `at.js custom events` について説明します。

以前は、mbox.js（現在は非推奨）を使用している場合、バックグラウンドでの処理内容を、ページ上で実行される他の JavaScript コードが把握することはできませんでした。 at.js の改良により、この問題を独自の方法で解決することができました。

当社のお客様によれば、次のような場合に通知が必要になります。

* タイムアウト、ステータスコードの誤り、JSON 解析エラーなどの理由で mbox リクエストが失敗した。
* mbox リクエストが成功した。
* ラッピング mbox 要素が欠落している、セレクターがないなどの理由でオファーのレンダリングが失敗した。
* オファーのレンダリングが成功した。DOM の変更が適用されました。

事前定義されたイベントの構造は、イベントのタイプに基づいて必要なデータを抽出できるようになっています。

イベントを様々なシナリオで使用できるようにするため、カスタムイベントにはペイロードオブジェクトがあります。このオブジェクトは（ハンドラーに渡される）イベントオブジェクトの詳細プロパティに割り当てられます。また、文字列をイベント名として渡さないようにするため、イベントは `adobe.target.event` 名前空間を使用して定数として公開されます。

## 構造 {#section_0E5C9A13DE234A5DAECBCBF9F23F94FE}

| キー | タイプ | 説明 |
|--- |--- |--- |
| type | 文字列 | at.js とのインタラクションの追跡、デバッグ、カスタマイズに役立つ通知を受け取るシナリオには、様々なものが考えられます。<br>以下の各カスタムイベントには、「定数」と「文字列値」の 2 つの形式があります。<ul><li>**定数**： 先頭に `adobe.target.event.` が追加されます。すべて大文字で記述され、アンダースコア文字が含まれます。at.js の読み込みの&#x200B;*後*&#x200B;から、mbox の応答の&#x200B;*前*&#x200B;までの間にカスタムイベントをサブスクライブする場合は、定数を使用します。</li><li>**文字列値**： 小文字で記述され、ダッシュが含まれます。at.js の読み込みの&#x200B;*前*&#x200B;にカスタムイベントをサブスクライブする場合は、文字列値を使用します。</li></ul>**Request Failed**<br>&#x200B;定数： `adobe.target.event.REQUEST_FAILED`<br>文字列値： `at-request-failed`<br>説明：タイムアウト、ステータスコードの誤り、JSON 解析エラーなどの理由で mbox リクエストが失敗しました。<br>**Request Succeeded**<br>&#x200B;定数： `adobe.target.event.REQUEST_SUCCEEDED`<br>文字列値： `at-request-succeeded`<br>説明：mbox リクエストが成功しました。<br>**コンテンツのレンダリングに失敗しました**<br>&#x200B;定数： `adobe.target.event.CONTENT_RENDERING_FAILED`<br>文字列値： `at-content-rendering-failed`<br>説明：ラッピング mbox 要素が欠落している、セレクターがないなどの理由で、オファーのレンダリングが失敗しました。<br>**Content Rendering Succeeded**<br>&#x200B;定数： `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`<br>文字列値： `at-content-rendering-succeeded`<br>説明：オファーのレンダリングが成功しました。 DOM の変更が適用されました。<br>**Library Loaded**<br>&#x200B;定数： `adobe.target.event.LIBRARY_LOADED`<br>文字列値： `at-library-loaded`<br>説明：このイベントは、at.js が完全に読み込まれたタイミングを追跡する場合に最適です。 このイベントを使用してグローバル mbox の実行をカスタマイズできます。グローバル mbox を無効にしてから、このイベントをリッスンして後でグローバル mbox を呼び出すこともできます。<br>**リクエスト開始**<br>&#x200B;定数： `adobe.target.event.REQUEST_START`<br>文字列値： `at-request-start`<br>説明：このイベントは、HTTP リクエストの実行前に発生します。 このイベントは、Resource Timing API によるパフォーマンス計測に使用できます。<br>**Content Rendering Start**<br>&#x200B;定数： `adobe.target.event.CONTENT_RENDERING_START`<br>文字列値： `at-content-rendering-start`<br>説明：このイベントは、セレクターポーリングが開始され、コンテンツがページにレンダリングされる前に発生します。 このイベントを使用して、コンテンツのレンダリングの進捗状況を追跡できます。<br>**Content Rendering No Offers**<br>&#x200B;定数： `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`<br>文字列値： `at-content-rendering-no-offers`<br>説明：このイベントは、オファーが返されない場合に発生します。<br>**Content Rendering Redirect**<br>&#x200B;定数： `adobe.target.event.CONTENT_RENDERING_REDIRECT`<br>文字列値： `at-content-rendering-redirect`<br>説明：このイベントは、オファーがリダイレクトで、Target が別の URL にリダイレクトする際に発生します。 |
| mbox | 文字列 | mbox 名 |
| message | 文字列 | 人間が解読可能な説明（何が起こったか、エラーメッセージの内容など）。 |
| トラッキング | オブジェクト | `sessionId` と `deviceId` が格納されます。場合によっては、`deviceId` が [!DNL Target] を取得できないため、この値が欠落することがあります。 |
| type | 文字列 | **オンデバイス判定アーティファクトが成功しました**<br>&#x200B;定数：<br>`adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`<br>文字列値： `artifactDownloadSucceeded`<br>説明：オンデバイス判定アーティファクトが正常にダウンロードされたときに呼び出されます。<br>**オンデバイス判定アーティファクトが失敗しました**<br>&#x200B;定数： `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`<br>文字列値： `artifactDownloadFailed`<br>説明：オンデバイス判定アーティファクトのダウンロードに失敗した場合に呼び出されます。 |

## 使用方法 {#section_0500FF09D3A04450B5DC8F85C6F793E0}

```javascript
document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(event) { 
  console.log('Event', event); 
});
```

## トレーニングビデオ：レスポンストークンと at.js カスタムイベント ![チュートリアルバッジ](/help/main/assets/tutorial.png) {#section_ED304A7137DC42A4BDCD6D57C989F1FA}

次のビデオでは、レスポンストークンと at.js カスタムイベントを使用して Target とサードパーティシステムの間でプロファイル情報を共有する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
