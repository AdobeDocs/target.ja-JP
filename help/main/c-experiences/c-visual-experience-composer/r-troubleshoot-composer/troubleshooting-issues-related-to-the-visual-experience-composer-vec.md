---
keywords: ターゲティング；visual experience composer;vec;visual experience composerのトラブルシューティング；トラブルシューティング；tls;tls 1.2
description: '[!UICONTROL Visual Experience Composer] （VEC）の問題のトラブルシューティング方法を説明します。'
title: '[!UICONTROL Visual Experience Composer]に関連する問題のトラブルシューティング方法を教えてください。'
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
TQID: https://experienceleague.adobe.com/VNkydzzU-WRRAL0pqQPOs-sKrY8a6DS5Go764UGh0Hs
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1042
ht-degree: 26%

---

# [!UICONTROL Visual Experience Composer]に関連する問題のトラブルシューティング

特定の条件で、[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）で表示の問題が発生することがあります。

## [!UICONTROL Visual Experience Composer]でweb サイトを開くと、[!DNL Target] ライブラリが読み込まれません。 （VEC のみ） {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

+++詳細
[!DNL Target]は、[!UICONTROL Visual Experience Composer]でweb サイトを開く際に2つのパラメーター（`mboxEdit=1`と`mboxDisable=1`）を追加します。

Web サイト（特にシングルページアプリ）で、あるページから別のページに移動する際にパラメーターをトリミングしたり、実際にパラメーターを削除したりする場合（ページのリロードを行わない場合）、[!DNL Target]機能が壊れ、[!DNL Target] ライブラリが読み込まれません。

この問題を防ぐには、この 2 つのパラメーターをトリミングまたは削除しないように設定します。

+++

## EEC でページが開かないか、読み込みに時間がかかります。 VEC でアクティビティやエクスペリエンスの読み込みに時間がかかります。 （VEC のみ） {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

+++詳細
[!UICONTROL Target] エクスペリエンスコンポーザーのページのパフォーマンスに影響する問題がいくつかあります。 よくある問題として以下のようなものがあります。

* ページに mbox がない。
* サイトでプロキシブロックを使用している。これにより、どちらのエクスペリエンスコンポーザーでもページを開くことが許可されません。
* サイトがサイト自体を iFrame で開くことを許可していない。

[!UICONTROL Enhanced Experience Composer]で問題が発生した場合は、[!UICONTROL Enhanced Experience Composer]をオフにして、代わりに[!UICONTROL Visual Experience Composer]を使用してください。

[!UICONTROL Enhanced Experience Composer]を無効にするには、**[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**&#x200B;に移動し、**[!UICONTROL Enable Enhanced Experience Composer]** オプションをオフにします。

コンソールに次のエラーメッセージが表示される場合があります。

![コンソールエラーメッセージ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

[!UICONTROL Visual Experience Composer]も[!UICONTROL Enhanced Experience Composer]も機能しない場合は、[!DNL Requestly] （[!DNL Chrome]または[!DNL Firefox]）などのブラウザー拡張機能または応答ヘッダーの変更（Firefox）を使用して、サイトのX フレーム ヘッダーのオプションを上書きし、iFramesに読み込めるようにして、VECを有効にします。 ブラウザー拡張機能を使用できない場合は、[ フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用してください。

>[!NOTE]
>
>次の情報に加えて、[!DNL Google Chrome]には[[!DNL Adobe Target] [!UICONTROL Visual Editing Helper]拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)を使用できます。

>[!NOTE]
>
>これらのプラグインは、VEC を編集する場合にのみ使用する必要があります。
>
>[!DNL Requestly]拡張機能の場合、ヘッダーを削除する必要がある場合は、次のいずれかの操作を行う必要があります。
>
>* VEC で開く URL の URL ルールを追加して、それらの URL についてのみヘッダーが削除されるようにします。
>
>* VEC で編集するときにはルールを有効にし、VEC を使用していないときはルールを無効にします。
>
>[!UICONTROL Modify Response Header]拡張機能（[!DNL Firefox]）の場合、URL ルールを追加できないため、次の操作を行う必要があります。
>
>* VEC で編集するときにはルールを有効にし、VEC を使用していないときはルールを無効にします。

**[!DNL Chrome]または[!DNL Firefox]で[!DNL Requestly]拡張機能を使用するには：**

1. [!UICONTROL Enhanced Experienced Composer]をオフにします。
1. [!DNL Requestly] ブラウザー拡張機能を[!DNL Chrome]または[!DNL Firefox]にインストールします。
1. 拡張機能を開いて、次を使用するように設定します。
1. **[!UICONTROL Modify headers]**&#x200B;を選択します。
1. 以下を入力します。

   * ルール名
   * 変更ルール

      * **[!UICONTROL Add]**&#x200B;を&#x200B;**[!UICONTROL Remove]**&#x200B;に切り替えます。
      * **[!UICONTROL Request]**&#x200B;を&#x200B;**[!UICONTROL Response]**&#x200B;に切り替えます。
      * ヘッダー名として &quot;X-Frame-Options&quot; と入力します。
      * 前述の手順を繰り返し、ヘッダー名に「x-frame-options」と入力します。

        >[!NOTE]
        >
        >[!DNL Requestly]を介して操作されるヘッダーでは、大文字と小文字が区別されます。

      * ソース URLの条件として&#x200B;**[!UICONTROL Equals]**&#x200B;を&#x200B;**[!UICONTROL Contains]**&#x200B;に変更し、VECに読み込もうとしているアクティビティのURLを入力します。

     ![chrome_extension image](assets/chrome_extension.png)

1. **[!UICONTROL Save]** をクリックします。

   ![要求画像](assets/requestly.png)

   これで、[!UICONTROL Visual Experience Composer]を使用してページをすばやく読み込めるようになります。

**[!UICONTROL Firefox]で[!DNL Modify Response Headers]拡張機能を使用するには：**

1. [!DNL Firefox]に[!UICONTROL Modify Response Headers]をインストールし、ブラウザーを再起動します。
1. [!DNL Firefox]拡張機能から、「応答ヘッダーを変更」拡張機能を選択します。
1. **[!UICONTROL Preferences]** をクリックします。
1. 「[!UICONTROL Action]」ドロップダウンから「**[!UICONTROL Filter]**」を選択します。
1. [!UICONTROL Header Name] フィールドに次のように入力します。**[!UICONTROL X-Frame-Options]**
1. 手順4と5を繰り返して、**[!UICONTROL x-frame-options]**&#x200B;を含むフィルターを追加します。
1. **[!UICONTROL Add]** をクリックします。
1. **[!UICONTROL Start]** をクリックします。

![Firefox拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

拡張機能を設定したら、[!DNL Target]を開きます。 [!UICONTROL Enhanced Experience Composer]が無効になっている場合でも、ページが[!UICONTROL Visual Experience Composer]に読み込まれるようになりました。

+++

## VEC にページが表示されません。（VEC のみ） {#does-not-load}

+++詳細
* VECとの最適な互換性は、最新バージョンの拡張機能によって保証されます：[[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper extension]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

  最新バージョンを使用しているかどうかを確認するには、[!UICONTROL Extensions] > [!UICONTROL Manage Extensions]に移動し、[!UICONTROL Details]をクリックします。

* [!UICONTROL Visual Experience Composer]には、Web ページで変更を実行するためにオーサリングライブラリが必要です。 これらのライブラリはat.js ライブラリに埋め込まれており、VECが使用されるたびに[!DNL Adobe] サーバーから拡張機能によってダウンロードされます。

  拡張機能は、at.jsまたは[!DNL Adobe Experience Platform Web SDK]が既にページに含まれているかどうかに関係なく、at.js ライブラリをダウンロードします。

  [!UICONTROL Administration] > [!UICONTROL Implementation] セクションで設定されたat.js ヘッダーに無効な変更が追加されていないことを確認します。

* iFrame内に埋め込まれた場合に、web ページが読み込み必須のリクエストをブロックしていないことを確認します。 これには、顧客web サイト、meta HTML タグ、またはx-frame-options ヘッダーに埋め込まれたframe-ancestors CSP ディレクティブまたはカスタム JS コードの使用が含まれます。

* Web ページのJavascriptがオーサリングライブラリに干渉していないことを確認します。 次の予約名を使用してファイルを使用またはインクルードしないでください。

   * `target-vec-helper.js`
   * `target-vec.js`
   * `target.js`
   * `admin.css`
   * `sizzle.js`
   * `mixContentCheck.html`

     さらに、これらのファイル内で定義された変数またはイベントを誤って上書きすると、VECで問題が発生する可能性があります。

* ブラウザーが、セキュリティで保護されているサイトのセキュリティで保護されていないページをブロックしています。

  ブラウザーのアドレスバーのURLの左側にあるアイコンをクリックし、**[!UICONTROL Disable protection on this page]**&#x200B;をクリックします

* 入力した URL が無効です。
* Web サイトがVECで読み込まれなかった場合、または予期しない動作をした場合は、Web サイトを[!DNL Target]で読み込む前に、ブラウザーでWeb サイトのCookieを受け入れることが修正される可能性があります。

+++

## [!UICONTROL Browse] モードを使用すると、VECが壊れているように見えます。 （VEC のみ） {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

+++詳細
[!UICONTROL Browse] モードを使用している間に、[!DNL Target] ライブラリが実装されていない（[at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=ja){target=_blank}または[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank}） URLにアクセスする場合、またはフレームバスターヘッダーを含むURLにアクセスする場合、VECが壊れているように見えます。 ブラウザーのセキュリティ上の懸念により、[!DNL Target]は移動したURLに適切にアクセスできないか、ページが読み込まれた場合、VEC URLが一貫して更新されません。

この問題は、VECが`<iframe>`でweb ページを読み込むために発生します。 ブラウザーの現在のセキュリティメカニズムは、同一オリジンのポリシーにより、[!DNL Target] UIが特定のフレームの要素にアクセスすることを禁止しています。 ブラウザーは、`location.href`などの情報を含む、別のオリジンのフレームにアクセスしようとするスクリプトをブロックします。

新しい[Visual Editing Helper拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)を使用して[!DNL Target] ライブラリをページに注入し、それらを最適に参照する必要があります。

+++

## [!UICONTROL Visual Experience Composer] での CSS の競合で発生する問題

+++詳細
エディターでweb ページを読み込む際に、表示に影響を与える可能性のあるCSS ファイルがあるかどうかを確認します。 例えば、ページ本文で`overflow: hidden` プロパティを使用すると、スクロールの問題やトリガークリックイベントが発生し、オーサリングのメニューが妨げられる可能性があります。

+++
