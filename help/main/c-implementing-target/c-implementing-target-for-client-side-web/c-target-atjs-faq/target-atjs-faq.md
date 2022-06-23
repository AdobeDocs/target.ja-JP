---
keywords: at.js の FAQ;at.js に関するよくある質問;FAQ;ちらつき;ローダー;ページローダー;クロスドメイン;ファイルサイズ;ファイルのサイズ;x-domain;at.js と mbox.js;x のみ;クロスドメイン;Safari;シングルページアプリ;セレクターが見つかりません;セレクター;シングルページアプリケーション;tt.omtrdc.net;SPA;Adobe Experience Manager;AEM;IP アドレス;httponly;HttpOnly;Secure;IP;Cookie ドメイン
description: Adobe  [!DNL Target]  at.js JavaScript ライブラリに関するよくある質問への回答を紹介します。
title: at.js に関するよくある質問と回答
feature: at.js
role: Developer
exl-id: 937f880a-1842-4655-be44-0a5614c2dbcc
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '2586'
ht-degree: 96%

---

# at.js に関するよくある質問

[!DNL Adobe Target] の at.js JavaScript ライブラリに関するよくある質問への回答

## mbox.js と比較して at.js を使用するメリットは何ですか。 {#section_FE30D01A577C46ACB0F787B85F5E0F6B}

[!DNL at.js] ライブラリは [!DNL mbox.js] に取って代わるものです。 [!DNL mbox.js] ライブラリはサポートされなくなりました。 ただし、ほとんどのユーザーにとって、[!DNL at.js] には [!DNL mbox.js] よりも優れた利点があります。

[!DNL at.js] のメリットの例として、Web 実装のページ読み込み時間の改善、セキュリティの強化、シングルページアプリケーション向けのより優れた実装オプションの提供があげられます。

次の図は、mbox.js と at.js を使用した場合のページ読み込みパフォーマンスを示しています。

![](assets/atjs_vesus_mboxjs.png)

上図のとおり、mbox.js を使用すると、[!DNL Target] の呼び出しが完了するまでページコンテンツの読み込みが開始されませんでした。at.js を使用すると、[!DNL Target] の呼び出しが開始するとページ内容が読み込まれ、呼び出しが完了するまで待ちません。 

## at.js および mbox.js はページ読み込み時間にどのように影響しますか？ {#page-load}

特に新しいユーザーとリピートユーザーのコンテキストにおいて [!DNL at.js] と [!DNL mbox.js] がページ読み込み時間に与える影響を知りたいと考えているお客様やコンサルタントは数多くいます。残念ながら、[!DNL at.js] または [!DNL mbox.js] が各ページの読み込み時間にどのように影響するかはお客様の実装に左右されるので、具体的な数値を測定して示すことは困難です。

ただし、訪問者 API がページに存在する場合は、[!DNL at.js] と [!DNL mbox.js] がページ読み込み時間にどのように影響するかを [!DNL Target] で把握しやすくなります。

>[!NOTE]
>
>訪問者 API と [!DNL at.js] または [!DNL mbox.js] は、（本文を非表示にする技術により）グローバル mbox を使用している場合にのみ、ページ読み込み時間に影響を与えます。リージョナル mbox は訪問者 API 統合の影響を受けません。

以降のセクションでは、新しい訪問者と再訪問者の一連のアクションについて説明します。

### 新しい訪問者

1. 訪問者 API が読み込まれ、解析され、実行されます。
1. at.js または mbox.js が読み込まれ、解析され、実行されます。
1. グローバル mbox の自動作成が有効な場合、Target JavaScript ライブラリは次の操作を実行します。

   * Visitor オブジェクトをインスタンス化します。
   * [!DNL Target] ライブラリは [!DNL Experience Cloud Visitor ID] データの取得を試みます。
   * この訪問者は新規訪問者なので、訪問者 API によって demdex.net へのクロスドメインリクエストがトリガーされます。
   * [!DNL Experience Cloud Visitor ID] データが取得されたら、[!DNL Target] へのリクエストがトリガーされます。

