---
keywords: ターゲット設定；Visual Experience Composer;vec;Visual Experience Composerのトラブルシューティング；トラブルシューティング；tls;tls 1.2
description: 特定の状況でVisual Experience Composer(VEC)で発生することがある問題のトラブルシューティング方法を説明します。
title: Visual Experience Composerに関連する問題のトラブルシューティング方法を教えてください。
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 89%

---


# Visual Experience Composerに関する問題のトラブルシューティング

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer](VEC)では、特定の状況で表示の問題が発生する場合があります。

## Visual Experience Composer で Web サイトを開いたときに、Target ライブラリが読み込まれません。（VEC のみ）{#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

Visual Experience Composer で Web サイトを開くと、Target によって 2 つのパラメーター（`mboxEdit=1` および `mboxDisable=1`）が追加されます。

Web サイト（特に単一ページアプリ）で、ページの再読み込みなしでページ間を移動するときにこのパラメーターがトリミングされたり、削除されたりすると、Target の機能が適切に動作せず、Target ライブラリが読み込まれません。この問題を防ぐには、この 2 つのパラメーターをトリミングまたは削除しないように設定します。

## EEC でページが開かないか、読み込みに時間がかかります。VEC でアクティビティやエクスペリエンスの読み込みに時間がかかります。（VEC のみ）{#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

いくつかの問題が Target のエクスペリエンスコンポーザーのページのパフォーマンスに影響する可能性があります。よくある問題として以下のようなものがあります。

* ページに mbox がない。
* サイトでプロキシブロックを使用している。これにより、どちらのエクスペリエンスコンポーザーでもページを開くことが許可されません。
* サイトがサイト自体を iFrame で開くことを許可していない。

拡張 Experience Composer で問題が発生した場合、拡張 Experience Composer をオフにして、代わりに Visual Experience Composer を使用します。

拡張Experience Composerを無効にするには、**[!UICONTROL 管理]**/**[!UICONTROL Visual Experience Composer]**&#x200B;に移動し、**[!UICONTROL 拡張Experience Composerを有効にする]**&#x200B;オプションをオフにします。

コンソールに次のエラーメッセージが表示される場合があります。

![コンソールエラーメッセージ](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

Visual Experience Composer も拡張 Experience Composer も動作しない場合、サイトの X-Frames ヘッダーオプションを上書きしてサイトでの iFrame への読み込みを許可し、VEC を有効にする、Requestly（Chrome または Firefox）や Modify Response Headers（Firefox）などのブラウザー拡張機能を使用します。ブラウザー拡張機能を使用できない場合は、フォームコンポーザーを使用します。

>[!NOTE]
>
>以下の情報に加えて、Google Chrome 用 [Adobe Target VEC ヘルパーブラウザー拡張機能](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)を使用できます。


>[!NOTE]
>
>これらのプラグインは、VEC を編集する場合にのみ使用する必要があります。
>
>Requestly 拡張機能の場合、ヘッダーを削除する必要があるときは必ず次のいずれかを実行する必要があります。
>
>* VEC で開く URL の URL ルールを追加して、それらの URL についてのみヘッダーが削除されるようにします。
   >
   >
* VEC で編集するときにはルールを有効にし、VEC を使用していないときはルールを無効にします。
>
>
Modify Response Headers 拡張機能（Firefox）の場合、URL ルールを追加できないので、次の操作をおこなう必要があります。
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

      ![](assets/chrome_extension.png)


1. 「**[!UICONTROL 保存]**」をクリックします。

   ![](assets/requestly.png)

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

![](assets/firefox_extension.png)

拡張機能を設定したら、Target を開きます。たとえ拡張 Experience Composer を無効にしていても、Visual Experience Composer でページを読み込めるようになっているはずです。

## VEC にページが表示されません。（VEC のみ） {#section_87B3BEA4B6174CFDA6C9A69A1A051FA1}

* ブラウザーがサポートされていません。
* ブラウザーが、セキュリティで保護されているサイトのセキュリティで保護されていないページをブロックしています。

   ブラウザーのアドレスバーの URL の左にあるアイコンをクリックして、「**[!UICONTROL このページの保護を無効にする」をクリックします。]**
* 入力した URL が無効です。
* アカウント設定ページにデフォルト URL が入力されていません。

この設定が有効になっていることを確認してから、Web サイトの mbox.js をダウンロードおよび更新してください。

## 参照モードを使用すると、VEC が壊れているように見えます。（VEC のみ）{#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

参照モードの使用中に、target.js を含まない URL またはフレームバスターヘッダーを含む URL にアクセスすると、Visual Experience Composer が壊れているように表示されます。ブラウザーのセキュリティ上の問題により、Target はこれらの URL にアクセスできません。
