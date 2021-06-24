---
keywords: 実装;Mbox;mbox.js;mbox.js のダウンロード;mbox.js の設定
description: Adobe Targetのレガシーmbox.js実装について説明します。 Adobe Experience Platform Web SDK(AEP Web SDK)または最新バージョンのat.jsに移行します。
title: 'mbox.jsライブラリをダウンロードする方法を教えてください。 [!DNL Target] '
feature: at.js
role: Developer
exl-id: 92096b1b-a8a5-435b-8e62-24b5d15d392f
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 74%

---

# mbox.js のダウンロード

Target  Standard および Premium では Adobe Target mbox.js ファイルの修正バージョンを使用します。

>[!IMPORTANT]
>
>**mbox.js のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しは失敗し、デフォルトのコンテンツを表示して [!DNL Target] アクティビティを実行しているページには影響があります。
>
>サイトで発生する可能性のある問題を回避するため、すべてのお客様にこの日までに新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに移行することをお勧めします。 詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

新しい [!DNL Adobe Target][!UICONTROL  Visual Experience Editor] を使用するには、[!DNL mbox.js] ファイルの一部に JavaScript の行を追加する必要があります。

1. [!DNL Target Standard]で&#x200B;**[!UICONTROL 管理]** /**[!UICONTROL 実装]**&#x200B;をクリックします。
1. 「**[!UICONTROL mbox.js をダウンロード]**」をクリックし、プロンプトに従ってファイルを保存します。
1. （条件付き）[!DNL mbox.js] バージョン 60 以降を使用する場合、mbox がレスポンシブサイトのフリッカーをロードするまでデフォルトでページのコンテンツを自動的に表示にするようライブラリを設定します。

1. Web サイトに [!DNL mbox.js] の参照を作成します。

   [!DNL mbox.js] バージョン 57 以降、[!DNL mbox.js] 参照はページの `<head>` セクション内の任意の場所に配置できます。

   >[!IMPORTANT]
   >
   >バージョン 57 未満のバージョンの [!DNL mbox.js] を使用する場合、参照はページの `<head>` セクションの最後の項目として配置する必要があります。mbox.js 参照が最後の項目になっていないと、表示またはパフォーマンス上の深刻な問題が発生する可能性があります。

1. 保存した [!DNL mbox.js] ファイルを、コード内で指定したホスティング環境の場所にアップロードします。