### 再訪問者

1. 訪問者 API が読み込まれ、解析され、実行されます。
1. at.js または mbox.js が読み込まれ、解析され、実行されます。
1. グローバル mbox の自動作成が有効な場合、[!DNL Target] JavaScript ライブラリは以下を実行します。

   * Visitor オブジェクトをインスタンス化します。
   * [!DNL Target] ライブラリは [!DNL Experience Cloud Visitor ID] データの取得を試みます。
   * 訪問者 API が、Cookie からデータを取得します。
   * [!DNL Experience Cloud Visitor ID] データが取得されたら、[!DNL Target] へのリクエストがトリガーされます。

>[!NOTE]
>
>新規訪問者の場合、訪問者 API が存在すると、[!DNL Target] は、[!DNL Target] リクエストに [!DNL Experience Cloud Visitor ID] データが含まれていることを確認するために複数回やり取りを行う必要があります。再訪問者の場合、[!DNL Target] は、パーソナライズされたコンテンツを取得するためにのみ [!DNL Target] とやり取りします。

## at.js を旧バージョンから 1.0.0 にアップグレードした後、応答時間が長くなったように感じるのはなぜですか。 {#section_DFBA5854FFD142B49AD87BFAA09896B0}

[!DNL at.js] バージョン 1.0.0 以降では、すべてのリクエストが同時並行で実行されます。以前のバージョンではリクエストが順番に実行されます。つまり、リクエストがキューに入り、[!DNL Target] は、最初のリクエストの処理が完了するまで待ってから次のリクエストに移ります。

この [!DNL at.js] の旧バージョンでのリクエストの実行方法では、いわゆる「ヘッドオブラインブロッキング」の問題が生じやすくなります。[!DNL at.js] 1.0.0 以降では、 が同時並行でリクエストを実行するように変更されました。[!DNL Target]

[!DNL at.js] 0.9.1 で「ネットワーク」タブのウォーターフォールをチェックすると、 の現在のリクエストの処理が完了するまで、次のリクエストが実行されないことがわかります。[!DNL Target][!DNL at.js] 1.0.0 以降では、このような順次処理は行われず、基本的にすべてのリクエストが同時に開始されます。

応答時間に関しては、次のような数式が成り立ちます。

<ul class="simplelist"> 
 <li> at.js 0.9.1:すべての応答時間 [!DNL Target] requests =リクエストの応答時間の合計 </li> 
 <li> at.js 1.0.0 以降：すべての応答時間 [!DNL Target] requests =最大リクエスト応答時間 </li> 
</ul>

[!DNL at.js] ライブラリバージョン 1.0.0 の方がリクエストの処理が早く完了します。 また、[!DNL at.js] のリクエストは非同期なので、 によってページレンダリングがブロックされることはありません。[!DNL Target]リクエストの処理に数秒を要した場合でも、レンダリングされたページが表示されます。[!DNL Target] が [!DNL Target] エッジサーバーからの応答を受け取るまで、ページの一部分が空白になるだけです。

## [!DNL Target] ライブラリを非同期で読み込むことはできますか？ {#section_AB9A0CA30C5440C693413F1455841470}

at.js 1.0.0 リリースでは、[!DNL Target] ライブラリを非同期で読み込めるようになりました。

at.js を非同期で読み込む手順は次のとおりです。

* [!DNL Adobe Experience Platform] のタグを使用する方法をお勧めします。
* at.js を読み込むスクリプトタグに async 属性を追加することで、at.js を非同期で読み込むこともできます。次のように使用します。

   ```
   <script src="<URL to at.js>" async></script>
   ```

* 次のコードでも、at.js を非同期で読み込むことができます。

   ```
   var script = document.createElement('script'); 
   script.async = true; 
   script.src = "<URL to at.js>"; 
   document.head.appendChild(script);
   ```

at.js を非同期で読み込む方法は、ブラウザーによるレンダリングのブロックを防ぐのに最適ですが、Web ページにちらつきが生じることがあります。

