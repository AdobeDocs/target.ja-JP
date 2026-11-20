---
keywords: qa、preview、ブックマークレット、リンクのプレビュー
description: Adobe [!DNL Target] QA ブックマークレットを使用して、[!DNL Target]に強制的にQA モードから解放する方法を説明します。
title: アクティビティ QA ブックマークレットの使用方法を教えてください。
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
TQID: 'https://experienceleague.adobe.com/kOQcdF2WgiAGkOS3rrLWfDSFTvRJX8jb-IeaahWnM0c'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0a683f6e68bb7481b9e45c91a275a46b84a1ffd8
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 13%
---
# アクティビティ QA ブックマークレット {#activity-qa-bookmarklet}

>[!BEGINSHADEBOX]

**このページ：** [!DNL Target] QA ブックマークレットを使用して&#x200B;**[!UICONTROL Activity QA]** モードを終了し、サイトを一般的な訪問者として表示する方法を説明します。

>[!ENDSHADEBOX]

Web サイトを[QA モード &#x200B;](/help/main/c-activities/c-activity-qa/activity-qa.md)で閲覧した後、QA モードは[!DNL Target] セッションが期限切れになるまでページ間で保持されます。 ブックマークレットは、JavaScriptを実行するブラウザーのブックマークです。 [!DNL Target] QA ブックレットでは、[!DNL Target]が強制的にQA モードから解放されるため、セッションの有効期限が切れるまで待つ必要はありません。 サイトにデプロイされたat.js バージョンと一致するバージョンを使用します。

>[!NOTE]
>
>ブックマークレットを作成するプロセスは、ブラウザーのタイプとバージョンによって異なります。 ブラウザの助けを借りるか、インターネット上で特定の方向を検索してください。

## at.js 1.*x* アクティビティ QA ブックマークレット

[!DNL Target] QA ブックマークレットを使用するには、次のJavaScript コードを含むブックマークレットを作成し、ブラウザーのブックマークツールバーに追加します。

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

また、`at_preview_token` パラメーターが空の値に設定されたサイト上のページを読み込むことで、手動でQA モードを強制的に解除することもできます。 次に例を示します。

`https://www.mysite.com/?at_preview_token=`

## at.js 2.*x* アクティビティ QA ブックマークレット

at.js 1.*x*&#x200B;とは対照的に、at.js 2.*x*&#x200B;はサードパーティ Cookieをサポートしていません。 QA モードは、at.jsによって設定されたファーストパーティ Cookieを使用して、ファーストパーティドメインに対してのみ保持されます。 その結果、QA モード セッションはクライアント側でのみ管理され、QA モード Cookieは[!DNL Target]に送信されません。

[!DNL Target] QA ブックマークレットを使用するには、次のJavaScript コードを含むブックマークレットを作成し、ブラウザーのブックマークツールバーに追加します。

```javascript
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {            
            document.cookie = AT_QA_MODE + ';domain='+window.location.hostname+";Path=/; Max-Age=-0;";
            var token = window.location.href.indexOf("?at_preview_token")<0? "&at_preview_token" : "?at_preview_token";
            var url = window.location.href.split(token,2)[0];
            window.open(url, '_self', 'noreferrer');
        }
    })(); 
```

## アクティビティ QA ブックマークレットの使用

at.jsのバージョンに一致するブックマークレットをブラウザーに追加したら、QA モードを終了するときにいつでも使用できます。

1. QA モードでサイトの任意のページを開きます。
1. ブラウザーのブックマークツールバーにあるブックマークレットをクリックします。
1. サイトのページを読み込みます。 [!DNL Target]はQA モードからセッションを解放し、サイトは一般的な訪問者と同じように表示されます。
