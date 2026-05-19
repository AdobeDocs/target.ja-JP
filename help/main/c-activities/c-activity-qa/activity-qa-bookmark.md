---
keywords: qa、preview、ブックマークレット、リンクのプレビュー
description: Adobe  [!DNL Target]  QA ブックマークレットを使用して、 [!DNL Target]  を強制的に QA モードからリリースする方法について説明します。
title: アクティビティ QA ブックマークレットの使用方法を教えてください。
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
TQID: https://experienceleague.adobe.com/kOQcdF2WgiAGkOS3rrLWfDSFTvRJX8jb-IeaahWnM0c
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: ht
source-wordcount: 272
ht-degree: 100%

---

# アクティビティ QA ブックマークレット

[!DNL Target] QA ブックマークレットを使用して、[!DNL Target] を強制的に QA モードからリリースするために役立つ情報です。

>[!NOTE]
>
>ブックマークレットを作成するプロセスは、ブラウザーのタイプとバージョンによって異なります。 ブラウザーのヘルプを参照するか、インターネットで特定の方向に検索してください。

## at.js 1.*x* アクティビティ QA ブックマークレット

[QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)はスティッキーなので、QA モードで web サイトを閲覧した後は、[!DNL Target] セッションの有効期限が切れるか、[!DNL Target] で QA モードを終了することで、通常の訪問者のようにサイトを表示できるようになります。QA [!DNL Target] ブックマークレットを使用すると、QA モードから強制的に離脱できます。

[!DNL Target] QA ブックマークレットを使用するには、次の JavaScript コードを含むブックマークレットを作成し、ブラウザーのブックマークツールバーに追加します。

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

また、`at_preview_token` パラメーターに空の値を指定してサイトのページを読み込むことで、手動で強制的に QA モードを終了することもできます。

例：

`https://www.mysite.com/?at_preview_token=`

## at.js 2.*x* アクティビティ QA ブックマークレット

at.js 1.*x* とは異なり、at.js 2.*x* はサードパーティ cookie をサポートしておらず、QA モードはファーストパーティドメインの場合のみスティッキーです（at.js によって設定されたファーストパーティ cookie を使用）。そのため、at.js 2.*x* では、QA モードセッションはクライアントサイドでのみ管理され、QA モード Cookie は Target に送信されません。

[!DNL Target] QA ブックマークレットを使用するには、次の JavaScript コードを含むブックマークレットを作成し、ブラウザーのブックマークツールバーに追加します。

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

ブラウザーのツールバーのブックマークレットをクリックします。