ページ（または指定された部分）を事前に非表示にしておき、at.js とグローバルリクエストが読み込まれてからページを表示するスニペットを使用すると、ちらつきを回避できます。このスニペットは、at.js の読み込みの前に追加する必要があります。

非同期 [!DNL Adobe Experience Platform] 実装を通じて at.js をデプロイする場合は、 [!DNL Adobe Experience Platform] 埋め込みコードを使用して [!DNL Target] を実装する前に、事前非表示のスニペットをページに直接含めてください。

同期 DTM 実装を介して at.js を導入する場合、ページの最上部にあるページ型ルールを通して、スニペットを非表示にすることができます。

詳しくは、「[at.js によるちらつきの制御方法](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/manage-flicker-with-atjs/)」を参照してください。

## at.js は [!DNL Adobe Experience Manager] 統合（Experience Manager）と互換性がありますか？ {#section_6177AE10542344239753764C6165FDDC}

[!DNL Adobe Experience Manager] 6.2 と FP-11577（またはそれ以降）で、[!DNL at.js] 実装とその [!UICONTROL Adobe Target Cloud Services] 統合をサポートします。

## どうしたら at.js を使用してページ読み込み時のちらつきを回避できますか？ {#section_4D78AAAE73C24E578C974743A3C65919}

Target には、ページ読み込み時のちらつきを回避する方法がいくつか用意されています。詳しくは、「[at.js によるちらつきの回避](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/manage-flicker-with-atjs/)」を参照してください。

## at.js のファイルサイズはどれくらいですか？ {#section_6A25C9A14C66441785A7635FEF5C4475}

at.js ファイルはダウンロード時には約 109 KB あります。ただし、ほとんどのサーバーは自動的にファイルを圧縮してファイルのサイズを小さくするので、（GZIP またはその他の方法を使用して）サーバーで圧縮され、ユーザーが Web サイトを訪問した際に読み込まれる at.js は約 34 KB になります。at.js をインストールしたサーバーの圧縮設定により、実際の圧縮サイズが決まります。

## at.js が mbox.js よりも大きいのはなぜですか？ {#section_AA1C43897E46448FA3E26EEC10ED7E51}

at.js 実装が単一のライブラリ（[!DNL at.js]）を使用するのに対して、mbox.js 実装は、実際には 2 つのライブラリ（[!DNL mbox.js] および [!DNL target.js]）を使用します。そのため、より公平な比較は、at.js 対 mbox.js *および* `target.js` になります。2 つのバージョンの gzip 圧縮サイズを比較すると、at.js バージョン 1.2 は 34 KB で、mbox.js バージョン 63 は 26.2 KB です。

at.js がより大きいのは、mbox.js に比べて、より多くの DOM 解析をおこなうためです。at.js は JSON 応答で「生」データを取得し、その意味を理解する必要があるので、これが必要です。mbox.js では `document.write()` を使用し、すべての解析はブラウザーによって行われます。

より大きなファイルサイズにもかかわらず、アドビのテストでは、at.js のページの読み込みは mbox.js に比べて高速であることを示しています。さらに、at.js は、追加のファイルを動的に読み込まず、`document.write` も使用しないので、セキュリティの観点からも優れています。

## at.js には jQuery が含まれていますか。既に Web ページに jQuery があるので、at.js のこの部分を削除できますか。 {#section_E4604E46E7B34460B8DD6A78D9B476F9}

at.js は、現在、jQuery の一部を使用しています。そのため、at.js の上部に MIT ライセンス通知が表示されます。jQuery は、公開されておらず、バージョンが異なる可能性のある、既にページにある jQuery ライブラリに干渉しません。at.js 内の jQuery コードの削除は、サポートされていません。

## at.js は、Safari とクロスドメインの「x のみ」の設定をサポートしますか。 {#section_114EC271A6E045E1B2183B66F1B71285}

いいえ、クロスドメインが「x のみ」に設定され、Safari がサードパーティの Cookie を無効化している場合、[!DNL mbox.js] と at.js の双方が無効化された Cookie を設定し、そのクライアントのドメインでは mbox のリクエストが実行されません。

