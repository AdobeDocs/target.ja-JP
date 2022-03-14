---
keywords: qa、preview、ブックマークレット、リンクのプレビュー
description: Adobe [!DNL Target] QA ブックマークレットで強制的に [!DNL Target] をクリックして、QA モードから解放します。
title: アクティビティ QA ブックマークレットの使用方法を教えてください。
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 27%

---

# アクティビティ QA ブックマークレット

使用に役立つ情報 [!DNL Target] QA ブックマークレットで強制的に [!DNL Target] をクリックして、QA モードから解放します。

>[!NOTE]
>
>ブックマークレットを作成するプロセスは、ブラウザーのタイプとバージョンによって異なります。ブラウザーのヘルプを参照するか、インターネットで特定の方向に検索してください。

## at.js 1.*x*

[QAモード](/help/main/c-activities/c-activity-qa/activity-qa.md) は定着なので、QAモードでWebサイトを参照すると、セッションが有効期限切れになります。また、通常の訪問者のようにサイトを表示するには、モードからTargetをリリースする必要があります。[!DNL Target][!DNL Target]QA の使用 [!DNL Target] ブックマークレットを使用して QA モードから強制的に離脱しない限り、QA モードから離脱しない限り、QA モードで離脱しない限り、

次の手順で [!DNL Target] QA ブックマークレットを使用する場合は、次の JavaScript コードを含むブックマークレットを作成し、ブラウザーのブックマークツールバーに追加します。

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

また、 `at_preview_token` パラメーターの値が空です。

次に例を示します。

`https://www.mysite.com/?at_preview_token=`

## at.js 2.*x*

at.js 1.*x*、at.js 2.*x* ではサードパーティ Cookie がサポートされておらず、QA モードは（at.js によって設定されるファーストパーティ Cookie を使用して）ファーストパーティドメイン用にのみ定着です。 したがって、at.js 2.*x*、QA モードのセッションはクライアント側でのみ管理され、QA モードの cookie は Target に送信されません。

次の手順で [!DNL Target] QA ブックマークレットを使用する場合は、次の JavaScript コードを含むブックマークレットを作成し、ブラウザーのブックマークツールバーに追加します。

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

ブラウザーのツールバーのブックマークレットをクリックします。
