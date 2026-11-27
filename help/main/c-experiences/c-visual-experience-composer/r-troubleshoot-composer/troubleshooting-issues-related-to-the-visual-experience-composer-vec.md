---
keywords: ターゲティング；visual experience composer;vec;visual experience composerのトラブルシューティング；トラブルシューティング；tls;tls 1.2
description: '[!UICONTROL Visual Experience Composer] （VEC）の問題のトラブルシューティング方法について説明します。'
title: '[!UICONTROL Visual Experience Composer]に関連する問題のトラブルシューティング方法を教えてください。'
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
TQID: 'https://experienceleague.adobe.com/VNkydzzU-WRRAL0pqQPOs-sKrY8a6DS5Go764UGh0Hs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 4%
---
# [!UICONTROL Visual Experience Composer]に関連する問題のトラブルシューティング {#vec-issues}

>[!BEGINSHADEBOX]

**このページ：** **[!UICONTROL Visual Experience Composer]** （VEC）のみに影響する問題を解決する方法を説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target] **[!UICONTROL Visual Experience Composer]** （VEC）で、特定の条件の下で表示の問題が発生することがあります。 以下の項目では、VECのみに影響する問題とその解決方法について説明します。

+++ VECでweb サイトを開いたときに[!DNL Target] ライブラリが読み込まれない

Web サイトが&#x200B;**[!UICONTROL Visual Experience Composer]**&#x200B;で開かれると、[!DNL Target]はパラメーター`mboxEdit=1`と`mboxDisable=1`をURLに追加します。

ページをリロードせずにページ間を移動する際に、これらのパラメーターをトリミングまたは削除するweb サイト（特にシングルページアプリケーション）は、[!DNL Target]機能を壊し、[!DNL Target] ライブラリが読み込まれません。 この問題を回避するには、両方のパラメーターをURLに保持します。

+++

+++ ページがEECで開かない、または読み込みが遅い、またはアクティビティとエクスペリエンスがVECで読み込みが遅い

[!DNL Target] エクスペリエンスコンポーザーのページのパフォーマンスに影響する問題がいくつかあります。 最も一般的なものは次のとおりです。

* このページにはmboxがありません。
* このサイトでは、プロキシブロッキングを使用しています。これにより、どのExperience Composerでもページを開くことができなくなります。
* このサイトでは、iFrameでサイトを開くことはできません。

**[!UICONTROL Enhanced Experience Composer]**&#x200B;で問題が発生した場合は、これをオフにして&#x200B;**[!UICONTROL Visual Experience Composer]**&#x200B;を代わりに使用してください。 これを行うには、**[!UICONTROL 管理]** > **[!UICONTROL Visual Experience Composer]**&#x200B;に移動し、**[!UICONTROL 拡張Experience Composer]**&#x200B;を有効にするオプションをオフにします。

コンソールに次のエラーメッセージが表示される場合があります。

![X-Frame-OptionsがSAMEORIGIN](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)に設定されているため、ページがフレーム内に表示されることを拒否されたというブラウザーコンソールエラーメッセージ

