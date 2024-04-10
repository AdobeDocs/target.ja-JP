---
keywords: ターゲット設定；visual experience composer;vec;visual experience composer のトラブルシューティング；トラブルシューティング；tls;tls 1.2
description: で問題のトラブルシューティングを行う方法を説明します [!UICONTROL Visual Experience Composer] （VEC）。
title: に関連する問題のトラブルシューティング方法 [!UICONTROL Visual Experience Composer]?
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: 7c0d0154b81fbd3f89a82b31cd18541a7f0ea1a7
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 24%

---

# に関連した問題のトラブルシューティング [!UICONTROL Visual Experience Composer]

で表示の問題が発生することがある [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）一定の条件下で。

## で Web サイトを開いたとき [!UICONTROL Visual Experience Composer], [!DNL Target] ライブラリが読み込まれない。 （VEC のみ） {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

[!DNL Target] 2 つのパラメーターを追加（`mboxEdit=1` および `mboxDisable=1`）を使用して、Web サイトをで開きます [!UICONTROL Visual Experience Composer].

Web サイト（特に単一ページアプリ）で、ページからページに移動する際に、パラメーターをトリミングしたり、実際に削除した場合（ページを再読み込みせずに）、 [!DNL Target] 機能によって機能が中断され、 [!DNL Target] ライブラリが読み込まれない。

この問題を防ぐには、この 2 つのパラメーターをトリミングまたは削除しないように設定します。

## EEC でページが開かないか、読み込みに時間がかかります。VEC でアクティビティやエクスペリエンスの読み込みに時間がかかります。（VEC のみ） {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

のページパフォーマンスに影響を与える問題がいくつかあります [!UICONTROL Target] 作曲家を体験しなさい。 よくある問題として以下のようなものがあります。

* ページに mbox がない。
* サイトでプロキシブロックを使用している。これにより、どちらのエクスペリエンスコンポーザーでもページを開くことが許可されません。
* サイトがサイト自体を iFrame で開くことを許可していない。

で問題が発生した場合 [!UICONTROL Enhanced Experience Composer]をオフにしてみてください [!UICONTROL Enhanced Experience Composer] を使用する [!UICONTROL Visual Experience Composer] その代わり。

を無効にするには [!UICONTROL Enhanced Experience Composer]に移動します。 **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** をオフにします。 **[!UICONTROL Enable Enhanced Experience Composer]** オプション。

コンソールに次のエラーメッセージが表示される場合があります。

![コンソールエラーメッセージ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

もし両方とも [!UICONTROL Visual Experience Composer] また、 [!UICONTROL Enhanced Experience Composer] 機能する、のようなブラウザー拡張機能を使用する [!DNL Requestly] （[!DNL Chrome] または [!DNL Firefox]）または応答ヘッダーを変更する（Firefox）。これにより、サイトの X-Frames ヘッダーオプションが上書きされ、これらのオプションを iFrames に読み込んで VEC が有効になります。 ブラウザー拡張機能を使用できない場合は、 [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>以下の情報に加えて、を使用できます。 [[!DNL Adobe Target] [!UICONTROL Visual Editing Helper] 拡張子](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) （用） [!DNL Google Chrome].


>[!NOTE]
>
>これらのプラグインは、VEC を編集する場合にのみ使用する必要があります。
>
>の場合 [!DNL Requestly] 拡張機能では、ヘッダーを削除する必要がある場合は常に、次のいずれかを実行する必要があります。
>
>* VEC で開く URL の URL ルールを追加して、それらの URL についてのみヘッダーが削除されるようにします。
>
>* VEC で編集するときにはルールを有効にし、VEC を使用していないときはルールを無効にします。
>
>の場合 [!UICONTROL Modify Response Header] 拡張子（[!DNL Firefox]）。URL ルールを追加できないので、次の手順を実行する必要があります。
>
>* VEC で編集するときにはルールを有効にし、VEC を使用していないときはルールを無効にします。

**を使用するには [!DNL Requestly] 拡張子： [!DNL Chrome] または [!DNL Firefox]:**

1. をオフにする [!UICONTROL Enhanced Experienced Composer].
1. のインストール [!DNL Requestly] のブラウザー拡張機能 [!DNL Chrome] または [!DNL Firefox].
1. 拡張機能を開いて、次を使用するように設定します。
1. を選択 **[!UICONTROL Modify headers]**.
1. 以下を入力します。

   * ルール名
   * 変更ルール

      * 切り替え **[!UICONTROL Add]** 対象： **[!UICONTROL Remove]**.
      * 切り替え **[!UICONTROL Request]** 対象： **[!UICONTROL Response]**.
      * ヘッダー名として &quot;X-Frame-Options&quot; と入力します。
      * 前述の手順を繰り返し、ヘッダー名に「x-frame-options」と入力します。

        >[!NOTE]
        >
        >経由で操作されるヘッダー [!DNL Requestly] では大文字と小文字が区別されます。

      * 変更 **[!UICONTROL Equals]** 対象： **[!UICONTROL Contains]** ソース URL の条件として、VEC に読み込もうとするアクティビティの URL を入力します。

     ![chrome_extension 画像](assets/chrome_extension.png)

1. **[!UICONTROL Save]** をクリックします。

   ![requestly 画像](assets/requestly.png)

   これで、を使用してページをすばやく読み込むことができます [!UICONTROL Visual Experience Composer].

**を使用するには [!DNL Modify Response Headers] 拡張子： [!UICONTROL Firefox]:**

1. のインストール [!UICONTROL Modify Response Headers] 日付： [!DNL Firefox] ブラウザーを再起動します。
1. から [!DNL Firefox] 拡張機能で、「応答ヘッダーを変更」拡張機能を選択します。
1. **[!UICONTROL Preferences]** をクリックします。
1. を選択 **[!UICONTROL Filter]** から [!UICONTROL Action] ドロップダウン。
1. が含まれる [!UICONTROL Header Name] フィールドに次を入力： **[!UICONTROL X-Frame-Options]**.
1. 手順 4 と 5 を繰り返して、次のフィルターを追加します **[!UICONTROL x-frame-options]**.
1. **[!UICONTROL Add]** をクリックします。
1. **[!UICONTROL Start]** をクリックします。

![Firefox 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

拡張機能を設定したら、を開きます [!DNL Target]. ページは、に読み込まれます。 [!UICONTROL Visual Experience Composer]（次の場合でも） [!UICONTROL Enhanced Experience Composer] が無効になっています。

## VEC にページが表示されません。（VEC のみ） {#does-not-load}

* VEC との最高の互換性は、拡張機能の最新バージョンによって確保されます。 [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper extension]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).

  最新バージョンを使用しているかどうかを確認するには、にアクセスしてください。 [!UICONTROL Extensions] > [!UICONTROL Manage Extensions] 次に、 [!UICONTROL Details].

* この [!UICONTROL Visual Experience Composer] web ページで変更を実行するには、オーサリングライブラリが必要です。 これらのライブラリは at.js ライブラリに埋め込まれ、から拡張機能によってダウンロードされます。 [!DNL Adobe] vec を使用するたびにサーバーを監視します。

  この拡張機能は、at.js か a.js かに関係なく、at.js ライブラリをダウンロードします [!DNL Adobe Experience Platform Web SDK] は既にページに含まれています。

  で設定された at.js ヘッダーに無効な変更が追加されていないことを確認します。 [!UICONTROL Administration] > [!UICONTROL Implementation] セクション。

* Web ページが、iFrame に埋め込まれた場合の読み込みに必須なリクエストをブロックしていないことを確認します。 これには、顧客の web サイト、メタHTMLタグ、x-frame-options ヘッダーに埋め込まれた、frame-ancestors CSP 指令またはカスタム JS コードの使用が含まれます。

* Web ページの JavaScript がオーサリングライブラリに干渉しないことを確認します。 次の予約名を使用したファイルを使用したりインクルードしたりしないでください。

   * `target-vec-helper.js`
   * `target-vec.js`
   * `target.js`
   * `admin.css`
   * `sizzle.js`
   * `mixContentCheck.html`

     さらに、これらのファイル内で定義された変数やイベントを誤って上書きすると、VEC で問題が発生する可能性があります。

* ブラウザーが、セキュリティで保護されているサイトのセキュリティで保護されていないページをブロックしています。

  ブラウザーのアドレスバーにある URL の左側のアイコンをクリックし、 **[!UICONTROL Disable protection on this page]**

* 入力した URL が無効です。
* Web サイトが VEC への読み込みに失敗した場合や、予期しない動作が発生した場合は、で web サイトを読み込む前に、ブラウザーで web サイトの Cookie を受け入れることで解決できる可能性があります [!DNL Target].

## 参照モードを使用すると、VEC が壊れているように見えます。（VEC のみ） {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

参照モードの使用中に、が含まれていない URL にアクセスした場合 [!DNL Target] 実装されたライブラリ （[at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=ja){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank}）またはフレームバスターヘッダーが含まれている場合、VEC が壊れているように見えます。 ブラウザーのセキュリティ上の問題により、 [!DNL Target] 移動先の URL に正しくアクセスできないか、ページが読み込まれても VEC URL が一貫して更新されない。

この問題は、VEC が `<iframe>`. ブラウザーの現在のセキュリティメカニズムでは、 [!DNL Target] 同じオリジンポリシーが原因で、UI が指定のフレームの要素にアクセスできない。 ブラウザーが、別の接触チャネルを持ち、 `location.href`.

新しいを使用する必要があります [Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) （推奨）または [古い拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) を注入する [!DNL Target] ページを最適に参照するために、ページにライブラリ化します。

## での CSS の競合に起因する問題 [!UICONTROL Visual Experience Composer]

エディターで web ページを読み込む際に、表示に影響を与える可能性のある CSS ファイルが存在するかどうかを確認します。 例えば、 `overflow: hidden` ページ本文のプロパティを使用すると、スクロールの問題やトリガーのクリックイベントが発生して、オーサリングのメニューが妨げられる可能性があります。
