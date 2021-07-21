---
keywords: ターゲット設定；visual experience composer；ホワイトリスト；ホワイトリスト；許可リスト;許可リスト；拡張visual experience composer;vec;visual experience composerのトラブルシューティング；トラブルシューティング；eec；拡張experience composer;tls;tls 1.2
description: Adobe [!DNL Target] Visual Experience Composer(VEC)と拡張Experience Composer(EEC)で特定の条件下で発生することがある問題のトラブルシューティング方法について説明します。
title: Visual Experience Composerと拡張Experience Composerに関連する問題のトラブルシューティング方法を教えてください。
feature: Visual Experience Composer（VEC）
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: 1da930f2dfe13fc7710da000f0d13d6aacd223b1
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 49%

---

# Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer](VEC)と[!UICONTROL 拡張Experience Composer](EEC)では、特定の条件下で表示の問題やその他の問題が発生する場合があります。

## Google Chrome SameSite cookieの適用ポリシーは、VECとEECにどのような影響を与えますか？ {#samesite}

次のChromeリリースを使用する際のVECとEECに影響する変更点に注意してください。

**Chrome 94（2021年9月22日）**:Chrome 94リリース（2021年9月22日）に予定されている差し迫った変更により、次の変更はChrome 94以降のブラウザーバージョンを使用するすべてのユーザーに影響します。

* コマンドラインフラグ`--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure`は削除されます。

**Chrome 91（2021年5月26日）**:Chrome 91リリース（2021年5月26日）用に実装された変更点を使用すると、Chrome 91以降のブラウザーバージョンを使用しているすべてのユーザーに次の変更が影響します。

* フラグ`#same-site-by-default-cookies`と`#cookies-without-same-site-must-be-secure`が`chrome://flags`から削除されました。 この動作は、デフォルトで有効になりました。

**Chrome 80（2020年8月）**:2020年8月に実装された変更により、Chrome 80以降のブラウザーバージョンを持つすべてのユーザーは、以下のようになります。

* サイトのパスワードで保護されたページでVECを（VECヘルパー拡張機能がインストールされ有効になっているかどうかに関わらず）*使用できない*。 サイトのログインCookieはサードパーティCookieと見なされ、ログインリクエストと共に送信されます。 唯一の例外は、サイトのログインcookieにSameSiteパラメーターが既に「none」に設定されている場合です。
* アクティビティの編集中に&#x200B;**&#x200B;が[!DNL Target]ライブラリをダウンロードできない（サイトにまだない場合）。 これは、ダウンロード呼び出しが顧客ドメインからセキュリティで保護されたAdobeドメインに向けておこなわれ、未認証として拒否されるからです。
* EECは`adobemc.com domain`のcookieに対してSameSite属性を設定できないので、すべてのユーザーに対して&#x200B;**&#x200B;機能を実行しません。 この属性がない場合、ブラウザーはこれらのCookieを拒否し、EECが失敗します。

### ブロックされているCookieの特定

SameSite cookieの適用ポリシーが原因でブロックされているcookieを判断するには、Chromeの開発者ツールを使用します。

1. 開発者ツールにアクセスするには、ChromeでVECを表示している間に、Chromeの右上隅にある&#x200B;**[!UICONTROL 省略記号]**&#x200B;アイコンをクリックします。 **[!UICONTROL その他のツール]** / **[!UICONTROL 開発者ツール]**
1. 「**[!UICONTROL Network]**」タブをクリックし、ブロックされているcookieを探します。

   >[!NOTE]
   >
   >**[!UICONTROL 「Has blocked cookies]**」チェックボックスを使用すると、ブロックされたCookieを見つけやすくなります。

   次の図は、ブロックされたCookieを示しています。

   ![開発者ツール/「 Network 」タブで、ブロックされたCookieが表示される](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/chrome-developer-tools.png)

### Google VECヘルパー拡張機能

Adobeは、更新されたVECヘルパー拡張機能をGoogle Chrome Storeに送信しました。 この拡張機能は、必要に応じてCookieの属性を上書きし、`SameSite="none"`属性を設定します。 [更新された拡張は、](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en)で確認できます。 VECヘルパー拡張機能のインストールと使用について詳しくは、「[Visual Experience Composerヘルパー拡張機能](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)」を参照してください。