Safari の訪問者をサポートするには、「無効化」（ファーストパーティの cookie のみ設定）または「有効化」（Safari ではファーストパーティの cookie のみ設定、他のブラウザーではファーストパーティとサードパーティの cookie を設定）の方がクロスドメインの設定として優れています。

## [!DNL Target] Visual Experience Composer（VEC）を単一ページアプリケーションで使用できますか？ {#section_459C1BEABD4B4A1AADA6CF4EC7A70DFB}

はい。at.js 2.x を使用する場合は、SPA に VEC を使用できます。詳しくは、[単一ページアプリケーション（SPA）Visual Experience Composer](/help/main/c-experiences/spa-visual-experience-composer.md) を参照してください。

## [!DNL Adobe Experience Cloud] デバッガーを at.js 実装と一緒に使用できますか？ {#section_FF3CF4C5FD2F4DB1BF1A6B39DA161637}

はい。また、mboxTrace をデバッグ目的で使用したり、ブラウザーの開発者ツールを使用して、ネットワーク要求を調査し、「mbox」にフィルターして mbox 呼び出しを分離することもできます。

## at.js を使用した mbox 名に特殊文字を使用できますか。 {#section_8E31D2E8A27642098934D7DACFB2A600}

はい、mbox.js の場合と同じです。

## Web ページで mbox が実行されないのはなぜですか。 {#section_4BA5DA424B734324AAB51E4588FA50F5}

