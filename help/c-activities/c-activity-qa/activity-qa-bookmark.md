---
keywords: qa、preview、ブックマークレット、リンクのプレビュー
description: Adobe [!DNL Target] QA bookmarklet to force [!DNL Target] を使用してQAモードから解放する方法を説明します。
title: アクティビティQAブックマークレットの使用方法
feature: アクティビティ
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 28%

---

# アクティビティ QA ブックマークレット

[!DNL Target] QAブックマークレットを使用して[!DNL Target]にQAモードからの解放を強制するのに役立つ情報です。

>[!NOTE]
>
>ブックマークレットを作成するプロセスは、ブラウザーのタイプとバージョンによって異なります。ブラウザーのヘルプを参照するか、インターネットで特定の方向に検索してください。

## at.js 1用のアクティビティQAブックマークレット&#x200B;*x*

[QAモード](/help/c-activities/c-activity-qa/activity-qa.md) は定着なので、QAモードでWebサイトを参照すると、セッションが有効期限切れになります。また、通常の訪問者のようにサイトを表示するには、モードからTargetをリリースする必要があります。[!DNL Target][!DNL Target]QA [!DNL Target]ブックマークレットを使用して、QAモードを強制的に終了します。

[!DNL Target] QAブックマークレットを使用するには、次のJavaScriptコードを含むブックマークレットを作成し、ブラウザーのブックマークツールバーに追加します。

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

また、空の値を持つ`at_preview_token`パラメーターを持つページをサイトに読み込むことで、手動でQAモードを強制的に終了することもできます。

次に例を示します。

`https://www.mysite.com/?at_preview_token=`

## at.js 2用のアクティビティQAブックマークレット&#x200B;*x*

at.js 1とは対照的に。*x*、at.js 2.** xはサードパーティcookieをサポートしません。また、QAモードは、（at.jsによって設定されたファーストパーティcookieを使用して）ファーストパーティドメインに対してのみ固定されます。at.js 2では次のようになります。*x*、QAモードのセッションはクライアント側でのみ管理され、QAモードのcookieはターゲットに送信されません。

[!DNL Target] QAブックマークレットを使用するには、次のJavaScriptコードを含むブックマークレットを作成し、ブラウザーのブックマークツールバーに追加します。

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

## アクティビティQAブックマークレットの使用

ブラウザーのツールバーのブックマークレットをクリックします。
