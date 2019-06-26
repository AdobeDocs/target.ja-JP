---
description: このページには、mbox.js の各バージョンに対する変更が表示されます。
keywords: mbox. jsの変更;mbox. jsのバージョン
seo-description: このページには、mbox.js の各バージョンに対する変更が表示されます。
seo-title: mbox.js のバージョンの詳細
solution: 'Target '
subtopic: 導入
title: mbox.js のバージョンの詳細
uuid: 5f8e0511-637b-4c17-bb19-aa7f4d7c98ea
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# mbox.js のバージョンの詳細{#mbox-js-version-details}

このページには、mbox.js の各バージョンに対する変更が表示されます。

>[!NOTE]
>
>すべての mbox.js ユーザーにバージョン 57 以降にアップグレードすることをお勧めします。`target.js` が読み込めなかった場合にタイムアウトの問題が発生することがあります。バージョン 57 で、この問題を修正しました。ただし、[!DNL Experience Cloud Visitor ID] サービスを使用している場合、バージョン 58 以降が必要です。

ページからの呼び出しに Target がどのように応答するかは、使用する Target ライブラリのバージョン、訪問者 ID 実装が存在するかどうか、および訪問者 ID があるかどうかによって異なります。詳しくは、[ライブラリバージョン別の Target の呼び出しと応答答](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/call-responses-library-version.md#concept_A95A4758A1E7405D947E9B4BCB5D62F0)を参照してください。

>[!NOTE]
>
>mbox.js ライブラリの開発は終了しました。すべてのお客様が mbox.js から at.js に移行する必要があります。詳しくは、「[mbox.js から at.js への移行](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)」を参照してください。

## mbox.js バージョン 63 {#section_ED8EFCF653A845ED8927F759578C4A33}

**Target リリース：** 17.7.1

[!DNL mbox.js] バージョン 63 がリリースされました。詳しくは、[mbox.js のダウンロード](https://marketing.adobe.com/resources/help/en_US/target/ov/t_target-download-config-mbox.html)を参照してください。

[!DNL mbox.js] バージョン 63 には、次の機能強化および修正が含まれています。

* `mboxDefine()` と `mboxUpdate()` を使用する際の SDID の生成に関する問題を修正しました。対象となるのは、ページで訪問者 API を使用しているお客様のみです。

## mbox.js バージョン 62 {#section_723A9119FE204183847D3B0929A99B41}

* Google Chrome ブラウザーでリダイレクトアクティビティを表示した際のちらつきの問題を修正しました。
* `secureOnly` 設定が追加され、mbox.js で HTTPS のみ使用可能にするか、ページのプロトコルによって HTTP と HTTPS との切り替えを許可するかを指定できるようになりました。これは詳細設定で、デフォルトでは False に設定されています。

## mbox.js バージョン 61 {#section_F3B59C5578B64883AE013B9342151193}

**Target リリース：** 16.7.2

**リリース日：** 2016 年 7 月 29 日

mbox.js バージョン 61 には、次の機能強化が含まれています。

* JavaScript Date API の mboxSession ID 生成アルゴリズムでは、タイムスタンプとランダム文字列を使用する代わりに、ランダム文字列を生成するようになりました。
* 次の詳細は、ページで Visitor API を使用する場合にのみ適用されます。

   * [!DNL mbox.js] バージョン 61 では、Visitor API の `loadTimeout` プロパティをオーバーライドすることはありません。クライアントは `visitorApiTimeout` および `visitorApiPageDisplayTimeout` を使用して、Visitor API 統合を制御できます。
   * 将来の Adobe Experience Cloud オプトアウト機能をサポートするために `optoutEnabled` 設定が追加されました。デフォルト値は false です。このプロパティを有効化すると、バージョン 60 と同様、すべての要求が [!DNL /ajax] に対して非同期で実行されます。
   * 本文の非表示機能はデフォルトで無効にされています。Target では、グローバル mbox 自動作成と本文の非表示機能が有効である場合にのみ、本文の非表示機能を使用します。
   * Experience Cloud 訪問者 ID Cookie がない場合、すべてのリクエストが最初のページ読み込みで [!DNL /ajax] に対して非同期に実行されます。2 番目のページ読み込みでは、訪問者 ID の値が既に存在するので、Target では通常のフローを使用します。
   * Adobe Analytics をアクティビティのレポートソースとして使用する場合、 mbox.js バージョン 61 （またはそれ以降）または at.js バージョン 0.9.1 （またはそれ以降）を使用しているのであれば、アクティビティを作成する際にトラッキングサーバーを指定する必要はありません。mbox.js または at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。

## mbox.js バージョン 60 {#section_3BDAB885FA13444A8D35940A4BFF5825}

**Target リリース：** 16.4.1

**リリース日：** 2016 年 4 月 22 日

デフォルトでは、ページのコンテンツは非表示にはなりません。バージョン 60 では、「グローバル mbox 自動作成」オプションが有効な場合にのみ、ページコンテンツを非表示にします。ページを非表示にするために、`opacity:0` ではなく、CSS の `display:none` プロパティを使用します。これにより、レスポンシブサイトの適切な配信ができるようになり、[!DNL at.js] と整合するようになります。

本文の非表示は 2 つの設定で有効にできます。

* `bodyHidingEnabled`デフォルト値は false です。この場合、HTML BODY は非表示にはなりません。

* bodyHiddenStyle

   デフォルト値は `body{opacity:0}` です。この値は `body{display:none}` など他の値に変更することもできます。

これらの設定は、次のようにして上書きすることもできます。

```
<script> 
window.targetGlobalSettings = { 
 bodyHidingEnabled: true, 
 bodyHiddenStyle: "body{opacity:0}", 
 visitorApiPageDisplayTimeout: 2000 
}; 
</script>
```

このページの非表示手法では、STYLE タグを使用してスタイルの追加と削除をおこないます。これにより、ページの非表示コードが実行された後も、サイトのスタイルが変更されずに維持されます。

**DTM ユーザー：** Target UI では前述の構成を保存できないので、これにより、自動読み込みオプションを使用できなくなることに注意してください。前述の手順を使用して、カスタムホスティングオプションのコードボックスにコンテンツを貼り付けることが必要になります。

また、バージョン 60 では、Experience Cloud 訪問者 ID サービス用に [!DNL visitorAPI.js] ファイルが存在する場合、すべての mbox は AJAX エンドポイントを通じてリクエストされます。訪問者 API メソッドは非同期なので、これが必要です。このアプローチの利点の 1 つは、mbox リクエストによってレンダリングがブロックされることがないので、レンダリング開始時間が大幅に短縮されることです。ただし、これはまた、すべての [!DNL Target] オファーコンテンツが非同期に実行されるので、すべてのオファーコードが適切に記述されている必要があるということを意味します。`document.write` および最初のページ読み込みの際に実行されると想定されるその他のコードを含むオファーは、期待どおりに実行されません。

* バージョン 60 の非同期呼び出し

   訪問者 ID サービスでバージョン 60 を使用している場合は、すべての mbox 呼び出しが非同期でおこなわれます。これは、従来の mbox の動作方法に対する変更点であり、このバージョンにアップグレードする場合は注意してください。『[ ドキュメント』の](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#section_B586360A3DD34E2995AE25A18E3FB953)非同期に関する考慮事項[!DNL at.js]の節を参照し（[!DNL at.js] でも非同期呼び出しを使用するため）、そのリスクについて確認してください。
* 新しい訪問者のシナリオでは、ちらつきが発生する可能性があります。

   訪問者 ID サービスでバージョン 58～60 を使用している場合は、訪問者 ID が設定されるまで（またはタイムアウトまで）待ってから、mbox の呼び出しが実行されます。これは、新しい訪問者の最初のページ読み込みで発生します。

## mbox.js バージョン 59 {#section_FF0E70C4C17E402D8374DE428C5D996E}

**Target リリース：** 16.2.1

**リリース日：** 2016 年 2 月 18 日

mbox.js バージョン 59 には、次の機能強化が含まれています。

* 無効な mbox は、30 分に引き下げられました。
* ページの表示／非表示に関連する問題が修正されました。

   バージョン 58 のように `display:none` を使用してページを非表示にするのではなく、`opacity:0` が使用されます。これにより、レスポンシブデザインのサイトでページを非表示にするための以前の方法による問題を解決します。

## mbox.js バージョン 58 {#section_5070B0D1C87F4937BB97727923DD36C7}

**Target リリース：** 15.7.1

**リリース日：** 2015 年 7 月 31 日

このバージョンの mbox.js は、Target のレポートソースとして Analytics を使用する場合に必要です。また、プロファイルおよびオーディエンスに強くお勧めします。

mbox.js のバージョン 58 では、Target の呼び出しがおこなわれる前に、確実に Experience Cloud 訪問者 ID サービスが訪問者 ID を返します。これにより、プロファイルおよびオーディエンスコアサービスによって共有されるオーディエンスデータを、訪問者のセッションの最初の Target 呼び出しで利用できるようになります。テストコンテンツが返される前にデフォルトコンテンツのちらつきを防ぐために、Target は、訪問者 ID サービスが返されるまで `<BODY>` を非表示にします。`display:none` を使用してページを非表示にします。

また、この更新は、Analytics を Target のレポートソースとして使用する際に、1 ページのみに含まれる訪問に対して Analytics でレポートされる訪問者の数が水増しされていた問題を修正します。

mbox.js は、訪問者 ID サービスが返されない場合に備えて、タイムアウト値を設定します。訪問者 ID サービスのデフォルトタイムアウトは、500 ms（0.5 秒）です。追加のタイムアウトで、`<BODY>` タグを非表示にしておく時間の上限を設定します。デフォルト値は、500 ms（0.5 秒）です。これらのタイムアウトは、各ページの mbox.js 参照の前に次のコードを挿入することで変更できます。

```
<script> 
window.targetGlobalSettings = { 
 visitorApiTimeout: 500, 
 visitorApiPageDisplayTimeout: 500 
}; 
</script> 
```

mbox.js バージョン 58 以降では、HTML `BODY` タグのすぐ後で、グローバル mbox の非 JavaScript コンテンツが実行されます。グローバル mbox の `<script>` タグ内の JavaScript コンテンツは、`DOMContentLoaded` イベントの発生後に実行されます。このようなコンテンツの配信順序によって、グローバル mbox の JavaScript コンテンツが適切に配信かつレンダリングされます。

## mbox.js バージョン 57 {#section_6BA1CDBF75B14A94B59E8624ACF583D4}

**Target リリース：** 15.4.1

**リリース日：** 2015 年 4 月 22 日

このバージョンでは、次の変更がおこなわれました。

* Target Standard の自動作成されるグローバル mbox 応答では、document.write() が使用されなくなりました。また、 <div> 要素も作成されません。

   これにより、mbox.js ファイルをページの <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> 最後の項目にするという要件は必要なくなりました。この新しいバージョンにアップグレードする場合は、十分な QA を実施することをお勧めします。

   この変更によって、一部のタイプのオファーを提供する場合に、動作が変わる可能性があります。考慮が必要となる具体的な状況についていくつか説明します。

   * 「プラグインオファー」の一部として返される HTML コンテンツが正しく表示されませんが、オファー内の JavaScript は予期したとおりに実行されます。
   * グローバル mbox に返される JavaScript オファーには、`<script>` タグに埋め込まれた JavaScript コード、または `src` 属性で参照される JavaScript コードを組み込めます。

      これをおこなうには、次のようにスクリプトの呼び出しに `async` 属性を追加します。

      `<script src='external-url' async='true'></script>`

      Internet Explorer では、`async` 属性は限定的にしかサポートされていないので（詳しくは [https://developer.mozilla.org/ja/docs/Web/HTML/Element/script#Browser_compatibility](https://developer.mozilla.org/en/docs/Web/HTML/Element/script#Browser_compatibility) を参照）、古いバージョンの IE を使用している訪問者は、これらのサードパーティスクリプトを含むテストから除外する必要があります。

* バージョン 56 で報告された、mbox.js の Extra JavaScript セクションの変更に起因する問題を修正しました。Extra JavaScript セクション内のすべてのコードは、再びグローバルスコープで利用できるようになりました。

次の機能は、mbox.js バージョン 57 ではサポートされていません。

* Target Standard で生成された、自動作成されるグローバル mbox は、Target Classic のホストされたオファータイプでは動作しません。ホストされたオファータイプには、「サイト上のオファー」および「Test&amp;Target の外部のオファー」があります。

   つまり、Target Classic では、これらのいずれかのオファーが必要な場合、Target Standard から自動作成されるグローバル mbox を選択してはいけません。
* JavaScript プラグインのみがサポートされています。

   プラグインのオファーで JavaScript コードと HTML が組み合わせて使用されている場合、JavaScript コードは実行されますが、HTML コンテンツは表示されません。

mbox.js バージョン 57 にも、重要な修正が含まれています。

* mbox.js v56 で SiteCatalyst プラグインが動作しない原因となっていた問題を修正しました。
* スコープの変更によって Extra JavaScript エラーを発生させていた問題を修正しました。
* mboxFactory のコンストラクターに対する変更を元に戻しました。

## mbox.js バージョン 56 {#section_C4F4A53584B741FF9FD907D81CB7E164}

**Target リリース：** 15.1.2

**リリース日：** 2015 年 2 月 18 日

>[!NOTE]
>
>`target.js` が読み込めなかった場合にタイムアウトの問題が発生することがあります。バージョン 57 で、この問題を修正しました。ただし、[!DNL Experience Cloud Visitor ID] サービスを使用している場合、バージョン 58 以降が必要です。

このバージョンでは、次の変更がおこなわれました。

* Recommendations Premium が変更され、グローバル mbox にパラメーターを渡せるようになりました。
* target.js の読み込み呼び出しに 5 秒のタイムアウトが追加されました。まれにファイルが読み込まれない場合があり、その場合、ページは表示されますが、Target Standard のアクティビティは表示されません。
* 「Extra JavaScript」の実行を、グローバル mbox の前に移動しました。

   バージョン 56 以降のすべての設定には名前空間が付加されます。「Extra JavaScript」に宣言されている関数がある場合は、それらの関数の前に `window` を付加する必要があります。

   次に例を示します。

   `function foo {`

   `}`

   これを、次のように記述します。

   `window.foo = function() {`

   `}`

   グローバルにアクセスできるすべての変数の前にも、`window` を付加する必要があります。

* 配信中に target.js の読み込みに失敗した場合に mbox.js がユーザーに対して設定する「em-disabled」という名前の cookie が追加されました。この cookie は、Visual Experience Composer を使用して作成されたオファーがサイトに表示されないようにします。この cookie が設定されたユーザーには、テストコンテンツが表示されず、それらのアクティビティレポートでもカウントされません。その他すべてのオファーコンテンツ（例えば Target Classic のキャンペーンのコンテンツ）は引き続き読み込まれます。この cookie の有効期間は、読み込み失敗時から 30 分です。

## mbox バージョン 55

**Target リリース：** 15.1

**リリース日：** 2015 年 1 月 19 日

バージョン 53 に IE の修正を加えました。

## mbox バージョン 54

**Target リリース：** 14.9.2

**リリース日：** 2014 年 9 月 30 日

グローバル mbox の実装を、document.write から AJAX に変更しました。これにより、mbox.js ファイルをページの <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> の最後の項目にするという要件は必要なくなりました。このバージョンは、API からのみ利用できます。クライアントは、この mbox.js ファイルをダウンロードして使用できます。サイトによっては、コンテンツでこの実装を使用している場合と使用していない場合があります。サイトの統合の状況を確認してください。

## mbox バージョン 53

**Target リリース：** 14.9.1

**リリース日：** 2014 年 9 月 14 日

Target のページパラメーターが Internet Explorer で正しく呼び出されない問題を修正しました。

## mbox バージョン 52

**Target リリース：** 14.8

**リリース日：** 2014 年 8 月 14 日

mboxParameter 関数が Target Standard/Premium で動作するようになりました。

Analytics の追跡が IE 9 および 11 で動作しなかった問題を修正しました。この変更は、Analytics のユーザーのみに影響します。

targetPageParams() 関数を使用して target-global-mbox に配列、JSON オブジェクトまたはコンマ区切り形式のリスト（以前サポートされていた方法）で[パラメーターを渡す](https://marketing.adobe.com/resources/help/en_US/target/ov/c_pass_parameters_to_global_mbox.html)ことができるようになりました。

M2PcId、および VisitorId に関連するすべての名前を変更しました。

登録されている mbox の defaultDiv をクリアできるようになりました。

## mbox バージョン 51

**Target リリース：** 14.6

**リリース日：** 2014 年 6 月 25 日

トップレベルドメインの文字数が 2 文字のサイトに不正な Cookie が送信されるバグを修正しました。

ハッシュタグの値が返される mbox.js の軽微なバグを修正しました。

## mbox バージョン 50

Target Standard と Target Classic の間の同期を改善しました。

## mbox バージョン 49

ネストされた mbox の Internet Explorer 10 でのサポートを改善しました。

## mbox バージョン 48

Target のレポートソースとして Adobe Analytics のサポートが追加されました。

## mbox バージョン 47

mbox.js で、Target Standard 用のカスタムのグローバル mbox 名の使用をサポートするようになりました。

## mbox バージョン 46

Target Standard の単一行コード実装に、Experience Cloud の訪問者 ID サービスの完全なサポートが追加されました。これにより、サーバーサイドでの Adobe Analytics 統合および Experience Cloud 共有プロファイルが可能になります。

IE 10 でドキュメントモードでコンテンツを配信する場合の問題が修正されました。

## mbox バージョン 45

Experience Cloud の訪問者 ID サービスの完全なサポートが追加されました。これにより、サーバーサイドでの Adobe Analytics 統合および Experience Cloud 共有プロファイルが可能になります。

## mbox バージョン 44

mboxVizTarget により、URL に新しいパラメーターが追加されました。

mboxDOMLoaded

## mbox バージョン 43

Target Standard のサポートが追加されました。

## mbox バージョン 42

Experience Cloud 共有訪問者 ID サービスの初期サポートが追加されました。

## mbox バージョン 41

* x のみの設定でも、読み込み時間を短縮するため、および継続的なページ更新を防ぐために、ファーストパーティ cookie を無効化しました。

   Target への呼び出しが時間以内に戻らない場合は、タイムアウト Cookie が設定されます。これは、サードパーティ Cookie のみを使用する方法よりも高速です。サードパーティ Cookie のみを使用する場合は、Target サーバーから有効な応答が返されるのを待つ間、ページが継続的に更新されます。

* mbox.js が有効のときだけトラフィック制限が発生するように修正しました。

   この問題は、ユーザーの mbox.js に対してトラフィック制限が発生しており、タイムアウト設定が適切に動作しないことにより発生していました。これにより、Target サーバーから有効な応答が返されるのを待つ間、ページが更新されていました。

* SiteCatalyst プラグインが常に Ajax フェッチャーを使用するように修正しました。

   この変更をおこなう前は、Test&amp;Target から SiteCatalyst へのプラグインのユーザーに対して、プラグインのロードのタイミングによっては、ページを消去する document.write が呼び出されるという状況が発生していました。

## mbox バージョン 38

ページベースで SiteCatalyst を Test&amp;Target に統合するためのサポートが追加されました（有効にする必要あり）。

## mbox バージョン 37

エンコードされた URL キー

## mbox バージョン 36

mbox が tt.omtrdc.net を使用するように変更されました。

## mbox バージョン 35

* Mbox のデバッグが常にリモートになりました。
* mboxTime パラメーターが追加されました。このパラメーターは、ユーザーがそれを目にした時刻を表します（エポック（GMT）からの経過ミリ秒で表現）。この値は 1 回のみ計算されます。

## mbox バージョン 34

* キャッシュされたバージョンを参照するのではなく、常に最新のデフォルト div の取得を試みるようになりました。

   これにより、デフォルト div のコンテンツを提供する mboxUpdate のせいで、キャッシュされたデフォルトコンテンツ div が DOM 内に含まれなくなる問題が修正されました。

* mbox.getDefaultDiv に新しいオプションのブール型パラメーターが追加されました。この値が true の場合は、現在のデフォルト div が返されます。false の場合は、前回キャッシュされたデフォルト div が返されます。
* mbox.loaded が Ajax の読み込みをサポートするように修正されました。
* mboxURL パラメーターが、escape ではなく encodeURIComponent を使用してエンコードされるようになりました。
* ブラウザーが encodeURIComponent をサポートしているかどうかをテストし、サポートしていない場合はデフォルトコンテンツを表示するようになりました。また、次の mbox.js config オプションが削除されました。
   * encode\_mbox\_parameters
   * mbox\_signal\_support
