---
keywords: ターゲット設定；visual experience composer;vec;visual experience composer のトラブルシューティング；トラブルシューティング；tls;tls 1.2
description: Adobeで発生することのある問題のトラブルシューティング方法を説明します [!DNL Target] Visual Experience Composer(VEC) を使用している場合に限ります。
title: Visual Experience Composer に関連する問題のトラブルシューティング方法を教えてください。
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: ed6b1ef266f2e26cd80b6fa5099a42f6031448b5
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 79%

---

# Visual Experience Composer に関連する問題のトラブルシューティング

表示の問題が [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) を使用します。

## Visual Experience Composer で Web サイトを開くと、 [!DNL Target] ライブラリは読み込まれません。 （VEC のみ） {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

Visual Experience Composer で Web サイトを開くと、Target によって 2 つのパラメーター（`mboxEdit=1` および `mboxDisable=1`）が追加されます。

Web サイト（特に単一ページアプリ）で、ページの再読み込みなしでページ間を移動するときにこのパラメーターがトリミングされたり、削除されたりすると、Target の機能が適切に動作せず、Target ライブラリが読み込まれません。この問題を防ぐには、この 2 つのパラメーターをトリミングまたは削除しないように設定します。

## EEC でページが開かないか、読み込みに時間がかかります。VEC でアクティビティやエクスペリエンスの読み込みに時間がかかります。（VEC のみ） {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

いくつかの問題が Target のエクスペリエンスコンポーザーのページのパフォーマンスに影響する可能性があります。よくある問題として以下のようなものがあります。

* ページに mbox がない。
* サイトでプロキシブロックを使用している。これにより、どちらのエクスペリエンスコンポーザーでもページを開くことが許可されません。
* サイトがサイト自体を iFrame で開くことを許可していない。

拡張 Experience Composer で問題が発生した場合、拡張 Experience Composer をオフにして、代わりに Visual Experience Composer を使用します。

拡張 Experience Composer を無効にするには、に移動します。 **[!UICONTROL 管理]** > **[!UICONTROL Visual Experience Composer]** そしてオフにする **[!UICONTROL 拡張 Experience Composer の有効化]** オプション。

コンソールに次のエラーメッセージが表示される場合があります。

![コンソールエラーメッセージ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

Visual Experience Composer も拡張 Experience Composer も動作しない場合、サイトの X-Frames ヘッダーオプションを上書きしてサイトでの iFrame への読み込みを許可し、VEC を有効にする、Requestly（Chrome または Firefox）や Modify Response Headers（Firefox）などのブラウザー拡張機能を使用します。ブラウザー拡張機能を使用できない場合は、フォームコンポーザーを使用します。

>[!NOTE]
>
>以下の情報に加えて、Google Chrome 用 [Adobe Target VEC ヘルパーブラウザー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)を使用できます。


>[!NOTE]
>
>これらのプラグインは、VEC を編集する場合にのみ使用する必要があります。
>
>Requestly 拡張機能の場合、ヘッダーを削除する必要があるときは必ず次のいずれかを実行する必要があります。
>
>* VEC で開く URL の URL ルールを追加して、それらの URL についてのみヘッダーが削除されるようにします。
>
>* VEC で編集するときにはルールを有効にし、VEC を使用していないときはルールを無効にします。
>
>Modify Response Headers 拡張機能（Firefox）の場合、URL ルールを追加できないので、次の操作をおこなう必要があります。
>
>* VEC で編集するときにはルールを有効にし、VEC を使用していないときはルールを無効にします。


**Chrome または Firefox の Requestly 拡張機能を使用する方法は次のとおりです。**

1. 拡張 Experienced Composer をオフにします。
1. Chrome または Firefox に Requestly ブラウザー拡張機能をインストールします。
1. 拡張機能を開いて、次を使用するように設定します。
1. 「**[!UICONTROL Modify headers（ヘッダーを変更）]**」を選択します。
1. 以下を入力します。

   * ルール名
   * 変更ルール

      * 「**[!UICONTROL Add（追加）]**」を「**[!UICONTROL Remove（削除）]**」に切り替えます。
      * 「**[!UICONTROL Request（リクエスト）]**」を「**[!UICONTROL Response（応答）]**」に切り替えます。
      * ヘッダー名として &quot;X-Frame-Options&quot; と入力します。
      * 前述の手順を繰り返し、ヘッダー名に「x-frame-options」と入力します。

         >[!NOTE]
         >
         >Requestly を使用して編集したヘッダーでは、大文字と小文字が区別されます。

      * ソース URL の条件を「**[!UICONTROL Equals（等しい）]**」を「**[!UICONTROL Contains（含む）]**」に変更し、VEC で読み込もうとするアクティビティの URL を入力します。

      ![chrome_extension image](assets/chrome_extension.png)


1. 「**[!UICONTROL 保存]**」をクリックします。

   ![要求画像](assets/requestly.png)

   これで、Visual Experience Composer でページをすばやく読み込むことができるはずです。

**Firefox の Modify Response Headers 拡張機能を使用する方法は次のとおりです。**

1. Firefox に Modify Response Headers をインストールし、ブラウザーを再起動します。
1. Firefox 拡張機能から、Modify Response Headers 拡張機能を選択します。
1. 「**[!UICONTROL 環境設定]**」をクリックします。
1. Action（アクション）ドロップダウンから **[!UICONTROL Filter（フィルター）]** を選択します。
1. 「Header Name（ヘッダー名）」フィールドに、「**[!UICONTROL X- Frame- Options]**」と入力します。
1. 手順 4 と 5 を繰り返して、**[!UICONTROL x-frame-options]** によるフィルターを追加します。
1. 「**[!UICONTROL 追加]**」をクリックします。
1. 「**[!UICONTROL Start（開始）]**」をクリックします。

![firefox_extension image](assets/firefox_extension.png)

拡張機能を設定したら、Target を開きます。たとえ拡張 Experience Composer を無効にしていても、Visual Experience Composer でページを読み込めるようになっているはずです。

## VEC にページが表示されません。（VEC のみ） {#does-not-load}

* ブラウザーがサポートされていません。
* ブラウザーが、セキュリティで保護されているサイトのセキュリティで保護されていないページをブロックしています。

   ブラウザーのアドレスバーの URL の左にあるアイコンをクリックして、「**[!UICONTROL このページの保護を無効にする」をクリックします。]**
* 入力した URL が無効です。
* アカウント設定ページにデフォルト URL が入力されていません。

   この設定が有効になっていることを確認してから、Web サイトで at.js をダウンロードして更新します。

* を使用してみると、 [新規 [!UICONTROL ビジュアル編集ヘルパー] 拡張](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) その後、 [古い拡張子](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) および [!DNL Target] web サイトの読み込みに失敗し、すべてのブラウザーデータを消去して、新しい拡張機能を無効にします。

* Web サイトを VEC で読み込めなかったり、予期せぬ動作が発生した場合は、で Web サイトを読み込む前に、ブラウザーで Web サイトの Cookie を受け入れるという問題が修正される可能性があります。 [!DNL Target].

## 参照モードを使用すると、VEC が壊れているように見えます。（VEC のみ） {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

参照モードの使用中に、target.js を含まない URL またはフレームバスターヘッダーを含む URL にアクセスすると、Visual Experience Composer が壊れているように表示されます。ブラウザーのセキュリティ上の問題により、Target はこれらの URL にアクセスできません。
