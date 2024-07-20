---
keywords: qa、preview、ブックマークレット、リンクのプレビュー
description: Adobe [!DNL Target] QA ブックマークレットを使用して、強制的に QA モードから解放  [!DNL Target]  る方法を説明します。
title: アクティビティ QA ブックマークレットの使用方法
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 13%

---

# アクティビティ QA ブックマークレット

[!DNL Target] の QA ブックマークレットを使用して、ユーザーに QA モードからのリリースを強制する [!DNL Target] めに役立つ情報です。

>[!NOTE]
>
>ブックマークレットを作成するプロセスは、ブラウザーのタイプとバージョンによって異なります。ブラウザーのヘルプを参照するか、インターネットで特定の方向に検索してください。

## at.js 1. アクティビティ QA ブックマークレット&#x200B;*x*

[QA モード ](/help/main/c-activities/c-activity-qa/activity-qa.md) はスティッキーなので、QA モードで web サイトを閲覧した後は、[!DNL Target] セッションの有効期限が切れるか、通常の訪問者のようにサイトを表示す [!DNL Target] 前に QA モードを終了する必要があります。 QA [!DNL Target] ブックマークレットを使用して、QA モードを強制的に終了します。

[!DNL Target] QA ブックマークレットを使用するには、以下のJavaScript コードを含むブックマークレットを作成して、ブラウザーのブックマークツールバーに追加します。

```javascript
javascript:(
    function () {
        if (window.location.href.indexOf('?') != -1) {
            var parts = window.location.href.split('at_preview_token',2);
            if (parts.length > 1) {
                window.location.href = parts[0].concat('at_preview_token=');
            } else {
                window.location.href = window.location.href.concat("&at_preview_token=")
            }
        } else {
            window.location.href = window.location.href.concat("?at_preview_token=")
        }
    }
)();
```

また、`at_preview_token` パラメーターの値が空のページをサイトに読み込むことで、手動で QA モードを強制終了することもできます。

次に例を示します。

`https://www.mysite.com/?at_preview_token=`

## at.js 2. アクティビティ QA ブックマークレット&#x200B;*x*

at.js 1 とは異なります。*x*、at.js 2.*x* はサードパーティ cookie をサポートしておらず、QA モードはファーストパーティドメインの場合のみスティッキーです（at.js によって設定されたファーストパーティ cookie を使用）。 そのため、at.js 2.*x*、QA モードセッションはクライアントサイドでのみ管理され、QA モード Cookie は Target に送信されません。

[!DNL Target] QA ブックマークレットを使用するには、以下のJavaScript コードを含むブックマークレットを作成して、ブラウザーのブックマークツールバーに追加します。

```javascript
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {
            document.cookie = AT_QA_MODE + '; Path=/; Max-Age=-0;';
            var url = window.location.href.split('at_preview_token',2)[0];
            window.open(url.substring(0, url.length - 1), '_self', 'noreferrer');
        }
    })();
```

## アクティビティ QA ブックマークレットの使用

ブラウザーのツールバーでブックマークレットをクリックします。
