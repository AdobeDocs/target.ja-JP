---
description: at.js の各バージョンでの変更の詳細について説明します。
keywords: at.js リリース;at.js バージョン
seo-description: at.js の各バージョンでの変更の詳細について説明します。
seo-title: at.js のバージョンの詳細
solution: 'Target '
subtopic: 導入
title: at.js のバージョンの詳細
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# at.js のバージョンの詳細 {#at-js-version-details}

[!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。

>[!IMPORTANT]
>
>Target チームがサポートを提供しているのは、[!DNL at.js] の最新バージョンとその 1 つ前のバージョンの 2 つのみです。必要に応じて [!DNL at.js] をアップグレードし、サポート対象のバージョンを使用するようにしてください。

## at. jsバージョン2.1.0（2019年6月3日）

このリリースには、次の機能および機能強化が含まれています。

* **アドビオプトインのサポート**:アドビオプトインは、アドビソリューション統合を、同意管理プラットフォームと単純化するための手段です。For more information about Adobe Opt-in, see [Privacy and General Data Protection Regulation (GDPR)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md).

* **業界標準のCSP準拠**:at. jsは、eval（）を使用してJavaScriptを実行しなくなりました。

* **クライアント側の分析ログ**:顧客側またはサーバー側でAnalyticsデータをAdobe Analyticsに送信する方法をユーザーに完全に制御します。

   For more information, see [Client-side Analytics logging](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) in *Before you implement*.

* **通知**&#x200B;の送信:エクスペリエンスが使用 `applyOffer()` せずにコードによってレンダリングされた場合に、開発者に通知を送信することを許可 `applyOffers()`します。

   For more information, see [adobe.target.sendNotifications(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md).

* **at. jsサイズが~24%減少**&#x200B;した場合:at. jsのサイズは24%減少します。ファイルサイズが小さければページの読み込みパフォーマンスが向上し、ページにat. jsをダウンロードする時間が短縮されます。

## at.js バージョン 2.0.1（2019 年 3 月 20 日）

これはメンテナンスリリースで、次の機能強化および修正が含まれています。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

* 特定の顧客に JavaScript の例外が発生する、DOM ポーリングコードの競合状態を解消しました。（TNT-31869）
* 表示される通知が、クリック追跡イベントハンドラーから切り離されていた問題を修正しました。当初、レンダリングされたビューに属するクリックイベントハンドラーをアタッチできなかった場合、Target は通知を送信しませんでした。クリック要素が見つからない場合でも、Target がビュー通知を送信するようになりました。（TNT-31969）
* リクエストに成功したイベントのリダイレクトフラグが常に true に設定されていた問題を修正しました。（TNT-31907）
* 要素が見つからない場合でも VEC の並べ替えアクションが成功として記録される問題を修正しました。（TNT-31924）
* 特定の顧客への通知に Enterprise 権限のプロパティトークンが含まれていない問題を修正しました。（TNT-31999）

## at.js バージョン 1.7.1（2019 年 3 月 20 日）

これはメンテナンスリリースで、次の修正が含まれています。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

* 特定の顧客に JavaScript の例外が発生する、DOM ポーリングコードの競合状態を解消しました。（TNT-31869）

## at.js バージョン 2.0.0 {#at-js-200}

at.js 2.x は、次世代のクライアントサイドテクノロジーでパーソナライゼーションを実行するための機能セットを提供します。この新しいバージョンは、シングルページアプリケーション（SPA）と調和したインタラクションを実現するための at.js のアップグレードに焦点を当てています。

以前のバージョンでは利用できない、at.js 2.x を使用するメリットを紹介します。

* ページ読み込み時にすべてのオファーをキャッシュして、単一のサーバーコールに対する複数のサーバー呼び出しを減らす機能。
* 従来のサーバー呼び出しで発生する遅延時間なしで、キャッシュ経由でオファーが即座に表示されるため、サイトでのエンドユーザーのエクスペリエンスが著しく向上します。
* 単純な 1 行のコードと一度限りの開発者セットアップで、マーケティング担当者は、シングルページアプリケーション上の Visual Experience Composer（VEC）を介して A/B およびエクスペリエンス（XT）アクティビティを作成して実行できます。

at.js 2.x では、次の新しい関数が導入されています。

* getOffers（）
* applyOffers（）
* triggerView（）

at.js 2 x の導入に伴い、次の関数が廃止されました。

* mboxCreate()
* mboxDefine
* registerExtension()

詳しくは、「[at.js 1.x から at.js 2 へのアップグレード](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md)」と「[at.js 関数](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)」を参照してください。

>[!NOTE]
>
>[一般的なデータ保護規則](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) （GGPR）のAdobeオプトインサポートが必要な場合は、現在at. js1.7.0またはat. js2.1.0を使用する必要があります。

## at.js バージョン 1.7.0 {#at-js-170}

at.js 1.7.0 では、Adobe Opt-in サポートが導入されています。Adobe Opt-In は、アドビソリューションと同意管理プラットフォームの統合を簡略化する方法です。

Adobe Opt-in に関する詳細については、「[プライバシーと一般データ保護規則](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)（GDPR）」を参照してください。

また、このリリースでは、リダイレクト URL から取得されたパラメーターを使用して Target がリダイレクト URL パラメーターを上書きする場合がある問題も修正されました。

>[! 注意]
>
>If you require Adobe Opt-in support for GDPR, you must currently use at.js 1.7.0 or 2.1.0.<br>For a list of all versions, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## at.js バージョン 1.6.4 {#at-js-164}

at.js 1.6.4 は メンテナンスリリースで、次の問題に対応しています。

* Microsoft Internet Explorer 11 で、重複するオファーが適用される競合条件のマニフェストを修正しました。

## at.js バージョン 1.6.3 {#section_484A56774E004282B98FFFF851E4E670}

at.js バージョン 1.6.3 には、次の修正および機能強化が含まれています。

* 先頭が数字、2 つのハイフン、またはハイフンの後に数字が続く（例えば #-123）ID や CSS クラスがセレクターに含まれる場合、セレクターは CSS エスケープされるようになりました。（TNT-31061）
* at.js 1.6.2 で発生した、同じ CSS セレクターに適用される異なるアクティビティから Visual Experience Composer（VEC）オファーによってアクティビティの優先度が考慮されない問題を修正しました。（TNT-31052）
* プロミスのネイティブサポートがない環境で、プロミスのタイムアウトに関する問題を修正しました。（TNT-30974）
* コンテンツレンダリングに失敗したイベントを使用して、問題が正しくキャプチャおよびレポートされるようになりました。以前は、JavaScript が大文字と小文字が異なる場合でも、正常に実行されていた可能性がありました。（TNT-30599）

## at.js バージョン 1.6.2 {#section_88BE2F69943D4280B8170F377886B58E}

これはメンテナンスリリースで、次の問題に対処しています。

* 一部のお客様サイトで「非同期」ループが発生する問題を修正しました。

>[!IMPORTANT]
>
>また、at.js バージョン 1.6.2 には at.js バージョン 1.6.1 および 1.6.0 に含まれている機能強化と修正がすべて含まれています。これらのバージョンは既にダウンロードできなくなっています。1.6.1 または 1.6.0 を使用している場合は、バージョン 1.6.2 にアップグレードすることをお勧めします。

at.js バージョン 1.6.1 に含まれている機能強化と修正を以下に示します。

* Microsoft Internet Explorer 11 でレコメンデーションエクスペリエンスが重複する原因となっていた at.js 1.6.0 の問題を修正しました。（TNT-30593）
* at.js のエッジオーバーライドロジックでエッジクラスター Cookie の存在がチェックされるようになりました。これにより、ユーザーがセッション中にエッジ間を移動した場合に異なるエッジ番号が使用される問題を回避できます。（TNT-30563）
* HTML コンテンツに無効な JS コードが含まれている場合に at.js が後続のアクションを実行できなかった問題を修正しました。これにより、at.js でエラーが記録され、残りのアクションが問題なくレンダリングされるようになりました。（TNT-30546）
* リダイレクトページがリダイレクトアクティビティの条件を再度満たしたときに例外をスローするように変更を加えました。（TNT-30532）
* getOffer() API リクエストから正しいリクエストタイムアウトが伝達されていなかった問題を修正しました。（TNT-30498）
* ファイルプロトコルが使用されている場合に at.js 1.6.0 が Cookie を保存できなかった問題を修正しました。（TNT-30454）
* Analytics for Target（A4T）が使用されている場合にリダイレクトと共にすべてのエクスペリエンスが配信されていないように見える問題を修正しました。（TNT-30444）
* Target 呼び出しが成功した後にページが非表示になる問題を修正しました。（TNT-30358）

at.js バージョン 1.6.0 に含まれている機能強化と修正を以下に示します。

* Analytics for Target（A4T）統合でリダイレクトオファーが自動的にサポートされるようになりました。クライアント側の回避策は削除されました。（TNT-30247）
* クライアント側のエッジルーティングがデフォルトで有効になりました。（TNT-30261）
* アクション間に依存関係がある場合に Visual Experience Composer（VEC）でアクションをレンダリングするときに発生していた問題を修正しました。（TNT-30248）

## at.js バージョン 1.5.0 {#section_128C6761884C4DA8AE50D6A605FF6F55}

at.js バージョン 1.5.0 がリリースされました。

* `at-request-succeeded` イベントの詳細には、リダイレクトフラグが含まれています。このフラグを使用すると、ページが別の URL にリダイレクトされるかどうかを判断することができます。その URL を知る必要がある場合は、subscribe to `at-content-rendering-redirect` をサブスクライブします。（TNT-29834）
* `window.targetGlobalSettings.enabled` を false に設定すると失敗して実行時例外が発生する原因となっていた問題を修正しました。（TNT-29829）
* グローバル mbox リクエストを発行したり本文を非表示にしたりすると、Visual Experience Composer（VEC）への読み込み中にページが失敗する原因となっていた問題を修正しました。（TNT-29795）
* `screenOrientation`、`devicePixelRatio`、および `webGLRenderer` のサポートを追加しました。これらの新しい Target リクエストパラメーターは、iPhone X やその他の最新型デバイスの検出に使用されます。詳しくは、[モバイル](../../c-target/c-audiences/c-target-rules/mobile.md#concept_2A794199DC1A4D349FFFBC7DCF1FEB89)を参照してください。（TNT-29781）
* Adobe Audience Manager（AAM）のロケーションヒントが送信されないことがある問題を修正しました。（TNT-29695）
* これをサポートしているブラウザーの場合、at.js 1.5.0 はセレクターポーリングの際に MutationObserver に切り替わります。at.js 1.0.0 以前のバージョンでは、MutationObserver ポリフィルを使用していましたが、これは問題があることがわかっていました。ポリフィルの問題を回避するために、バージョン 1.5.0 では次の擬似コードを使用して、どのスケジューリングメカニズムを使用するかを決定しています。

   ```
   if MutationObserver is supported
     scheduler = MutationObserver
   else if document is visible
     scheduler = requestAnimationFrame
   else
     scheduler = setTimeout
   ```

## at.js バージョン 1.3.0 {#section_24EAAE1CFA814EF8B19E61842F4D8321}

at.js バージョン 1.3.0 がリリースされました。

* at.js とのインタラクションの追跡、デバッグ、カスタマイズに役立つ次の新しいイベントを利用できます。

   * LIBRARY_LOADED
   * REQUEST_START
   * CONTENT_RENDERING_START
   * CONTENT_RENDERING_NO_OFFERS
   * CONTENT_RENDERING_REDIRECT
   詳細については、「[at.js カスタムイベント](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md)」を参照してください。

* データプロバイダーから取得した追加パラメーターを利用して at.js リクエストを拡張できます。データプロバイダーは、`dataProviders key` の `window.targetGlobalSettings` に追加する必要があります。

   詳細については、「[データプロバイダー](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)」を参照してください。

* at.js リクエストで GET が使用されるようになりましたが、URL が 2,048 文字を超える場合は POST に切り替わります。`urlSizeLimit` という名前の新しいプロパティを利用して、この文字数の上限を引き上げることができます。この変更により Target は、at.js と、同一の技術を使用する AppMeasurement を連携させることができるようになります。
* Target では、`adobe.target.applyOffer(options)` 関数で `mbox` キーが強制されるようになりました。これまでもこのキーは必須でしたが、Target では、適切な検証がおこなわれ、お客様がこの関数を正しく利用するために、使用が強制されるようになりました。
* at.js のイベントとクリック追跡機能が強化されました。at.js では、`navigator.sendBeacon()` を使用してイベント追跡データを送信し、`navigator.sendBeacon()` がサポートされていない場合は同期 XHR にフォールバックします。このフォールバックが影響するのは、主に Internet Explorer 10 および 11 と、Safari の一部のバージョンです。Safari では、今後の iOS 11.3 のリリースで `navigator.sendBeacon()` のサポートが追加されます。
* at.js で、バックグラウンドタブでページが開かれている場合でもオファーをレンダリングできるようになりました。Target の一部のお客様では、バックグラウンドのタブに対するブラウザーの調整動作が原因で、`requestAnimationFrame()` が無効になっている場合に問題が発生していました。
* このリリースで、Chrome の CPU プロファイルを検査する際のコールスタックの短縮など、パフォーマンスの改良が多数加えられています。
* at.js 1.3.0 では、Microsoft Internet Explorer 9 でのコンテンツ配信がサポート対象外になりました。サポートされているブラウザーの一覧については、[サポートされているブラウザー](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)を参照してください。今後、すべてのリクエストは、JSONP リクエストを使用せず、CORS に対応した `XMLHttpRequest` を介して実行されます。この変更によってセキュリティが大幅に高まります。

## at.js バージョン 1.2.3 {#section_CE4D14AF00D04F4C8A2F0513F5EA1A84}

[!DNL at.js] バージョン 1.2.3 がリリースされました。

* JSON オファーのサポートを追加しました。JSON オファーは、フォームベースの Experience Composer を使用して作成されたアクティビティでのみ利用できます。現時点で JSON オファーを使用できる方法は、直接の API 呼び出しのみとなっています。「[JSON オファーの作成](../../c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D)」を参照してください。

## at.js バージョン 1.2.2 {#section_4E96D13F2DFE4F1F81A1089877D53649}

[!DNL at.js] バージョン 1.2.2 がリリースされました。

* ページに読み込まれたターゲットライブラリで QUIRKS モードを使用している場合に JavaScript エラーが返されていた問題を修正しました。（TNT-28312）
* Target のクリック追跡が原因となって Analytics のデータ収集の呼び出しが中止される問題を修正しました。（TNT-28261）
* `targetPageParams()` が空の文字列を返した場合に `getOffer() params` が失敗する問題を修正しました。（TNT-28359）
* 「x のみ」を使用している場合にセッション ID の生成で発生する問題を修正しました。（TNT-28361）

## at.js バージョン 1.2.1 {#section_F757C8174BBA4F68AC5524ADC3D9C5E3}

[!DNL at.js] バージョン 1.2.1 がリリースされました。

* target="_blank" を含むリンクでのクリック追跡時に、Target からリンクを新しいタブで開くことができない問題を修正しました。

## at.js バージョン 1.2.0 {#section_1C3A18C595C34B25A14A440D213F3B9C}

[!DNL at.js] バージョン 1.2 が、大部分のバグ修正を含むメンテナンスリリースとして公開されました。

* クリック追跡の特殊なケースでのデフォルトのアクションを妨げていた問題を修正しました。（TNT-28089）
* `target="_blank"` を含むリンクでのクリック追跡時に、Target からリンクを新しいタブで開けない問題を修正しました。（TNT-28072）
* IP アドレスを Cookie ドメインとして使用できます。（TNT-28002）
* グローバル mbox またはその他のリージョナル mbox を含むリダイレクトオファーでちらつきが生じる問題を修正しました。（TNT-27978）
* VEC で参照と構成を切り替えると、エクスペリエンスのターゲット設定アクティビティの設定が失敗する問題を修正しました。（TNT-27942）
* クリック追跡要素の flicker スタイルクラスの処理に関する問題を修正しました。（TNT-27896）
* グローバル mbox パラメーターがすべての mbox パラメーターと混同される問題を修正しました。（TNT-27846）
* Handlebars、Mustache、その他のクライアント側テンプレートライブラリが [!DNL at.js] によって適切に処理されるよう変更を加えました。（TNT-27831）
* `sdidParamExpiry` が適切に初期化され、訪問者 API に渡されるよう変更しました。これは、`at.js 1.1.0` に追加された回帰です。それより前のバージョンの [!DNL at.js] には影響はありません。リダイレクトオファーと A4T を使用するクライアントのみに影響します。（TNT-27791）
* どの type 属性を使用していても `SCRIPT` が実行されるよう変更しました。（TNT-27865）

## at.js バージョン 1.1.0 {#section_8F494E1EA94E48A9B169F5CF9FE6DC56}

**日付：** 2017 年 8 月 3 日

[!DNL at.js] バージョン 1.1 には、次の機能強化および修正が含まれています。

* レスポンストークンの処理を追加しました。詳しくは、[レスポンストークン](../../administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4)を参照してください。
* 問題を解消し、`document.currentScript polyfill` が Angular 1.X に干渉しないようにしました。
* 変更を加え、クリック追跡が visibility プロパティに干渉しないようにしました。クリック追跡要素が、`at-element-click-tracking` ではなく `at-element-marker` の CSS クラスに分類されます。

## at.js バージョン 1.0.0 {#section_37A3D23FC4AD42A68AA831B89E03E725}

**日付：** 2017 年 7 月 8 日

at.js バージョン 1.0 には、次の機能強化および修正が含まれています。

* ページ読み込みを高速化するために、at.js の非同期での読み込みに対応。
* at.js を非同期で読み込む際のページコンテンツの事前非表示に対応。
* コンテンツ配信が無効にされたときのエラーメッセージを改善。
* 複数のアクティビティを配信する際のパフォーマンスを向上。
* YUI Compressor に対応。
* アクティビティ配信時のカスタムイベントのバグ／エラーレポート。
* Microsoft Internet Explorer 11 のパフォーマンスの問題を修正。
* 一部の Web サイトで `getOffer()` 関数によりエラーが発生する問題を修正。
* Target ライブラリを非同期で読み込み。詳細については、「[at.js に関するよくある質問](../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769)」を参照してください。

## at.js バージョン 0.9.7 {#section_6C7B698BE21E40E495FD2850EFBF3E80}

**日付：** 2017 年 5 月 23 日

[!DNL at.js] バージョン 0.9.7 には、次の機能強化および修正が含まれています。

* Visual Experience Composer（VEC）で、`insertAfter` および `insertBefore` アクションにないアセットキーに関連する問題を修正しました。これは、ビジュアルオファーからオファーテンプレートへの移行に関連する問題でした。

## at.js バージョン 0.9.6 {#section_EEFA6413F2F947AD8C4A88128B90245D}

**日付：** 2017 年 4 月 14 日

[!DNL at.js] バージョン 0.9.6 には、次の機能強化および修正が含まれています。

* A4T のリダイレクトオファーのサポート。[!DNL at.js] バージョン 0.9.6 をダウンロードしてインストールすると、[!DNL Adobe Analytics]（A4T）のレポートソースとして [!DNL Target] を使用するアクティビティでリダイレクトオファーを使用できます。[!DNL at.js] バージョン 0.9.6 のほかにも、リダイレクトオファーと A4T を使用するために実装が満たす必要があるその他の最小要件があります。詳細および追加の重要な情報については、[リダイレクトオファー - A4T に関する FAQ](../../c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905) を参照してください。
* [!DNL at.js] 0.9.6 より前では、訪問者 API がページにある場合に、`visitorApiTimeout` 設定が積極的すぎると、[!DNL Target] リクエストで MCID データが送信されないという状況が発生する可能性がありました。その結果、A4T を使用しているときに、[!DNL Analytics] で未関連付けヒットなどの問題が発生することがありました。

   この動作は、[!DNL at.js] 0.9.6 で変更されました。`visitorApiTimeout` が 1 ミリ秒に設定されていても、Target は SDID、トラッキングサーバーおよび顧客 ID データを収集して Target リクエストで送信しようとします。

* `selectorsPollingTimeout` 設定が追加されました。詳しくは、[targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) を参照してください。
* `getOffer()` からの応答の形式が変更されました。詳しくは、[adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) を参照してください。
* サポートされていない `<!DOCTYPE>` 宣言のコンソールログが追加されました。
* 1つの mbox に複数のデフォルトオファーが配信されると [!DNL Target Classic] のプラグインが正しく適用されない問題が修正されました。（TGT-22664） For more information, see [Plug-Ins](https://marketing.adobe.com/resources/help/en_US/tnt/help/t_Using_Plug-Ins.html) in the Adobe Target Classic documentation.
* 2 文字のトップレベルドメイン（TLD）の Cookie 設定が改良され、これらのドメイン（[!DNL test.no]、[!DNL autodrives.ca] など）に対して mbox Cookie が正しく設定されるようになりました。
* at.js バージョン 0.9.6 で、Cookie の保存時に使用するトップレベルドメインを抽出するアルゴリズムが変更されました。これにより、IP を使用するアドレスには Cookie を保存できなくなりました。IP アドレスはテスト目的で使用されるケースがほとんどですが、DNS エントリを使用したり、ローカルボックスのホストファイルを変更したりすることで対処できます。
* プロパティが整数値ではなく文字列値の場合の移動および整列操作の処理に関する記述を修正しました。

## at.js バージョン 0.9.4 {#section_A15B12F12CD94F07B3F56613A79A815F}

**日付：** 2017 年 1 月 20 日

* mbox.js 使用時の mbox 名のネーミング要件に対応して、mbox 名にアンパサンド（&amp;）を含む特殊文字を使用できるようになりました。

   使用可能な特殊文字のリストについては、「[at.js の設定](../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_2FA0456607D04F82B0539C5BF5309812)」を参照してください。

* `secureOnly` 設定が追加され、at.js で HTTPS のみを使用するか、ページのプロトコルによって HTTP と HTTPS との切り替えを許可するかを指定できるようになりました。この詳細設定のデフォルト値は False で、`targetGlobalSettings` で上書きできます。
* 「[!UICONTROL レガシーブラウザーのサポート]」オプションは、at.js バージョン 0.9.3 以前で使用できます。このオプションは、at.js バージョン 0.9.4 で削除されました。

## at.js バージョン 0.9.3 {#section_DF13BC1D7C994AE7A36B81937A699DF4}

**日付：** 2016 年 10 月 11 日

* at.js 設定でレガシーブラウザーが無効になっている場合に、Microsoft Internet Explorer 11 で mbox 呼び出しを実行します。
* 動的リモートオファーに失敗する場合（例えば、URL が正しくなく、404 エラーが返される場合）に、デフォルトコンテンツがレンダリングされます。
* VEC クリックトラッキングセレクターが DOM で見つからない場合に、要素がすばやく表示されます。

## at.js バージョン 0.9.2 {#section_148549CBB4F046BAA8F79C79B64EC889}

**日付：** 2016 年 9 月 22日

* デバイスグラフオプトアウト機能を有効化または無効化するための `optoutEnabled` 設定が追加されました。これが `true` に設定されており、訪問者がトラッキングをオプトアウトしている場合は、訪問者のブラウザーで mbox の呼び出しは一切おこなわれません。Device Graph は現在ベータ版です。この設定はデフォルトでは `false` に設定されていますが、デバイスグラフを使用するには `true` に設定する必要があります。類似のオプションが mbox.js バージョン 61 にあります。
* `CustomEvent` のサポートを通知メカニズムに追加しました。以前は at.js のイベント通知メカニズムが `document.addEventListener()` () など通常の DOM API では使用できませんでした。現在は、`document.addEventListener()` を使用し、リクエストイベントやコンテンツレンダリングイベントなどの at.js イベントに登録できます。
* Visual Experience Composer（VEC）で作成されたオファーに関連する問題が修正されました。このリリース前は、Target ではセレクターを非表示にして、すべてのセレクターが一致する場合にのみ非表示を解除していました。at.js 0.9.2 では、一致するセレクターの非表示が直ちに解除されます。

## at.js バージョン 0.9.1 {#section_DAFB99114D604CFB8416C1BC7DEEAEEE}

**日付：** 2016 年 7 月 15 日

* at.js で訪問者 ID サービス用のタイムアウトを提供します。このタイムアウトは、サービス自体のタイムアウトとは独立したものです。
* 一部のページでは at.js を使用し、別のページでは mbox.js を使用する、実装に影響のあった 0.9.0 の問題を修正します。
* Adobe Analytics をアクティビティのレポートソースとして使用する場合、 mbox.js バージョン 61 （またはそれ以降）または at.js バージョン 0.9.1 （またはそれ以降）を使用しているのであれば、アクティビティを作成する際にトラッキングサーバーを指定する必要はありません。mbox.js または at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。

## at.js バージョン 0.9.0 {#section_2981CC9792F245389B39BB5B69F84C4E}

**Target リリース：** 16.6.1

**日付：** 2016 年 6 月 24 日

* VEC オファー使用中の白い画面の問題を修正します。[!DNL at.js] を使用している方は全員、この新しいバージョンへアップグレードしてください。
* 新規 `registerExtension` API

   この新しい API は、[!DNL at.js] で使用される jQuery モジュールの一部へ開発者がアクセスし、ライブラリの拡張（プラグイン）を開発することを可能にします。この変更に伴い、気をつけるべき事項がいくつかあります。これは、次の機能を使用しているユーザーのみに影響します。

   * `getSettings()` API は廃止されましたが、`registerExtension()` を使用すると同じ機能が利用できます。
   * `getTracking()` API は廃止されましたが、`registerExtension()` を使用すると同じ機能が利用できます。

   * 既存の拡張（AngularJS 拡張など）は `registerExtension()` の手法を使用するように更新する必要があります。

* 新規 at.js 通知 API

   この通知システムの目的は、問題が発生した際に [!DNL at.js] がページ上でどう動作していたかについての理解を助けることです。VEC でよく見られる問題は、IT がページの変更をリリースすると VEC セレクターが壊れ、テストがコンテンツを正しく配信しなくなることです。この通知システムの目的は、この配信の問題をページに知らせることで、開発者がその情報にアクセスして [!DNL Adobe Analytics] のようなシステムに渡し、テストが壊れたという通知をビジネスオーナーに送信できるようにすることです。

* 新規 `targetGlobalSettings()` API メソッド

   [!DNL Target Standard/Premium UI] や REST API を使用して設定を構成する代わりに、at.js ライブラリで設定を上書きできます。

## at.js バージョン 0.8.0 {#section_E1C7B08EC0494388A022C28A8B8FE807}

**日付：** 2016 年 5 月 6 日

[!DNL at.js] ライブラリの最初の正式リリースです。

[!DNL at.js] は、一般的な Web 実装とシングルページアプリケーションの両方のために設計された、[!DNL Target] の新しい実装ライブラリです。

[!DNL at.js] は、[!DNL Adobe Target] 実装の [!DNL mbox.js] を置き換えます。

>[!NOTE]
>
>[!DNL at.js] は [!DNL mbox.js] に替わって使用されますが、mbox.js も引き続きサポートされます。ほとんどのユーザーにとって、[!DNL at.js] には [!DNL mbox.js] よりもメリットがあります。このサポートの継続により、[!DNL at.js] をテストしてページ上の実装を変更するための時間が得られます。

多くのメリットがある中でも、[!DNL at.js] は、Web 実装のページ読み込み時間を強化し、セキュリティを強化して、シングルページアプリケーション向けのより優れた実装オプションを提供します。

[!DNL at.js] は、[!DNL target.js] に含まれるコンポーネントを含んでいるので、[!DNL target.js] を呼び出す必要がありません。

[!DNL at.js] を実装する際には、以下のことに注意してください。

* Internet Explorer 8 より前のバージョンはサポートされません。
* 非同期実装は、[!DNL Test&Target] と [!DNL SiteCatalyst] プラグインのような従来の統合が動作しない可能性があることを意味します。
* [!DNL Target] オブジェクトおよびメソッドを参照する プラグインはサポートされません。[!DNL mbox.js]
* [!DNL Target] に対するすべての呼び出しは XMLHTTPRequest を使用しておこなわれ、コンテンツは JSON を使用して返されます。
