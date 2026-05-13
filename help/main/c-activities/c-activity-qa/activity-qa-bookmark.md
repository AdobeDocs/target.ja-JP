---
keywords: qa、preview、ブックマークレット、リンクのプレビュー
description: Adobe [!DNL Target] QA ブックマークレットを使用して、強制的に [!DNL Target] QA モードから解放する方法を説明します。
title: アクティビティ QA ブックマークレットの使用方法を教えてください。
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
TQID: https://experienceleague.adobe.com/kOQcdF2WgiAGkOS3rrLWfDSFTvRJX8jb-IeaahWnM0c
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 12%

---

# アクティビティ QA ブックマークレット

[!DNL Target] QA ブックマークレットを使用して[!DNL Target]に強制的にQA モードから解放してもらうための情報です。

>[!NOTE]
>
>ブックマークレットを作成するプロセスは、ブラウザーのタイプとバージョンによって異なります。 ブラウザーのヘルプを参照するか、インターネットで特定の方向に検索してください。

## at.js 1.*x*&#x200B;のアクティビティ QA ブックマークレット

[QA モード &#x200B;](/help/main/c-activities/c-activity-qa/activity-qa.md)はスティッキーなので、QA モードでweb サイトを閲覧した後は、[!DNL Target] セッションの有効期限が切れる必要があります。または、一般的な訪問者のようにサイトを表示する前に、[!DNL Target]がQA モードから解放する必要があります。 QA [!DNL Target] ブックマークレットを使用して、強制的にQA モードを解除します。

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

また、空の値を持つ`at_preview_token` パラメーターを使用してサイト上のページを読み込むことで、手動でQA モードを強制的に解除することもできます。

次に例を示します。

`https://www.mysite.com/?at_preview_token=`

## at.js 2.*x*&#x200B;のアクティビティ QA ブックマークレット

at.js 1.*x*&#x200B;とは対照的に、at.js 2.*x*&#x200B;はサードパーティ Cookieをサポートしておらず、QA モードは（at.jsによって設定されたファーストパーティ Cookieを使用して）ファーストパーティドメインに対してのみ固定されます。 したがって、at.js 2.*x*&#x200B;では、QA モードセッションはクライアントサイドでのみ管理され、QA モードクッキーはTargetに送信されません。

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

## Activity QA ブックマークレットの使用

ブラウザーのツールバーのブックマークレットをクリックします。