独自のサイトのcookieに対して、名前でcookieを指定する必要があります。

>[!NOTE]
>
>この方法は、すべてのCookieが単一のドメインに設定されている場合にのみ適しています。 VECヘルパーでは、[!DNL Target]で複数のドメインに対してcookieを指定できません。

[!UICONTROL Cookie]スライダーをオンの位置に切り替え、名前とcookieドメインを指定します。 Cookie名は「mbox」で、Cookieドメインはmboxを扱うドメインの第2の最上位レベルです。 会社のドメインなので、cookie はファーストパーティ cookie になります。例: `mycompany.com`. 詳しくは、『*Experience Cloudインターフェイスユーザーガイド*』の[Adobe Target Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html?lang=ja)を参照してください。

![VECヘルパー拡張機能でのcookieの切り替え](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

### 代替策と回避策

次のいずれかのオプションを使用して、VECとEECが引き続き期待どおりに動作することを確認します。

* 更新された[VECヘルパー拡張機能](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en)をダウンロードして使用します。
* Mozilla Firefoxブラウザーを使用します。 Firefoxは、このポリシーを適用していません。
* 2021年9月22日までの間にコマンドラインからGoogle Chromeを実行するには、次のフラグを使用します。 9月21日以降、WebサイトはVECで機能しなくなります。 Chrome 94にアップデートした場合は、Webサイト上で`SameSite=none`と`Secure`のCookieを手動で生成する必要があります。

   ```
   --disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure
   ```

## [!DNL Target]は複数レベルのiframeをサポートしますか？

[!DNL Target] は、複数レベルの iframe をサポートしていません。Webサイトが子iframeを含むiframeを読み込む場合、at.jsは親iframeとのみやり取りします。 [!DNL Target] ライブラリは子 iframe とやり取りしません。

回避策として、子 iframe の URL を持つエクスペリエンスにページを追加できます。

## ページを編集しようとすると、ページではなく、スピナーが表示されます。（VEC と EEC） {#section_313001039F79446DB28C70D932AF5F58}

この状況は、URLに#文字が含まれている場合に発生する可能性があります。 この問題を修正するには、Visual Experience Composer を「参照」モードに切り替えて、その後「構成」モードに戻します。スピナーの表示が消えて、ページが読み込まれます。

## コンテンツセキュリティポリシー(CSP)ヘッダーにより、Webサイト上の[!DNL Target]ライブラリがブロックされます。 （VEC と EEC） {#section_89A30C7A213D43BFA0822E66B482B803}

Web サイトの CSP ヘッダーによって Target ライブラリがブロックされることにより、Web サイトは読み込まれるものの編集できない場合は、Target ライブラリがブロックされないようにします。

>[!NOTE]
>
>以下の情報に加えて、Google Chrome 用 [Adobe Target VEC ヘルパーブラウザー拡張機能](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)を使用できます。

![](assets/cps_headers.png)

次のように、Requestly ルールを設定して CSP ヘッダーを削除することで対処できます。

![](assets/cps_headers_2.png)

VEC 内でのリソースの読み込みを妨げているヘッダーに、同様の Requestly ルールを設定できます。

Requestly の場合、ヘッダーを削除する必要があるときは必ず次のいずれかを実行する必要があります。

* VEC で開く URL の URL ルールを追加して、それらの URL についてのみヘッダーが削除されるようにします。
* VEC で編集するときにはルールを有効にし、VEC を使用していないときはルールを無効にします。

## 保存されているアクティビティの再編集時に、VEC または EEC が壊れているように見えたり、初期化されなかったりします。（VEC と EEC） {#section_5AC3BA8F8FBB451EA814F298D0645E54}

Web サイトが、エクスペリエンスの定義後に Visual Experience Composer 外で変更された場合、それよりも前にアクションがおこなわれたセレクターは、アクティビティを再編集で開くときに検出できません。ページは壊れているように表示され、警告は表示されません。

## JavaScript を含む回転バナーなどのコンテンツが VEC または EEC に表示されません。（VEC と EEC） {#section_8B5BE6EB050B42D6A14A054724C41330}

デフォルトでは、Visual Experience Composer は JavaScript 要素をブロックします。Visual Experience Composer の設定で JavaScript を無効にすると、これらの要素を使用できます。セットアップするサイトによっては、それでも一部のアイテムの表示が正しくなかったり表示できなかったりする場合があります。

## ページ内の 1 つの要素を変更すると、複数の要素が変更されます。（VEC と EEC） {#section_309188ACF34942989BE473F63C5710AF}

同じ DOM 要素 ID がページ内の複数の要素に使用されている場合、それらの要素のいずれかを変更するとその ID の要素がすべて変更されます。この現象を予防するには、各ページで ID は 1 回のみ使用するようにしてください。これは、標準のHTMLベストプラクティスです。 詳しくは、[ページ修正のシナリオ](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)を参照してください。

## iFrame バスティングのサイトのエクスペリエンスを編集できない。（VEC と EEC） {#section_9FE266B964314F2EB75604B4D7047200}

この問題は、拡張 Experience Composer を有効にすることで対処できます。**[!UICONTROL 管理]** / **[!UICONTROL Visual Experience Composer]**&#x200B;をクリックし、拡張Experience Composerを有効にするチェックボックスをオンにします。 拡張 Experience Composer は、編集するページの読み込みに、アドビが管理するプロキシを使用します。このプロキシを使用すると、iFrameバスティングのサイトで編集でき、まだAdobe Targetコードを追加していないサイトやページで編集できます。 コードが追加されるまで、サイトにアクティビティは配信されません。サイトによっては、拡張 Experience Composer を介して読み込むことができない場合があります。その場合は、このオプションをオフにして、iFrame を介して Visual Experience Composer を読み込むことができます。

>[!NOTE]
>
>ローカルでホストされているページや、ネットワーク外からアクセスできないページは、アドビのプロキシサーバーにアクセスできず、EEC で開くことができません。こうしたページには、ステージング URL、ユーザー受け入れテスト（UAT）URL またはローカルでホストされているページなどがあります。

## mbox/target をまだ実装していないページでテストを設定したい。（VEC と EEC） {#section_DE63BCCB5B124E10A71FA579B582A80A}

上記の「iFrame バスティングのサイトのエクスペリエンスを編集できない」を参照してください。

## 「テキスト／HTML を編集」または「テキスト／HTML を変更」でテキストスタイルの太字および斜体がページで表示されません。これらのスタイル変更を適用すると、テキストが消えることがあります。（VEC と EEC） {#section_7A71D6DF41084C58B34C18701E8774E5}

Visual Experience Composer で A/B またはエクスペリエンスターゲット設定アクティビティに「**[!UICONTROL テキスト／HTML を編集]**」を使用したり、自動パーソナライゼーションまたは多変量分析テストアクティビティに「**[!UICONTROL テキスト／HTML を変更]**」を使用して、テキストに太字や斜体を設定すると、Visual Experience Composer でこれらのスタイルがページに適用できないか、ページからテキストが消えることがあります。これは、リッチテキストエディターがこれらのスタイルを適用する方法が、Webサイトのマークアップに影響を与える可能性があるためです。

この問題が発生した場合、次の手順に従ってください。

1. リッチテキストエディターの **[!UICONTROL HTML]** ボタンをクリックして、ソース編集モードに入ります。
1. スタイルテキスト要素を検索します。

   * 太字テキストの場合は、`<strong>`要素を`<b>`に変更します。

   * 斜体の場合は、`<em>`要素を`<i>`に変更します。

## 自動パーソナライゼーションアクティビティで、VEC または EEC の画像のスワップが壊れているように見えます。（VEC と EEC） {#section_88AABFDFE6A3420299B0D508B12A3994}

場所に画像オファーを追加するときは、VEC または EEC の元の画像スペースのフルサイズが利用されます。配信時には、画像が拡大されずそのまま表示されるので、配信には影響しません。