[!DNL Target] のお客様は、[!DNL Target] でクラウドベースのインスタンスを使用してテストをおこなったり、簡単な概念実証に利用したりする場合があります。これらのドメインは、他の多くのドメインと同様に[パブリックサフィックスリスト](https://publicsuffix.org/list/public_suffix_list.dat)に含まれています。

これらのドメインを使用する場合は、targetGlobalSettings() を使用して `cookieDomain` 設定をカスタマイズしない限り、最新のブラウザーでは Cookie が保存されません。詳しくは、「[Target でのクラウドベースのインスタンスの使用](https://developer.adobe.com/target/implement/client-side/target-debugging-atjs/targeting-using-cloud-based-instances/)」を参照してください。

## at.js を使用する際に、IP アドレスを Cookie ドメインとして使用することはできますか。 {#section_8BEEC91A3410459D9E442840A3C88AF7}

はい。[at.js バージョン 1.2 以降](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)では使用可能です。ただし、[!DNL Adobe] では、常に最新バージョンを使用することを強くお勧めします。

>[!NOTE]
>
>次の例は、at.js バージョン 1.2 以降を使用する場合は不要です。

[targetGlobalSettings](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) の使用方法によっては、at.js をダウンロードした後にコードを追加修正する必要があります。例えば、様々な Web サイトで [!DNL Target] の実装にそれぞれ若干異なる設定が必要で、これらの設定をカスタム JavaScript により動的に定義することができない場合、ファイルをダウンロードした後、各 Web サイトにアップロードする前に、カスタマイズを手動でおこなってください。

次の例では、`targetGlobalSettings()` at.js 関数を使用して、IP アドレスをサポートするためのコードスニペットを挿入できます。

この例は単一の IP アドレス向けです。

```
if (window.location.hostname === '123.456.78.9') { 
    window.targetGlobalSettings = window.targetGlobalSettings || {}; 
    window.targetGlobalSettings.cookieDomain = window.location.hostname; 
}
```

この例は IP アドレスの範囲向けです。

```
if (/^123\.456\.78\..*/g.test(window.location.hostname)) { 
    window.targetGlobalSettings = window.targetGlobalSettings || {}; 
    window.targetGlobalSettings.cookieDomain = window.location.hostname; 
}
```

## 「アクションでセレクターが見つかりません」などの警告メッセージが表示されるのはなぜですか。 {#section_C36BED5B16634361A1BA46FCB731489D}

これらのメッセージは [!DNL at.js] 機能と関係がありません。[!DNL at.js] ライブラリは、DOM 内で見つからないすべてのものを報告します。

この警告メッセージが表示された場合は、次のような原因が考えられます。

* ページが動的に作成されており、at.js が要素を見つけられない。
* （ネットワークが低速なので）ページの作成に時間がかかり、at.js が DOM でセレクターを見つけられない。
* アクティビティ[!UICONTROL が実行されているページの構造が変更されている。]Visual Experience Composer（VEC）でアクティビティを再度開くと、警告メッセージが表示されます。アクティビティを更新して、必要な要素がすべて見つかるようにします。
* 基になるページが[!UICONTROL 単一ページアプリケーション]（SPA）の一部であるか、ページの下部に表示される要素がページに含まれていて、[!DNL at.js] の「セレクターポーリングメカニズム」でこれらの要素が見つからない。`selectorsPollingTimeout` の値を増やすと問題が解決する場合があります。詳しくは、[targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) を参照してください。
* いずれかのクリック追跡指標が、その指標が設定された URL に関係なく、それ自体をすべてのページに追加しようとしている。害はありませんが、この状況ではこれらのメッセージの多くが表示されます。

   最良の結果を得るには、[!DNL at.js] の最新バージョンをダウンロードして使用してください。詳しくは、「[at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)」および「[at.js のダウンロード](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)」を参照してください。

## [!DNL Target] のサーバー呼び出しが送られる tt.omtrdc.net というドメインは何ですか？ {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] は、Target のすべてのサーバー呼び出しを受信する Adobe の EDGE ネットワークの名前です。

## at.js で HttpOnly および Secure の Cookie フラグが常に使用されるとは限らないのはなぜですか？ {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly はサーバー側コードでのみ設定できます。[!DNL Target]mbox などの Cookieは JavaScript コードで作成され保存されるので、 では HttpOnly の [!DNL Target] Cookie フラグを使用できません。[!DNL Target] では、クロスドメインが有効な場合にサーバー側から設定されたサードパーティ Cookie に対して HttpOnly を設定します。

Secure は、ページが HTTPS でロードされた場合にのみ、JavaScript で設定できます。ページが最初 HTTP でロードされる場合、JavaScript ではこのフラグを設定できません。さらに、Secure フラグを使用する場合、Cookie は HTTPS ページでのみ使用できます。HTTPS を介して読み込まれたページの場合、[!DNL Target] は Secure 属性と SameSite=None 属性を設定します。

Cookie がクライアント側で生成されるので、[!DNL Target] がユーザーを適切に追跡できるようにするため、[!DNL Target] では、上記の状況を除き、これらのフラグのどちらも使用しません。

## at.js はどのくらいの頻度でネットワークリクエストを送信しますか？ {#section_57C5235DF7694AF093A845D73EABADFD}

[!DNL Target] は、すべての決定をサーバー側で実行します。つまり、at.js は、ページの再読み込みが発生するたび、または at.js パブリック API が呼び出されるたびに、ネットワークリクエストを送信します。

## ベストケースのシナリオの場合、コンテンツの非表示、置換、表示に関連するページ読み込みの際に、ユーザーが何らかの目に見える効果に気付くことはないと考えてもよいですか？ {#section_CB3C566AD61F417FAC0EC5AC706723EB}

at.js は、HTML BODY 要素やその他の DOM 要素があらかじめ非表示にされている時間が長くならないように努めますが、これはネットワークの状態やアクティビティの設定に依存します。at.js [設定](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)を使用すると、BODY を非表示にする CSS スタイルをカスタマイズして、HTML BODY 全体を非表示にする代わりに、ページの一部のみをあらかじめ非表示にできます。これらの部分には、「パーソナライズ」する必要のある DOM 要素が含まれていることが予想されます。

## ユーザーがアクティビティの対象になる標準的なシナリオにおいてイベントはどのような順序で発生しますか？ {#section_56E6F448E901403FB77DF02F44C44452}

at.js リクエストは非同期の `XMLHttpRequest` なので、次の手順が実行されます。

1. ページが読み込まれます。
1. at.js により、HTML BODY があらかじめ非表示にされます。HTML BODY の代わりに特定のコンテナをあらかじめ非表示にする設定もあります。
1. at.js リクエストが送信されます。
1. [!DNL Target] 応答が受信された後、[!DNL Target] が CSS セレクターを抽出します。
1. [!DNL Target] が CSS セレクターを使用して、カスタマイズする DOM 要素をあらかじめ非表示にするための STYLE タグを作成します。
1. HTML BODY をあらかじめ非表示にする STYLE が削除されます。
1. [!DNL Target] が DOM 要素のポーリングを開始します。
1. DOM 要素が見つかった場合は、[!DNL Target] が DOM の変更を適用し、その要素をあらかじめ非表示にする STYLE が削除されます。
1. DOM 要素が見つからない場合は、破損したページにならないように、グローバルタイムアウトによって要素の非表示が解除されます。

## アクティビティによって変更されている要素の非表示が at.js によって最終的に解除された後、ページのコンテンツはどのくらいの頻度で完全に読み込まれて表示されますか？ {#section_01AFF476EFD046298A2E17FE3ED85075}

「アクティビティによって変更されている要素の非表示が at.js によって最終的に解除された後、ページのコンテンツはどのくらいの頻度で完全に読み込まれて表示されますか？」という上記のシナリオを検討してみましょう。言い換えると、そのページはアクティビティのコンテンツを除いて完全に表示され、その少し後にアクティビティのコンテンツが表示されます。

at.js は、ページのレンダリングをブロックしません。ユーザーは、ページ上のいくつかの空白領域に気付く可能性があります。これらの領域は、[!DNL Target] によってカスタマイズされる要素の配置場所になります。適用されるコンテンツに SCRIPT や IMG などのリモートアセットが多く含まれていない場合は、すべてが瞬時にレンダリングされます。

## 完全にキャッシュされたページは上記のシナリオにどのように影響しますか？ページ上の他のコンテンツが読み込まれた後は、アクティビティのコンテンツがよりはっきりと見えるようになるのですか？ {#section_CE76335A3E0B41CB8253DEE5E060FCDA}

ユーザーの場所から近くても [!DNL Target] エッジからは遠い CDN にページがキャッシュされている場合、そのユーザーは多少の遅延を感じる可能性があります。[!DNL Target] エッジは世界中に分散されているので、ほとんどの場合、これは問題になりません。

## ヒーロー画像が表示された後に、少し遅れてスワップアウトされる可能性はありますか？ {#section_C25B07B25B854AAE8DEE1623D0FA62A3}

次のシナリオを考えてみましょう。

[!DNL Target] のタイムアウトは 5 秒です。ヒーロー画像をカスタマイズするアクティビティが存在するページをユーザーが読み込みます。適用するアクティビティがあるかどうかを確認するリクエストを at.js が送信したところ、初期応答がありません。関連付けられているアクティビティがあるかどうかに関する応答を [!DNL Target] から受け取っていないので、ユーザーにはヒーロー画像の通常のコンテンツが表示されるとします。4 秒後、[!DNL Target] がアクティビティコンテンツを含んだ応答を返します。

この段階で代替バージョンが表示される可能性はありますか？つまり、4 秒後にヒーロー画像がスワップアウトされて、この画像のスワップにユーザーが気付く可能性はありますか？

最初は、画像ヒーロー DOM 要素は非表示になっています。[!DNL Target] からの応答を受信した後、at.js は、DOM の変更（IMG の置き換えや、カスタマイズされたヒーロー画像の表示など）を適用します。

## at.js にはどのような HTML の doctype が必要ですか?

a.js には HTML5 の doctype が必要です。

この構文は次のとおりです。

`<!DOCTYPE html>`

HTML5 の doctype を使用すると、ページが標準モードで読み込まれます。互換モードでロードする場合、at.js が依存する一部の JS API は無効になります。[!DNL Target]は、互換モードで at.js を無効にします。
