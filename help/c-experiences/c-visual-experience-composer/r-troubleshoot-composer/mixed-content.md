---
keywords: mixed content;secure;insecure;chrome;troubleshooting;vec;visual experience composer;unsecure;http;https;firefox;internet explorer
description: 安全なコンテンツと安全でないコンテンツが混在している場合、一部のブラウザーではページの表示がブロックされます。
title: ブラウザーで混合コンテンツを有効にする
feature: null
topic: Advanced,Standard,Classic
uuid: 6944ce97-ff73-4b61-b006-35862ff83ef1
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 35%

---


# Enabling mixed content in your browser{#enabling-mixed-content-in-your-browser}

混在コンテンツは、同じWebページを表示するためにHTTPS（セキュア） *と* HTTP（セキュア）の両方のコンテンツが読み込まれ、初期要求がHTTPSでセキュリティで保護されている場合に発生します。

最新のブラウザーでは、セキュリティで保護されたコンテンツが安全でないコンテンツと混在している場合、ページの表示がブロックされたり、警告メッセージが表示されたりする場合があります。

If the [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Target] tries to open a page containing mixed content, a message displays showing how to disable blocking in your browser so you can open an HTTP site or a site that has mixed calls (HTTPS and HTTP).

![混合内容警告](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

以前までは、このような混合コンテンツが許可されていない場合でも、アクティビティの作成時に、3 ステップのガイドによるワークフローのステップ 1 については一部の操作を実行することができました。[!DNL Target] では、ステップ 1 の操作がブロックされるようになりました。このメッセージが表示されたら、アクティビティの作成を続行する前に混合コンテンツを有効にする必要があります。

ブラウザーのセキュリティ設定によって、混合コンテンツや安全でない（HTTP）コンテンツが、安全な（HTTPS）ページやフレーム（VEC など）に読み込まれないようにブロックされている場合があります。ブラウザーのセキュリティ設定を無効にしたくない場合は、HTTPS の Web サイトが必要です。

Web サイトが安全でない（HTTP）ドメインで実行されている場合は、VEC によるアクティブな混合コンテンツの読み込みを許可する必要があります。

>[!NOTE]
>
>混合コンテンツの許可によって影響が生じるのは VEC のみです。ライブ Web サイトには影響しません。

詳しくは、*Mozilla Developer Network*（MDN）の Web サイトにある[混在コンテンツ](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content)を参照してください。

## Enabling mixed content in Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

安全な接続を介してサイトに訪問している場合、ChromeはWebページ上のコンテンツが安全に送信されたことを確認します。

Google Chrome ヘルプの[安全でないコンテンツを含むページ](https://support.google.com/chrome/answer/1342714?hl=en)に関する説明を参照してください。

最新バージョンのChrome（バージョン79.0.3945.117以降）でVECを使用している場合は、サイト設定を更新する必要があります。 サイトへの訪問者は、これらの手順を実行する必要はありません。

1. ロックまたは注意アイコンをクリックし、「 **[!UICONTROL サイトの設定]**」をクリックします。

   ![サイトの設定](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. 「 **[!UICONTROL セキュリティで保護されていないコンテンツ]**」までスクロールし、ドロップダウンリストを使用して「ブロック（デフォルト）」を「許可」に変更します。

   ![安全でないコンテンツ](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. VECページをリロードします。

## Enabling mixed content in Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

Firefox では、安全なコンテンツと安全でないコンテンツが混在しているページは、デフォルトではブロックされます。この設定は、[!DNL Target] を使用するように永久的に変更することをお勧めします。サイトへの訪問者は、これらの手順を実行する必要はありません。

1. Firefox で、アドレスバーに`about:config`を入力します。
1. Firefox に表示された警告メッセージを確認します。

   ![Firefoxの警告](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. 検索バーに「`block_active`」と入力 します。

   ![Firefoxブロックのアクティブ設定](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. ダブルクリック ` **[!UICONTROL security.mixed_content.block_active_content]**` .

   値を「True」から「False」に変更します。値が「False」と表示されたら、完了です。

   ![Firefoxのセキュリティ](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

この設定を変更した後、コンピューターを再起動することをお勧めします。

## Microsoft Edgeで混合コンテンツを有効にする

安全な接続を介してサイトに訪問している場合、Edgeは、Webページ上のコンテンツが安全に送信されたことを確認します。

最新バージョンのEdgeでVECを使用している場合は、サイト設定を更新する必要があります。 サイトへの訪問者は、これらの手順を実行する必要はありません。

1. ロックまたは注意アイコンをクリックし、「 **[!UICONTROL サイト権限]**」をクリックします。

   ![Microsoft Edgeでのサイト権限](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. 「 **[!UICONTROL セキュリティで保護されていないコンテンツ]**」までスクロールし、ドロップダウンリストを使用して「ブロック（デフォルト）」を「許可」に変更します。

   ![安全でないコンテンツ](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. VECページをリロードします。