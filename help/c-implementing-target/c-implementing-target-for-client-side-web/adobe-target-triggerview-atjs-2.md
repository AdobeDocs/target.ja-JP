---
keywords: adobe.target.triggerView;triggerView;triggerview;trigger view;at.js;関数;viewName;viewname;view name
description: Adobe Target at.js JavaScript ライブラリの adobe.target.triggerView (viewName, options) 関数について説明します。
title: Adobe.ターゲット.トリガービュー（Viewname、オプション） - at.js 2.x
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 91%

---


# adobe.triggerView (viewName, options) - at.js 2.x

この関数は、新しいページが読み込まれるときや、ページ上のコンポーネントが再レンダリングされるときに呼び出すことができます。Visual Experience Composer（VEC）を使用してA/Bテストおよびエクスペリエンスターゲット設定（XT）アクティビティを作成するためには、`adobe.target.triggerView()` をシングルページアプリケーション（SPA）に実装する必要があります。サイトに `adobe.target.triggerView()` が実装されていない場合、VEC は SPA に使用できません。詳細については、「[シングルページアプリケーションの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)」を参照してください。

>[!NOTE]
>
>この関数は at.js 2.x で導入されました。この関数は at.js バージョン 1.x では使用できません。*x*.

| パラメーター | タイプ | 必須？ | 説明 |
| --- | --- | --- | --- |
| viewName | 文字列 | ○ | ビューを表す文字列型として任意の名前を渡します。このビュー名は、VEC の「[!UICONTROL 変更]」パネルに表示されます。マーケティング担当者はこれを使用してアクションを作成し、A/B および XT アクティビティを実行します。 |
| options | オブジェクト | × |  |
| options > page | ブール値 | × | **TRUE：** ページのデフォルト値は true です。page = true の場合、インプレッション数を増分するために [!DNL Target] のバックエンドに通知が送信されます。<br>通知は、オプション/ページがfalseに設定されている場合を除き、が呼び出さ `triggerView` れたときに常にデフォルトで送信されます。<br>**FALSE：** page = false の場合、インプレッション数を増分するための通知は送信されません。オファーを含むページ上のコンポーネントを再レンダリングする場合にのみ使用します。 |

## 例：True

アクティビティインプレッション数およびその他の指標の値を増加させるために Target バックエンドに通知を送信するための `triggerView()` 呼び出し。

```javascript
adobe.target.triggerView("homeView")
```

## 例：False

Target バックエンドにインプレッションをカウントするための通知を送信しないようにするための `triggerView()` 呼び出し。

```javascript
adobe.target.triggerView("homeView", {page: false})
```
