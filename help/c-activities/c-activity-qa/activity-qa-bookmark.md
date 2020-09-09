---
keywords: qa;preview;bookmarklet;preview links
description: ターゲットにQAモードからの解放を強制するために、Adobe TargetQAブックマークレットを使用するのに役立つ情報です。
title: Adobe Target向けアクティビティQAブックマークレット
feature: qa
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: 620bb6dfbe160cf27ef5de9199c3d91fb806f316
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 26%

---


# アクティビティ QA ブックマークレット{#activity-qa-bookmarklet}

Information to help you use the [!DNL Target] QA bookmarklet to force [!DNL Target] to release you from QA mode.

>[!NOTE]
>
>ブックマークレットを作成するプロセスは、ブラウザーのタイプとバージョンによって異なります。ブラウザーのヘルプを参照するか、インターネットで特定の方向に検索してください。

## at.js 1用のアクティビティQAブックマークレット&#x200B;*x*

[QAモード](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) は定着なので、QAモードでWebサイトを参照すると、セッションが有効期限切れになります。また、通常の訪問者のようにサイトを表示するには、モードからTargetをリリースする必要があります。[!DNL Target][!DNL Target]Use the QA [!DNL Target] bookmarklet to force yourself out of QA mode.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser&#39;s Bookmarks Toolbar:

```
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

## at.js 2用のアクティビティQAブックマークレット&#x200B;*x*

at.js 1とは対照的に。*x*、at.js 2.*x* はサードパーティcookieをサポートしておらず、QAモードはファーストパーティドメインの固定値にすぎません（at.jsが設定するファーストパーティcookieを使用）。 at.js 2では次のようになります。*x*、QAモードのセッションはクライアント側でのみ管理され、QAモードのcookieはターゲットに送信されません。

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser&#39;s Bookmarks Toolbar:

```
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {
            document.cookie = AT_QA_MODE + '; Max-Age=-99999999;';
            var url = window.location.href.split('at_preview_token',2)[0];
            window.location.href = url.substring(0, url.length - 1);
        }
    })();
```

## アクティビティQAブックマークレットの使用

ブラウザーのツールバーのブックマークレットをクリックします。

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value.

次に例を示します。

`https://www.mysite.com/?at_preview_token=`
