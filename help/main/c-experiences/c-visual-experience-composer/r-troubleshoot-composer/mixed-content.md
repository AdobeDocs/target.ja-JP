---
keywords: 混在コンテンツ;安全な;安全でない;chrome;トラブルシューティング;vec;visual experience composer;安全でない;http;https;firefox;internet explorer
description: ' [!DNL Chrome]、 [!DNL Firefox]、 [!DNL Edge] で混在したコンテンツを有効にする方法について説明します。'
title: ブラウザーで混在したコンテンツを有効にする方法
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
source-git-commit: c5b43faa2fc55c2c8737e586cfdfaa1444a05880
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 87%

---

# ブラウザーで混在したコンテンツを有効化する

混在コンテンツは、最初のリクエストが HTTPS で保護されているが、Web ページを表示するために HTTPS コンテンツ&#x200B;*と* HTTP コンテンツが読み込まれる場合に発生します。HTTPS コンテンツはセキュリティで保護されています。HTTP コンテンツは安全ではありません。

安全なコンテンツと安全でないコンテンツが混在している場合、最新のブラウザーではページの表示がブロックされたり、警告メッセージが表示されたりする場合があります。

[!UICONTROL Visual Experience Composer] の [!DNL Adobe Target] （VEC）が混合コンテンツを含むページを開こうとすると、警告メッセージが表示されます。 このメッセージでは、ブラウザーでブロックを無効にする方法を示します。ブロックを無効にすると、HTTP サイトまたは（HTTPS と HTTP の）コンテンツが混在するサイトを開くことができます。

![混在コンテンツの警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

以前までは、このような混在コンテンツが許可されていない場合でも、アクティビティの作成時に、3 ステップのガイドによるワークフローのステップ 1 については一部の操作を実行することができました。[!DNL Target] では、ステップ 1 の操作がブロックされるようになりました。このメッセージが表示された場合は、混合コンテンツを許可しないとアクティビティの作成を続行できません。

ブラウザーのセキュリティ設定によって、混合コンテンツや安全でない（HTTP）コンテンツが、安全な（HTTPS）ページやフレーム（VEC など）に読み込まれないようにブロックされている場合があります。ブラウザーのセキュリティ設定を無効にしたくない場合は、HTTPS の web サイトが必要です。

Web サイトが安全でない（HTTP）ドメインで実行されている場合は、VEC によるアクティブな混在コンテンツの読み込みを許可する必要があります。

>[!IMPORTANT]
>
>混在コンテンツの許可によって影響が生じるのは VEC のみです。ライブ web サイトには影響しません。

詳しくは、*Mozilla Developer Network*（MDN）の Web サイトにある[混在コンテンツ](https://developer.mozilla.org/ja/docs/Web/Security/Mixed_content)を参照してください。

## [!DNL Google Chrome] で混在したコンテンツを有効にする {#task_FF297A08F66E47A588C14FD67C037B3A}

安全な接続を介してサイトにアクセスしている場合は、[!DNL Chrome] は web ページ上のコンテンツが安全に送信されたことを確認します。

Google Chrome ヘルプの[安全でないサイトに関する警告の管理](https://support.google.com/chrome/answer/99020?hl=ja)を参照してください。

最新バージョンの [!DNL Chrome]（バージョン 79.0.3945.117 以降）で VEC を使用している場合は、サイト設定を更新する必要があります。サイトの訪問者は、これらの手順を完了する必要はありません。

1. ロック（注意）アイコン、「**[!UICONTROL Site settings]**」の順にクリックします。

   ![サイト設定](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. スクロールして **[!UICONTROL Insecure content]** に移動し、ドロップダウンリストを使用して「ブロック （デフォルト）」を「許可」に変更します。

   ![安全でないコンテンツ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. VEC ページをリロードします。

## [!DNL Mozilla Firefox] で混在したコンテンツを有効にする {#task_5448763B8DC941FD80F84041AEF0A14D}

[!DNL Firebox] では、安全なコンテンツと安全でないコンテンツが混在しているページは、デフォルトではブロックされます。この設定は、[!DNL Target] を使用するように永続的に変更することをお勧めします。サイトの訪問者は、これらの手順を完了する必要はありません。

1. Firefox で、アドレスバーに「`about:config`」と入力します。
1. [!DNL Firefox] で表示される警告メッセージを確認します。

   ![Firefox 警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. 検索バーに「`block_active`」と入力 します。

   ![Firefox block_active 設定](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. ` **[!UICONTROL security.mixed_content.block_active_content]**` をダブルクリックします。

   値を「True」から「False」に変更します。値が「False」と表示されたら、完了です。

   ![Firefox のセキュリティ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

1. この設定を変更した後、コンピューターを再起動します。

## [!DNL Microsoft Edge] で混在したコンテンツを有効にする

安全な接続を介してサイトにアクセスしている場合は、[!DNL Edge] は web ページ上のコンテンツが安全に送信されたことを確認します。

最新バージョンの [!DNL Edge] で VEC を使用している場合は、サイト設定を更新する必要があります。サイトの訪問者は、これらの手順を完了する必要はありません。

1. [!DNL Edge] で、メニューバーの「**[!DNL Microsoft Edge]**」をクリック **[!UICONTROL Settings]**、「**Cookie とサイト権限**」をクリックします。

1. **[!UICONTROL Insecure content]** までスクロールします。

1. [**[!UICONTROL Insecure content]**] をクリックし、[**[!UICONTROL Add]**] の横にある [**[!UICONTROL Allow]**] をクリックして、セキュリティで保護されていないコンテンツを許可するサイトを追加し、[**[!UICONTROL Add]**] をクリックします。

1. VEC ページをリロードします。
