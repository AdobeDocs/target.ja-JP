---
description: Target QA ブックマークレットを使用し、QA モードから強制的に離脱するよう設定する際に役立つ情報をまとめています。
keywords: qa、preview、ブックマークレット、リンクのプレビュー
seo-description: Target QA ブックマークレットを使用し、QA モードから強制的に離脱するよう設定する際に役立つ情報をまとめています。
seo-title: アクティビティ QA ブックマークレット
solution: 'Target '
title: アクティビティ QA ブックマークレット
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# アクティビティ QA ブックマークレット{#activity-qa-bookmarklet}

Target QA ブックマークレットを使用し、QA モードから強制的に離脱するよう設定する際に役立つ情報をまとめています。

[QAモード](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) は定着なので、QAモードでWebサイトを参照すると、Targetセッションが有効期限切れになります。また、通常の訪問者のようにサイトを表示するには、TargetモードからTargetをリリースする必要があります。Target QA ブックマークレットを使用すると、QA モードから強制的に離脱できます。

Target QAブックマークレットを使用するには、次のJavaScriptコードを含むブックマークレットを作成し、ブラウザーのブックマークツールバーに追加します。

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

また、値が空の `at_preview_token` 場合（など `https://www.mysite.com/?at_preview_token=`）、サイト上のページを読み込むことでQAモードを手動で強制的に除外することもできます。
