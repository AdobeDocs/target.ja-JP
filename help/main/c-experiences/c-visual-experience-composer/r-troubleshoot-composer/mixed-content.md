---
keywords: 混在コンテンツ;安全な;安全でない;chrome;トラブルシューティング;vec;visual experience composer;安全でない;http;https;firefox;internet explorer
description: '[!DNL Chrome]、[!DNL Firefox]および[!DNL Edge]で混在コンテンツを有効にする方法について説明します。'
title: ブラウザーで混在したコンテンツを有効にする方法
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
TQID: 'https://experienceleague.adobe.com/6Q1UvNmU-vSr9sp3pe2JN-wkjFUMWFxtPkgQegArrVw'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 11%
---
# ブラウザーでの混在コンテンツの有効化 {#mixed-content}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;混在コンテンツを[!DNL Google Chrome]、[!DNL Mozilla Firefox]、[!DNL Microsoft Edge]で有効にして、**[!UICONTROL Visual Experience Composer]** （VEC）で混在コンテンツを含むHTTP サイトとサイトを開く方法を説明します。

>[!ENDSHADEBOX]

ページには、HTTPS経由で安全にリクエストされた場合に混在コンテンツが含まれますが、HTTPSとHTTP コンテンツの両方が読み込まれます。 HTTPS コンテンツは安全ですが、HTTP コンテンツは安全ではないため、最新のブラウザーでは、そのようなページをブロックしたり、警告メッセージを表示したりする可能性があります。

[!DNL Adobe Target]の&#x200B;**[!UICONTROL Visual Experience Composer]** （VEC）が混在コンテンツを含むページを開こうとすると、ブラウザーでブロッキングを無効にする指示を含む警告メッセージが表示されます。 ブロッキングを無効にすると、HTTP サイトまたは混在コンテンツ（HTTPSとHTTP）を持つサイトを開くことができます。

![ ブラウザーの再読み込みプロンプトのイラストの横に、ブラウザースクリプトの読み込みを許可する必要があるというメッセージが表示されたアクティビティ作成ページ ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

以前は、3段階のガイド付きワークフローの手順1の一部のアクションは、混在コンテンツが許可されていない場合でも使用できたままでした。 [!DNL Target]は、手順1のすべてのアクションをブロックするようになりました。アクティビティの作成を続行するには、混在コンテンツを有効にする必要があります。

ブラウザーのセキュリティ設定により、VECなどのセキュア（HTTPS）ページまたはフレームに読み込まれる安全でない（HTTP）コンテンツがブロックされる場合があります。 これらの設定を変更する代わりに、HTTPS web サイトを使用します。 Web サイトが安全でない（HTTP） ドメインで実行されている場合、VECはアクティブな混在コンテンツの読み込みを許可する必要があります。

>[!IMPORTANT]
>
>混在コンテンツを許可すると、VECにのみ影響し、ライブ web サイトには影響しません。

詳しくは、*Mozilla Developer Network*（MDN）の Web サイトにある[混在コンテンツ](https://developer.mozilla.org/ja/docs/Web/Security/Mixed_content)を参照してください。

## [!DNL Google Chrome]で混在コンテンツを有効にする

[!DNL Chrome]は、安全な接続を通じて要求されたページのコンテンツが安全に送信されたかどうかを確認します。 Google Chrome ヘルプの[安全でないサイトに関する警告の管理](https://support.google.com/chrome/answer/99020?hl=ja)を参照してください。

最新バージョンの[!DNL Chrome] （バージョン 79.0.3945.117以降）でVECを使用するには、次のようにサイト設定を更新します。 サイトへの訪問者は、これらの手順を完了する必要はありません。

1. ロック（注意）アイコンをクリックし、**[!UICONTROL サイト設定]**&#x200B;をクリックします。

   ![接続メニューが開き、サイト設定がハイライト表示されたChromeのアドレスバー](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. **[!UICONTROL 安全でないコンテンツ]**&#x200B;で、ドロップダウンリストの「ブロック（デフォルト）」を「許可」に変更します。

   ![安全でないコンテンツ ドロップダウンを開き、選択したコンテンツを許可する](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)のChrome サイト設定

1. VEC ページをリロードします。

## [!DNL Mozilla Firefox]で混在コンテンツを有効にする

既定では、[!DNL Firefox]は安全でないコンテンツを混在させるページをブロックするので、[!DNL Target]を使用するには、この設定を完全に変更する必要があります。 サイトへの訪問者は、これらの手順を完了する必要はありません。

1. [!DNL Firefox]に、アドレスバーに`about:config`と入力します。
1. [!DNL Firefox]が表示する警告メッセージを確認します。

   ![ リスクを受け入れて続行ボタンを使用して、約:configの注意警告ページを読み進める](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. 検索バーに`block_active`と入力します。

   security.mixed_content.block_active_contentがtrue](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)に設定されているblock_activeを![Firefox about:config検索

1. `security.mixed_content.block_active_content`をダブルクリックします。

   値が「True」から「False」に変更されます。 値が「False」の場合、変更は完了します。

   security.mixed_content.block_active_contentがfalse](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)に設定されていることを示す![Firefox about:config

1. この設定を変更した後、コンピューターを再起動します。

## [!DNL Microsoft Edge]で混在コンテンツを有効にする

[!DNL Edge]は、安全な接続を通じて要求されたページのコンテンツが安全に送信されたかどうかを確認します。 最新バージョンの[!DNL Edge]でVECを使用するには、次のようにサイト設定を更新します。 サイトへの訪問者は、これらの手順を完了する必要はありません。

1. [!DNL Edge]で、メニューバーの&#x200B;**[!DNL Microsoft Edge]**&#x200B;をクリックし、**[!UICONTROL 設定]**&#x200B;をクリックしてから、**Cookieとサイト権限**&#x200B;をクリックします。
1. **[!UICONTROL 安全でないコンテンツ]**&#x200B;までスクロールして、クリックします。
1. **[!UICONTROL 許可]**&#x200B;の横にある&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックし、安全でないコンテンツを許可するサイトを入力してから、**[!UICONTROL 追加]**&#x200B;をクリックします。
1. VEC ページをリロードします。
