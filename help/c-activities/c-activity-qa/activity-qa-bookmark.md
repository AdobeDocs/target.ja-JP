---
description: Adobe Target QAブックマークレットを使用してTargetにQAモードからのリリースを強制するのに役立つ情報です。
keywords: qa、preview、ブックマークレット、リンクのプレビュー
seo-description: Adobe Target QAブックマークレットを使用してTargetにQAモードからのリリースを強制するのに役立つ情報です。
seo-title: Adobe targetのアクティビティQAブックマークレット
solution: 'Target '
title: アクティビティ QA ブックマークレット
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: 1df7fbf78f9e20d8a907809b228ed591036c1a24

---


# アクティビティ QA ブックマークレット{#activity-qa-bookmarklet}

Information to help you use the [!DNL Target] QA bookmarklet to force [!DNL Target] to release you from QA mode.

[QAモード](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) は定着なので、QAモードでWebサイトを参照すると、セッションが有効期限切れになります。また、通常の訪問者のようにサイトを表示するには、モードからTargetをリリースする必要があります。[!DNL Target][!DNL Target]Use the QA [!DNL Target] bookmarklet to force yourself out of QA mode.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser's Bookmarks Toolbar:

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

そうすると、ブックマークレットがツールバーに表示され、再利用できるようになります。

>[!NOTE]
>
>ブックマークレットを作成するプロセスは、ブラウザーのタイプとバージョンによって異なります。ブラウザーのヘルプを参照するか、インターネットで特定の方向に検索してください。

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value.

次に例を示します。

`https://www.mysite.com/?at_preview_token=`
