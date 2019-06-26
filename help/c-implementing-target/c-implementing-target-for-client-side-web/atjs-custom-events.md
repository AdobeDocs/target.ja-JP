---
description: 'at.js のカスタムイベントについて説明します。 '
keywords: adobe.target.notification;要素;セレクター;通知;拡張子
seo-description: Adobe Target at.js JavaScript ライブラリのカスタムイベントについて説明します。
seo-title: Adobe Target at.js JavaScript ライブラリのカスタムイベントについて説明します。
solution: 'Target '
subtopic: 導入
title: at.js カスタムイベント
topic: Standard
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# at.js カスタムイベント

mbox リクエストまたはオファーの失敗や成功を把握するための `at.js custom events` について説明します。

以前は、mbox.js を使用している場合、バックグラウンドでの処理内容を、ページ上で実行される他の JavaScript コードが把握することはできませんでした。at.js の改良により、この問題を独自の方法で解決することができました。

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
| type | 文字列 | at.js とのインタラクションの追跡、デバッグ、カスタマイズに役立つ通知を受け取るシナリオには、様々なものが考えられます。<br>以下の各カスタムイベントには、「定数」と「文字列値」の 2 つの形式があります。<ul><li>**定数**： 先頭に `adobe.target.event.` が追加されます。すべて大文字で記述され、アンダースコア文字が含まれます。at.js の読み込みの*後*から、mbox の応答の*前*までの間にカスタムイベントをサブスクライブする場合は、定数を使用します。</li><li>**文字列値**： 小文字で記述され、ダッシュが含まれます。at.js の読み込みの*前*にカスタムイベントをサブスクライブする場合は、文字列値を使用します。</li></ul>**Request Failed**<br>定数： `adobe.target.event.REQUEST_FAILED`<br>文字列： `at-request-failed`<br>説明： タイムアウト、ステータスコードの誤り、JSON 解析エラーなどの理由で mbox リクエストが失敗しました。<br>**Request Succeeded**<br>定数：`adobe.target.event.REQUEST_SUCCEEDED`<br>文字列値：`at-request-succeeded`<br>説明： mbox リクエストが成功しました。<br>**Content Rendering Failed**<br>定数：`adobe.target.event.CONTENT_RENDERING_FAILED`<br>文字列値：`at-content-rendering-failed`<br>説明： ラッピング mbox 要素が欠落している、セレクターがないなどの理由で、オファーのレンダリングが失敗しました。<br>**Content Rendering Succeeded**<br>定数：`adobe.target.event.CONTENT_RENDERING_SUCCEEDED`<br>文字列値：`at-content-rendering-succeeded`<br>説明： オファーのレンダリングが成功しました。DOM の変更が適用されました。<br>**Library Loaded**<br>定数：`adobe.target.event.LIBRARY_LOADED`<br>文字列値：`at-library-loaded`<br>説明： このイベントは、at.js が完全に読み込まれたタイミングを追跡する場合に最適です。このイベントを使用してグローバル mbox の実行をカスタマイズできます。グローバル mbox を無効にしてから、このイベントをリッスンして後でグローバル mbox を呼び出すこともできます。<br>**Request Start**<br>定数：`adobe.target.event.REQUEST_START`<br>文字列値：`at-request-start`<br>説明： このイベントは、HTTP リクエストの実行前に発生します。このイベントは、Resource Timing API によるパフォーマンス計測に使用できます。<br>**Content Rendering Start**<br>定数：`adobe.target.event.CONTENT_RENDERING_START`<br>文字列値：`at-content-rendering-start`<br>説明： このイベントは、セレクターポーリングが開始され、コンテンツがページにレンダリングされる前に発生します。このイベントを使用して、コンテンツのレンダリングの進捗状況を追跡できます。<br>**Content Rendering No Offers**<br>定数：`adobe.target.event.CONTENT_RENDERING_NO_OFFERS`<br>文字列値：`at-content-rendering-no-offers`<br>説明： このイベントは、オファーが返されなかったときに発生します。<br>**Content Rendering Redirect**<br>定数：`adobe.target.event.CONTENT_RENDERING_REDIRECT`<br>文字列値：`at-content-rendering-redirect`<br>説明： このイベントは、オファーがリダイレクトであり、Target によって別の URL にリダイレクトされるときに発生します。 |
| mbox | 文字列 | mbox 名 |
| message | 文字列 | 人間が解読可能な説明（何が起こったか、エラーメッセージの内容など）。 |
| トラッキング | オブジェクト | `sessionId` と `deviceId` が格納されます。場合によっては、`deviceId` が [!DNL Target] を取得できないため、この値が欠落することがあります。 |

## 使用方法 {#section_0500FF09D3A04450B5DC8F85C6F793E0}

```
document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(event) { 
  console.log('Event', event); 
});
```

## トレーニングビデオ： レスポンストークンと at.js カスタムイベント{#section_ED304A7137DC42A4BDCD6D57C989F1FA}

次のビデオでは、レスポンストークンと at.js カスタムイベントを使用して Target とサードパーティシステムの間でプロファイル情報を共有する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/23253/?captions=jpn)