---
keywords: 混合コンテンツ；安全な；安全でない；chrome；トラブルシューティング；vec;visual experience composer；安全でない；http;https;firefox;internet explorer
description: 安全なコンテンツと安全でないコンテンツが混在している場合、一部のブラウザーではページの表示がブロックされます。Chrome、Firefox および Edge で混合コンテンツを有効にする方法を説明します。
title: ブラウザーで混在するコンテンツを有効にする方法を教えてください。
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 26%

---

# ブラウザーで混在したコンテンツを有効化する

混合コンテンツは、最初のリクエストが HTTPS で保護されているが HTTPS の場合に発生します *および* Web ページを表示するために HTTP コンテンツが読み込まれます。 HTTPS コンテンツはセキュリティで保護されています。 HTTP コンテンツは安全ではありません。

安全なコンテンツと安全でないコンテンツが混在している場合、最新のブラウザーではページの表示がブロックされたり、警告メッセージが表示されたりする場合があります。

警告メッセージは、 [!UICONTROL Visual Experience Composer] (VEC) [!DNL Target] 混合コンテンツを含むページを開こうとします。 このメッセージでは、ブラウザーでブロックを無効にする方法を示します。 ブロックを無効にすると、HTTP サイトまたは複数の呼び出し（HTTPS と HTTP）が混在するサイトを開くことができます。

![混合コンテンツの警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

以前までは、このような混合コンテンツが許可されていない場合でも、アクティビティの作成時に、3 ステップのガイドによるワークフローのステップ 1 については一部の操作を実行することができました。[!DNL Target] では、ステップ 1 の操作がブロックされるようになりました。このメッセージが表示されたら、アクティビティの作成を続行する前に混合コンテンツを有効にする必要があります。

ブラウザーのセキュリティ設定によって、混合コンテンツや安全でない（HTTP）コンテンツが、安全な（HTTPS）ページやフレーム（VEC など）に読み込まれないようにブロックされている場合があります。ブラウザーのセキュリティ設定を無効にしたくない場合は、HTTPS Web サイトが必要です。

Web サイトが安全でない (HTTP) ドメインで実行されている場合、VEC によるアクティブな混合コンテンツの読み込みを許可する必要があります。

>[!NOTE]
>
>混合コンテンツの許可によって影響が生じるのは VEC のみです。ライブ Web サイトには影響しません。

詳しくは、*Mozilla Developer Network*（MDN）の Web サイトにある[混在コンテンツ](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content)を参照してください。

## Google Chrome で混合コンテンツを有効化 {#task_FF297A08F66E47A588C14FD67C037B3A}

安全な接続を介してサイトに訪問している場合、Chrome は Web ページ上のコンテンツが安全に転送されたことを確認します。

参照：[このページには安全でないコンテンツが含まれています](https://support.google.com/chrome/answer/1342714?hl=en)」( Google Chrome ヘルプ ) を参照してください。

最新バージョンの Chrome（バージョン 79.0.3945.117 以降）で VEC を使用している場合は、サイト設定を更新する必要があります。 サイトの訪問者は、これらの手順を完了する必要はありません。

1. ロック（注意）アイコンをクリックし、 **[!UICONTROL サイト設定]**.

   ![サイト設定](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. スクロールして **[!UICONTROL 安全でないコンテンツ]**&#x200B;をクリックし、ドロップダウンリストを使用して「ブロック（デフォルト）」を「許可」に変更します。

   ![安全でないコンテンツ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. VEC ページをリロードします。

## Mozilla Firefox で混合コンテンツを有効化 {#task_5448763B8DC941FD80F84041AEF0A14D}

Firefox では、安全なコンテンツと安全でないコンテンツが混在しているページは、デフォルトではブロックされます。この設定は、[!DNL Target] を使用するように永久的に変更することをお勧めします。サイトの訪問者は、これらの手順を完了する必要はありません。

1. Firefox で、アドレスバーに`about:config`を入力します。
1. Firefox に表示された警告メッセージを確認します。

   ![Firefox 警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. 検索バーに「`block_active`」と入力 します。

   ![Firefox block_active 設定](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. ダブルクリック ` **[!UICONTROL security.mixed_content.block_active_content]**` .

   値を「True」から「False」に変更します。値が「False」と表示されたら、完了です。

   ![Firefox のセキュリティ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

この設定を変更した後、コンピュータを再起動します。

## Microsoft Edge で混合コンテンツを有効化

安全な接続を介してサイトに訪問している場合、Edge は Web ページ上のコンテンツが安全に転送されたことを確認します。

最新バージョンの Edge で VEC を使用している場合は、サイト設定を更新する必要があります。 サイトの訪問者は、これらの手順を完了する必要はありません。

1. ロック（注意）アイコンをクリックし、 **[!UICONTROL サイトの権限]**.

   ![Microsoft Edge でのサイト権限](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. スクロールして **[!UICONTROL 安全でないコンテンツ]**&#x200B;をクリックし、ドロップダウンリストを使用して「ブロック（デフォルト）」を「許可」に変更します。

   ![安全でないコンテンツ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. VEC ページをリロードします。