どちらのコンポーザーも機能しない場合、[!DNL Requestly] （[!DNL Chrome]または[!DNL Firefox]）や応答ヘッダーの変更（[!DNL Firefox]）など、サイトのX-Frame-Options ヘッダーを上書きするブラウザー拡張機能により、サイトがiFrameに読み込まれるようになり、VECが有効になります。 ブラウザー拡張機能を使用できない場合は、[ フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用してください。 [!DNL Google Chrome]の[[!DNL Adobe Target] **[!UICONTROL Visual Editing Helper ]**拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)も、以下の手順に加えて使用できます。

>[!NOTE]
>
>これらの拡張機能は、VEC編集のみを目的としています。
>
>[!DNL Requestly]では、ヘッダーを削除する必要がある場合は、次のいずれかの操作を行います。
>
>* VECで開くURLのURL ルールを追加して、これらのURLに対してのみヘッダーが削除されるようにします。
>* VECでの編集中にルールを有効にし、VECが使用されていない場合はルールを無効にします。
>
>**[!UICONTROL 応答ヘッダーを変更]** （[!DNL Firefox]）では、URL ルールは使用できません。そのため、VECでの編集中はルールを有効にし、VECが使用されていないときはルールを無効にする必要があります。

拡張機能を設定すると、**[!UICONTROL 拡張Experience Composer]**&#x200B;が無効になっている場合でも、**[!UICONTROL Visual Experience Composer]**&#x200B;でページが読み込まれます。

+++

+++ RequestlyでX-Frame-Options ヘッダーを削除する（ChromeまたはFirefox）

1. **[!UICONTROL Enhanced Experience Composer]**&#x200B;をオフにします。
1. [!DNL Requestly] ブラウザー拡張機能を[!DNL Chrome]または[!DNL Firefox]にインストールします。
1. 拡張機能を開き、**[!UICONTROL ヘッダーを変更]**&#x200B;を選択します。
1. ルール名を入力します。
1. 修正ルールで、ヘッダーを削除するルールを作成します。

   * 「**[!UICONTROL Add（追加）]**」を「**[!UICONTROL Remove（削除）]**」に切り替えます。
   * 「**[!UICONTROL Request（リクエスト）]**」を「**[!UICONTROL Response（応答）]**」に切り替えます。
   * ヘッダー名として &quot;X-Frame-Options&quot; と入力します。

1. 前の手順を繰り返し、ヘッダー名として「x-frame-options」と入力します。

   >[!NOTE]
   >
   >[!DNL Requestly]で操作されるヘッダーでは、大文字と小文字が区別されます。

1. ソース URLの条件として&#x200B;**[!UICONTROL Equals]**&#x200B;を&#x200B;**[!UICONTROL Contains]**&#x200B;に変更し、VECに読み込むアクティビティのURLを入力します。

   ![Adobe.com](assets/chrome_extension.png)を含むURLのX-Frame-Options応答ヘッダーを削除するIframe バストリングコードをバイパスという名前のルールをリクエストします

1. 「**[!UICONTROL Save]**」をクリックします。

   ![すべてのURLのX-FRAME-OPTIONSおよびX-frame-options応答ヘッダーを削除するルール ](assets/requestly.png)

これで、**[!UICONTROL Visual Experience Composer]**&#x200B;でページを素早く読み込めるようになりました。

+++

+++ 応答ヘッダーの変更によるX-Frame-Options ヘッダーの削除（Firefox）

1. [!DNL Modify Response Headers]拡張機能を[!DNL Firefox]にインストールし、ブラウザーを再起動します。
1. [!DNL Firefox]拡張機能から、[!DNL Modify Response Headers]拡張機能を選択します。
1. 「**[!UICONTROL 環境設定]**」をクリックします。
1. 「**[!UICONTROL アクション]**」ドロップダウンリストから「**[!UICONTROL フィルター]**」を選択します。
1. 「**[!UICONTROL ヘッダー名]**」フィールドに、**[!UICONTROL X-Frame-Options]**&#x200B;と入力します。
1. 前の2つの手順を繰り返して、**[!UICONTROL x-frame-options]**&#x200B;のフィルターを追加します。
1. 「**[!UICONTROL 追加]**」をクリックします。
1. 「**[!UICONTROL Start（開始）]**」をクリックします。

![X-Frame-Options ヘッダーにフィルターが有効と表示された状態でFirefoxの応答ヘッダーウィンドウを変更する](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

+++

+++ VECにページが表示されない

次の原因を確認します。

* **拡張機能バージョン：** [[!DNL Adobe Experience Cloud] **[!UICONTROL Visual Editing Helper ]**拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)の最新バージョンは、VECとの最適な互換性を提供します。 インストール済みのバージョンを確認するには、**[!UICONTROL &#x200B;拡張機能&#x200B;]**>**[!UICONTROL &#x200B;拡張機能の管理&#x200B;]**に移動し、**[!UICONTROL &#x200B;詳細&#x200B;]**をクリックします。
* **オーサリングライブラリ：** VECは、web ページを変更するためにオーサリングライブラリを必要としています。 これらはat.js ライブラリに埋め込まれており、at.jsまたは[!DNL Adobe Experience Platform Web SDK]が既にページ上にあるかどうかにかかわらず、VECが使用されるたびに[!DNL Adobe] サーバーから拡張機能がダウンロードされます。 **[!UICONTROL 管理]**/**[!UICONTROL 実装]**&#x200B;で設定されたat.js ヘッダーに無効な変更が含まれていないことを確認してください。
* **ブロックされた要求：** ページは、iFrameに埋め込まれた場合に読み込みに必須の要求をブロックしてはなりません。 ブロックには、`frame-ancestors` CSP ディレクティブ、web サイト内のカスタム JavaScript コード、meta HTML タグ、および`x-frame-options` ヘッダーが含まれます。
* **予約済みのファイル名：** ページのJavaScriptがオーサリングライブラリに影響を与えることはありません。 次の予約名を持つファイルは使用しないでください。

  * `target-vec-helper.js`
  * `target-vec.js`
  * `target.js`
  * `admin.css`
  * `sizzle.js`
  * `mixContentCheck.html`

  これらのファイルで定義されている変数またはイベントを誤って上書きすると、VECに問題が発生する可能性もあります。

* **安全なサイト上の安全でないページ：** ブラウザーがページをブロックします。 アドレスバーのURLの左側にあるアイコンをクリックし、**[!UICONTROL このページの保護を無効にする]**&#x200B;をクリックします。
* **無効なURL:**&#x200B;入力されたURLが無効です。
* **Cookie:** Web サイトがVECで読み込まれなかったり、予期せず動作した場合は、[!DNL Target]でWeb サイトを読み込む前にブラウザーでCookieを受け入れると、問題を解決できます。

+++

+++ 参照モードでVECが壊れているように見える

**[!UICONTROL 参照]** モードでは、[!DNL Target] ライブラリ （[at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=ja){target=_blank}または[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank}）が含まれていないURL、またはフレームバスターヘッダーが含まれているURLを開くと、VECが壊れて表示されます。 ブラウザーのセキュリティ上の理由から、[!DNL Target]はナビゲーションされたURLに適切にアクセスできないか、ページの読み込み時にVEC URLが一貫して更新されません。

VECは`<iframe>`でweb ページを読み込み、ブラウザーの現在のセキュリティ メカニズムにより、[!DNL Target] UIが同一生成元ポリシーの下にあるフレームの要素にアクセスできなくなります。 ブラウザーは、`location.href`などの情報を含む、別のオリジンのフレームにアクセスしようとするスクリプトをブロックします。

新しい[Visual Editing Helper拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)を使用して[!DNL Target] ライブラリをページに挿入し、ページを最適に参照できるようにします。

+++

+++ 問題は、VECでのCSS競合によって発生します

ページの読み込み中にCSS ファイルが表示に影響するかどうかを確認します。 例えば、ページ本文の`overflow: hidden` プロパティは、スクロールの問題や、オーサリングメニューに影響を与えるトリガークリックイベントの原因になる可能性があります。

+++
