---
keywords: 混在コンテンツ;安全な;安全でない;chrome;トラブルシューティング;vec;visual experience composer;安全でない;http;https;firefox;internet explorer
description: で混合コンテンツを有効にする方法を説明します。 [!DNL Chrome], [!DNL Firefox]、および [!DNL Edge].
title: ブラウザーで混在するコンテンツを有効にする方法
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
source-git-commit: c5b43faa2fc55c2c8737e586cfdfaa1444a05880
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 64%

---

# ブラウザーで混在したコンテンツを有効化する

混在コンテンツは、最初のリクエストが HTTPS で保護されているが、Web ページを表示するために HTTPS コンテンツ&#x200B;*と* HTTP コンテンツが読み込まれる場合に発生します。HTTPS コンテンツはセキュリティで保護されています。HTTP コンテンツは安全ではありません。

安全なコンテンツと安全でないコンテンツが混在している場合、最新のブラウザーではページの表示がブロックされたり、警告メッセージが表示されたりする場合があります。

[!DNL Adobe Target] の [!UICONTROL Visual Experience Composer]（VEC）が混合コンテンツを含むページを開こうとすると、警告メッセージが表示されます。このメッセージでは、ブラウザーでブロックを無効にする方法を示します。ブロックを無効にすると、HTTP サイトまたは混合コンテンツ（HTTPS と HTTP）を持つサイトを開くことができます。

![混在コンテンツの警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

以前までは、このような混在コンテンツが許可されていない場合でも、アクティビティの作成時に、3 ステップのガイドによるワークフローのステップ 1 については一部の操作を実行することができました。[!DNL Target] では、ステップ 1 の操作がブロックされるようになりました。このメッセージが表示された場合は、混合コンテンツを許可しないとアクティビティの作成を続行できません。

ブラウザーのセキュリティ設定によって、混合コンテンツや安全でない（HTTP）コンテンツが、安全な（HTTPS）ページやフレーム（VEC など）に読み込まれないようにブロックされている場合があります。ブラウザーのセキュリティ設定を無効にしたくない場合は、HTTPS の web サイトが必要です。

Web サイトが安全でない（HTTP）ドメインで実行されている場合は、VEC によるアクティブな混在コンテンツの読み込みを許可する必要があります。

>[!IMPORTANT]
>
>混在コンテンツの許可によって影響が生じるのは VEC のみです。ライブ web サイトには影響しません。

詳しくは、*Mozilla Developer Network*（MDN）の Web サイトにある[混在コンテンツ](https://developer.mozilla.org/ja/docs/Web/Security/Mixed_content)を参照してください。

## での混在するコンテンツの有効化 [!DNL Google Chrome] {#task_FF297A08F66E47A588C14FD67C037B3A}

安全な接続を介してサイトに訪問する場合は、 [!DNL Chrome] web ページ上のコンテンツが安全に送信されたことを確認します。

参照：[安全でないサイトに関する警告を管理する](https://support.google.com/chrome/answer/99020?hl=ja)」( Google Chrome ヘルプ ) を参照してください。

VEC をの最新バージョンで使用している場合 [!DNL Chrome] （バージョン 79.0.3945.117 以降）、サイト設定を更新する必要があります。 サイトの訪問者は、これらの手順を完了する必要はありません。

1. ロック（注意）アイコン、**[!UICONTROL サイト設定]**&#x200B;の順にクリックします。

   ![サイト設定](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. スクロールして&#x200B;**[!UICONTROL 安全でないコンテンツ]**&#x200B;に移動し、ドロップダウンリストを使用して「ブロック (デフォルト)」を「許可」に変更します。

   ![安全でないコンテンツ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. VEC ページをリロードします。

## での混在するコンテンツの有効化 [!DNL Mozilla Firefox] {#task_5448763B8DC941FD80F84041AEF0A14D}

デフォルトでは、 [!DNL Firebox] は、安全なコンテンツと安全でないコンテンツが混在するページをブロックします。 この設定を恒久的に変更して、 [!DNL Target]. サイトの訪問者は、これらの手順を完了する必要はありません。

1. Firefox で、アドレスバーに`about:config`を入力します。
1. 次の手順で表示された警告メッセージを確認 [!DNL Firefox].

   ![Firefox 警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. 検索バーに「`block_active`」と入力 します。

   ![Firefox block_active 設定](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. ` **[!UICONTROL security.mixed_content.block_active_content]**` をダブルクリックします。

   値を「True」から「False」に変更します。値が「False」と表示されたら、完了です。

   ![Firefox のセキュリティ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

1. この設定を変更した後、コンピューターを再起動します。

## での混在するコンテンツの有効化 [!DNL Microsoft Edge]

安全な接続を介してサイトに訪問する場合は、 [!DNL Edge] web ページ上のコンテンツが安全に送信されたことを確認します。

VEC をの最新バージョンで使用している場合 [!DNL Edge]を更新する場合は、サイトの設定を更新する必要があります。 サイトの訪問者は、これらの手順を完了する必要はありません。

1. In [!DNL Edge]をクリックし、 **[!DNL Microsoft Edge]** メニューバーで、 **[!UICONTROL 設定]**&#x200B;を選択し、次に **Cookie とサイトの権限**.

1. スクロールして **[!UICONTROL 安全でないコンテンツ]**.

1. クリック **[!UICONTROL 安全でないコンテンツ]**&#x200B;を選択し、次に **[!UICONTROL 追加]** 次の **[!UICONTROL 許可]**&#x200B;安全でないコンテンツを許可するサイトを追加し、「 **[!UICONTROL 追加]**.

1. VEC ページをリロードします。
