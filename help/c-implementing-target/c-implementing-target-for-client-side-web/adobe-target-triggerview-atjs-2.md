---
description: 'at. jsのadobe. target. triggerView（viewName， options）関数について取り上げます。 '
keywords: adobe.target.notification;要素;セレクター;通知;拡張子
seo-description: Adobe Target at. js JavaScriptライブラリのadobe. target. triggerView（viewName， options）関数について取り上げます。
seo-title: Adobe Target at. js JavaScriptライブラリのadobe. target. triggerView（viewName， options）関数について取り上げます。
solution: 'Target '
subtopic: 導入
title: adobe.target.triggerView (viewName, options)
topic: Standard
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# adobe. target. triggerView（viewName， options）- at. js2. x

この関数は、新しいページが読み込まれるときや、ページ上のコンポーネントが再レンダリングされるときに呼び出すことができます。Visual Experience Composer（VEC）を使用してA/Bテストおよびエクスペリエンスターゲット設定（XT）アクティビティを作成するためには、`adobe.target.triggerView()` をシングルページアプリケーション（SPA）に実装する必要があります。サイトに `adobe.target.triggerView()` が実装されていない場合、VEC は SPA に使用できません。詳細については、「[シングルページアプリケーションの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)」を参照してください。

>[!NOTE]
>
>この関数はat. js2. xで導入されました。この関数はat. jsバージョン1では使用できません。*x*.

| パラメーター | タイプ | 必須？ | 説明 |
| --- | --- | --- | --- |
| viewName | 文字列 | ○ | ビューを表す文字列型として任意の名前を渡します。このビュー名は、VEC の「[!UICONTROL 変更]」パネルに表示されます。マーケティング担当者はこれを使用してアクションを作成し、A/B および XT アクティビティを実行します。 |
| options | オブジェクト | × |
| options &gt; page | ブール値 | × | **TRUE：** ページのデフォルト値は true です。page = true の場合、インプレッション数を増分するために [!DNL Target] のバックエンドに通知が送信されます。<br>**FALSE:** page= falseの場合、インプレッション数の増分に通知は送信されません。これは、オファーを含むページ上のコンポーネントを再レンダリングするだけの場合に使用します。 |

## インプレッション数を増加させるために Target のバックエンドに通知を送信する `triggerView()` の呼び出し例

```
adobe.target.triggerView("homeView")
```

## Target のバックエンドにインプレッション数のための通知を送信しないようにする `triggerView()` の呼び出し例

```
adobe.target.triggerView("homeView", {page: false})
```
