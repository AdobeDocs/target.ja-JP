---
keywords: ターゲット設定；visual experience composer；許可リスト；ホワイトリスト；許可リスト;許可リスト；拡張 visual experience composer;vec;visual experience composer のトラブルシューティング；トラブルシューティング；eec；拡張 experience composer;tls;tls 1.2
description: 特定の条件下でAdobe [!DNL Target] Visual Experience Composer （VEC）および拡張 Experience Composer （EEC）で発生する場合がある問題のトラブルシューティング方法を説明します。
title: Visual Experience Composer と拡張 Experience Composer に関連する問題をトラブルシューティングする方法
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1401'
ht-degree: 46%

---

# [!UICONTROL Visual Experience Composer] および [!UICONTROL Enhanced Experience Composer] に関連する問題のトラブルシューティング

特定の条件下で、[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）と [!UICONTROL Enhanced Experience Composer] （EEC）でディスプレイの問題やその他の問題が発生することがあります。

## Google Chrome の SameSite cookie 実施ポリシーは、VEC および EEC にどのような影響を与えますか？ {#samesite}

次のChrome リリースを使用する場合は、VEC および EEC に影響を与える変更点に注意してください。

>[!NOTE]
>
>次の変更は、以下に示す 3 つの更新すべてに影響します。
>
> * VEC Helper 拡張機能 *インストールされ* サイトのパスワードで保護されたページに対して有効になっていない場合、VEC を使用できません。 サイトのログイン Cookie はサードパーティ Cookie と見なされ、参照モードの VEC エディター内のログインリクエストでは送信されません。 唯一の例外は、サイトのログイン Cookie に `SameSite=None` 属性と `Secure` 属性が既に設定されている場合です。

**Chrome 94 （2021 年 9 月 21 日（PT））**: Chrome 94 リリース（2021 年 9 月 21 日（PT））で予定されている差し迫った変更は、次の変更がChrome 94 以降のブラウザーバージョンのすべてのユーザーに影響します。

* コマンド ライン フラグ `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure` は削除されます。

**Chrome 91 （2021 年 5 月 25 日（PT））**: Chrome 91 リリース（2021 年 5 月 25 日（PT））に実装された変更は、次の変更がChrome 91 以降のブラウザーバージョンのすべてのユーザーに影響します。

* フラグ `#same-site-by-default-cookies` と `#cookies-without-same-site-must-be-secure` が `chrome://flags` から削除されました。 この動作は、デフォルトで有効になっています。

**Chrome 80 （2020 年 8 月）**: 2020 年 8 月に実装された変更により、Chrome 80 以降のブラウザーバージョンを使用するすべてのユーザーは次のようになります。

* アクティビティの編集中は *ダウンロードでき [!DNL Target] せん* アクティビティがサイトにまだ存在しない場合）。 これは、ダウンロード呼び出しが顧客ドメインからセキュリティで保護された [!DNL Adobe] ドメインに対して行われ、未認証として拒否されるためです。
* EEC は、`adobemc.com domain` で Cookie の SameSite 属性を設定できないので、すべてのユーザーに対して *機能しません*。 この属性がない場合、ブラウザーはこれらの Cookie を拒否し、EEC が失敗します。

### ブロックされている Cookie の特定

同じ SameSite cookie 強制ポリシーによってブロックされている cookie を確認するには、Chromeの Developer Tools を使用します。

1. デベロッパーツールにアクセスするには、Chromeで VEC を表示しているときに、Chrome / **[!UICONTROL More Tools]** / **[!UICONTROL Developer Tools]** の右上隅にある「**[!UICONTROL ellipsis]**」アイコンをクリックします。
1. **[!UICONTROL Network]** タブをクリックして、ブロックされた Cookie を探します。

   >[!NOTE]
   >
   >「**[!UICONTROL Has blocked cookies]**」チェックボックスを使用すると、ブロックされた Cookie を見つけやすくなります。

   次の図に、ブロックされた Cookie を示します。

   ![ 開発者ツール/ブロックされた Cookie を表示する「ネットワーク」タブ ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/chrome-developer-tools.png)

### [!DNL Adobe Target] VEC Helper 拡張機能

バージョン 0.7.1 以降、[!DNL Adobe Target] VEC Helper ブラウザー拡張機能は、拡張機能 UI で「Cookie」トグルをオンにすると、VEC 内で編集された web ページからの応答に対して、`SameSite=None` 属性と `Secure` 属性をすべて追加します。

![Adobe Target VEC Helper 拡張機能 UIAdobe Target VEC Helper 拡張機能 UI](assets/cookies-vec-helper.png)

### 代替手段と回避策

VEC と EEC が引き続き期待どおりに動作することを確認するには、次のいずれかのオプションを使用します。

* 更新された [VEC Helper 拡張機能 ](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en) をダウンロードして使用します。
* Mozilla Firefox ブラウザーを使用します。 Firefox はまだこのポリシーを実施していません。
* 2021 年 9 月 21 日（PT）までコマンドラインからGoogle Chromeを実行するには、次のフラグを使用します。 9 月 21 日（PT）以降、ログインや cookie 同意のポップアップなど、cookie を必要とする機能は VEC で機能しなくなります。 Chrome 94 に更新する場合、web サイト上の `SameSite=none` および `Secure` を使用して Cookie を手動で生成する必要があります。

  ```
  --disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure
  ```

## [!DNL Target] はマルチレベル iframe をサポートしていますか。

[!DNL Target] はマルチレベル iframe をサポートしていません。 Web サイトが子 iframe を持つ iframe を読み込む場合、at.js は親 iframe のみとやり取りします。 [!DNL Target] ライブラリは子 iframe とやり取りしません。

回避策として、子 iframe の URL を持つエクスペリエンスにページを追加できます。

## ページを編集しようとすると、ページではなく、スピナーが表示されます。（VEC と EEC） {#section_313001039F79446DB28C70D932AF5F58}

この状況は、URL に#文字が含まれている場合に発生する可能性があります。 この問題を修正するには、Visual Experience Composer を「参照」モードに切り替えて、その後「構成」モードに戻します。スピナーの表示が消えて、ページが読み込まれます。

## コンテンツセキュリティポリシー（CSP）ヘッダーは、Web サイト上の [!DNL Target] ライブラリをブロックします。 （VEC と EEC） {#section_89A30C7A213D43BFA0822E66B482B803}

Web サイトの CSP ヘッダーによって Target ライブラリがブロックされることにより、Web サイトは読み込まれるものの編集できない場合は、Target ライブラリがブロックされないようにします。

>[!NOTE]
>
>以下の情報に加えて、Google Chrome 用 [Adobe Target VEC ヘルパーブラウザー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)を使用できます。

![cps_headers image](assets/cps_headers.png)

次のように、Requestly ルールを設定して CSP ヘッダーを削除することで対処できます。

![cps_headers_2 画像 ](assets/cps_headers_2.png)

VEC 内でのリソースの読み込みを妨げているヘッダーに、同様の Requestly ルールを設定できます。

Requestly の場合、ヘッダーを削除する必要があるときは必ず次のいずれかを実行する必要があります。

* VEC で開く URL の URL ルールを追加して、それらの URL についてのみヘッダーが削除されるようにします。
* VEC で編集するときにはルールを有効にし、VEC を使用していないときはルールを無効にします。

## 保存されているアクティビティの再編集時に、VEC または EEC が壊れているように見えたり、初期化されなかったりします。（VEC と EEC） {#section_5AC3BA8F8FBB451EA814F298D0645E54}

Web サイトが、エクスペリエンスの定義後に Visual Experience Composer 外で変更された場合、それよりも前にアクションがおこなわれたセレクターは、アクティビティを再編集で開くときに検出できません。ページは壊れているように表示され、警告は表示されません。

## JavaScript を含む回転バナーなどのコンテンツが VEC または EEC に表示されません。（VEC と EEC） {#section_8B5BE6EB050B42D6A14A054724C41330}

デフォルトでは、Visual Experience Composer は JavaScript 要素をブロックします。Visual Experience Composer の設定で JavaScript を無効にすると、これらの要素を使用できます。セットアップするサイトによっては、それでも一部のアイテムの表示が正しくなかったり表示できなかったりする場合があります。

## ページ内の 1 つの要素を変更すると、複数の要素が変更されます。（VEC と EEC） {#section_309188ACF34942989BE473F63C5710AF}

同じ DOM 要素 ID がページ内の複数の要素に使用されている場合、それらの要素のいずれかを変更するとその ID の要素がすべて変更されます。この現象を予防するには、各ページで ID は 1 回のみ使用するようにしてください。これは、標準のHTMLベストプラクティスです。 詳しくは、[ ページ修正のシナリオ ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB) を参照してください。

## iFrame バスティングのサイトのエクスペリエンスを編集できない。（VEC と EEC） {#section_9FE266B964314F2EB75604B4D7047200}

この問題は、拡張 Experience Composer を有効にすることで対処できます。**[!UICONTROL Administation]**/**[!UICONTROL Visual Experience Composer]** をクリックし、拡張 Experience Composer を有効にするチェックボックスをオンにします。 拡張 Experience Composer は、編集するページの読み込みに、アドビが管理するプロキシを使用します。このプロキシを使用すると、iFrame でバスティングサイトを編集したり、Adobe Target コードをまだ追加していないサイトやページを編集したりできます。 コードが追加されるまで、サイトにアクティビティは配信されません。サイトによっては、拡張 Experience Composer を介して読み込むことができない場合があります。その場合は、このオプションをオフにして、iFrame を介して Visual Experience Composer を読み込むことができます。

>[!NOTE]
>
>ローカルでホストされているページや、ネットワーク外からアクセスできないページは、アドビのプロキシサーバーにアクセスできず、EEC で開くことができません。こうしたページには、ステージング URL、ユーザー受け入れテスト（UAT）URL またはローカルでホストされているページなどがあります。

## mbox/target をまだ実装していないページでテストを設定したい。（VEC と EEC） {#section_DE63BCCB5B124E10A71FA579B582A80A}

上記の「iFrame バスティングのサイトのエクスペリエンスを編集できない」を参照してください。

## 「テキスト／HTML を編集」または「テキスト／HTML を変更」でテキストスタイルの太字および斜体がページで表示されません。これらのスタイル変更を適用すると、テキストが消えることがあります。（VEC と EEC） {#section_7A71D6DF41084C58B34C18701E8774E5}

Visual Experience Composer for A/B または Experience Targeting アクティビティで **[!UICONTROL Edit Text/HTML]** を使用している場合や、Automated Personalizationまたは多変量分析テスト アクティビティで **[!UICONTROL Change Text/HTML]** を使用してテキストを太字または斜体にする場合、これらのスタイルがページに適用されなかったり、Visual Experience Composer のページからテキストが消えたりする場合があります。 これは、リッチテキストエディターがこれらのスタイルを適用する方法により、web サイトのマークアップが妨げられる可能性があるために発生します。

この問題が発生した場合、次の手順に従ってください。

1. リッチテキストエディターの「**[!UICONTROL HTML]**」ボタンをクリックして、ソース編集モードに入ります。
1. スタイルテキスト要素を検索します。

   * 太字テキストの場合は、`<strong>`要素を`<b>`に変更します。

   * 斜体の場合は、`<em>`要素を`<i>`に変更します。

## Automated Personalizationアクティビティで、VEC または EEC の画像のスワップが壊れているように見えます。（VEC と EEC） {#section_88AABFDFE6A3420299B0D508B12A3994}

場所に画像オファーを追加するときは、VEC または EEC の元の画像スペースのフルサイズが利用されます。配信時には、画像が拡大されずそのまま表示されるので、配信には影響しません。
